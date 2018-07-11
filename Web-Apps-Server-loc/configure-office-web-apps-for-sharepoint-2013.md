---
title: Configurare Office Web Apps per l'uso con SharePoint 2013
TOCTitle: Configurare Office Web Apps per l'uso con SharePoint 2013
ms:assetid: a5276781-133b-413c-beca-b851e17c2081
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ff431687(v=office.15)
ms:contentKeyID: 49652279
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Configurare Office Web Apps per l'uso con SharePoint 2013 

_**Si applica a:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:** 2016-12-16_

**Riepilogo:** in questo articolo viene illustrato come configurare SharePoint 2013 per l'utilizzo di Office Web Apps.

**Destinatari:** professionisti IT

Questo articolo riprende da dove [Distribuire il server Office Web Apps](deploy-office-web-apps-server.md) era terminato. Mentre il primo articolo spiegava come configurare il server che esegue il server Office Web Apps, questo spiega come configurare SharePoint 2013 per l'uso del server Office Web Apps. Prima di tutto è necessario eseguire alcuni cmdlet di Windows PowerShell da SharePoint 2013, in modo da consentire agli utenti di aprire file di Office da raccolte documenti di SharePoint 2013 in un browser.

Se non si ha familiarità con le caratteristiche del server Office Web Apps, [vedere la panoramica del prodotto](office-web-apps-server-overview.md).

Contenuto dell'articolo:

  - Prima di configurare SharePoint 2013 per l'uso del server Office Web Apps

  - Configurare SharePoint 2013 per l'uso del server Office Web Apps

  - Risolvere gli errori in Office Web Apps se usato con SharePoint 2013

  - Disconnettere SharePoint 2013 da Office Web Apps Server

## Prima di configurare SharePoint 2013 per l'uso del server Office Web Apps

Ecco alcune cose da verificare prima di iniziare:

  - Installare SharePoint 2013. Per istruzioni, vedere [Installare SharePoint 2013](https://technet.microsoft.com/it-it/library/cc303424\(v=office.15\)).

  - Verificare che tutte le applicazioni Web di SharePoint 2013 usino l'autenticazione basata sulle attestazioni. Il rendering e la modifica di Office Web Apps non funzionano nelle applicazioni Web di SharePoint 2013 che usano l'autenticazione in modalità classica. Per altre informazioni, vedere [SharePoint authentication requirements for Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md)

  - Per consentire agli utenti di modificare, oltre che di leggere, i documenti di Office in un Web browser, è necessario disporre di una licenza per la modifica e abilitare la modifica nella farm di server Office Web Apps. Per altre informazioni sui requisiti di licenza, vedere [Licensing Office Web Apps for editing Office files](plan-office-web-apps-used-with-sharepoint-2013.md)

  - Se si accede a SharePoint 2013 con l'account di sistema, non sarà possibile testare la connessione tra SharePoint 2013 e il server Office Web Apps. Per testare la connessione è necessario accedere con un account diverso.

  - Condizioni di scarsa memoria possono impedire la visualizzazione delle anteprime dei documenti di Office in Office Web Apps. Rivedere l'articolo [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/it-it/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) per SharePoint 2013. Sono gli stessi requisiti usati dal server Office Web Apps.

## Configurare SharePoint 2013 per l'uso del server Office Web Apps

Scegliere una delle sezioni seguenti a seconda che si voglia usare HTTP o HTTPS. HTTP generalmente è consigliato solo per gli ambienti di testing. Negli ambienti di produzione il protocollo HTTPS, più sicuro, è la scelta migliore.

## In un ambiente di testing che usa HTTP

Per questa configurazione, verificare di avere installato il server Office Web Apps seguendo i passaggi descritti in [Deploy a single-server Office Web Apps Server farm that uses HTTP](deploy-office-web-apps-server.md). Configurare la farm di server Office Web Apps per l'uso di un URL interno e del protocollo HTTP. Il [Video: Configurare Office Web Apps per SharePoint 2013](video-configure-office-web-apps-for-sharepoint-2013.md) mostra come installare il server Office Web Apps e configurare SharePoint 2013 per l'uso del server Office Web Apps in un ambiente di testing.

## Passaggio 1: aprire SharePoint 2013 Management Shell con privilegi elevati

Scegliere la procedura che corrisponde al sistema operativo del proprio server.

**In Windows Server 2008 R2**

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi** e quindi **Prodotti Microsoft SharePoint 2013**.

2.  Fare clic con il pulsante destro del mouse su **SharePoint 2013 Management Shell** e scegliere **Esegui come amministratore**.

**In Windows Server 2012**

1.  Premere il tasto logo Windows + Q e scorrere dal bordo dello schermo per visualizzare gli accessi, quindi fare clic su **Cerca** per visualizzare tutte le applicazioni installate nel computer.

2.  Fare clic con il pulsante destro del mouse su **SharePoint 2013 Management Shell** per visualizzare la barra dell'app.

3.  Nella barra dell'app fare clic su **Esegui come amministratore**.

## Passaggio 2: creare l'associazione tra SharePoint 2013 e il server Office Web Apps

Eseguire il comando seguente, dove \<WacServerName\> è il nome di dominio completo (FQDN) dell'URL impostato come URL interno e rappresenta il punto di ingresso del traffico del server Office Web Apps. In questo ambiente di testing è necessario specificare il parametro –AllowHTTP per consentire a SharePoint 2013 di ricevere le informazioni di individuazione dalla farm di server Office Web Apps usando il protocollo HTTP. Se non si specifica –AllowHTTP, SharePoint 2013 tenterà di usare il protocollo HTTPS per comunicare con la farm di server Office Web Apps e il comando non riuscirà.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> -AllowHTTP
```

Dopo l'esecuzione del comando, dovrebbe comparire un elenco di associazioni nel prompt dei comandi di Windows PowerShell.

Per informazioni, vedere [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Passaggio 3: visualizzare le aree WOPI per le associazioni di SharePoint

Il server Office Web Apps usa le zone per determinare quale URL (interno o esterno) e quale protocollo (HTTP o HTTPS) usare per comunicare con l'host, che in questo caso è SharePoint 2013. Per impostazione predefinita, SharePoint Server 2013 usa la zona **internal-https**. Verificare qual è la zona corrente eseguendo il comando seguente:

```PowerShell
    Get-SPWOPIZone
```

La zona WOPI visualizzata mediante questo comando deve essere **internal-http**. Se viene visualizzata correttamente, andare direttamente al passaggio 5, altrimenti vedere il prossimo passaggio.

Per informazioni, vedere [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Passaggio 4: modificare l'area WOPI e impostarla su internal-http

Se il risultato del passaggio 3 era **internal-https**, eseguire il comando seguente per modificare la zona in **internal-http**. Questa modifica è necessaria poiché la zona di SharePoint 2013 deve corrispondere alla zona della farm di server Office Web Apps.

```PowerShell
    Set-SPWOPIZone -zone "internal-http"
```

Verificare che la nuova zona sia **internal-http** eseguendo di nuovo **Get-SPWOPIZone**.

Per informazioni, vedere [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps) e [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Passaggio 5: modificare l'impostazione AllowOAuthOverHttp in SharePoint 2013 su True

Per usare Office Web Apps con SharePoint 2013 su HTTP in un ambiente di testing, è necessario impostare AllowOAuthOverHttp su **True**, altrimenti Office Web Apps non funzionerà. È possibile verificare lo stato corrente eseguendo il comando seguente:

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Se il comando restituisce **False**, eseguire i comandi seguenti per impostare il valore su **True**.

```PowerShell
    $config = (Get-SPSecurityTokenServiceConfig)

    $config.AllowOAuthOverHttp = $true

    $config.Update()
```

Eseguire di nuovo il comando seguente per verificare che AllowOAuthOverHttp sia impostato su **True**.

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Per informazioni, vedere [Get-SPSecurityTokenServiceConfig](https://technet.microsoft.com/it-it/library/ff607642\(v=office.15\)).

## Passaggio 6: verificare che Office Web Apps funzioni

In SharePoint 2013 assicurarsi di non avere effettuato l'accesso con l'account di sistema, altrimenti non è possibile modificare o visualizzare i documenti con Office Web Apps. Passare a una raccolta documenti di SharePoint 2013 che contiene documenti di Office e visualizzare un file di Word, PowerPoint, Excel o OneNote. Il documento dovrebbe aprirsi in un browser che mostra il file in Office Web Apps.

Se questo passaggio ha esito negativo, vedere Risolvere gli errori in Office Web Apps se usato con SharePoint 2013.

## In un ambiente di produzione che usa HTTPS

Prima di continuare con le procedure seguenti, assicurarsi di avere configurato il server Office Web Apps mediante i passaggi illustrati in [Deploy a single-server Office Web Apps Server farm that uses HTTPS](deploy-office-web-apps-server.md#singlehttps) o [Distribuzione di una farm di server Office Web Apps con più server e bilanciamento del carico che utilizza il protocollo HTTPS](deploy-office-web-apps-server.md#multihttps).

## Passaggio 1: aprire SharePoint 2013 Managament Shell.

Scegliere la procedura che corrisponde al sistema operativo del proprio server.

**In Windows Server 2008 R2**

1.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi** e quindi **Prodotti Microsoft SharePoint 2013**.

2.  Fare clic con il pulsante destro del mouse su **SharePoint 2013 Management Shell** e scegliere **Esegui come amministratore** dal menu di scelta rapida.

**In Windows Server 2012**

1.  Premere il tasto logo Windows + Q e scorrere dal bordo dello schermo per visualizzare gli accessi, quindi fare clic su **Cerca** per visualizzare tutte le applicazioni installate nel computer.

2.  Fare clic con il pulsante destro del mouse su **SharePoint 2013 Management Shell** per visualizzare la barra dell'app.

3.  Nella barra dell'app fare clic su **Esegui come amministratore**.

## Passaggio 2: creare l'associazione tra SharePoint 2013 e il server Office Web Apps

Eseguire il comando seguente, dove \<WacServerName\> è il nome di dominio completo (FQDN) dell'URL impostato come URL interno e rappresenta il punto di ingresso del traffico del server Office Web Apps.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> 
```

Per informazioni, vedere [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Passaggio 3: visualizzare l'area WOPI di SharePoint 2013

Il server Office Web Apps usa le zone per determinare quale URL (interno o esterno) e quale protocollo (HTTP o HTTPS) usare per comunicare con l'host, che in questo caso è SharePoint 2013. Per impostazione predefinita, SharePoint Server 2013 usa la zona **internal-https**. Verificare che questa sia la zona corrente eseguendo il comando seguente:

```PowerShell
    Get-SPWOPIZone
```

Prendere nota della zona WOPI visualizzata.

Per informazioni, vedere [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Passaggio 4: modificare la zona WOPI, se necessario

A seconda dell'ambiente, potrebbe essere necessario modificare la zona WOPI. Se si dispone di una farm di SharePoint sia interna che esterna, specificare external. Se invece si dispone di una farm di SharePoint solo interna, specificare internal.

Se il risultato del passaggio 3 è **internal-https** e la farm di SharePoint è solo interna, è possibile saltare questo passaggio. Se invece la farm di SharePoint è sia interna che esterna, è necessario eseguire il comando seguente per modificare la zona in **external-https**.

```PowerShell
    Set-SPWOPIZone -zone "external-https"
```

Per informazioni, vedere [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps).

## Passaggio 5: verificare che Office Web Apps funzioni

In SharePoint 2013 assicurarsi di non avere effettuato l'accesso con l'account di sistema, altrimenti non è possibile modificare o visualizzare i documenti con Office Web Apps. Passare a una raccolta documenti di SharePoint 2013 che contiene documenti di Office e visualizzare un file di Word, PowerPoint, Excel o OneNote. Il documento dovrebbe aprirsi in un browser che mostra il file in Office Web Apps.

Se questo passaggio ha esito negativo, vedere Risolvere gli errori in Office Web Apps se usato con SharePoint 2013.

## Risolvere gli errori in Office Web Apps se usato con SharePoint 2013

Se Office Web Apps non funziona correttamente con SharePoint 2013, individuare il sintomo del problema tra quelli elencati di seguito ed espandere il titolo per visualizzare la risoluzione.

## Problema: quando si seleziona il collegamento "nuovo documento" in una raccolta documenti di SharePoint, viene richiesto di caricare un documento invece di visualizzare l'opzione per la creazione di un nuovo documento di Office. Selezionando (con un clic singolo) un documento di Office, il file viene aperto nell'applicazione client. Le anteprime dei documenti di Office non sono visualizzate.

Ecco alcune opzioni per la risoluzione che è possibile tentare.

**Verificare che l'applicazione Web di SharePoint utilizzata per creare il nuovo documento utilizzi l'autenticazione basata sulle attestazioni**

Solo le applicazioni Web che utilizzano l'autenticazione basata sulle attestazioni possono aprire file in Office Web Apps. Per determinare il provider di autenticazione di un'applicazione Web, seguire questi passaggi:

1.  In Amministrazione centrale SharePoint 2013 selezionare **Gestisci applicazioni Web**.

2.  Selezionare l'applicazione Web da verificare e quindi fare clic su **Provider di autenticazione** sulla barra multifunzione.

Per funzionare correttamente con l'applicazione Web, il provider di autenticazione deve essere visualizzato come **Autenticazione basata sulle attestazioni** per Office Web Apps. Per risolvere il problema, è possibile eliminare l'applicazione Web e crearla nuovamente usando l'autenticazione basata sulle attestazioni oppure modificare il metodo di autenticazione dell'applicazione Web. Per altre informazioni, vedere [SharePoint authentication requirements for Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

**Verificare che le zone WOPI corrispondano nella farm di SharePoint 2013 e del server Office Web Apps.**

A tale scopo, eseguire il comando seguente in SharePoint Server:

```PowerShell
    Get-SPWopiZone 
```

Il risultato sarà uno dei seguenti valori:

  - internal-https

  - internal-http

  - external-https

  - external-http

Eseguire quindi il comando seguente in SharePoint Server:

```PowerShell
    Get-SPWOPIBinding
```

Nell'output cercare **WopiZone: *zona***. Se i risultati di Get-SPWopiZone non corrispondono alla zona restituita da Get-SPWOPIBinding, è necessario eseguire il cmdlet **Set-SPWOPIZone -Zone** in SharePoint Server per modificare la zona WOPI in modo che corrisponda al risultato di Get-SPWOPIBinding. Per informazioni sull'uso di questi cmdlet, vedere [Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps), [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps) e [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Problema: quando si tenta di modificare un documento di Office in Office Web Apps, viene visualizzato l'errore "Non è possibile aprire il documento per la modifica".

In alcune situazioni, gli utenti che sono membri di gruppi di sicurezza di Active Directory non sono in grado di modificare documenti nel browser. La soluzione consiste nel verificare che l'applicazione del servizio profili utente sia configurata correttamente e perfettamente sincronizzata con le appartenenze di utenti e gruppi. Per ulteriori informazioni, vedere l'articolo della Knowledge Base relativo al [problema di SharePoint 2013 che impedisce di modificare file di Office Web Apps 2013 per utenti che sono membri di gruppi di sicurezza](http://support.microsoft.com/kb/2908321?ln=it-it).

## Problema: quando si cerca di visualizzare un documento di Office in Office Web Apps, viene visualizzato un messaggio di errore generico.

Assicurarsi di non avere effettuato l'accesso con l'account di sistema, altrimenti non è possibile modificare o visualizzare i documenti con. Usare un account utente diverso e provare di nuovo ad accedere a Office Web Apps.

## Problema: quando si cerca di visualizzare un documento di Office in Office Web Apps, viene visualizzato un messaggio di errore che indica che non è possibile aprirlo.

Se è stato installato Office Web Apps in un ambiente di testing che usa il protocollo HTTP, assicurarsi di avere impostato AllowOAuthOverHttp su **True**, come illustrato nel Passaggio 5: modificare l'impostazione AllowOAuthOverHttp in SharePoint 2013 su True.

Se sono stati aggiunti domini all'elenco Consenti mediante il cmdlet [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps), verificare di avere eseguito l'accesso a Office Web Apps da un dominio host incluso nell'elenco Consenti. Per visualizzare i domini host nell'elenco Consenti, nel server Office Web Apps aprire il prompt di Windows PowerShell come amministratore ed eseguire il cmdlet [Get-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappshost?view=officewebapps-ps). Per aggiungere un dominio all'elenco Consenti, usare il cmdlet [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps).

## Problema: quando si cerca di visualizzare un documento di Office in Office Web Apps, viene visualizzato un messaggio di errore che indica che Word Web App non riesce ad aprire il documento perché il servizio è occupato.

  - Verificare che il server Office Web Apps non sia stato installato in un controller di dominio. Il server Office Web Apps non può infatti essere eseguito in un controller di dominio. Il server Office Web Apps deve essere installato in un server separato appartenente a un dominio. Per altre informazioni, vedere [Software, hardware, and configuration requirements for Office Web Apps Server](plan-office-web-apps-server.md).

  - Verificare che sia in esecuzione SharePoint 2013 build 15.0.4420.1017 o versione successiva. Nel server di SharePoint 2013 attenersi alla procedura seguente per verificare il numero di buid:
    
    1.  Fare clic su **Start** \> **Tutti i programmi** \> **Prodotti Microsoft SharePoint 2013** \> **Amministrazione centrale SharePoint 2013**.
    
    2.  Scegliere **Impostazioni di sistema** \> **Gestisci server della farm**.
    
    Verificare che l'opzione **Versione database di configurazione** sia impostata su **15.0.4420.1017** o una versione successiva. In caso contrario, visitare la pagina [Centro aggiornamenti per Office, Office Server e prodotti correlati](http://go.microsoft.com/fwlink/p/?linkid=160585) per ulteriori informazioni.

## Problema: quando si cerca di visualizzare un documento di Office in Office Web Apps usando un URL generato dall'utente, viene visualizzato il messaggio di errore "File non trovato. L'URL del file originale non è valido o il documento non è accessibile pubblicamente. Verificare che l'URL sia corretto, quindi contattare il proprietario del documento".

Se si sta cercando di aprire un documento con dimensioni superiori a 10 MB da un URL generato dall'utente, verificare che il documento non superi i 10 MB.

## Problema: in SharePoint 2013 non vengono visualizzate le anteprime di Office e al loro posto viene visualizzato l'errore "Impossibile visualizzare questi contenuti in un frame".

Condizioni di scarsa memoria possono creare problemi di visualizzazione delle anteprime dei documenti di Office. Vedere [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/it-it/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) per visualizzare i requisiti di memoria di SharePoint 2013. Sono gli stessi requisiti usati dal server Office Web Apps.

## Problema: viene visualizzato il messaggio di errore "Una connessione dati è impostata per usare sempre il file di connessione e {0:ExcelWebApp} non supporta file di connessione esterni. Non è possibile aggiornare le seguenti connessioni: Connessioni dati."

Questo si verifica perché il server Office Web Apps non supporta il file di connessione dati (ODC) di Office in cui sono archiviate le informazioni della connessione dati. Per risolvere il problema, attenersi alla procedura seguente:

1.  Aprire la cartella di lavoro nell'applicazione client Excel.

2.  Fare clic su **Dati** \> **Connessioni**.

3.  Selezionare le connessioni dati elencate nel messaggio e quindi fare clic su **Proprietà**.

4.  Fare clic sulla scheda **Definizione**.

5.  Deselezionare la casella di controllo **Usa sempre file di connessione**.

6.  Ricaricare la cartella di lavoro nella raccolta documenti di SharePoint.

Per consentire alle persone di interagire con cartelle di lavoro che contengono un modello di dati o visualizzazioni di Power View in una finestra del browser, configurare Excel Services in SharePoint Server per visualizzare le cartelle di lavoro. Questa operazione richiede che un amministratore di SharePoint esegua il cmdlet New-SPWOPISupressionSetting nel server in cui è installato SharePoint Server. Per ulteriori informazioni, vedere [New-SPWOPISuppressionSetting](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPISuppressionSetting?view=sharepoint-ps) e [Amministrare Excel Services in SharePoint Server 2013](https://technet.microsoft.com/it-it/library/ee681487\(v=office.15\)).

## Disconnettere SharePoint 2013 da Office Web Apps Server

Se, per qualunque motivo, si vuole disconnettere SharePoint 2013 dal server Office Web Apps, usare il comando di esempio seguente:

```PowerShell
    Remove-SPWOPIBinding -All:$true
```

Per informazioni, vedere [Remove-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Remove-SPWOPIBinding?view=sharepoint-ps).

## Vedere anche


[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps)  
[Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire il server Office Web Apps](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

