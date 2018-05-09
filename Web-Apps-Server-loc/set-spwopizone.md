---
title: Set-SPWOPIZone
TOCTitle: Set-SPWOPIZone
ms:assetid: bc751cc4-8ac8-45f7-b6ea-da6fcb5473ac
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219451(v=office.15)
ms:contentKeyID: 49652288
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIZone

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Configura l'area che verrà utilizzata dalla farm di SharePoint corrente per passare con il browser all'applicazione WOPI.

## Sintassi

    Set-SPWOPIZone [[-Zone] <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Set-SPWOPIZone** configura l'area che verrà utilizzata dalla farm di SharePoint corrente per passare con il browser all'applicazione WOPI, ad esempio un server Office Web Apps. La pagina di SharePoint Server nel browser crea un frame contenente una pagina dell'applicazione WOPI. L'area dell'URL dell'applicazione WOPI è determinata da questa applicazione.

Se non si imposta l'area, l'impostazione predefinita è "internal-HTTPS". Se si seleziona un'area non supportata dall'applicazione WOPI, Office Web Apps non funzionerà. Utilizzare HTTP solo quando si utilizza una rete completamente sicura basata su IPSEC (crittografia completa) o un ambiente di testing in cui non sono contenuti dati riservati.

SharePoint Management Shell

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
<th>Parametro</th>
<th>Obbligatorio</th>
<th>Tipo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Zone</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'area. Per un elenco di aree supportare dall'applicazione WOPI, eseguire <strong>Get-SPWOPIBinding</strong>.</p>
<p>Se si dispone di una farm di SharePoint interna ed esterna, specificare external. Se invece si dispone di una farm di SharePoint solo interna, specificare internal. Utilizzare HTTP solo quando si utilizza una rete completamente sicura basata su IPSEC (crittografia completa) o un ambiente di testing in cui non sono contenuti dati riservati. Le opzioni sono le seguenti:</p>
<p>- Internal-HTTP</p>
<p>- Internal-HTTPS</p>
<p>- External-HTTP</p>
<p>- External-HTTPS</p></td>
</tr>
<tr class="even">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Consente di gestire gli oggetti ai fini della corretta eliminazione dalla memoria. Oggetti quali <strong>SPWeb</strong> o <strong>SPSite</strong> richiedono quantità di memoria elevate e per utilizzarli negli script Windows PowerShell è necessario gestire la memoria in modo appropriato. Tramite l'oggetto <strong>SPAssignment</strong> è possibile assegnare oggetti a una variabile ed eliminarli quando è necessario liberare memoria. Gli oggetti <strong>SPWeb</strong>, <strong>SPSite</strong> o <strong>SPSiteAdministration</strong> utilizzati vengono automaticamente eliminati dalla memoria se non viene utilizzato un insieme di assegnazioni o il parametro <strong>Global</strong>.</p>
<div class="alert">

> [!NOTE]
> Quando viene utilizzato il parametro <STRONG>Global</STRONG> tutti gli oggetti vengono memorizzati nell'area di archiviazione globale. Se gli oggetti non vengono utilizzati immediatamente o eliminati dalla memoria tramite il comando <STRONG>Stop-SPAssignment</STRONG>, può verificarsi una condizione di memoria insufficiente.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Visualizza un messaggio che illustra gli effetti del comando anziché eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO-----------------

    Set-SPWOPIZone -Zone "external-https"

In questo esempio viene configurata la farm di SharePoint corrente per utilizzare le connessioni esterne tramite HTTPS per l'applicazione WOPI, ad esempio un server Office Web Apps.

## Vedere anche


[Get-SPWOPIZone](get-spwopizone.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

