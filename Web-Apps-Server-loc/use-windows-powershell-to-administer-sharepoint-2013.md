---
title: Utilizzare Windows PowerShell per amministrare SharePoint 2013
TOCTitle: Utilizzare Windows PowerShell per amministrare SharePoint 2013
ms:assetid: ae4901b4-505a-42a9-b8d4-fca778abc12e
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ee806878(v=office.15)
ms:contentKeyID: 49652284
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Utilizzare Windows PowerShell per amministrare SharePoint 2013

 

_**Si applica a:**SharePoint Foundation 2013, SharePoint Server 2013 Enterprise, SharePoint Server 2013 Standard_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** informazioni sui cmdlet e sui concetti di base di Windows PowerShell, nonché sull'utilizzo di Windows PowerShell con SharePoint 2013.

Contenuto dell'articolo:

  - Panoramica

  - Accesso a Windows PowerShell per SharePoint 2013

  - Autorizzazioni

  - Script e criteri di esecuzione

  - Apprendimento dell'utilizzo di Windows PowerShell

## Panoramica

Windows PowerShell è uno strumento di scripting da riga di comando che offre a un amministratore l'accesso completo alle API (Application Programming Interface), oltre alla possibilità di interagire direttamente con SharePoint 2013 per modificare applicazioni Web, raccolte siti, siti, elenchi e altro ancora. L'amministratore può inoltre creare cmdlet (pronunciato "command-let") per gli script.

Windows PowerShell 3.0 è un componente prerequisito per l'installazione di SharePoint 2013. Se necessario, verrà installato al momento dell'esecuzione di Utilità preparazione prodotti Microsoft SharePoint. Per impostazione predefinita, Windows PowerShell è disponibile nel percorso seguente: \<%SystemRoot%\>\\System32\\WindowsPowerShell\\v1.0\\PowerShell.exe.

Per un elenco delle nuove funzionalità per Windows PowerShell 3.0 vedere [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=272782).

Per uno strumento interattivo e una guida all'apprendimento della sintassi di Windows PowerShell, vedere lo [strumento Windows PowerShell Command Builder](http://go.microsoft.com/fwlink/p/?linkid=229854) e la relativa [guida introduttiva](http://www.microsoft.com/download/en/details.aspx?id=27588).

Per l'esecuzione di attività amministrative dalla riga di comando è consigliabile utilizzare Windows PowerShell. Lo strumento da riga di comando Stsadm è deprecato, ma è stato incluso per garantire la compatibilità con le versioni precedenti del prodotto.

## Accesso a Windows PowerShell per SharePoint 2013

Dopo aver installato SharePoint 2013, i cmdlet di Windows PowerShell applicabili saranno disponibili tramite Shell di gestione di SharePoint 2013. Con SharePoint Management Shell è possibile gestire tutti gli aspetti di SharePoint 2013. È possibile creare nuove raccolte siti, applicazioni Web, account utente, applicazioni di servizio, proxy e quant'altro. I comandi immessi in SharePoint Management Shell generano come output oggetti di SharePoint basati sulla piattaforma Microsoft .NET. Tali oggetti possono essere applicati come input per i comandi successivi o archiviati in variabili locali per essere utilizzati in un secondo momento.

Con SharePoint Management Shell non è necessario registrare lo snap-in contenente i cmdlet. La registrazione del modulo Microsoft.SharePoint.PowerShell.dll per i cmdlet di SharePoint 2013 è automatica e deriva dalla riga `Add-PSSnapin Microsoft.SharePoint.PowerShell` nel file SharePoint.ps1 disponibile in *%CommonProgramFiles%*\\Microsoft Shared\\Web Server Extensions\\15\\Config\\PowerShell\\Registration. Per utilizzare la console Windows PowerShell, è necessario registrare manualmente tale snap-in.

Sia che si utilizzi SharePoint Management Shell o la console Windows PowerShell, è anche possibile caricare snap-in aggiuntivi. Per ulteriori informazioni, vedere [Potenza dei profili](http://go.microsoft.com/fwlink/p/?linkid=183166).

**Per accedere a SharePoint Management Shell**

1.  Avviare SharePoint Management Shell.
    
      - Per Windows Server 2008 R2:
        
          - Fare clic sul pulsante **Start**, scegliere **Prodotti Microsoft SharePoint 2013** e quindi **SharePoint Management Shell**.
    
      - Per Windows Server 2012:
        
          - Nella schermata **Start** fare clic su **SharePoint Management Shell**.
            
            Se **SharePoint Management Shell** non è disponibile nella schermata **Start**:
        
        <!-- end list -->
        
          - Fare clic con il pulsante destro del mouse su **Computer**, scegliere **Tutte le app** e quindi **SharePoint Management Shell**.
    
    Per ulteriori informazioni su come interagire con Windows Server 2012, vedere [Attività di gestione comuni e spostamento in Windows Server 2012](http://technet.microsoft.com/it-it/library/hh831491.aspx).


> [!NOTE]
> Shell di gestione di SharePoint 2013 e la console Windows PowerShell inoltre si differenziano per l'utilizzo dell'opzione <CODE>ReuseThread</CODE>, che definisce la modalità di utilizzo del modello di threading. L'utilizzo da parte di Shell di gestione di SharePoint 2013 è definito dalla riga <CODE>{Host.Runspace.ThreadOptions = "ReuseThread"}</CODE>, inclusa nel file SharePoint.ps1. Per ulteriori informazioni, vedere l'argomento relativo alle <A href="http://go.microsoft.com/fwlink/p/?linkid=183145">opzioni dei thread PS</A>.



## Autorizzazioni

## Locali

Prima di poter utilizzare il cmdlet **Add-SPShellAdmin** per concedere autorizzazioni agli utenti per l'esecuzione dei cmdlet SharePoint 2013, verificare che siano soddisfatti i requisiti minimi seguenti:

  - È necessaria l'appartenenza al ruolo predefinito del server **securityadmin** nell'istanza di SQL Server

  - È necessaria l'appartenenza al ruolo predefinito del database **db\_owner** in tutti i database da aggiornare.

  - È necessario essere membri del gruppo Administrators nel server in cui si esegue il cmdlet Windows PowerShell.


> [!NOTE]
> Se non si dispone di queste autorizzazioni, rivolgersi all'amministratore dell'installazione o all'amministratore di SQL Server per richiederle.



Per ulteriori informazioni sulle autorizzazioni di Windows PowerShell, vedere Autorizzazioni e [Add-SPShellAdmin](https://technet.microsoft.com/it-it/library/ff607596\(v=office.15\))

Se non si appartiene al ruolo **SharePoint\_Shell\_Access** o al gruppo locale **WSS\_Admin\_WPG**, utilizzare il cmdlet **Add-SPShellAdmin** per aggiungere l'utente al gruppo **WSS\_Admin\_WPG** in tutti i server Web front-end della farm di SharePoint e al ruolo **SharePoint\_Shell\_Access**. Se il database SQL Server non dispone di un ruolo **SharePoint\_Shell\_Access**, questo verrà creato automaticamente quando si esegue il cmdlet **Add-SPShellAdmin**. Dopo l'esecuzione di questo**Add-SPShellAdmin**cmdlet, l'utente può eseguire i cmdlet di Windows PowerShell per SharePoint in un ambiente farm multiserver.


> [!NOTE]
> Quando si installa SharePoint 2013, all'account utente utilizzato per eseguire l'installazione vengono concesse le autorizzazioni appropriate per eseguire i cmdlet Windows PowerShell. Se non sono stati aggiunti utenti per eseguire un cmdlet Windows PowerShell, è possibile utilizzare il cmdlet <STRONG>Add-SPShellAdmin</STRONG> per aggiungerli.



È necessario eseguire il cmdlet **Add-SPShellAdmin** per tutti i database a cui si desidera concedere l'accesso. Se non si specifica alcun database, verrà utilizzato il database di configurazione della farm. Se invece si specifica un database, oltre al database di configurazione della farm specificato, verrà incluso anche il database del contenuto della farm.

Per visualizzare un elenco di tutti i cmdlet **SPShellAdmin**, al prompt dei comandi di Windows PowerShell digitare `Get-Command -Noun SPShellAdmin`.

## SharePoint Online

Accertarsi di disporre delle seguenti autorizzazioni amministrative:

  - È necessario avere il ruolo di amministratore globale nel sito di SharePoint Online in cui si esegue il cmdlet di Windows PowerShell. Per ulteriori informazioni, vedere l'argomento relativo ai [ruoli amministrativi e gruppi di utenti predefiniti](http://go.microsoft.com/fwlink/p/?linkid=242451).
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>È possibile utilizzare un gruppo specifico di Windows PowerShell con SharePoint Online. Per ulteriori informazioni, vedere <a href="https://technet.microsoft.com/it-it/library/fp161362(v=office.15)">Office 365 PowerShell per SharePoint Online</a>.</td>
    </tr>
    </tbody>
    </table>


## Script e criteri di esecuzione

Sebbene sia possibile utilizzare Windows PowerShell per eseguire una sola attività amministrativa, è anche possibile utilizzare uno script per automatizzare una serie di attività. Uno script è un file di testo che contiene uno o più comandi di Windows PowerShell. Gli script di Windows PowerShell hanno un'estensione di file .ps1.

Per eseguire gli script, il criterio di esecuzione minimo necessario per SharePoint 2013 è RemoteSigned, sebbene il criterio predefinito per Windows PowerShell sia Restricted. Se si lascia il criterio Restricted, SharePoint 2013 Management Shell modificherà il criterio per Windows PowerShell in RemoteSigned, pertanto sarà necessario selezionare **Esegui come amministratore** per avviare SharePoint 2013 Management Shell con l'autorizzazione amministrativa elevata. Questa modifica verrà applicata a tutte le sessioni di Windows PowerShell. Per ulteriori informazioni, vedere l'argomento relativo all'[enumerazione ExecutionPolicy](http://go.microsoft.com/fwlink/p/?linkid=242452).

Per ulteriori informazioni sugli script e sui criteri di esecuzione, vedere rispettivamente [about\_scripts](http://go.microsoft.com/fwlink/p/?linkid=144310) e [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050).

## Apprendimento dell'utilizzo di Windows PowerShell

Per i professionisti IT SharePoint sono disponibili numerose risorse didattiche relative a Windows PowerShell.

**Centro di scripting TechNet**

Nel Centro di scripting TechNet sono disponibili diverse risorse per apprendere le nozioni fondamentali di Windows PowerShell. Sono inoltre presenti archivi con esempi di script di utilizzo comune con diversi prodotti Microsoft. Nella tabella seguente sono riportate le risorse didattiche principali.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pagina</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187813">Documentazione relativa a Windows PowerShell su TechNet</a></p></td>
<td><p>In questa sezione della Libreria TechNet sono disponibili copie Web degli argomenti Get-Help di base di Windows PowerShell. Vengono inoltre fornite copie Web della Guida introduttiva a Windows PowerShell, della Guida di PowerShell.exe e di un documento con le nozioni fondamentali su Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187815">Creazione di script con Windows PowerShell</a></p></td>
<td><p>Home page delle risorse didattiche sulla creazione e l'utilizzo di script con Windows PowerShell.</p></td>
</tr>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187817">Manuale del proprietario di Windows PowerShell</a></p></td>
<td><p>Guida basata sul Web per iniziare a utilizzare Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187819">Guida di riferimento rapido su Windows PowerShell</a></p></td>
<td><p>Copia scaricabile del documento di riferimento rapido installato con Windows PowerShell.</p></td>
</tr>
</tbody>
</table>


Man mano che si consultano tali risorse, tenere presente che è utile acquisire familiarità con i seguenti concetti e i cmdlet prima di utilizzare Windows PowerShell per SharePoint 2013:

  - [Get-Command](http://go.microsoft.com/fwlink/p/?linkid=171069)

  - [Get-Member](http://go.microsoft.com/fwlink/p/?linkid=171070)

  - [Get-Help](http://go.microsoft.com/fwlink/p/?linkid=171068)

  - [about\_Aliases](http://go.microsoft.com/fwlink/p/?linkid=113207)

  - [Invio tramite pipe e pipeline in Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=187808)

  - [Set di parametri per i cmdlet](http://go.microsoft.com/fwlink/p/?linkid=187810)

  - [Foreach-Object](http://go.microsoft.com/fwlink/p/?linkid=187812)

  - [Where-Object](http://go.microsoft.com/fwlink/p/?linkid=187811)

