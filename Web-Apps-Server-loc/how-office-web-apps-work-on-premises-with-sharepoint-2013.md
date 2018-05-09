---
title: Funzionamento di Office Web Apps in locale con SharePoint 2013
TOCTitle: Office Web Apps locale con SharePoint 2013
ms:assetid: 8480064e-14a4-4b46-ad6b-0c836b192af2
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ff431685(v=office.15)
ms:contentKeyID: 49652274
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Funzionamento di Office Web Apps in locale con SharePoint 2013

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** fornisce informazioni su Office Web Apps, il server Office Web Apps e il loro funzionamento locale con SharePoint 2013.

**Destinatari:** professionisti IT

Quando usato con SharePoint Server 2013, server Office Web Apps fornisce versioni aggiornate di Word Web App, Excel Web App, PowerPoint Web App e OneNote Web App. Gli utenti possono visualizzare e, in alcuni casi, modificare i documenti di Office nelle raccolte di SharePoint mediante un Web browser supportato in computer e numerosi dispositivi mobili, come Windows Phone, iPhone, iPad, tablet Windows 8 e dispositivi Android.


**Figura: funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi.**

![Grafico in cui vengono riepilogate le funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi. Sono evidenziate quelle ottimizzate per i dispositivi touchscreen.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Grafico in cui vengono riepilogate le funzionalità di visualizzazione e modifica di Office Web Apps in diversi tipi di dispositivi. Sono evidenziate quelle ottimizzate per i dispositivi touchscreen.")

## server Office Web Apps è ora installato come server autonomo

Office Web Apps non è installato negli stessi server che eseguono SharePoint 2013. Distribuire uno o più server fisici o virtuali che eseguono server Office Web Apps. Configurare quindi la farm di SharePoint 2013 per l'uso della farm di server Office Web Apps in modo da fornire le funzionalità di Office Web Apps agli utenti che creano o aprono i file di Office dalle raccolte di SharePoint. Per altre informazioni, vedere [Panoramica sul server Office Web Apps](office-web-apps-server-overview.md).

## Opzioni di licenza di Office Web Apps usato con SharePoint 2013

La licenza di Office Web Apps offre due opzioni:

  - **Sola visualizzazione**. Per impostazione predefinita, Office Web Apps è disponibile in sola visualizzazione. La funzionalità di sola visualizzazione viene fornita gratuitamente.

  - **Modifica e visualizzazione**. Per usare le caratteristiche per la modifica di Office Web Apps con SharePoint 2013 è necessario acquistare una licenza di modifica. La modifica viene abilitata durante la creazione della farm di server Office Web Apps.

Le organizzazioni che dispongono di un contratto multilicenza per Office 2013 possono abilitare la modifica di Office Web Apps per SharePoint 2013 in locale, facendo così in modo che gli utenti dispongano di funzionalità di modifica di Office a casa o in altri luoghi in cui i client Office potrebbero non essere installati. Le licenze per la modifica di Office Web Apps non sono acquistabili separatamente.

Per i dettagli esatti della licenza, consultare le Condizioni di licenza software Microsoft visualizzate durante l'installazione del server Office Web Apps.

SharePoint 2013 fornisce un nuovo sistema di applicazione delle licenze che funziona con Office Web Apps. Se si abilitano le licenze di SharePoint e quindi si abilita la modifica di Office Web Apps, solo gli utenti che dispongono della licenza appropriata saranno in grado di modificare effettivamente i file di Office in un browser. Se per gli utenti non vengono applicate licenze di modifica di Office Web Apps, sarà supportata la sola visualizzazione.

Per altre informazioni sul funzionamento delle licenze in SharePoint 2013, vedere [Configurare la gestione delle licenze in SharePoint Server 2013](https://technet.microsoft.com/it-it/library/jj219627\(v=office.15\)). Per una descrizione del parametro EditingEnabled che abilita la caratteristica di modifica, vedere [New-OfficeWebAppsFarm](new-officewebappsfarm.md) e [Set-OfficeWebAppsFarm](set-officewebappsfarm.md).

I file inviati utilizzando la caratteristica Condividi tramite collegamento di SharePoint 2013 possono essere modificati in Office Web Apps anche se non è presente alcuna licenza di modifica e quando la modifica è disabilitata per la farm di server Office Web Apps.

## Usare i visualizzatori per dispositivi mobili per Office per accedere ai file nei siti di SharePoint

server Office Web Apps offre visualizzatori per dispositivi mobili per Office che rendono Office Web Apps disponibile agli utenti di dispositivi mobili che accedono ai siti di SharePoint Server. Questi visualizzatori sono abilitati per impostazione predefinita, ma possono essere disabilitati dall'amministratore del sito di SharePoint Server. Quando sono abilitati, gli utenti possono accedere al sito di SharePoint Server usando il browser del dispositivo mobile e toccare il documento che vogliono aprire nella raccolta SharePoint Server per aprirlo in quel browser.

Per altre informazioni sull'uso delle raccolte di SharePoint nei dispositivi mobili, vedere [Novità per i dispositivi mobili in SharePoint 2013](https://technet.microsoft.com/it-it/library/fp161352\(v=office.15\)) e [Panoramica dei dispositivi mobili e SharePoint Server 2013](https://technet.microsoft.com/it-it/library/fp161351\(v=office.15\)). Per altre informazioni su come usare i visualizzatori per dispositivi mobili per Office sul proprio dispositivo, vedere [Usare Office Web Apps nel proprio telefono Android, iPhone o Windows Phone](http://go.microsoft.com/fwlink/p/?linkid=271045). Se si decide di disabilitare i visualizzatori in SharePoint 2013, usare il cmdlet [Remove-SPWOPIBinding](remove-spwopibinding.md).

## Differenze tra Excel Web App ed Excel Services in SharePoint

Excel Web App e Excel Services in SharePoint hanno molte caratteristiche comuni, ma non sono uguali. Excel Services è disponibile solo nell'edizione Enterprise di SharePoint Server 2013. Excel Web App è disponibile in SharePoint Server 2013 e SharePoint Foundation 2013. Entrambe le applicazioni consentono di visualizzare cartelle di lavoro in una finestra del browser e di esplorare e interagire con i dati.

Tuttavia, tra Excel Web App e Excel Services in SharePoint esistono alcune differenze. Ad esempio, Excel Services supporta le connessioni dati esterne, i modelli di dati e l'interazione con elementi che usano modelli di dati (come i rapporti di grafico pivot e tabella pivot e i controlli sequenza temporale). Excel Services offre più funzionalità di business intelligence rispetto a Excel Web App, ma Excel Services non consente agli utenti di creare o modificare cartelle di lavoro in una finestra del browser.

Per informazioni sulle differenze tra Excel Web App ed Excel Services, vedere [Panoramica di Excel Services in SharePoint Server 2013](https://technet.microsoft.com/it-it/library/ee424405\(v=office.15\)) e [Confronto tra Excel Services in SharePoint e Excel Web App](http://go.microsoft.com/fwlink/p/?linkid=255460).

Se l'organizzazione decide di utilizzare Excel Services anziché Excel Web App per la visualizzazione delle cartelle di lavoro nel browser, è possibile utilizzare il cmdlet Windows PowerShell **New-SPWOPISuppressionSettings** per disattivare Excel Web App per le cartelle di lavoro di Excel. Per ulteriori informazioni, vedere [New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md).

## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Pianificare Office Web Apps (utilizzato con SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
  

[](plan-office-web-apps-used-with-sharepoint-2013.md)

