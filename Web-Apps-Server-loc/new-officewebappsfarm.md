---
title: New-OfficeWebAppsFarm
TOCTitle: New-OfficeWebAppsFarm
ms:assetid: 3616a668-f76f-45c6-914c-3103cbded5d2
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219436(v=office.15)
ms:contentKeyID: 49652262
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsFarm

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-26_

Crea una nuova farm di server Office Web Apps nel computer locale.

## Sintassi

    New-OfficeWebAppsFarm [-AllowCEIP <SwitchParameter>] [-AllowHttp <SwitchParameter>] [-AllowHttpSecureStoreConnections <SwitchParameter>] [-CacheLocation <String>] [-CacheSizeInGB <Nullable>] [-CertificateName <String>] [-ClipartEnabled <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DocumentInfoCacheSize <Nullable>] [-EditingEnabled <SwitchParameter>] [-ExcelAllowExternalData <SwitchParameter>] [-ExcelConnectionLifetime <Nullable>] [-ExcelExternalDataCacheLifetime <Nullable>] [-ExcelPrivateBytesMax <Nullable>] [-ExcelRequestDurationMax <Nullable>] [-ExcelSessionTimeout <Nullable>] [-ExcelWarnOnDataRefresh <SwitchParameter>] [-ExcelWorkbookSizeMax <Nullable>] [-ExternalURL <String>] [-FarmOU <String>] [-Force <SwitchParameter>] [-InternalURL <String>] [-LogLocation <String>] [-LogRetentionInDays <Nullable>] [-LogVerbosity <String>] [-MaxMemoryCacheSizeInMB <Nullable>] [-MaxTranslationCharacterCount <Nullable>] [-OpenFromUncEnabled <SwitchParameter>] [-OpenFromUrlEnabled <SwitchParameter>] [-OpenFromUrlThrottlingEnabled <SwitchParameter>] [-PicturePasteDisabled <SwitchParameter>] [-Proxy <String>] [-RecycleActiveProcessCount <Nullable>] [-RemovePersonalInformationFromLogs <SwitchParameter>] [-RenderingLocalCacheLocation <String>] [-SSLOffloaded <SwitchParameter>] [-TranslationEnabled <SwitchParameter>] [-TranslationServiceAddress <String>] [-TranslationServiceAppId <String>] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **New-OfficeWebAppsFarm** crea una nuova farm di server Office Web Apps nel computer locale. Eseguire questo cmdlet nel primo server della farm di server Office Web Apps e quindi aggiungere altri server alla farm utilizzando il cmdlet **New-OfficeWebAppsMachine**.

## Parametri


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Parametro</strong></th>
<th>Obbligatorio</th>
<th>Tipo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AllowCEIP</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Abilita la creazione di report di Analisi utilizzo software in tutti i server della farm di server Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>AllowHttp</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indica che il provisioning dei siti IIS deve essere eseguito sulla porta 80 per l'accesso HTTP. Utilizzare <strong>AllowHTTP</strong> solo in ambienti in cui tutti i computer richiedono IPSEC (crittografia completa) o in ambienti di testing in cui non sono contenuti file riservati.</p>
<p>Abilitato automaticamente quando si abilita <strong>SSLOffloaded</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHttpSecureStoreConnections</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indica che è possibile creare connessioni di archiviazione sicura utilizzando connessioni non SSL, ad esempio HTTP. Il valore predefinito è <strong>False</strong>.</p>
<p>Utilizzare <strong>AllowHTTPSecureStoreConnections</strong> solo in ambienti in cui tutti i computer richiedono IPSEC (crittografia completa) o in ambienti di testing in cui non sono contenuti file riservati.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheLocation</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il percorso della cache del disco globale utilizzata per archiviare file di immagine sottoposti a rendering. Il percorso predefinito è <strong>%programdata%\Microsoft\OfficeWebApps\Working\d\</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheSizeInGB</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica la dimensione massima della cache del disco globale in gigabyte.</p>
<p>Il tipo deve essere un valore intero compreso tra <strong>0</strong> e un numero intero positivo. La dimensione predefinita è <strong>15</strong> GB.</p></td>
</tr>
<tr class="even">
<td><p><strong>CertificateName</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il nome descrittivo del certificato utilizzato da server Office Web Apps per creare binding HTTPS.</p>
<p>Se il certificato specificato non viene trovato o è scaduto oppure il valore specificato è associato a più certificati, verrà registrato un errore e la farm non verrà creata.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Questo valore viene utilizzato in ogni server che viene aggiunto alla farm di server Office Web Apps. Ogni server della farm pertanto deve disporre di un certificato con questo nome descrittivo.</td>
</tr>
</tbody>
</table>

</div>
<p>Non è necessario specificare il parametro <strong>CertificateName</strong> se si utilizza il parametro <strong>AllowHttp</strong> o <strong>SSLOffloaded</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClipartEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Abilita il supporto per l'inserimento di immagini Bing in documenti di Office. Per utilizzare questa funzionalità è necessaria la comunicazione da server a Web, configurata direttamente oppure usando un proxy specificato mediante il parametro <strong>Proxy</strong>.</p>
<p>Per il corretto funzionamento delle immagini Bing, il parametro <strong>OpenFromUrlEnabled</strong> deve essere impostato su <strong>True</strong>. Il valore predefinito è <strong>False</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>DocumentInfoCacheSize</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica il numero massimo di record di conversione di documenti archiviati in una cache di memoria.</p>
<p>Il valore predefinito è <strong>5000</strong> record.</p></td>
</tr>
<tr class="even">
<td><p><strong>EditingEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Abilita il supporto per la modifica nel browser. Il valore predefinito è <strong>False</strong>. Impostare <strong>True</strong> solo se si dispone della licenza appropriata per l'utilizzo della funzionalità di modifica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelAllowExternalData</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Abilita l'aggiornamento di dati esterni supportati nelle cartelle di lavoro di Excel Web App in cui sono contenute connessioni a dati esterni. Il valore predefinito è <strong>True</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelConnectionLifetime</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica la durata, espressa in secondi, delle connessioni di dati esterni per Excel Web App. Il valore predefinito è<strong>1800</strong> secondi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelExternalDataCacheLifetime</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica la durata, espressa in secondi, della cache dei dati esterni in Excel Web App. Il valore predefinito è<strong>300</strong> secondi.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelPrivateBytesMax</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica il numero massimo di byte privati, espresso in megabyte, utilizzati da Excel Web App. Se è impostato su <strong>-1</strong>, il numero massimo di byte privati utilizza il 50% della memoria fisica del computer.</p>
<p>Il tipo deve essere <strong>-1</strong> o qualsiasi numero intero positivo. Il valore predefinito è <strong>-1</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelRequestDurationMax</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica la durata massima, in secondi, di una singola richiesta in una sessione. Al termine di questo intervallo di tempo, si verifica il timeout della richiesta.</p>
<p>Il tipo deve essere <strong>-1</strong> (nessun limite) o un numero intero compreso tra <strong>1</strong> e <strong>2073600</strong>. Il valore predefinito è <strong>300</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelSessionTimeout</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica per quanto tempo (secondi) una sessione resta attiva in Excel Web App in assenza di attività dell'utente. Tra i valori validi sono inclusi i seguenti:</p>
<p><strong>-1</strong> La sessione non scade mai.</p>
<p><strong>0</strong> La sessione scade al termine di una singola richiesta.</p>
<p><strong>1</strong>-<strong>2073600</strong> La sessione resta attiva per un intervallo di tempo compreso tra 1 secondo e 24 giorni. Il valore predefinito è <strong>450</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelWarnOnDataRefresh</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Disattiva o attiva la finestra di dialogo di avviso visualizzata quando i dati vengono aggiornati in Excel Web App.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelWorkbookSizeMax</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica la dimensione massima, in megabyte, di una cartella di lavoro che è possibile caricare.</p>
<p>Il tipo deve essere un numero intero compreso tra <strong>1</strong> e <strong>2000</strong>. Il valore predefinito è <strong>10</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalURL</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica la radice dell'URL utilizzata dai client per accedere alla farm di server Office Web Apps da Internet. Nel caso di una farm di server Office Web Apps multiserver con carico bilanciato, l'URL esterno è associato all'indirizzo IP del servizio di bilanciamento del carico esposto verso l'esterno.</p>
<p>Una farm di server Office Web Apps richiede almeno un URL, impostato utilizzando <strong>ExternalURL</strong> o <strong>InternalURL</strong>. È inoltre possibile impostare URL interni ed esterni.</p></td>
</tr>
<tr class="even">
<td><p><strong>FarmOU</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il nome dell'unità organizzativa di Active Directory di cui devono essere membri i server per essere aggiunti alla farm di server Office Web Apps. Utilizzare questo parametro per evitare che vengano aggiunti a una farm di server Office Web Apps server non autorizzati, ovvero server che non sono membri dell'unità organizzativa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Elimina le richieste utente fornendo una risposta affermativa.</p></td>
</tr>
<tr class="even">
<td><p><strong>InternalURL</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica la radice dell'URL utilizzata dai client per accedere alla farm di server Office Web Apps dalla rete Intranet.</p>
<p>Una farm di server Office Web Apps richiede almeno un URL, impostato utilizzando <strong>ExternalURL</strong> o <strong>InternalURL</strong>. È inoltre possibile impostare URL interni ed esterni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogLocation</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il percorso del computer locale in cui vengono archiviati i registri attività.</p>
<p>Il percorso si applica a tutti i server della farm e non può essere personalizzato per ogni singolo server. Il percorso predefinito è <strong>%programdata%\Microsoft\OfficeWebApps\Data\Logs\ULS\.</strong></p>
<p>Lasciare spazio su disco sufficiente nell'unità in cui vengono archiviati i registri.</p></td>
</tr>
<tr class="even">
<td><p><strong>LogRetentionInDays</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica per quanti giorni vengono mantenute le voci di log. Le voci di log che risalgono a un periodo precedente alla data configurata vengono rimosse.</p>
<p>Il tipo deve essere un numero intero compreso tra <strong>0</strong> e <strong>365</strong>. Il valore predefinito è <strong>7</strong> giorni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogVerbosity</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il livello di dettagli delle informazioni archiviate nei file di log di traccia. I valori sono i seguenti:</p>
<p><strong>VerboseEX</strong> scrive informazioni con livello di dettagli ridotto nel file di log di traccia. Questa impostazione è utile per tracce di volume elevato.</p>
<p><strong>Verbose</strong> scrive informazioni con livello di dettagli ridotto nel file di log di traccia.</p>
<p><strong>Medium</strong> scrive informazioni con livello di dettagli medio nel file di log di traccia.</p>
<p><strong>High</strong> scrive informazioni con livello di dettagli elevato nel file di log di traccia.</p>
<p><strong>Monitorable</strong> scrive tracce che rappresentano un percorso di codice anomalo e azioni che devono essere monitorate.</p>
<p><strong>Unexpected</strong> scrive tracce che rappresentano un percorso di codice imprevisto e azioni che devono essere monitorate.</p>
<p><strong>None</strong> non scrive alcuna informazione di traccia nel file di log di traccia.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Il parametro <strong>LogVerbosity</strong> impostato su un valore basso per un lungo periodo di tempo produce un effetto negativo sulle prestazioni.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>MaxMemoryCacheSizeInMB</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica, in megabyte, la quantità massima di memoria che può essere utilizzata dalla cache di rendering.</p>
<p>Il tipo deve essere un valore intero compreso tra <strong>0</strong> e un numero intero positivo. La dimensione predefinita è <strong>75</strong> MB.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxTranslationCharacterCount</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica il numero massimo di caratteri che un documento può includere per essere tradotto.</p>
<p>Il tipo deve essere un valore intero. Il valore può essere impostato su <strong>0</strong> per indicare che non è presente alcun limite oppure su un valore compreso tra <strong>2000</strong> e <strong>2.000.000</strong>. Il valore predefinito è <strong>125.000</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUncEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Attiva o disattiva la possibilità di utilizzare Visualizzatori online per visualizzare i file di Office da un percorso UNC.</p>
<div class="alert">

> [!NOTE]
> È innanzitutto necessario impostare <STRONG>OpenFromUrlEnabled</STRONG> su <STRONG>True</STRONG> per consentire a Visualizzatori online di visualizzare i file nei percorsi UNC.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>OpenFromUrlEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Attiva o disattiva la possibilità di usare Visualizzatori online per visualizzare i file di Office da un percorso URL o UNC. Il valore predefinito è <strong>False</strong>.</p>
<p>Quando si usa <strong>ClipartEnabled</strong>, questo parametro deve essere impostato su True.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUrlThrottlingEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Limita il numero di richieste di apertura da URL di un server specifico in un determinato intervallo di tempo. I valori di limitazione predefiniti, non configurabili, evitano che una farm di server Office Web Apps possa sovraccaricare un singolo server con richieste di contenuto da visualizzare in Visualizzatori online.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PicturePasteDisabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Non consente agli utenti di incollare immagini da una pagina Web in Office Web Apps. Il valore predefinito è <strong>False</strong>. Se <strong>OpenFromURLEnabled</strong> è impostato su <strong>True</strong> e <strong>PicturePasteDisabled</strong> non è impostato o è impostato su <strong>False</strong>, gli utenti potranno incollare immagini in Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>Proxy</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'URL del server proxy configurato per consentire le richieste HTTP per siti esterni. Questo parametro in genere è configurato insieme ai parametri <strong>ClipartEnabled</strong> e <strong>TranslationEnabled</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecycleActiveProcessCount</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Nullable</p></td>
<td><p>Specifica il numero di file che possono essere sottoposti a rendering da un singolo processo di Word o PowerPoint prima che il processo venga riciclato.</p>
<p>Il tipo deve essere un numero intero compreso tra <strong>1</strong> e <strong>1000</strong>. Il valore predefinito è <strong>5</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>RemovePersonalInformationFromLogs</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Esegue lo scrubbing massimo possibile delle informazioni personali dai log di server Office Web Apps e sostituisce i valori con un hash SHA256. Le informazioni di cui è possibile eseguire lo scrubbing sono:</p>
<ul>
<li><p>Nomi di documento e URL</p></li>
<li><p>Indirizzi IP</p></li>
<li><p>Indirizzi di posta elettronica</p></li>
<li><p>Nomi utente</p></li>
</ul>
<p>Il valore predefinito è <strong>False</strong>. L'abilitazione di questo parametro non garantisce che le informazioni personali non verranno registrate nei log di server Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RenderingLocalCacheLocation</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il percorso della cache temporanea che deve essere utilizzato dai servizi di visualizzazione di Word e PowerPoint.</p>
<p>Il percorso predefinito è <strong>%programdata%\Microsoft\OfficeWebApps\Working\waccache\</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SSLOffloaded</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indica ai server della farm di server Office Web Apps che il carico di lavoro di SSL è ripartito nel servizio di bilanciamento del carico. Quando <strong>SSLOffloaded</strong> è abilitato, le applicazioni Web sono associate alla porta 80 (HTTP) nel server locale. Per HTML che fa riferimento ad altre risorse, ad esempio fogli di stile CSS o immagini, vengono utilizzati invece gli URL HTTPS per i riferimenti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationEnabled</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Abilita il supporto per la traduzione automatica dei documenti tramite Microsoft Translator, un servizio online per la traduzione di testo da una lingua a un'altra. Il file tradotto viene visualizzato in Word Web App. Poiché Microsoft Translator è un servizio online, è necessario abilitare la comunicazione da server a Web direttamente oppure tramite un proxy specificato utilizzando il parametro <strong>Proxy</strong>.</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>È possibile che Microsoft Translator raccolga dati per migliorare la qualità delle traduzioni.</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>TranslationServiceAddress</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'URL del server di traduzione a cui vengono inviate richieste di traduzione. Il valore predefinito è il servizio online Microsoft Translator. Questo parametro in genere non viene utilizzato, a meno che non sia necessario cambiare servizi di traduzione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationServiceAppId</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'ID applicazione del servizio di traduzione. Il valore predefinito è l'ID dell'applicazione pubblica di Office Web Apps. Questo parametro in genere non viene utilizzato, a meno che non siano stati negoziati servizi aggiuntivi con Microsoft Translator e che tali servizi non siano stati forniti con un ID applicazione privato.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Visualizza un messaggio che illustra gli effetti del comando anziché eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    New-OfficeWebAppsFarm -InternalUrl "https://server.corp.contoso.com" -ExternalUrl "https://server.external.contoso.com" -EditingEnabled:$true -SSLOffloaded

In questo esempio viene creata una farm di server Office Web Apps nel server locale in cui è abilitata la modifica per Office Web Apps. La farm è configurata per il bilanciamento del carico abilitando **SSLOffloaded**, che abilita automaticamente **AllowHttp**. Se non si utilizza un servizio di bilanciamento del carico, impostare **CertificateName**.

## Vedere anche


[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

