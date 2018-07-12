---
title: Applicare aggiornamenti software al server Office Web Apps
TOCTitle: Applicare aggiornamenti software al server Office Web Apps
ms:assetid: 5d15dbd9-374e-422a-a870-43270dd0a2db
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ966220(v=office.15)
ms:contentKeyID: 51658371
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Applicare aggiornamenti software al server Office Web Apps 

_**Si applica a:** Office Web Apps Server_

_**Ultima modifica dell'argomento:** 2016-12-16_

**Riepilogo:** in questo articolo viene illustrato come applicare gli aggiornamenti software a una server farm di Office Web Apps.

**Destinatari:** professionisti IT

Dopo l'uscita di una nuova versione del server Office Web Apps, Microsoft rende disponibile una serie di aggiornamenti software per aumentare il livello di sicurezza, le prestazioni e l'affidabilità dei server. In questo articolo viene descritto come applicare gli aggiornamenti software a singoli server in una farm di server Office Web Apps.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Questo articolo fa parte della <a href="content-roadmap-for-office-web-apps-server.md">Guida di orientamento al contenuto per il server Office Web Apps</a>. Utilizzare tale guida come punto di partenza per accedere ad articoli, download e video utili per distribuire e gestire server Office Web Apps.<br />
<strong>Per informazioni su Office Web Apps su dispositivi desktop o mobili</strong>, cercare &quot;Office Web Apps&quot; su <a href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.</td>
</tr>
</tbody>
</table>

> [!WARNING]
> L'applicazione degli aggiornamenti del server Office Web Apps mediante il processo di aggiornamento automatico non è supportata per il server Office Web Apps. Gli aggiornamenti a un server Office Web Apps devono infatti essere applicati in modo specifico, secondo quanto descritto in questo articolo. Se invece gli aggiornamenti del server Office Web Apps vengono applicati automaticamente, gli utenti potrebbero non essere in grado di visualizzare o modificare documenti in Office Web Apps. In tal caso, sarà necessario generare di nuovo la farm di server Office Web Apps. Per rigenerare una farm, è necessario rimuovere il server Office Web Apps dalla farm utilizzando <A href="https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps">Remove-OfficeWebAppsMachine</A>, disinstallare il server Office Web Apps tramite Installazione applicazioni, quindi reinstallare il server Office Web Apps seguendo la procedura descritta in <A href="deploy-office-web-apps-server.md">Distribuire il server Office Web Apps</A>. Dopo aver completato la reinstallazione, applicare l'aggiornamento seguendo la procedura descritta in questo articolo.<BR>È importante esaminare la linee guida disponibili in <A href="plan-office-web-apps-server.md">Planning updates for Office Web Apps Server</A> e definire un processo di aggiornamento per la farm di server Office Web Apps.



## Operazioni preliminari

È possibile trovare l'elenco più recente degli aggiornamenti disponibili per il server Office Web Apps nel [blog degli aggiornamenti di Microsoft Office](http://go.microsoft.com/fwlink/p/?linkid=280269) e su TechNet nel [Centro aggiornamenti per Office, server di Office e prodotti correlati](http://go.microsoft.com/fwlink/p/?linkid=280271).

Gli aggiornamenti rilasciati per il server Office Web Apps effettuano l'aggiornamento del server Office Web Apps e degli eventuali Language Pack del server Office Web Apps installati. Non sono disponibili aggiornamenti distinti per i Language Pack del server Office Web Apps.

Nell'ambito del processo di aggiornamento, sarà necessario creare di nuovo la farm di server Office Web Apps. Per prepararsi alla nuova creazione della farm di server Office Web Apps, esaminare le proprietà dell'attuale farm di server Office Web Apps eseguendo il cmdlet Windows PowerShell**Get-OfficeWebAppsFarm** ed esaminare i parametri relativi a [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps). I parametri usati per **New-OfficeWebAppsFarm** dovranno essere gli stessi usati per la configurazione iniziale della farm di server Office Web Apps.


> [!NOTE]
> È possibile eseguire le attività descritte in questo articolo utilizzando il mouse, le scelte rapide da tastiera o la modalità tocco. Per ulteriori informazioni, vedere le risorse seguenti: 
> <UL>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249150">Scelte rapide da tastiera</A></P>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249151">Tocco</A></P></LI></UL>



## Applicare aggiornamenti software a una farm di server Office Web Apps a server singolo

Per applicare aggiornamenti software a una farm di server Office Web Apps a server singolo, rimuovere il server Office Web Apps dalla farm, applicare l'aggiornamento software e creare di nuovo la farm di server Office Web Apps. Se nella farm di server Office Web Apps è presente un solo server, gli utenti non saranno in grado di utilizzare Office Web Apps durante l'aggiornamento del server. Si consideri pertanto la possibilità di aggiornare il server Office Web Apps in orari non critici o d'ufficio.

**Per applicare aggiornamenti software a una farm a server singolo**

1.  Se l'aggiornamento non è già stato scaricato nel server Office Web Apps, scaricare l'aggiornamento del server Office Web Apps che si desidera applicare dall'[Area download Microsoft](http://go.microsoft.com/fwlink/p/?linkid=280274).

2.  Sul server Office Web Apps a cui si desidera applicare l'aggiornamento software, aprire il prompt di Windows PowerShell come amministratore ed eseguire il comando seguente.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```

3.  Installare l'aggiornamento del server Office Web Apps in tale server e, se richiesto, riavviarlo.

4.  Aprire il prompt di Windows PowerShell come amministratore ed eseguire il cmdlet **New-OfficeWebAppsFarm** per ricreare una farm di server Office Web Apps. L'URL specificato per **–InternalURL** corrisponde al nome del server che esegue il server Office Web Apps, ad esempio **http://Contoso-WAC**. In questo caso, si indicherà lo stesso nome utilizzato per la farm di server Office Web Apps precedente. Utilizzare gli stessi parametri aggiuntivi specificati per la creazione iniziale della farm di server Office Web Apps. Il parametro **–AllowHttp**, ad esempio, configura la farm per l'utilizzo di HTTP, mentre il parametro **–EditingEnabled** abilita la modifica in Office Web Apps quando viene utilizzato con SharePoint 2013. Il parametro **–EditingEnabled** non viene utilizzato in Lync Server 2013 o Exchange Server 2013 in quando tali host non supportano la modifica.
    
    Il codice nell'esempio seguente crea una nuova farm di server Office Web Apps denominata http://Contoso-WAC.
    
    ```PowerShell
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Ulteriori parametri per la configurazione dei servizi di traduzione, server proxy, supporto per le ClipArt e visualizzatori online sono descritti in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Applicare aggiornamenti software a una farm di server Office Web Apps con più server

Per applicare aggiornamenti software a una farm di server Office Web Apps con più server, è necessario rimuovere innanzitutto uno dei server dal pool di bilanciamento del carico e dalla farm, applicare l'aggiornamento software e creare una farm di server Office Web Apps aggiornata. Rimuovere e aggiornare quindi i server rimanenti nella farm di server Office Web Apps e aggiungerli alla nuova farm aggiornata. Si procederà al bilanciamento del traffico per la nuova farm quando sarà presente un numero sufficiente di server per supportare il traffico corrente. Questo processo di aggiornamento consente agli utenti di aprire e modificare documenti in Office Web Apps senza interruzioni.

**Per applicare aggiornamenti software a una farm con più server**

1.  Scaricare l'aggiornamento del server Office Web Apps che si desidera applicare dall'[Area download Microsoft](http://go.microsoft.com/fwlink/p/?linkid=280274) in un percorso di rete disponibile per la farm di server Office Web Apps.

2.  Rimuovere il server Office Web Apps a cui si desidera applicare l'aggiornamento dal pool di bilanciamento del carico.

3.  Su tale server Office Web Apps aprire il prompt di Windows PowerShell come amministratore ed eseguire il comando seguente.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```

4.  Installare l'aggiornamento del server Office Web Apps in tale server e, se richiesto, riavviarlo.

5.  Aprire il prompt di Windows PowerShell come amministratore e creare una farm di server Office Web Apps aggiornata utilizzando il cmdlet **New-OfficeWebAppsFarm**. L'URL specificato per **–InternalURL** corrisponde al nome del server che esegue il server Office Web Apps, ad esempio **http://Contoso-WAC**. In questo caso, utilizzare lo stesso nome della farm di server Office Web Apps esistente. Utilizzare gli stessi parametri aggiuntivi specificati per la creazione iniziale della farm di server Office Web Apps. Il parametro **–AllowHttp**, ad esempio, configura la farm per l'utilizzo di HTTP, mentre il parametro **–EditingEnabled** abilita la modifica in Office Web Apps quando viene utilizzato con SharePoint 2013. Il parametro **–EditingEnabled** non viene utilizzato in Lync Server 2013 o Exchange Server 2013 in quando tali host non supportano la modifica.
    
    Il codice nell'esempio seguente crea una nuova farm di server Office Web Apps denominata http://Contoso-WAC.
    
    ```PowerShell
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Ulteriori parametri per la configurazione dei servizi di traduzione, server proxy, supporto per le ClipArt e visualizzatori online sono descritti in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

6.  A seconda del numero di server presenti nella farm di server Office Web Apps, eseguire il bilanciamento del traffico per la nuova farm. Questo passaggio può essere rimandato finché non saranno disponibili più server aggiornati da aggiungere alla farm.

7.  Per ogni server rimanente nella farm, eseguire la procedura seguente.
    
    1.  Rimuovere il successivo server Office Web Apps dal pool di bilanciamento del carico.
    
    2.  Installare l'aggiornamento del server Office Web Apps in tale server e, se richiesto, riavviarlo.
    
    3.  Aprire il prompt di Windows PowerShell come amministratore ed eseguire il comando seguente. Il parametro **–MachineToJoin** aggiunge il server corrente a una farm di server Office Web Apps esistente. In questo caso, si aggiungerà il server alla farm di server Office Web Apps aggiornata. Utilizzare pertanto il nome computer di uno dei server presenti nella farm di server Office Web Apps aggiornata.
        
        ```PowerShell
            New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
        ```

## Vedere anche


[Remove-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[Get-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappsfarm?view=officewebapps-ps)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
  

[](content-roadmap-for-office-web-apps-server.md)

