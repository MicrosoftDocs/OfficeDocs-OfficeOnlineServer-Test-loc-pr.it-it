---
title: Windows PowerShell per server Office Web Apps
TOCTitle: Windows PowerShell per server Office Web Apps
ms:assetid: 56bfd3b3-f563-423d-aea0-65b331f73b96
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Ee890080(v=office.15)
ms:contentKeyID: 49652267
ms.date: 01/07/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Windows PowerShell per server Office Web Apps

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** articoli relativi ai cmdlet OfficeWebApps di Windows PowerShell necessari per la configurazione di Office Web Apps Server.

**Destinatari:** professionisti IT

Il server Office Web Apps è un nuovo prodotto server di Office che fornisce versioni basate su browser di Word, PowerPoint, Excel e OneNote. Una singola farm di Office Web Apps Server può supportare utenti che accedono ai file di Office mediante SharePoint 2013, Lync Server 2013, Exchange Server 2013, cartelle condivise e siti Web.

![Logo di Office 2013](images/JJ219447.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Logo di Office 2013")Nella tabella seguente sono elencati e descritti gli articoli relativi a ciascun cmdlet OfficeWebApps di Windows PowerShell per il server Office Web Apps.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.tip(Office.15).gif" title="Suggerimento" alt="Suggerimento" /><strong>Suggerimento:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se Windows PowerShell non riconosce questi cmdlet quando vengono eseguiti, può essere necessario importare il modulo <strong>OfficeWebApps</strong> utilizzando il comando seguente:<br />
<code>Import-Module -Name OfficeWebApps</code></td>
</tr>
</tbody>
</table>



### Cmdlet OfficeWebApps di Windows PowerShell

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Articolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-officewebappsfarm.md">Get-OfficeWebAppsFarm</a></p></td>
<td><p>Restituisce informazioni dettagliate sull'oggetto OfficeWebAppsFarm di cui è membro il server corrente.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-officewebappshost.md">Get-OfficeWebAppsHost</a></p></td>
<td><p>Restituisce l'elenco di domini host contenuti nell'elenco Consenti di una farm di server Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-officewebappsmachine.md">Get-OfficeWebAppsMachine</a></p></td>
<td><p>Restituisce informazioni dettagliate sul server corrente incluso in una farm di server Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsfarm.md">New-OfficeWebAppsFarm</a></p></td>
<td><p>Crea una nuova farm di server Office Web Apps nel computer locale.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-officewebappshost.md">New-OfficeWebAppsHost</a></p></td>
<td><p>Aggiunge un dominio host all'elenco Consenti di una farm di server Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsmachine.md">New-OfficeWebAppsMachine</a></p></td>
<td><p>Aggiunge il server corrente a una farm di server Office Web Apps esistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-officewebappshost.md">Remove-OfficeWebAppsHost</a></p></td>
<td><p>Rimuove un dominio host dall'elenco Consenti di una farm di server Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-officewebappsmachine.md">Remove-OfficeWebAppsMachine</a></p></td>
<td><p>Rimuove il server corrente dalla farm di server Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><a href="repair-officewebappsfarm.md">Repair-OfficeWebAppsFarm</a></p></td>
<td><p>Rimuove da una farm di server Office Web Apps tutti i server contrassegnati come non integri.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-officewebappsfarm.md">Set-OfficeWebAppsFarm</a></p></td>
<td><p>Configura le impostazioni di una farm di server Office Web Apps esistente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-officewebappsmachine.md">Set-OfficeWebAppsMachine</a></p></td>
<td><p>Modifica le impostazioni del server corrente di una farm di server Office Web Apps.</p></td>
</tr>
</tbody>
</table>


### Altre risorse Office per i professionisti IT

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/JJ219447.22cad0f4-303d-4a40-90a3-fa08e69dfdaf(Office.15).png" title="Icona novità (casella)" alt="Icona novità (casella)" /></p></td>
<td><p><strong>Nuovo contenuto pubblicato</strong></p></td>
<td><p>Per un elenco degli articoli sul server Office Web Apps nuovi o aggiornati di recente, vedere l'articolo seguente.</p>
<ul>
<li><p><a href="https://technet.microsoft.com/it-it/library/ff433481(v=office.15)">Nuovo contenuto pubblicato per Office Web Apps e Office Web Apps Server</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><img src="images/JJ219447.6b2d6dfa-7dc8-40fb-8335-af68b575f8cb(Office.15).png" title="Introduzione" alt="Introduzione" /></p></td>
<td><p><strong>Guida introduttiva</strong></p></td>
<td><p>Scaricare il server Office Web Apps.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256561">Volume Licensing Service Center (VLSC)</a></p>
<p>Per scaricare server Office Web Apps è necessario disporre di una licenza nell'ambito di un contratto multilicenza per Office Professional Plus 2013, Office Standard 2013 o Office per Mac 2011. L'opzione di download è disponibile sotto questi prodotti di Office nel portale VLSC.</p></li>
</ul>
<p>Scaricare i Language Pack per il server Office Web Apps.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=263945">Area download Microsoft</a></p></li>
</ul>
<p>Altre informazioni sul server Office Web Apps.</p>
<ul>
<li><p><a href="deploy-the-infrastructure-office-web-apps-server.md">Distribuire l'infrastruttura: Server Office Web Apps</a></p></li>
</ul>
<p>Visitare questi collegamenti per informazioni su come i prodotti server di Office possono utilizzare il server Office Web Apps per fornire funzionalità di modifica e visualizzazione basate sul Web dei file di Office.</p>
<ul>
<li><p><a href="use-office-web-apps-with-sharepoint-2013.md">Utilizzare Office Web Apps con SharePoint 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256902">Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256611">Integrazione del server Office Web Apps (Exchange Server 2013)</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/JJ219447.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="Icona chat" alt="Icona chat" /></p></td>
<td><p><strong>Commenti e suggerimenti</strong></p></td>
<td><p>Per inviare commenti e suggerimenti sulla documentazione relativa a Office 2013Office 365 ProPlus, scegliere il collegamento <strong>Commenti e suggerimenti</strong> nella parte inferiore della pagina. I commenti e i suggerimenti verranno inviati direttamente al team della documentazione.</p>
<p><img src="images/JJ219456.1863f854-8ce5-40e4-bd40-9bbe16591834(Office.15).png" title="e-mail" alt="e-mail" />  Per suggerire contenuti, richiedere altra documentazione o segnalare un errore, scrivere all'indirizzo <a href="mailto:feedork@microsoft.com">feedork@microsoft.com</a>.</p></td>
</tr>
</tbody>
</table>


## Formazione e altre risorse relative a Office


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Download</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/evalcenter/hh973391">Office 365 ProPlus</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/p/?linkid=507653">Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/evalcenter/ee390818.aspx">Office 2013</a></p></li>
<li><p><a href="https://code.msdn.microsoft.com/office/">Esempi di codice di Office</a></p></li>
<li><p><a href="https://gallery.technet.microsoft.com/office/">Script e file di esempio di Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/office/aa905351">Download per sviluppatori di Office</a></p></li>
<li><p><a href="https://www.microsoft.com/it-it/download/office.aspx?q=office">Download di Office</a></p></li>
<li><p><a href="http://www.microsoft.com/it-it/download/search.aspx?q=office+365">Download di Office 365</a></p></li>
</ul></td>
<td><p><strong>Procedure</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/it-it/library/jj220060.aspx">Creare app per Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/library/cc178982.aspx">Distribuire Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/library/cc179068.aspx">Gestire Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/office/ff381682.aspx">Formazione e preparazione tecnica dell'utente per Office 2010</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/office/aa905496.aspx">SDK di Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/office/aa905375">Formazione per sviluppatori di Office</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/it-it/office/media/video/video.html?cid=odc%26from=mscomodc">Video per sviluppatori di Office</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/it-it/office/media/video/video.html?cid=o365%26from=mscomo365">Video per sviluppatori di Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/office/ff519671">Formazione su Office per professionisti IT</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/it-it/office/media/video/video.html?cid=otc%26from=mscomotc">Video su Office per professionisti IT</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/it-it/office/media/video/video.html?cid=o365%26from=mscomo365">Video su Office 365 per professionisti IT</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/openspecifications/">Specifiche tecniche</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/library/cc307282(v=office.12).aspx">Protocolli di Office</a></p></li>
</ul></td>
<td><p><strong>Sites</strong></p>
<ul>
<li><p><a href="https://msdn.microsoft.com/it-it/office">Sviluppatori di Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/office">Office per professionisti IT</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/office/hh506337">Sviluppatori di Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/hh912691">Office 365 per professionisti IT</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/library/cc303401.aspx">Office 2013 Resource Kit</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/sharepoint">Sviluppatori di SharePoint</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/sharepoint">SharePoint per professionisti IT</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/vstudio/aa718325">Sviluppatori di Visual Studio</a></p></li>
<li><p><a href="http://office.microsoft.com/">Office.com</a></p></li>
</ul></td>
<td><p><strong>Help</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/it-it/office/ee748587.aspx">Aggiornamenti di Office</a></p></li>
<li><p><a href="https://blogs.msdn.com/b/officeapps">Blog sulle app per Office e SharePoint</a></p></li>
<li><p><a href="https://social.msdn.microsoft.com/forums/it-it/category/officedev%2coldevelopment%2csharepoint2010%2csharepoint%2cprojectserver2010%2cprojectprofessional2010%2cuc/">Forum: Office per sviluppatori</a></p></li>
<li><p><a href="https://answers.microsoft.com/it-it/msoffice">Forum: Office 365</a></p></li>
<li><p><a href="https://social.technet.microsoft.com/wiki">Wiki di TechNet</a></p></li>
<li><p><a href="https://stackoverflow.com/search?q=office">StackOverflow: Office</a></p></li>
<li><p><a href="https://mvp.microsoft.com/it-it/mvp/search-mvp.aspx?kw=office">MVP di Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/it-it/ms772425">Supporto per professionisti IT di Office</a></p></li>
<li><p><a href="https://msdn.microsoft.com/it-it/office/aa905515">Supporto per sviluppatori di Office</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


[](use-office-web-apps-with-sharepoint-2013.md)

