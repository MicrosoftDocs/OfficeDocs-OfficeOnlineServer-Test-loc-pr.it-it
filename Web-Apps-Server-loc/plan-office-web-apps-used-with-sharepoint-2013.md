---
title: Pianificare Office Web Apps (utilizzato con SharePoint 2013)
TOCTitle: Pianificare Office Web Apps
ms:assetid: 3bd0a617-5f12-4a7e-bb75-b15c86c7e504
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ff431682(v=office.15)
ms:contentKeyID: 49652264
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Pianificare Office Web Apps (utilizzato con SharePoint 2013)

 

_<strong>Si applica a:</strong>Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Ultima modifica dell'argomento:</strong>2016-12-16_

**Riepilogo:** indicazioni di pianificazione per Office Web Apps se utilizzato con SharePoint 2013 in locale.

**Destinatari:** professionisti IT

Per pianificare l'utilizzo di Office Web Apps con SharePoint 2013 in locale, è necessario consultare le informazioni sul supporto dei browser, sui requisiti di autenticazione di SharePoint e sulle licenze per la visualizzazione e la modifica dei file di Office mediante Office Web Apps. Sarà quindi possibile decidere se SharePoint 2013 deve utilizzare il Web browser o un'applicazione client quando un utente apre i file di Office da una raccolta documenti di SharePoint 2013.

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


Contenuto dell'articolo:

  - Informazioni sulla pianificazione per Office Web Apps

  - Supporto dei browser per Office Web Apps

  - Requisiti di autenticazione di SharePoint per Office Web Apps

  - Licenze di Office Web Apps per la modifica dei file di Office

  - Considerazioni relative ai clienti che utilizzano il metodo basato sul collegamento di database per effettuare l'upgrade da SharePoint 2010

  - Comportamento di apertura predefinito per i documenti aperti dalle raccolte documenti di SharePoint 2013

## Informazioni sulla pianificazione per Office Web Apps

Le indicazioni contenute in questo articolo sono un sottoinsieme della pianificazione generale da eseguire per la distribuzione locale di server Office Web Apps all'interno dell'organizzazione. I requisiti hardware, software e di virtualizzazione, le dimensioni e la topologia della farm nonché la sicurezza, ad esempio, fanno parte della pianificazione di server Office Web Apps. Dopo aver preso tali decisioni, è possibile pianificare la configurazione della funzionalità di Office Web Apps specifica di SharePoint 2013. Se non si conosce server Office Web Apps o se non sono stati esaminati i relativi requisiti e le indicazioni di pianificazione, vedere [Panoramica sul server Office Web Apps](office-web-apps-server-overview.md) e [Pianificare il server Office Web Apps](plan-office-web-apps-server.md).

## Supporto dei browser per Office Web Apps

Il supporto dei browser per Office Web Apps è uguale al supporto per SharePoint 2013. Per ulteriori informazioni, fare riferimento all'articolo [Pianificare il supporto dei browser in SharePoint 2013](https://technet.microsoft.com/it-it/library/cc263526\(v=office.15\)).

## Requisiti di autenticazione di SharePoint per Office Web Apps

Office Web Apps può essere utilizzato solo dalle applicazioni Web di SharePoint 2013 che utilizzano l'autenticazione basata sulle attestazioni. Il rendering e la modifica di Office Web Apps non funzioneranno nelle applicazioni Web di SharePoint 2013 che utilizzano l'autenticazione in modalità classica. Se si esegue la migrazione di applicazioni Web di SharePoint 2010 che utilizzano l'autenticazione in modalità classica a SharePoint 2013, è necessario eseguire la migrazione all'autenticazione basata sulle attestazioni per consentire alle applicazioni di funzionare con Office Web Apps. Per ulteriori informazioni, vedere [Eseguire la migrazione dall'autenticazione in modalità classica a quella basata su attestazioni in SharePoint 2013](https://technet.microsoft.com/it-it/library/gg251985\(v=office.15\)).

## Licenze di Office Web Apps per la modifica dei file di Office

Le aziende che dispongono di un contratto multilicenza per Office 2013 possono abilitare la modifica di Office Web Apps per SharePoint 2013 locale, in modo che gli utenti dispongano delle funzionalità di modifica di Office a casa o altrove, dove è possibile che i client Office non siano installati.

Per i dettagli esatti della licenza, consultare le Condizioni di licenza software Microsoft visualizzate durante l'installazione del server Office Web Apps. Per altre informazioni sul funzionamento delle licenze in SharePoint 2013, vedere [Configurare la gestione delle licenze in SharePoint Server 2013](https://technet.microsoft.com/it-it/library/jj219627\(v=office.15\)).

## Considerazioni relative ai clienti che utilizzano il metodo basato sul collegamento di database per effettuare l'upgrade da SharePoint 2010

Se Office Web Apps è stato installato con SharePoint 2010, non sarà disponibile dopo l'aggiornamento a SharePoint 2013. Sarà necessario distribuire il server Office Web Apps e quindi connettervi SharePoint 2013 dopo l'aggiornamento dei database del contenuto. Non è necessario attendere che le raccolte siti vengano aggiornate perché il server Office Web Apps supporta le modalità 2010 e 2013 delle raccolte siti in SharePoint 2013. Per ulteriori informazioni sul metodo basato sul collegamento di database, vedere [Panoramica del processo di aggiornamento a SharePoint 2013](https://technet.microsoft.com/it-it/library/cc262483\(v=office.15\)).

## Comportamento di apertura predefinito per i documenti aperti dalle raccolte documenti di SharePoint 2013

È possibile specificare se i file di Word, PowerPoint, Excel e OneNote devono essere aperti in un'applicazione client (se installata) o nel browser. Per impostazione predefinita, quando SharePoint 2013 è configurato per l'utilizzo del server Office Web Apps, i file di Office vengono aperti nel browser. Per modificare il comportamento predefinito e consentire alle applicazioni client di aprire direttamente i file sono disponibili due modalità:

  - **Per la farm di SharePoint 2013** È possibile modificare il comportamento di apertura predefinito per ogni tipo di file per la farm di SharePoint 2013 utilizzando i cmdlet Windows PowerShell[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) e [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps).

  - **Nelle raccolte siti o documenti** Gli amministratori e gli utenti delle raccolte siti possono specificare se i file di Office devono essere aperti nelle applicazioni client (se installate). Gli utenti possono modificare tale impostazione nelle proprietà della raccolta documenti, mentre gli amministratori delle raccolte siti possono modificare tale impostazione in Amministrazione raccolta siti oppure utilizzando il cmdlet Install-SPFeature per l'installazione della caratteristica OpenInClient. Per ulteriori informazioni, vedere [Install-SPFeature](https://technet.microsoft.com/it-it/library/ff607825\(v=office.15\)).

## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Funzionamento di Office Web Apps in locale con SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  


[In a test environment that uses HTTP](configure-office-web-apps-for-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

