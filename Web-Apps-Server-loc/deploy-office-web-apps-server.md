---
title: Distribuire il server Office Web Apps
TOCTitle: Distribuire il server Office Web Apps
ms:assetid: e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219455(v=office.15)
ms:contentKeyID: 49652297
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Distribuire il server Office Web Apps 

_<strong>Si applica a:</strong>Office Web Apps Server_

_<strong>Ultima modifica dell'argomento:</strong>2017-10-05_

**Riepilogo:** spiega come distribuire il server Office Web Apps in locale per l'uso con SharePoint 2013 e Lync Server 2013.

**Destinatari:** professionisti IT

In questo articolo viene illustrata l'installazione di server Office Web Apps per l'azienda. Se si necessita di assistenza con la copia personale di Office o Office Web Apps, vedere <https://support.office.com>.

La distribuzione del [server Office Web Apps](office-web-apps-server-overview.md) implica l'installazione di alcuni componenti software prerequisiti e l'esecuzione di alcuni comandi di Windows PowerShell, ma nel complesso la procedura è piuttosto semplice. Questo articolo illustra nel dettaglio le operazioni da eseguire per preparare i server, quindi fornisce i comandi di Windows PowerShell necessari per configurare la farm di server Office Web Apps.

Contenuto dell'articolo:

  - Guardare un video per vedere i passaggi di configurazione

  - Esaminare queste risorse prima di iniziare

  - Preparazione dei server per l'esecuzione del server Office Web Apps

  - Distribuire la farm di server Office Web Apps

  - Se viene visualizzato il messaggio di errore "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server"

## Guardare un video per vedere i passaggi di configurazione

Guardare il video seguente per vedere come installare il server Office Web Apps in un ambiente di testing e per una panoramica della configurazione di SharePoint 2013 per l'uso del server Office Web Apps.

**Installare il server Office Web Apps in un ambiente di testing**

> [!VIDEO https://www.microsoft.com/it-it/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

## Esaminare queste risorse prima di iniziare

Prima di iniziare, è consigliabile esaminare le risorse seguenti:

  - Per informazioni sui requisiti hardware e software, [vedere le linee guida sulla pianificazione](plan-office-web-apps-server.md).

  - Per impostazione predefinita, il server Office Web Apps consente di visualizzare i file di Office ma non di modificarli. Per modificare i file è necessaria una licenza apposita, illustrata in [Pianificare Office Web Apps (utilizzato con SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md) e [Configurare la gestione delle licenze in SharePoint Server 2013](https://technet.microsoft.com/it-it/library/jj219627\(v=office.15\)).


> [!NOTE]
> In tutte le famiglie di prodotti Office 2013 è possibile eseguire attività utilizzando il mouse, le scelte rapide da tastiera o la modalità tocco. Per informazioni su come utilizzare le scelte rapide da tastiera e la modalità tocco con i prodotti e i servizi di Office, vedere l'articolo relativo alle <A href="https://go.microsoft.com/fwlink/p/?linkid=249150">scelte rapide da tastiera</A> e <A href="https://go.microsoft.com/fwlink/p/?linkid=253163">Guida ai gesti di Office</A>.



## Preparazione dei server per l'esecuzione del server Office Web Apps

Eseguire queste procedure su tutti i server che eseguiranno il server Office Web Apps.

**Figura: passaggi da eseguire per preparare i server per il server Office Web Apps**

![Le tre fasi principali della preparazione dei server per il server Office Web Apps](images/JJ219455.af2a4690-4f8b-42c3-aab5-f7066bc0a936(Office.15).gif "Le tre fasi principali della preparazione dei server per il server Office Web Apps") 

## Passaggio 1: installare i prerequisiti software per il server Office Web Apps

Windows Server 2008 R2, Windows Server 2012 e Windows Server 2012 R2 hanno prerequisiti leggermente diversi. Selezionare quindi la procedura appropriata per installare i prerequisiti corretti per il sistema operativo in uso.

**In Windows Server 2008 R2**

1.  Installare il seguente software:
    
      - [Windows Server 2008 R2 Service Pack 1](http://go.microsoft.com/fwlink/p/?linkid=252370)
    
      - [.NET Framework 4.5](https://go.microsoft.com/fwlink/p/?linkid=256560)
    
      - [Windows PowerShell 3.0](https://go.microsoft.com/fwlink/p/?linkid=244693)
    
      - [Aggiornamento piattaforma Windows 7 SP1 e Windows Server 2008 R2 SP1 (KB2670838)](https://go.microsoft.com/fwlink/p/?linkid=293629)

2.  Aprire il prompt di Windows PowerShell come amministratore ed eseguire i comandi seguenti per installare i ruoli e i servizi richiesti.
    
    ```PowerShell
        Import-Module ServerManager
    ```
    
    Eseguire quindi il comando seguente:
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-WebServer,Web-Common-Http,Web-Static-Content,Web-App-Dev,Web-Asp-Net,Web-Net-Ext,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,Web-Security,Web-Windows-Auth,Web-Filtering,Web-Stat-Compression,Web-Dyn-Compression,Web-Mgmt-Console,Ink-Handwriting,IH-Ink-Support,NET-Framework,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-Win-CFAC
    ```
    
    Se richiesto, riavviare il server.

**In Windows Server 2012**

1.  Aprire il prompt di Windows PowerShell come amministratore ed eseguire il comando seguente per installare i ruoli e i servizi richiesti.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Se richiesto, riavviare il server.

**In Windows Server 2012 R2**

1.  Installare il seguente software:
    
      - [.NET Framework 4.5.2](https://go.microsoft.com/fwlink/p/?linkid=510096)

2.  Aprire il prompt di Windows PowerShell come amministratore ed eseguire il comando seguente per installare i ruoli e i servizi richiesti.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Se richiesto, riavviare il server.

## Passaggio 2: installare Office Web Apps Server e i relativi aggiornamenti

Completare questa procedura su tutti i server che eseguiranno server Office Web Apps.

1.  Scaricare server Office Web Apps dal [Volume Licensing Service Center (VLSC)](https://go.microsoft.com/fwlink/p/?linkid=256561). Per scaricare server Office Web Apps è necessario disporre di una licenza nell'ambito di un contratto multilicenza per Office Professional Plus 2013, Office Standard 2013 o Office per Mac 2011. L'opzione di download è disponibile sotto questi prodotti di Office nel portale VLSC.

2.  Eseguire una delle operazioni seguenti:
    
      - Per Windows Server 2012 o Windows Server 2012 R2, aprire direttamente il file .img ed eseguire **Setup.exe**.
    
      - Per Windows Server 2008 R2 SP1, usare un programma in grado di montare o estrarre file img, quindi eseguire **Setup.exe**.

3.  Nella pagina **Condizioni di licenza software Microsoft** selezionare **Accetto i termini del contratto** e quindi fare clic su **Continua**.

4.  Nella pagina **Scegliere il percorso del file** selezionare la cartella in cui installare i file del server Office Web Apps (ad esempio, C:\\Programmi\\Microsoft Office Web Apps), quindi selezionare **Installa**. Se la cartella specificata non esiste, viene creata automaticamente.
    
    È consigliabile installare server Office Web Apps sull'unità di sistema.

5.  Al termine dell'installazione del server Office Web Apps, scegliere **Chiudi**.

6.  Scaricare e installare [Office Web Apps Server SP1](https://go.microsoft.com/fwlink/p/?linkid=510097) (Consigliato per Windows Server 2012 e Windows Server 2008 R2 SP1. Obbligatorio per Windows Server 2012 R2.)
    

    > [!NOTE]
    > Se si intende installare Office Web Apps Server SP1 in un secondo tempo, seguire le istruzioni riportate in <A href="apply-software-updates-to-office-web-apps-server.md">Applicare aggiornamenti software al server Office Web Apps</A>.



7.  Controllare gli aggiornamenti più recenti di server Office Web Apps rivedendo l'elenco disponibile in [Download e aggiornamenti per Office](https://go.microsoft.com/fwlink/p/?linkid=280271).
    

    > [!NOTE]
    > Se Office Web Apps Server SP1 non è stato installato, seguire le istruzioni riportate in <A href="https://go.microsoft.com/fwlink/p/?linkid=296579">KB2810007</A>.



## Passaggio 3: installare i Language Pack per il server Office Web Apps

I Language Pack per il server Office Web Apps 2013 consentono agli utenti di visualizzare i file di Office basati sul Web in più lingue dalle raccolte documenti di SharePoint 2013, da Outlook Web Access (come anteprime degli allegati) e da Lync 2013 (come trasmissioni di PowerPoint). Per altre informazioni sul funzionamento dei Language Pack, vedere [Planning language packs for Office Web Apps Server](plan-office-web-apps-server.md).

Per installare i Language Pack, eseguire la procedura seguente:


1.  Scaricare i Language Pack per il server Office Web Apps dall'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?linkid=263945).

2.  Eseguire **WebAppsServerLP\_en\_us\_x64.exe**.

3.  Nella procedura guidata dei Language Pack del server Office Web Apps 2013, nella pagina **Condizioni di licenza software Microsoft**, selezionare **Accetto i termini del contratto** e quindi **Continua**.

4.  Al termine dell'installazione del server Office Web Apps, scegliere **Chiudi**.

> [!IMPORTANT]
> <ul>
> <li><p>Per installare i Language Pack dopo la creazione della farm di server Office Web Apps, è necessario rimuovere il server dalla farm, installarvi il Language Pack, quindi aggiungere nuovamente il server alla farm.</p></li>
> <li><p>Perché un Language Pack funzioni correttamente, deve essere installato in tutti i server della farm.</p></li>
> </ul>

## Distribuire la farm di server Office Web Apps

Eseguire le procedure illustrate in una delle tre sezioni seguenti, a seconda del tipo di farm di server Office Web Apps che si vuole creare.

> [!TIP]
> Se Windows PowerShell non riconosce il cmdlet <strong>New-OfficeWebAppsFarm</strong> quando viene eseguito, può essere necessario importare il modulo <strong>OfficeWebApps</strong> utilizzando il comando seguente:<br />
<code>Import-Module -Name OfficeWebApps</code>

## Distribuire una farm di server Office Web Apps a server singolo che usa HTTP

Questa è la procedura da eseguire se si vuole distribuire il server Office Web Apps solo a scopo di testing o per uso interno e non si ha la necessità di fornire le funzionalità del server Office Web Apps a Lync Server 2013. In questo caso occorre installare una farm di server Office Web Apps a server singolo che usa HTTP. Non è necessario un certificato o un servizio di bilanciamento del carico, ma piuttosto un server fisico dedicato o un'istanza di macchina virtuale che non esegua altre applicazioni server.

È possibile usare questa farm di server Office Web Apps per fornire le funzionalità Office Web Apps a SharePoint 2013.

**Figura: passaggi da eseguire per distribuire il server Office Web Apps**

![Le tre fasi principali della distribuzione di una farm di server Office Web Apps a server singolo.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Le tre fasi principali della distribuzione di una farm di server Office Web Apps a server singolo.")

## Passaggio 1: creare la farm di server Office Web Apps

Usare il comando **New-OfficeWebAppsFarm** per creare una nuova farm di server Office Web Apps costituita da un solo server, come illustrato nell'esempio seguente.

```PowerShell
    New-OfficeWebAppsFarm -InternalURL "http://servername" -AllowHttp -EditingEnabled
```

**Parametri**

  - **–InternalURL** è il nome del server che esegue server Office Web Apps, ad esempio **http://servername**.

  - **–AllowHttp** configura la farm per l'uso di HTTP.

  - **–EditingEnabled** consente la modifica in Office Web Apps quando usato con SharePoint 2013. Questo parametro non viene usato da Lync Server 2013 perché questo host non supporta la modifica.

Ulteriori parametri per la configurazione dei servizi di conversione, server proxy, supporto per le ClipArt e visualizzatori online sono descritti in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Se viene visualizzato il messaggio di errore "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server"

## Passaggio 2: verificare che la farm di server Office Web Apps sia stata creata correttamente

Al termine della creazione della farm, i relativi dettagli vengono visualizzati nel prompt di Windows PowerShell. Per verificare che il server Office Web Apps sia installato e configurato correttamente, usare un Web browser per accedere all'URL di individuazione del server Office Web Apps, come indicato nell'esempio seguente. L'URL di individuazione è il parametro *InternalUrl* specificato al momento della configurazione della farm di server Office Web Apps, seguito da **/hosting/discoperse**, ad esempio:

```
    http://servername/hosting/discovery
```

Se il server Office Web Apps funziona come previsto, nel Web browser verrà visualizzato un file XML di individuazione COPI (Web Application Open Platform Interface Protocol). Le prime righe del file dovrebbero avere un aspetto simile al seguente:

```XML
    <?xml version="1.0" encoding="utf-8" ?> 
    - <wopi-discovery>
    - <net-zone name="internal-http">
    - <app name="Excel" favIconUrl="http://servername/x/_layouts/images/FavIcon_Excel.ico" checkLicense="true">
    <action name="view" ext="ods" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xls" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsb" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsm" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
```

## Passaggio 3: configurare l'host

A questo punto, la farm è pronta per fornire agli host le funzionalità di Office Web Apps tramite HTTP. Visitare [Configurare Office Web Apps per l'uso con SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md) per ulteriori informazioni sulla configurazione degli host.

## Distribuzione di una farm di server Office Web Apps a server singolo che utilizza il protocollo HTTPS
<a name="singlehttps"> </a>

Per la maggior parte degli ambienti di produzione, l'uso di HTTPS è decisamente consigliato per via delle sue funzionalità di sicurezza. HTTPS è inoltre necessario per fornire le funzionalità del server Office Web Apps a Lync Server 2013, che consente agli utenti di visualizzare trasmissioni di PowerPoint in un browser. Per installare una farm di server Office Web Apps a server singolo che usa HTTPS è necessario installare un certificato sul server, come descritto in [Securing Office Web Apps Server communications by using HTTPS](plan-office-web-apps-server.md).

Questa farm di server Office Web Apps fornirà le funzionalità di Office Web Apps a SharePoint 2013 e Lync Server 2013.

**Figura: passaggi da eseguire per distribuire il server Office Web Apps**

![Le tre fasi principali della distribuzione di una farm di server Office Web Apps a server singolo.](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Le tre fasi principali della distribuzione di una farm di server Office Web Apps a server singolo.")

## Passaggio 1: creare la farm di server Office Web Apps

Usare il comando **New-OfficeWebAppsFarm** per creare una nuova farm di server Office Web Apps costituita da un solo server, come illustrato nell'esempio seguente.

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -CertificateName "OfficeWebApps Certificate" -EditingEnabled
```

**Parametri**

  - **–InternalURL** è il nome di dominio completo (FQDN) del server che esegue il server Office Web Apps, ad esempio **http://server.contoso.com**.

  - **–ExternalURL** è il nome di dominio completo accessibile su Internet.

  - **–CertificateName** è il nome descrittivo del certificato.

  - **–EditingEnabled** è facoltativo e consente la modifica in Office Web Apps quando usato con SharePoint 2013. Questo parametro non viene usato da Lync Server 2013 perché questo host non supporta la modifica.

Ulteriori parametri per la configurazione dei servizi di conversione, server proxy, supporto per le ClipArt e visualizzatori online sono descritti in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Se viene visualizzato il messaggio di errore "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server"

## Passaggio 2: verificare che la farm di server Office Web Apps sia stata creata correttamente

Al termine della creazione della farm, i relativi dettagli vengono visualizzati nel prompt di Windows PowerShell. Per verificare che il server Office Web Apps sia installato e configurato correttamente, usare un Web browser per accedere all'URL di individuazione del server Office Web Apps, come indicato nell'esempio seguente. L'URL di individuazione è il parametro *InternalUrl* specificato al momento della configurazione della farm di server Office Web Apps, seguito da **/hosting/discovery**, ad esempio:

```
    https://server.contoso.com/hosting/discovery
```

Se il server Office Web Apps funziona come previsto, nel Web browser verrà visualizzato un file XML di individuazione WOPI (Web Application Open Platform Interface Protocol). Le prime righe del file dovrebbero avere un aspetto simile al seguente:

```XML 
<?xml version="1.0" encoding="UTF-8"?>
<wopi-discovery><net-zone 
name="internal-https"><app name="Excel" checkLicense="true" 
favIconUrl="https://wac.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action 
name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="ods"/><action name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="xls"/><action name="view" 
```

> [!NOTE]
> A seconda delle impostazioni di sicurezza del Web browser, è possibile che venga visualizzato un messaggio in cui si richiede di selezionare <STRONG>Mostra tutto il contenuto</STRONG> prima che vengano visualizzati i contenuti del file XML di individuazione.

## Passaggio 3: configurare l'host

A questo punto, la farm è pronta per fornire agli host le funzionalità di Office Web Apps tramite HTTPS. Per ulteriori informazioni su come configurare gli host, vedere gli articoli seguenti.

  - [Configurare Office Web Apps per l'uso con SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Distribuzione di una farm di server Office Web Apps con più server e bilanciamento del carico che utilizza il protocollo HTTPS
<a name="multihttps"> </a>

Se si prevede un traffico elevato nella farm di server Office Web Apps e si vuole renderla disponibile sia su Internet che nella rete interna aziendale, questo tipo di topologia è quella più adatta. Questa sezione illustra come installare una farm di server Office Web Apps multiserver che usa un servizio di bilanciamento del carico e HTTPS. Se si è interessati, sono disponibili [altre informazioni su questa topologia](plan-office-web-apps-server.md).

Prima di iniziare, verificare che il servizio di bilanciamento del carico sia configurato come descritto in [Load balancer requirements for Office Web Apps Server](plan-office-web-apps-server.md). Occorre anche installare un certificato sul servizio di bilanciamento del carico, come descritto in [Securing Office Web Apps Server communications by using HTTPS](plan-office-web-apps-server.md). Questa farm di server Office Web Apps fornirà le funzionalità di Office Web Apps a SharePoint 2013 e Lync Server 2013.

**Figura: passaggi da eseguire per distribuire il server Office Web Apps**

![Le quattro fasi principali della distribuzione di una farm di server Office Web Apps con più server.](images/JJ219455.4c4b31cb-961b-4efd-b755-a18bdcb5c191(Office.15).gif "Le quattro fasi principali della distribuzione di una farm di server Office Web Apps con più server.")

## Passaggio 1: creare la farm di server Office Web Apps nel primo server

Usare il comando **New-OfficeWebAppsFarm** per creare una nuova farm di server Office Web Apps nel primo server, come illustrato nell'esempio seguente.

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -SSLOffloaded -EditingEnabled
```

**Parametri**

  - **–InternalURL** è il nome di dominio completo (FQDN) del server che esegue il server Office Web Apps, ad esempio **http://server.contoso.com**.

  - **–ExternalURL** è il nome di dominio completo accessibile su Internet.

  - **-SSLOffloaded** consente l'offload della terminazione SSL al servizio di bilanciamento del carico.

  - **–EditingEnabled** è facoltativo e consente la modifica in Office Web Apps quando usato con SharePoint 2013. Questo parametro non viene usato da Lync Server 2013 perché questo host non supporta la modifica.

Ulteriori parametri per la configurazione dei servizi di conversione, server proxy, supporto per le ClipArt e visualizzatori online sono descritti in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Se viene visualizzato il messaggio di errore "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server"

## Passaggio 2: aggiungere altri server alla farm

Quando nel primo server è in esecuzione il server Office Web Apps, eseguire il comando **New-OfficeWebAppsMachine** su ogni server che si vuole aggiungere alla farm di server Office Web Apps. Per il parametro **–MachineToJoin** usare il nome computer di uno dei server già presenti nella farm di server Office Web Apps. Ad esempio, se server1.contoso.com è già nella farm, usare il comando seguente:

```PowerShell
    New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
```

È possibile trovare altre informazioni su questi parametri in [New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps).

## Passaggio 3: verificare che la farm di server Office Web Apps sia stata creata correttamente

Al termine della creazione della farm, i relativi dettagli vengono visualizzati nel prompt di Windows PowerShell. Per verificare che il server Office Web Apps sia installato e configurato correttamente, usare un Web browser per accedere all'URL di individuazione del server Office Web Apps, come indicato nell'esempio seguente. L'URL di individuazione è il parametro *InternalUrl* specificato al momento della configurazione della farm di server Office Web Apps, seguito da **/hosting/discovery**. Ad esempio:

```
    https://server.contoso.com/hosting/discovery
```

Se il server Office Web Apps funziona come previsto, nel Web browser verrà visualizzato un file XML di individuazione WOPI (Web Application Open Platform Interface Protocol). Le prime righe del file dovrebbero avere un aspetto simile al seguente:

```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <wopi-discovery><net-zone name="internal-https"><app name="Excel" checkLicense="true" favIconUrl="https://officewebapps.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="ods"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xls"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xlsb"/> 
```

> [!NOTE]
> A seconda delle impostazioni di sicurezza del Web browser, è possibile che venga visualizzato un messaggio in cui si richiede di selezionare <STRONG>Mostra tutto il contenuto</STRONG> prima che vengano visualizzati i contenuti del file XML di individuazione.

## Passaggio 4: configurare l'host

A questo punto, la farm è pronta per fornire agli host le funzionalità di Office Web Apps tramite HTTPS. Per ulteriori informazioni su come configurare gli host, vedere gli articoli seguenti.

  - [Configurare Office Web Apps per l'uso con SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Se viene visualizzato il messaggio di errore "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server"

Se le caratteristiche di .NET Framework 3.5 sono state installate e successivamente rimosse, quando si eseguono i cmdlet di Office Web Apps potrebbe essere visualizzato il messaggio "500 - Eccezioni servizio Web" o "500.21 - Errore interno del server". Per correggere gli errori, eseguire i seguenti comandi di esempio da un prompt dei comandi con privilegi elevati per pulire le impostazioni che possono impedire il corretto funzionamento del server Office Web Apps:

**Per Windows Server 2008 R2**

   ```PowerShell
    %systemroot%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -iru 
   
    iisreset /restart /noforce
   ```

**Per Windows Server 2012 o Windows Server 2012 R2**

   ```PowerShell
    dism /online /enable-feature /featurename:IIS-ASPNET45
   ``` 

## Vedere anche


[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Pianificare il server Office Web Apps](plan-office-web-apps-server.md)  
[Configurare Office Web Apps per l'uso con SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)  


[Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)  
  

[](configure-office-web-apps-for-sharepoint-2013.md)

