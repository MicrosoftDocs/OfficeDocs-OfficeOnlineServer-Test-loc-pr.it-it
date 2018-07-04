---
title: Pianificare il server Office Web Apps
TOCTitle: Pianificare il server Office Web Apps
ms:assetid: 2e147f11-6f47-46bc-90bf-b2f179958d11
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219435(v=office.15)
ms:contentKeyID: 49652259
ms.date: 02/08/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Pianificare il server Office Web Apps

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2017-10-10_

**Riepilogo:** vengono descritti i requisiti e i prerequisiti del server Office Web Apps, tra cui protocollo HTTPS, certificati, virtualizzazione, bilanciamento del carico, topologie e sicurezza.

**Destinatari:** professionisti IT

Il server Office Web Apps fornisce versioni basate sul browser delle app di Office in un ambiente locale, offrendo agli utenti maggiori opportunità di collaborazione e flessibilità. In questo articolo vengono descritti i requisiti da soddisfare e i passaggi da eseguire per installare il server Office Web Apps nell'organizzazione.

È importante pianificare con attenzione in modo che tutti gli host, ad esempio SharePoint 2013 e Lync Server 2013, è possono comunicare con server Office Web Apps. Per ulteriori informazioni su come configurare gli host, vedere le risorse seguenti:

  - [Pianificare Office Web Apps (utilizzato con SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)

  - [Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)


> [!NOTE]
> Prodotti SharePoint 2010 non può essere un host per server Office Web Apps. server Office Web Apps non è supportata dal SharePoint Foundation 2010 o SharePoint Server 2010. server Office Web Apps non è supportato anche da Exchange Server 2013.



Contenuto dell'articolo:

  - Requisiti software, hardware e di configurazione per il server Office Web Apps

  - Supporto per la virtualizzazione del server Office Web Apps

  - Requisiti del firewall per il server Office Web Apps

  - Requisiti del servizio di bilanciamento del carico per il server Office Web Apps

  - Requisiti di DNS per il server Office Web Apps

  - Pianificazione dei Language Pack per il server Office Web Apps

  - Pianificazione della topologia per il server Office Web Apps

  - Pianificazione della sicurezza per il server Office Web Apps

  - Pianificazione di Visualizzatori online con il server Office Web Apps

  - Pianificazione degli aggiornamenti per il server Office Web Apps

## Requisiti software, hardware e di configurazione per il server Office Web Apps

È possibile installare il server Office Web Apps come farm di server Office Web Apps con un singolo server oppure come farm di server Office Web Apps con più server e carico bilanciato. È possibile utilizzare server fisici o istanze di macchina virtuale, ma non installare altre applicazioni server (ad esempio SharePoint 2013 o SQL Server) nello stesso server del server Office Web Apps.

Negli ambienti che contengono dati utente effettivi è sempre consigliabile utilizzare il protocollo HTTPS, per il quale sarà necessario ottenere un certificato. Se nella farm si utilizzano più server, sarà necessario configurare una soluzione di bilanciamento del carico hardware o software. Ulteriori informazioni su questi scenari sono disponibili nelle sezioni successive.

## Requisiti hardware per il server Office Web Apps

Il server Office Web Apps prevede gli stessi requisiti hardware minimi di SharePoint Server 2013. I requisiti completi di SharePoint 2013 sono illustrati in [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/it-it/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver).

## Sistemi operativi supportati per il server Office Web Apps

È possibile eseguire il server Office Web Apps nei sistemi operativi seguenti:

  - L'edizione a 64 bit di Windows Server 2008 R2 Service Pack 1 (SP1) Standard, Enterprise o Datacenter con l' [aggiornamento per Windows Server 2008 R2 x64 Edition](https://go.microsoft.com/fwlink/p/?linkid=236954) installato

  - Edizione a 64 bit di Windows Server 2012 Standard o Datacenter

  - Edizione a 64 bit di Windows Server 2012 R2. Per usare questo sistema operativo, è necessario disporre di Office Web Apps Server Service Pack 1 (SP1).

## Requisiti di dominio per il server Office Web Apps

Tutti i server della farm di server Office Web Apps devono far parte di un dominio. Possono trovarsi nello stesso dominio (configurazione consigliata) o in domini appartenenti alla stessa foresta. Se tuttavia si tenta di installare il server server Office Web Appsin un controller di dominio, si verificano problemi di funzionamento.

## Ruoli del server, servizi e altri programmi software necessari per il server Office Web Apps

Di seguito sono innanzitutto elencate alcune operazioni da NON eseguire durante la distribuzione del server Office Web Apps.

  - **Non installare altre applicazioni server nel server che esegue il server Office Web Apps**, inclusi Exchange Server, SharePoint Server, Lync Server e SQL Server. Se i server non sono sufficienti, valutare se eseguire il server Office Web Apps in un'istanza di macchina virtuale in uno dei server disponibili.

  - **Non installare servizi o ruoli dipendenti dal ruolo Server Web (IIS) sulla porta 80, 443 o 809** poiché il server Office Web Apps rimuove periodicamente le applicazioni Web su queste porte.

  - **Non installare alcuna versione di Office**. Se è già installata una versione, è necessario disinstallarla prima di installare il server Office Web Apps.

  - **Non installare il server Office Web Apps in un controller di dominio**, poiché non viene eseguito in un server con Servizi di dominio Active Directory.

Per informazioni dettagliate sugli elementi che è invece necessario installare, vedere la tabella che segue.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /> <strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>server Office Web Apps è disponibile solo per il download da <a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Volume Licensing Service Center (VLSC)</a>. Per scaricare server Office Web Apps è necessario disporre di una licenza in un contratto multilicenza Office Professional Plus 2013, Office Standard 2013 o Office per Mac 2011. Il download si trova in tali prodotti Office sul portale VLSC.</td>
</tr>
</tbody>
</table>


### Download, ruoli del server e caratteristiche necessari per il server Office Web Apps

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Download, ruolo del server o caratteristica</th>
<th>Installazione in Windows Server 2008 R2</th>
<th>Installazione in Windows Server 2012</th>
<th>Se si esegue l'installazione in Windows Server 2012 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Download:</strong> server Office Web Apps</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Server Office Web Apps</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Server Office Web Apps</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Server Office Web Apps</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Download:</strong> Office Web Apps Server SP1</p></td>
<td><p>Consigliato</p></td>
<td><p>Consigliato</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510097">Office Web Apps Server SP1</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Download:</strong> versione corretta di .NET Framework</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256560">.NET Framework 4.5</a></p></td>
<td><p>.NET framework 4.5 è già installato</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510096">.NET Framework 4.5.2</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Download:</strong> aggiornamento per Windows Server 2008 R2 x64 Edition</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=236954">Aggiornamento per Windows Server 2008 R2 x64 Edition</a></p></td>
<td><p>Non applicabile</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p><strong>Download:</strong> Windows PowerShell 3.0</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=244693">Windows PowerShell 3.0</a></p></td>
<td><p>Già installato</p></td>
<td><p>Già installato</p></td>
</tr>
<tr class="even">
<td><p><strong>Ruolo del server:</strong> Server Web (IIS)</p></td>
<td><p>Di seguito sono elencati i servizi ruolo minimi per il ruolo <strong>Server Web (IIS)</strong>.</p>
<p><strong>Caratteristiche HTTP comuni</strong></p>
<ul>
<li><p>Contenuto statico</p></li>
<li><p>Documento predefinito</p></li>
</ul>
<p><strong>Sviluppo di applicazioni</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>Estendibilità .NET</p></li>
<li><p>Estensioni ISAPI</p></li>
<li><p>Filtri ISAPI</p></li>
<li><p>Inclusioni sul lato server</p></li>
</ul>
<p><strong>Sicurezza</strong></p>
<ul>
<li><p>Autenticazione di Windows</p></li>
<li><p>Filtro richieste</p></li>
</ul>
<p><strong>Strumenti di gestione</strong></p>
<ul>
<li><p>Console di gestione IIS</p></li>
</ul>
<p>Le seguenti opzioni sono consigliate ma non obbligatorie:</p>
<p><strong>Prestazioni</strong></p>
<ul>
<li><p>Compressione del contenuto statico</p></li>
<li><p>Compressione del contenuto dinamico</p></li>
</ul></td>
<td><p>Di seguito sono elencati i servizi ruolo minimi per il ruolo <strong>Server Web (IIS)</strong>.</p>
<p><strong>Strumenti di gestione</strong></p>
<ul>
<li><p>Console di gestione IIS</p></li>
</ul>
<p><strong>Server Web</strong></p>
<ul>
<li><p>Caratteristiche HTTP comuni</p></li>
<li><p>Documento predefinito</p></li>
<li><p>Contenuto statico</p></li>
</ul>
<p><strong>Sicurezza</strong></p>
<ul>
<li><p>Filtro richieste</p></li>
<li><p>Autenticazione di Windows</p></li>
</ul>
<p><strong>Sviluppo di applicazioni</strong></p>
<ul>
<li><p>Estendibilità .NET 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>Estensioni ISAPI</p></li>
<li><p>Filtri ISAPI</p></li>
<li><p>Inclusioni sul lato server</p></li>
</ul>
<p>I seguenti servizi sono consigliati ma non obbligatori:</p>
<p><strong>Prestazioni</strong></p>
<ul>
<li><p>Compressione del contenuto statico</p></li>
<li><p>Compressione del contenuto dinamico</p></li>
</ul></td>
<td><p>Di seguito sono elencati i servizi ruolo minimi per il ruolo <strong>Server Web (IIS)</strong>.</p>
<p><strong>Strumenti di gestione</strong></p>
<ul>
<li><p>Console di gestione IIS</p></li>
</ul>
<p><strong>Server Web</strong></p>
<ul>
<li><p>Caratteristiche HTTP comuni</p></li>
<li><p>Documento predefinito</p></li>
<li><p>Contenuto statico</p></li>
</ul>
<p><strong>Sicurezza</strong></p>
<ul>
<li><p>Filtro richieste</p></li>
<li><p>Autenticazione di Windows</p></li>
</ul>
<p><strong>Sviluppo di applicazioni</strong></p>
<ul>
<li><p>Estendibilità .NET 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>Estensioni ISAPI</p></li>
<li><p>Filtri ISAPI</p></li>
<li><p>Inclusioni sul lato server</p></li>
</ul>
<p>I seguenti servizi sono consigliati ma non obbligatori:</p>
<p><strong>Prestazioni</strong></p>
<ul>
<li><p>Compressione del contenuto statico</p></li>
<li><p>Compressione del contenuto dinamico</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Caratteristica:</strong> Servizi di riconoscimento della grafia</p></td>
<td><p><strong>Servizi di riconoscimento della grafia</strong></p>
<ul>
<li><p>Supporto per l'input penna</p></li>
</ul></td>
<td><p><strong>Servizi di riconoscimento della grafia</strong></p>
<ul>
<li><p>Supporto per l'input penna non obbligatorio.</p></li>
</ul></td>
<td><p><strong>Servizi di riconoscimento della grafia</strong></p>
<ul>
<li><p>Supporto per l'input penna non obbligatorio.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Supporto per la virtualizzazione del server Office Web Apps

Il server Office Web Apps è pienamente supportato se distribuito mediante la tecnologia Hyper-V di Windows Server. Se si prevede di virtualizzare il server Office Web Apps, attenersi alle linee guida seguenti:

  - Installare il server Office Web Apps in una propria istanza di macchina virtuale. Non installare altre applicazioni server, ad esempio SharePoint 2013, in questa istanza.

  - Se necessario, è possibile installare il server Office Web Apps in un'istanza di macchina virtuale ospitata da un server che esegue SharePoint 2013.

  - Per le farm di server Office Web Apps con più server, ogni istanza deve trovarsi in un host macchina virtuale separato. In tal modo, la farm di server Office Web Apps continuerà a essere disponibile in caso di errore di uno degli host.

## Requisiti del firewall per il server Office Web Apps

I firewall possono causare problemi bloccando la comunicazione tra il Web browser, i server che eseguono il server Office Web Apps e i server che eseguono SharePoint 2013. Questi problemi possono accentuarsi quando i server si trovano in parti diverse di una rete.

Verificare che le porte indicate di seguito non siano bloccate da firewall sul server che esegue il server Office Web Apps o il servizio di bilanciamento del carico:

  - Porta 443 per il traffico HTTPS

  - Porta 80 per il traffico HTTP

  - Porta 809 per il traffico privato tra i server che eseguono il server Office Web Apps (in caso di impostazione di una farm con più server)

## Requisiti del servizio di bilanciamento del carico per il server Office Web Apps

Quando si esegue il server Office Web Apps in due o più server, è consigliabile adottare una soluzione di bilanciamento del carico. È possibile utilizzare qualsiasi soluzione di bilanciamento del carico, incluso un server con il ruolo Server Web (IIS) che esegue Application Request Routing (ARR). È infatti possibile eseguire ARR in uno dei server che eseguono il server Office Web Apps. Se non si dispone di una soluzione di bilanciamento del carico, di seguito sono elencate alcune risorse per l'utilizzo di IIS con ARR:

  - [Installazione di Application Request Routing](https://go.microsoft.com/fwlink/?linkid=236955)

  - [Application Request Routing della Guida in linea](https://go.microsoft.com/fwlink/?linkid=236956)

Se possibile, scegliere una soluzione di bilanciamento del carico che supporti le caratteristiche seguenti:

  - Routing del livello 7

  - Abilitazione dell'affinità client o dell'affinità front-end

  - Abilitazione dell'offload di SSL

Se si utilizza un servizio di bilanciamento del carico, è necessario installare il relativo certificato, come descritto nella sezione Protezione delle comunicazioni del server Office Web Apps mediante il protocollo HTTPS di questo articolo.

## Requisiti di DNS per il server Office Web Apps

Negli ambienti che utilizzano il protocollo HTTPS e il bilanciamento del carico, è necessario aggiornare il sistema DNS affinché il nome di dominio completo (FQDN) del certificato venga risolto nell'indirizzo IP del server che esegue il server Office Web Apps o nell'indirizzo IP assegnato al servizio di bilanciamento del carico per la farm di server Office Web Apps.

## Pianificazione dei Language Pack per il server Office Web Apps

I Language Pack per il server Office Web Apps 2013 consentono agli utenti di visualizzare i file di Office basati sul Web in più lingue da raccolte documenti di SharePoint 2013, Outlook Web App (come anteprime di allegati) e Lync 2013 (come trasmissioni di PowerPoint). Questa caratteristica dipende tuttavia dalle lingue configurate nell'host. Per visualizzare i file di Office basati sul Web da host in più lingue, è necessario che siano soddisfatte le condizioni seguenti:

  - L'host (ad esempio SharePoint Server 2013 o Lync Server 2013 ) è configurato per eseguire le applicazioni in altre lingue. Il processo di installazione e configurazione di language pack nell'host è indipendentemente dal programma di installazione del language pack nella farm di server Office Web Apps.

  - Le lingue devono essere installate e disponibili in tutti i server della farm di server Office Web Apps.

Ecco dove per [scaricare i language pack per Office Web Apps Server](https://go.microsoft.com/fwlink/p/?linkid=263945).

## Pianificazione della topologia per il server Office Web Apps

Almeno una topologia server Office Web Apps includerà una macchina virtuale che esegue server Office Web Apps e almeno un host (ad esempio, un server che esegue Lync Server 2013 o SharePoint 2013 ) o computer fisici. E, naturalmente, è necessario un client PC o un dispositivo per la connessione a uno degli host e utilizzare la funzionalità Office Web Apps. Da tale topologia minima, è possibile aggiungere ulteriori server alla farm server Office Web Apps come richiesto per soddisfare le esigenze dell'organizzazione e altri host.

Di seguito è riportato un elenco di indicazioni da tenere presenti man mano che la topologia del server Office Web Apps diventa più complessa.

  - **Garantire la ridondanza.** Se si utilizzano istanze di macchina virtuale, collocarle su host macchina virtuale separati per garantire la ridondanza. L'esecuzione di applicazioni server da parte di altre istanze nell'host è ammessa, purché le altre applicazioni server non vengano eseguite nella stessa istanza del server Office Web Apps.

  - **Utilizzare un solo data center.** I server di una farm di server Office Web Apps devono trovarsi nello stesso data center e non essere distribuiti geograficamente. In genere, è sufficiente una sola farm, a meno che non sia necessaria una rete isolata con una propria farm di server Office Web Apps per esigenze di sicurezza.

  - **Collocare la farm il più vicino possibile agli host.** La farm di server Office Web Appsnon deve necessariamente trovarsi nello stesso data center degli host gestiti, ma in caso di modifiche frequenti è consigliabile posizionare la farm di server Office Web Apps il più vicino possibile agli host. Questo aspetto è meno importante per organizzazioni che utilizzano Office Web Apps prevalentemente per la visualizzazione di file di Office.

  - **Pianificare le connessioni.** Connettere tutti i server della farm di server Office Web Apps solo tra loro. Per connetterli a una rete più ampia, utilizzare un firewall di bilanciamento del carico di tipo proxy inverso.

  - **Configurare il firewall per richieste HTTP o HTTPS.** Verificare che il firewall consenta ai server che eseguono il server Office Web Apps di inviare richieste HTTP o HTTPS agli host.

  - **Pianificare le comunicazioni in arrivo e in uscita.** In una distribuzione Internet, instradare tutte le comunicazioni in uscita tramite un dispositivo NAT. In una farm con più server, gestire tutte le comunicazioni in arrivo con un servizio di bilanciamento del carico.

  - **Verificare che tutti i server nella farm di server Office Web Apps appartengano a un dominio e facciano parte della stessa unità organizzativa.** Utilizzare il parametro **FarmOU** nel cmdlet [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) per impedire ad altri server non appartenenti all'unità organizzativa di unirsi alla farm.

  - **Utilizzare il protocollo HTTPS (Hypertext Transfer Protocol Secure) per tutte le richieste in arrivo.**

  - **Se nella rete è distribuito IPsec, utilizzarlo per crittografare il traffico tra i server.**

  - **Pianificare le caratteristiche di Office che utilizzano Internet.** Se sono necessarie caratteristiche quali ClipArt e servizi di traduzione e i server della farm non sono in grado di inviare richieste su Internet, è necessario configurare un server proxy per la farm di server Office Web Apps. In questo modo, le richieste HTTP verso siti esterni saranno consentite.

## Pianificazione della sicurezza per il server Office Web Apps

Di seguito sono riportate alcune indicazioni sulla sicurezza per il server Office Web Apps.

## Protezione delle comunicazioni del server Office Web Apps mediante il protocollo HTTPS

server Office Web Apps possono comunicare con SharePoint 2013 e Lync Server 2013 utilizzando il protocollo HTTPS. Negli ambienti di produzione, è consigliabile utilizzare HTTPS. È necessario installare un certificato del Server Internet che può essere assegnato al server che esegue server Office Web Apps (se si utilizza un server singolo) o per il bilanciamento del carico (se si utilizza più server che eseguono server Office Web Apps ).

In ambienti di testing che non contengono dati utente, è possibile utilizzare HTTP per SharePoint 2013 e ignorare la richiesta del certificato. Lync Server 2013 supporta solo HTTPS.

I certificati utilizzati dal server Office Web Apps devono soddisfare i requisiti seguenti:

  - Il certificato deve provenire da un'autorità di certificazione attendibile e includere il nome di dominio completo (FQDN) della farm di server Office Web Apps nel campo SAN (nome alternativo del soggetto). Se quando si tenta di utilizzare il certificato il nome FQDN non è indicato nel campo SAN, nel browser saranno visualizzati avvisi di sicurezza o non verrà elaborata la risposta.

  - Il certificato deve disporre di una chiave privata esportabile. Nelle farm a server singolo questa opzione è selezionata per impostazione predefinita quando si utilizza lo snap-in Gestione Internet Information Services (IIS) per importare il certificato.

  - Il campo Nome descrittivo deve essere univoco nell'archivio delle autorità di certificazione radice attendibili. Se più certificati condividono un campo Nome descrittivo, la creazione della farm non verrà eseguita poiché il cmdlet New-OfficeWebAppsFarm non sarà in grado di stabilire quale certificato utilizzare.

  - Il server Office Web Apps non richiede proprietà o estensioni del certificato specifiche. Non sono ad esempio necessarie estensioni per utilizzo chiavi avanzato (EKU) nel client o nel server.

  - In Windows Server 2012 o Windows Server 2012 R2 è necessario installare la funzionalità di Windows Communication Foundation (WCF) che consente l'attivazione HTTP.

Il certificato deve essere importato come indicato di seguito:

  - **Per farm a server singolo**   È necessario importare il certificato direttamente nel server che esegue il server Office Web Apps. Non associare manualmente il certificato. Tale operazione verrà effettuata dal cmdlet New-OfficeWebAppsFarm eseguito successivamente. Se il certificato viene associato manualmente, verrà eliminato a ogni riavvio del server.

  - **Per farm con carico bilanciato**   In caso di offload di SSL, il certificato deve essere importato nel dispositivo di bilanciamento del carico hardware. In caso contrario, è necessario installare il certificato in ogni server della farm di server Office Web Apps.


> [!NOTE]
> Non utilizzare certificati autofirmati, fatta eccezione per gli ambienti di test non critici.



Per ulteriori informazioni sui certificati, vedere [come ottenere un certificato SSL](https://go.microsoft.com/fwlink/p/?linkid=269700).

## Utilizzo dell'offload di SSL per i dispositivi di bilanciamento del carico hardware

Quando si configura una nuova farm di server Office Web Apps, l'offload di SSL è disattivato per impostazione predefinita. Se si utilizza un dispositivo di bilanciamento del carico hardware, è consigliabile attivare l'offload di SSL affinché ogni server Office Web Apps nella farm sia in grado di comunicare con il dispositivo di bilanciamento del carico mediante il protocollo HTTP. L'attivazione dell'offload di SSL offre inoltre i vantaggi seguenti:

  - Gestione semplificata dei certificati

  - Affinità debole migliorata

  - Prestazioni migliorate

Quando si utilizza il protocollo HTTP, il traffico dal dispositivo di bilanciamento del carico ai server che eseguono il server Office Web Apps non viene crittografato ed è pertanto necessario accertarsi che la rete sia protetta. L'utilizzo di una subnet privata può contribuire a proteggere il traffico.

## Limitare i server che possono entrare a far parte della farm di server Office Web Apps in base all'appartenenza all'unità organizzativa

È possibile impedire ai server non autorizzati di entrare a far parte di una farm di server Office Web Apps creando un'unità organizzativa per tali server e specificando il parametro FarmOU durante la creazione della farm. Per ulteriori informazioni sul parametro FarmOU, vedere [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Limitare l'accesso host per il server Office Web Apps mediante l'elenco Consenti

L'elenco Consenti è una caratteristica di sicurezza che impedisce a host indesiderati di connettersi a una farm di server Office Web Apps e di utilizzarla per operazioni su file senza il consenso dell'utente. Aggiungendo i domini che contengono host approvati all'elenco Consenti, è possibile limitare gli host da cui il server Office Web Apps accetta richieste di operazioni su file, ad esempio il recupero di file o metadati e le modifiche di file.

È possibile aggiungere domini all'elenco Consenti dopo la creazione della farm di server Office Web Apps. Per informazioni sull'aggiunta di domini all'elenco Consenti, vedere [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps).

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /> <strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se non si aggiungono domini all'elenco Consenti, il server Office Web Apps consentirà agli host di qualsiasi dominio di inviare richieste di file. Non lasciare vuoto questo elenco se la farm di server Office Web Apps è accessibile da Internet. In caso contrario, chiunque potrà utilizzare la farm di server Office Web Apps per visualizzare e modificare contenuto.</td>
</tr>
</tbody>
</table>


## Pianificazione di Visualizzatori online con il server Office Web Apps

Per impostazione predefinita, la caratteristica Visualizzatori online viene abilitata dopo l'installazione del server Office Web Apps. Consultare le linee guida riportate di seguito se si prevede di utilizzare Visualizzatori online nell'organizzazione. In alcuni casi è consigliabile disabilitare determinate caratteristiche di Visualizzatori online. In queste linee guida si fa riferimento a parametri impostati mediante i cmdlet Windows PowerShell[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) e [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps).

## Considerazioni sulla sicurezza per Visualizzatori online

I file da visualizzare in un Web browser mediante Visualizzatori online non devono richiedere l'autenticazione. In altri termini, i file devono essere disponibili pubblicamente poiché la caratteristica Visualizzatori online non è in grado di eseguire l'autenticazione durante il recupero di file. È consigliabile impostare la farm di server Office Web Apps utilizzata per Visualizzatori online in modo che sia in grado di accedere alla rete Intranet o a Internet, ma non a entrambe. Il server Office Web Apps non è infatti in grado di distinguere le richieste di URL Intranet e Internet. Un utente su Internet potrebbe ad esempio richiedere un URL della rete Intranet, causando un rischio per la sicurezza se viene visualizzato un documento interno.

Per lo stesso motivo, se il server Office Web Apps è stato impostato per la sola connessione a Internet, è consigliabile disabilitare il supporto UNC in Visualizzatori online. Per disabilitare il supporto UNC, impostare il parametro OpenFromUncEnabled su False mediante il cmdlet Windows PowerShell[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) (per nuove farm) o [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps) (per farm esistenti).

Come misura di sicurezza aggiuntiva, la caratteristica Visualizzatori online consente di visualizzare solo file di Office con dimensioni massime di 10 MB.

## Opzioni di configurazione per Visualizzatori online

È possibile configurare Visualizzatori online utilizzando i parametri Windows PowerShell seguenti nel cmdlet [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) (per nuove farm) o [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps) (per farm esistenti).

  - **OpenFromUrlEnabled**   Attiva o disattiva Visualizzatori online. Questo parametro controlla Visualizzatori online per i file con percorsi URL e UNC. Per impostazione predefinita, questo parametro è impostato su False (disabilitato) quando si crea una nuova farm di server Office Web Apps.

  - **OpenFromUncEnabled**   Quando la caratteristica Visualizzatori online è attivata (impostata su True mediante OpenFromUrlEnabled), questo parametro attiva o disattiva la visualizzazione all'interno di Visualizzatori online di file presenti in percorsi UNC. Per impostazione predefinita, questo parametro è impostato su True, ma prima di abilitare l'apertura di file da percorsi UNC è necessario verificare che anche OpenFromUrlEnabled sia impostato su True. Come descritto in precedenza, è consigliabile impostare questo parametro su False se il server Office Web Apps è configurato in modo da connettersi a Internet.

  - **OpenFromUrlThrottlingEnabled**   Limita il numero di richieste di apertura da URL di un server specifico in un determinato intervallo di tempo. I valori di limitazione predefiniti, non configurabili, evitano che una farm di server Office Web Apps possa sovraccaricare un singolo server inviando richieste di contenuto da visualizzare in Visualizzatori online.

## Pianificazione degli aggiornamenti per il server Office Web Apps

Prima della distribuzione del server Office Web Apps, è necessario stabilire come verranno gestiti gli aggiornamenti software della farm di server Office Web Apps nell'organizzazione. Anche se gli aggiornamenti software contribuiscono a migliorare la sicurezza, le prestazioni e l'affidabilità del server, l'installazione non corretta degli aggiornamenti può essere causa di problemi del server Office Web Apps.

L'applicazione degli aggiornamenti del server Office Web Apps mediante il processo di aggiornamento automatico Microsoft non è supportata per il server Office Web Apps. Gli aggiornamenti di un server Office Web Apps devono infatti essere applicati in modo specifico, come descritto in [Applicare aggiornamenti software al server Office Web Apps](apply-software-updates-to-office-web-apps-server.md). Se invece gli aggiornamenti del server Office Web Apps vengono applicati automaticamente, gli utenti potrebbero non essere in grado di visualizzare o modificare documenti in Office Web Apps. In tal caso, sarà necessario creare di nuovo la farm di server Office Web Apps.

È consigliabile gestire gli aggiornamenti tramite Windows Server Update Services (WSUS) o System Center Configuration Manager che utilizza WSUS. Con WSUS è possibile gestire completamente la distribuzione degli aggiornamenti rilasciati tramite Microsoft Update per ogni server della farm di server Office Web Apps e decidere quali aggiornamenti possono essere applicati automaticamente alla server farm e quali, come gli aggiornamenti del server Office Web Apps, devono essere applicati manualmente. Per ulteriori informazioni su WSUS, vedere [Windows Server Update Services](https://go.microsoft.com/fwlink/p/?linkid=294822).

Se non si utilizza WSUS o System Center Configuration Manager, impostare gli aggiornamenti automatici Microsoft in ogni server della farm di server Office Web Apps sull'opzione che consente di scaricare gli aggiornamenti automaticamente avvisando però l'utente prima dell'installazione. Quando si riceve una notifica relativa a un aggiornamento del server Office Web Apps, attenersi alla procedura indicata in [Applicare aggiornamenti software al server Office Web Apps](apply-software-updates-to-office-web-apps-server.md). Per applicare gli aggiornamenti di Windows e mantenere protetti i server, accettare gli aggiornamenti di Windows quando viene segnalata la relativa disponibilità.

## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Panoramica sul server Office Web Apps](office-web-apps-server-overview.md)  
[Distribuire il server Office Web Apps](deploy-office-web-apps-server.md)  
[Applicare aggiornamenti software al server Office Web Apps](apply-software-updates-to-office-web-apps-server.md)  


[Office.com (per la Guida di Office Web Apps su dispositivi desktop o portatili)](https://go.microsoft.com/fwlink/p/?linkid=266657)  
  

[apply-software-updates-to-office-web-apps-server.md](apply-software-updates-to-office-web-apps-server.md)

