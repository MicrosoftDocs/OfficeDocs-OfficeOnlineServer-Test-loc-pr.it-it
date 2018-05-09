---
title: Windows PowerShell per Office Web Apps (SharePoint 2013)
TOCTitle: Windows PowerShell per Office Web Apps
ms:assetid: eb4b96e4-b12d-43e7-b1ce-fc04f5cbbd31
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219457(v=office.15)
ms:contentKeyID: 49652300
ms.date: 01/07/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Windows PowerShell per Office Web Apps (SharePoint 2013)

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** articoli relativi ai cmdlet di Windows PowerShell SPWOPI necessari per la configurazione di Office Web Apps.

**Destinatari:** professionisti IT

Quando viene utilizzato con SharePoint 2013 in locale, Office Web Apps fornisce versioni aggiornate di Word Web App, Excel Web App, PowerPoint Web App e OneNote Web App. Gli utenti possono visualizzare ed eventualmente modificare i documenti di Office utilizzando un Web browser supportato in computer e diversi dispositivi mobili, come Windows Phone, iPhone e iPad.

![Logo di Office 2013](images/JJ219447.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Logo di Office 2013")Nella tabella seguente sono elencati e descritti gli articoli relativi a ciascun cmdlet Windows PowerShell SPWOPI necessario per la configurazione di Office Web Apps per l'utilizzo con SharePoint 2013.


### Cmdlet Windows PowerShell SPWOPI

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
<td><p><a href="get-spwopibinding.md">Get-SPWOPIBinding</a></p></td>
<td><p>Restituisce un elenco di binding creati utilizzando <strong>New-SPWOPIBinding</strong> nella farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-spwopisuppressionsetting.md">Get-SPWOPISuppressionSetting</a></p></td>
<td><p>Restituisce le impostazioni di eliminazione relative alla farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-spwopizone.md">Get-SPWOPIZone</a></p></td>
<td><p>Restituisce l'area configurata nella farm di SharePoint corrente per l'applicazione WOPI da utilizzare.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-spwopibinding.md">New-SPWOPIBinding</a></p></td>
<td><p>Crea un nuovo binding per associare estensioni di nomi di file o applicazioni ad azioni nella farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-spwopisuppressionsetting.md">New-SPWOPISuppressionSetting</a></p></td>
<td><p>Disattiva Office Web Apps per l'azione e il tipo di documento o il binding specificato nella farm di SharePoint corrente.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-spwopibinding.md">Remove-SPWOPIBinding</a></p></td>
<td><p>Rimuove i binding per le applicazioni, le estensioni dei nomi di file e le relative azioni nella farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-spwopisuppressionsetting.md">Remove-SPWOPISuppressionSetting</a></p></td>
<td><p>Rimuove le impostazioni di eliminazione per un tipo di file o un ID programmatico (ProgID) nella farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-spwopibinding.md">Set-SPWOPIBinding</a></p></td>
<td><p>Aggiorna l'azione di clic predefinita per un binding di applicazione o di estensione di nome di file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-spwopizone.md">Set-SPWOPIZone</a></p></td>
<td><p>Configura l'area che verrà utilizzata dalla farm di SharePoint corrente per passare con il browser all'applicazione WOPI.</p></td>
</tr>
<tr class="even">
<td><p><a href="update-spwopiproofkey.md">Update-SPWOPIProofKey</a></p></td>
<td><p>Aggiorna la chiave pubblica utilizzata per la connessione all'applicazione WOPI nella farm di SharePoint corrente in cui viene eseguito il cmdlet.</p></td>
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
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/JJ219447.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="Icona chat" alt="Icona chat" /></p></td>
<td><p><strong>Commenti e suggerimenti</strong></p></td>
<td><p>Per inviare commenti e suggerimenti sulla documentazione relativa a Office 2013Office 365 ProPlus, scegliere il collegamento <strong>Commenti e suggerimenti</strong> nella parte inferiore della pagina. I commenti e i suggerimenti verranno inviati direttamente al team della documentazione.</p></td>
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

