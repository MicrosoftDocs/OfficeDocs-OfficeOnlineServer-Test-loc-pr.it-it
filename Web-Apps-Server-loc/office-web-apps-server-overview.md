---
title: Panoramica sul server Office Web Apps
TOCTitle: 'Panoramica: server Office Web Apps'
ms:assetid: 4b199a88-387f-4121-820d-7af580e2a3e8
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219437(v=office.15)
ms:contentKeyID: 49652265
ms.date: 02/08/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Panoramica sul server Office Web Apps

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2017-05-26_

**Riepilogo:** informazioni sul server Office Web Apps e su come utilizzarlo per fornire le funzionalità di Office basate su browser agli host supportati.

**Destinatari:** professionisti IT

server Office Web Apps è un nuovo prodotto Office server che fornisce le versioni basate su browser di Word, PowerPoint, Excel e OneNote. Una singola farm di Office Web Apps Server può supportare gli utenti che accedono ai file Office tramite SharePoint 2013, Lync Server 2013, cartelle condivise e siti Web. Il nuovo modello di distribuzione autonoma significa che è possibile gestire gli aggiornamenti a una farm di Server Office Web Apps indipendentemente dagli altri prodotti Server Office distribuite nell'organizzazione.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /> <strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Questo articolo fa parte della <a href="content-roadmap-for-office-web-apps-server.md">Guida di orientamento al contenuto per il server Office Web Apps</a>. Utilizzare tale guida come punto di partenza per accedere ad articoli, download e video utili per distribuire e gestire server Office Web Apps.<br />
<strong>Per informazioni relative a Office Web Apps su dispositivi desktop o mobili,</strong> cercare &quot;Office Web Apps&quot; su <a href="https://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</a>.</td>
</tr>
</tbody>
</table>


Contenuto dell'articolo:

  - Informazioni sul server Office Web Apps

  - Utilizzo del server Office Web Apps da parte di SharePoint 2013 per la visualizzazione e la modifica dei documenti di Office

  - Utilizzo del server Office Web Apps da parte di Lync Server 2013 per la visualizzazione delle trasmissioni di PowerPoint

  - Utilizzo dell'anteprima del server Office Web Apps per la visualizzazione dei file di Office in cartelle condivise e siti Web tramite i Visualizzatori online

## Informazioni sul server Office Web Apps

server Office Web Apps è un prodotto server Office che fornisce file basato su browser visualizzazione e modifica di servizi per i file Office. server Office Web Apps può essere utilizzato con prodotti e servizi che supportano WOPI, il protocollo Open Platform Interface Web app. Questi prodotti, noti come host, includono SharePoint 2013 e Lync Server 2013. Una farm di Office Web Apps Server può offrire servizi Office agli host locali più e è scalabile fuori della farm da un server in più server e alle nuove esigenze dell'organizzazione. Sebbene server Office Web Apps necessita di un server dedicato che non eseguono altre applicazioni server, è possibile installare server Office Web Apps sulle istanze di macchine virtuali.

È più semplice da distribuire e gestire Office Web Apps nell'organizzazione, ora che si tratta di un prodotto autonomo. Se si distribuisce SharePoint 2013, ad esempio, è non è più necessario ottimizzazione dell'infrastruttura di SharePoint per il supporto di Office Web Apps, che è stato strettamente integrato con SharePoint Server 2010 nelle versioni precedenti. È possibile inoltre applicare gli aggiornamenti per la farm di Server Office Web Apps separatamente e una frequenza diversa che l'aggiornamento di SharePoint o Lync Server. Disporre di una farm autonoma di Office Web Apps Server significa inoltre che gli utenti possono visualizzare o modificare il file Office vengono memorizzati esterno SharePoint Server, ad esempio quelle in cartelle condivise o altri siti Web. Questa funzionalità è fornita da una funzionalità nota come i visualizzatori Online.

Nell'illustrazione seguente vengono mostrate le differenze tra il modello di distribuzione precedente per Office Web Apps e il nuovo modello di distribuzione autonomo per Office Web Apps.

**Differenze tra i modelli di distribuzione di Office Web Apps**

![Differenza tra il modello di distribuzione precedente e il nuovo modello di distribuzione autonoma per il server Office Web Apps.](images/JJ219437.f16dd9d1-c9b7-4c8b-a8de-f1f82c0ee1e2(Office.15).gif "Differenza tra il modello di distribuzione precedente e il nuovo modello di distribuzione autonoma per il server Office Web Apps.")

## Utilizzo del server Office Web Apps da parte di SharePoint 2013 per la visualizzazione e la modifica dei documenti di Office

Quando viene utilizzato con SharePoint Server 2013, il server Office Web Apps fornisce versioni aggiornate di Word Web App, Excel Web App, PowerPoint Web App e OneNote Web App. Gli utenti possono visualizzare e, in alcuni casi, modificare i documenti di Office nelle raccolte di SharePoint mediante un Web browser supportato in computer e numerosi dispositivi mobili, come Windows Phone, iPhone, iPad e tablet Windows 8. Fra le molteplici caratteristiche introdotte in Office Web Apps, i miglioramenti apportati alle funzionalità di modifica e al supporto per il tocco consentono agli utenti di iPad e tablet Windows 8 di modificare e visualizzare i documenti di Office direttamente dai dispositivi.

Nell'illustrazione seguente vengono riepilogate le funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi.

**Funzionalità di modifica e visualizzazione di Office Web Apps**

![Grafico in cui vengono riepilogate le funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi. Sono evidenziate quelle ottimizzate per i dispositivi touchscreen.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Grafico in cui vengono riepilogate le funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi. Sono evidenziate quelle ottimizzate per i dispositivi touchscreen.")


> [!NOTE]
> La trasmissione di PowerPoint è stata rimossa da SharePoint 2013. È disponibile utilizzando OneDrive e Lync Server 2013.



Per ulteriori informazioni sulle novità di Office Web Apps, vedere [Funzionamento di Office Web Apps in locale con SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md).

## Utilizzo del server Office Web Apps da parte di Lync Server 2013 per la visualizzazione delle trasmissioni di PowerPoint

In Lync Server 2010, le presentazioni di PowerPoint vengono visualizzate in una delle seguenti modalità. Per gli utenti che eseguono Lync 2010, le presentazioni di PowerPoint vengono visualizzate nel formato di PowerPoint 97-2003 mediante una copia incorporata del visualizzatore di PowerPoint. Per gli utenti che eseguono Lync Web App, le presentazioni di PowerPoint vengono convertite in file HTML dinamici, che vengono quindi visualizzati mediante una combinazione di file DHTML personalizzati e Silverlight. Nonostante sia generalmente efficace, tale approccio presentava alcune limitazioni:

  - Il visualizzatore di PowerPoint incorporato (che garantiva un'esperienza di visualizzazione ottimale) è disponibile solo nella piattaforma Windows.

  - Molti dispositivi mobili (compresi alcuni dei cellulari più diffusi) non supportano Silverlight.
    
    Né visualizzatore di PowerPoint né l'approccio DHTML/Silverlight supportano tutte le caratteristiche (compresi i video incorporati e le transizioni dispositive) presenti nelle edizioni più recenti di PowerPoint.

Per la risoluzione di questi problemi e per il miglioramento dell'esperienza generale degli utenti che presentano o visualizzano le presentazioni di PowerPoint, Lync Server 2013 utilizza il server Office Web Apps per gestire le presentazioni di PowerPoint. Tra i vantaggi offerti, il nuovo approccio garantisce le seguenti funzionalità:

  - Visualizzazioni a risoluzione più elevata e un supporto migliorato per le funzionalità di PowerPoint come animazioni, transizioni dispositive e video incorporati.

  - L'accesso alle presentazioni è consentito a un numero più elevato di dispositivi mobili. Lync Server 2013 utilizza infatti DHTML e JavaScript standard per la trasmissione delle presentazioni di PowerPoint invece di formati Silverlight e DHTML personalizzati.

  - Gli utenti che dispongono dei privilegi appropriati possono scorrere una presentazione di PowerPoint indipendentemente dalla presentazione stessa. Durante la presentazione di Davide Garghentini, ad esempio, Luisa Cazzaniga può scorrere la presentazione e visualizzare le diapositive che desidera senza conseguenze sulla presentazione di Davide.

Per ulteriori informazioni su come configurare Lync Server 2013 per l'utilizzo di server Office Web Apps, vedere [distribuzione di Office Web Apps Server e Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902).

## Utilizzo del server Office Web Apps per la visualizzazione dei file di Office in cartelle condivise e siti Web tramite i Visualizzatori online

I Visualizzatori online consentono di utilizzare un Web browser per la visualizzazione dei file di Excel, PowerPoint e Word archiviati in server Web o cartelle condivise all'interno di un'organizzazione. Gli utenti possono comodamente visualizzare i file di Office in un Web browser senza aprire un'applicazione distinta. Inoltre, i Visualizzatori online non richiedono l'installazione di Office 2013 nei computer degli utenti. I Visualizzatori online generano inoltre il codice necessario per collegare o incorporare l'URL in una pagina Web. È possibile utilizzare i Visualizzatori online sia nella rete Intranet che in Internet.

Il server Office Web Apps fornisce una pagina all'indirizzo http://*NomeOfficeWebAppsServer*/op/generate.aspx che è possibile utilizzare per generare i collegamenti a documenti pubblici con indirizzi UNC o URL. Quando un utente sceglie un URL generato, i Visualizzatori online consentono al server Office Web Apps di accedere al file dal relativo percorso ed eseguirne il rendering utilizzando Office Web Apps. L'utente può visualizzare i file di Word, Excel o PowerPoint in un browser con le caratteristiche originali di Office. La formattazione e il layout nei documenti di Word vengono mantenuti, i dati presenti nelle cartelle di lavoro di Excel possono essere filtrati e ordinati e le animazioni delle presentazioni di PowerPoint vengono visualizzate. Si tenga tuttavia presente che i Visualizzatori online consentono agli utenti di visualizzare i file ma non di modificarli e non sono in grado di aprire file che richiedono l'autenticazione.

Ulteriori informazioni sui Visualizzatori online sono disponibili nella sezione [Planning for Online Viewers with Office Web Apps Server](plan-office-web-apps-server.md).


> [!NOTE]
> Microsoft ospita una versione solo per Internet di Crea URL in <A href="http://go.microsoft.com/fwlink/?linkid=256548">Office.com</A>.



## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Pianificare il server Office Web Apps](plan-office-web-apps-server.md)  
[Distribuire il server Office Web Apps](deploy-office-web-apps-server.md)  
  

[deploy-office-web-apps-server.md](deploy-office-web-apps-server.md)

