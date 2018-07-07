---
title: Comportamento di apertura predefinito per documenti (Office Web Apps)
TOCTitle: Impostare il comportamento di apertura predefinito per documenti abilitati per i browser
ms:assetid: e27e0bc8-5fb5-4bb1-8157-d7c90654175e
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ee837425(v=office.15)
ms:contentKeyID: 50580132
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Impostare il comportamento di apertura predefinito per documenti abilitati per i browser (utilizzo di Office Web Apps con SharePoint 2013)

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** in questo articolo viene illustrato come configurare il comportamento di apertura predefinito per documenti di Office in raccolte siti di SharePoint e raccolte documenti.

**Destinatari:** professionisti IT

Per aprire un documento di una raccolta documenti di SharePoint 2013, è sufficiente fare clic sul relativo titolo. La modalità di apertura, ovvero in un'applicazione client o nel browser, dipende da diversi fattori, tra cui il tipo di file, la configurazione della farm di server Office Web Apps e le impostazioni della caratteristica OpenInClient della raccolta documenti o della raccolta siti. Nella procedura che segue viene descritto come configurare il comportamento di apertura predefinito per i documenti di Office quando SharePoint 2013 è configurato in modo da utilizzare il server Office Web Apps.

## Impostazione della modalità di apertura dei documenti da raccolte di SharePoint 2013

Per impostazione predefinita, dopo aver configurato SharePoint 2013 per l'utilizzo del server Office Web Apps, quando si fa clic su un file di Word, PowerPoint, Excel o OneNote il relativo documento viene aperto nel browser. I documenti PDF vengono visualizzati nel Word Web App. Per modificare il comportamento predefinito in modo che i file vengano aperti nelle applicazioni client o nel lettore PDF predefinito, è possibile utilizzare i due metodi seguenti:

  - **Per la farm di SharePoint 2013**   È possibile modificare il comportamento di apertura predefinito in base al tipo di file per la farm di SharePoint 2013 utilizzando i cmdlet Windows PowerShell[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) e [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps). Questi cmdlet consentono inoltre di [modificare il comportamento di documenti PDF](http://go.microsoft.com/fwlink/p/?linkid=330246).

  - **In raccolte siti o raccolte documenti**   Gli utenti e gli amministratori di raccolte siti possono utilizzare la caratteristica OpenInClient di SharePoint 2013 per specificare se i file di Office verranno aperti nell'applicazione client o nel browser. Per modificare questa impostazione, gli utenti possono utilizzare le proprietà della raccolta documenti. Gli amministratori possono invece utilizzare Amministrazione raccolta siti oppure il cmdlet [Enable-SPFeature](https://technet.microsoft.com/it-it/library/ff607803\(v=office.15\)) per abilitare la caratteristica OpenInClient. Per informazioni sui vari metodi in cui è possibile abilitare la caratteristica OpenInClient, vedere la sezione successiva.

In generale, la caratteristica OpenInClient sostituisce tutte le associazioni WOPI impostate tra SharePoint 2013 e il server Office Web Apps. In altri termini, se la caratteristica OpenInClient di una raccolta documenti o una raccolta siti di SharePoint 2013 è abilitata, i documenti verranno aperti nell'applicazione client anche se il server di SharePoint 2013 è configurato in modo da utilizzare il server Office Web Apps.


> [!NOTE]
> La configurazione del comportamento di apertura predefinito per i documenti abilitati per i browser non influisce sulla possibilità di utilizzare le caratteristiche <STRONG>Estrai</STRONG> e <STRONG>Invia a</STRONG> di SharePoint 2013 per il download di documenti. Per informazioni sulla configurazione delle autorizzazioni di estrazione, download e visualizzazione in SharePoint 2013, vedere <A href="https://technet.microsoft.com/it-it/library/cc262939(v=office.15)">Pianificazione delle autorizzazioni per siti e contenuto in SharePoint 2013</A>.



## Impostazione della caratteristica OpenInClient per una raccolta documenti o una raccolta siti

Per impostare la caratteristica OpenInClient in SharePoint 2013, utilizzare una delle procedure riportate di seguito.


> [!NOTE]
> In alcune di queste procedure viene utilizzata la Shell di gestione di SharePoint 2013 per eseguire cmdlet di SharePoint. Se si sceglie di utilizzare la console di Windows PowerShell, è necessario aggiungere lo snap-in Microsoft.SharePoint.PowerShell utilizzando il cmdlet <STRONG>Add-PSSnapin</STRONG>. Per ulteriori informazioni sull'utilizzo di Windows PowerShell con SharePoint 2013, vedere <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Utilizzare Windows PowerShell per amministrare SharePoint 2013</A>.




> [!NOTE]
> In famiglie di prodotti Office 2013 è possibile eseguire attività utilizzando il mouse, le scelte rapide da tastiera o la modalità tocco. Per informazioni su come utilizzare le scelte rapide da tastiera e la modalità tocco con i prodotti e i servizi di Office, vedere l'articolo relativo alle <A href="http://go.microsoft.com/fwlink/p/?linkid=249150">scelte rapide da tastiera</A> e <A href="http://go.microsoft.com/fwlink/p/?linkid=253163">Guida ai gesti di Office</A>.



 **Impostazione della caratteristica OpenInClient per raccolte siti**

1.  Nella raccolta siti di SharePoint scegliere **Impostazioni** \> **Impostazioni sito**.

2.  Nella pagina **Impostazioni sito**, in **Amministrazione raccolta siti**, scegliere **Caratteristiche raccolta siti**.

3.  Nella pagina **Caratteristiche**, per la caratteristica **Apri documenti nelle applicazioni client per impostazione predefinita**, scegliere **Attiva** (caratteristica OpenInClient abilitata) per aprire i documenti nell'applicazione client oppure o **Disattiva** (caratteristica OpenInClient disabilitata) per aprire i documenti nel browser.

 **Impostazione del comportamento di apertura predefinito per le raccolte siti tramite Windows PowerShell**

1.  Verificare innanzitutto di essere membri dei ruoli e dei gruppi seguenti:
    
      - Ruolo predefinito del server **securityadmin** nell'istanza di SQL Server.
    
      - Ruolo predefinito del database **db\_owner** in tutti i database da aggiornare.
    
      - Gruppo Administrators sul server sul quale si eseguono i cmdlet di Windows PowerShell.
    
    Leggere inoltre l'argomento [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050) e aggiungere eventuali altre appartenenze necessarie.
    
    Un amministratore può usare il cmdlet **Add-SPShellAdmin** per concedere le autorizzazioni per l'uso dei cmdlet di SharePoint 2013.
    

    > [!NOTE]
    > Se non si dispone delle autorizzazioni, richiederle all'amministratore responsabile dell'installazione o all'amministratore di SQL Server. Per ulteriori informazioni sulle autorizzazioni di Windows PowerShell, vedere <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Permissions</A> e <A href="https://technet.microsoft.com/it-it/library/ff607596(v=office.15)">Add-SPShellAdmin</A>.



2.  Aprire una SharePoint 2013 Management Shell con privilegi elevati attenendosi alla procedura seguente:
    
    **In Windows Server 2008**
    
    1.  Fare clic sul pulsante **Start** e scegliere **Tutti i programmi**.
    
    2.  Selezionare **Prodotti Microsoft SharePoint 2013**.
    
    3.  Scegliere **Shell di gestione SharePoint 2013** e visualizzare il menu di scelta rapida facendo clic con il pulsante destro del mouse.
    
    4.  Scegliere **Esegui come amministratore** dal menu di scelta rapida.
    
    **In Windows Server 2012**
    
    1.  Scorrere rapidamente dal bordo dello schermo per visualizzare gli accessi e quindi scegliere **Cerca** per visualizzare tutte le applicazioni installate nel computer.
    
    2.  Fare clic con il pulsante destro del mouse su **Shell di gestione SharePoint 2013** per visualizzare la barra dell'app.
    
    3.  Nella barra delle applicazioni scegliere **Esegui come amministratore**.

3.  Al prompt dei comandi di Windows PowerShell digitare uno dei comandi seguenti:
    
      - Per abilitare la caratteristica OpenInClient per una raccolta siti specifica, ovvero per aprire i documenti nell'applicazione client, digitare il comando seguente:
        
            Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        
        Dove *\<SiteCollURL\>* è l'URL della raccolta siti.
    
      - Per abilitare la caratteristica OpenInClient per tutte le raccolte siti, ovvero per aprire i documenti nell'applicazione client, digitare il comando seguente:
        
            Get-SPSite -limit ALL |foreach{ Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }
    
      - Per disabilitare la caratteristica OpenInClient per una raccolta siti specifica, ovvero per aprire i documenti nel browser, digitare il comando seguente:
        
            Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        
        Dove *\<SiteCollURL\>* è l'URL della raccolta siti .
    
      - Per disabilitare la caratteristica OpenInClient per tutte le raccolte siti, ovvero per aprire i documenti nel browser, digitare il comando seguente:
        
            Get-SPSite -limit ALL |foreach{ Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }

 **Impostazione del comportamento di apertura predefinito per una raccolta documenti mediante la pagina Impostazioni avanzate raccolta documenti**

1.  Nella pagina della raccolta documenti scegliere la scheda **Raccolta**.

2.  Nel gruppo **Impostazioni** scegliere **Impostazioni raccolta**.

3.  Nella pagina **Impostazioni avanzate raccolta documenti** scegliere **Impostazioni avanzate**.

4.  Nella pagina **Impostazioni avanzate** selezionare una delle opzioni seguenti in **Apertura di documenti nel browser**:
    
      - **Apri nell'applicazione client** Quando un utente sceglie un documento in questa raccolta, il documento verrà aperto nell'applicazione client corrispondente, se disponibile.
    
      - **Apri nel browser** Quando un utente sceglie un documento in questa raccolta, il documento verrà aperto nel Web browser nell'applicazione Web corrispondente al tipo di documento. L'utente potrà poi decidere di aprire il documento nell'applicazione client.
    
      - **Usa impostazione predefinita server**   Quando un utente sceglie un documento in questa raccolta, il documento verrà aperto in base al comportamento di apertura predefinito specificato per il server che esegue SharePoint 2013.

 **Impostazione del comportamento di apertura predefinito per raccolte documenti protette tramite IRM mediante Windows PowerShell**

1.  Verificare innanzitutto di essere membri dei ruoli e dei gruppi seguenti:
    
      - Ruolo predefinito del server **securityadmin** nell'istanza di SQL Server.
    
      - Ruolo predefinito del database **db\_owner** in tutti i database da aggiornare.
    
      - Gruppo Administrators sul server sul quale si eseguono i cmdlet di Windows PowerShell.
    
    Leggere inoltre l'argomento [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050) e aggiungere eventuali altre appartenenze necessarie.
    
    Un amministratore può usare il cmdlet **Add-SPShellAdmin** per concedere le autorizzazioni per l'uso dei cmdlet di SharePoint 2013.
    

    > [!NOTE]
    > Se non si dispone delle autorizzazioni, richiederle all'amministratore responsabile dell'installazione o all'amministratore di SQL Server. Per ulteriori informazioni sulle autorizzazioni di Windows PowerShell, vedere <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Permissions</A> e <A href="https://technet.microsoft.com/it-it/library/ff607596(v=office.15)">Add-SPShellAdmin</A>.



2.  Aprire una SharePoint 2013 Management Shell con privilegi elevati attenendosi alla procedura seguente:
    
    **In Windows Server 2008**
    
    1.  Fare clic sul pulsante **Start** e scegliere **Tutti i programmi**.
    
    2.  Selezionare **Prodotti Microsoft SharePoint 2013**.
    
    3.  Scegliere **Shell di gestione SharePoint 2013** e visualizzare il menu di scelta rapida facendo clic con il pulsante destro del mouse.
    
    4.  Scegliere **Esegui come amministratore** dal menu di scelta rapida.
    
    **In Windows Server 2012**
    
    1.  Scorrere rapidamente dal bordo dello schermo per visualizzare gli accessi e quindi scegliere **Cerca** per visualizzare tutte le applicazioni installate nel computer.
    
    2.  Fare clic con il pulsante destro del mouse su **SharePoint 2013 Management Shell** per visualizzare la barra delle applicazioni.
    
    3.  Nella barra delle applicazioni scegliere **Esegui come amministratore**.

3.  Al prompt dei comandi di Windows PowerShell digitare il comando seguente:
    
        Get-SPWeb -site <SiteCollURL> | % {$_.Lists} | where {$_.IrmEnabled -eq $true} | % {$_.DefaultItemOpen =[Microsoft.Sharepoint.DefaultItemOpen]::<DefaultItemOpenSetting>; $_.Update()}
    
    dove:
    
      - *\<SiteCollURL\>* è l'URL della raccolta siti in cui si trovano le raccolte documenti.
    
      - *\<DefaultItemOpenSetting\>* è un valore di enumerazione di **DefaultItemOpen** che specifica il comportamento di apertura predefinito. Utilizzare **PreferClient** per aprire i documenti nelle applicazioni client eventualmente associate. Utilizzare **Browser** per aprire i documenti nel browser.

## Vedere anche


[Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Windows PowerShell per amministrare SharePoint 2013](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps)  
[Server Office Web Apps](office-web-apps-server.md)  


[Get-SPWeb](https://technet.microsoft.com/it-it/library/ff607807\(v=office.15\))  
[Get-SPSite](https://technet.microsoft.com/it-it/library/ff607950\(v=office.15\))  
[Get-SPFeature](https://technet.microsoft.com/it-it/library/ff607945\(v=office.15\))

