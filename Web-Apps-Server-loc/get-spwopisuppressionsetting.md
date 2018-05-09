---
title: Get-SPWOPISuppressionSetting
TOCTitle: Get-SPWOPISuppressionSetting
ms:assetid: a7924964-e16f-4eca-be91-7aff8d45e0c6
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219445(v=office.15)
ms:contentKeyID: 49652280
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPISuppressionSetting

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Restituisce le impostazioni di eliminazione relative alla farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Sintassi

    Get-SPWOPISuppressionSetting [-AssignmentCollection <SPAssignmentCollection>]

## Descrizione dettagliata

Il cmdlet **Get-SPWOPISuppressionSetting** restituisce le impostazioni di eliminazione relative alla farm di SharePoint corrente in cui viene eseguito.

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
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Consente di gestire gli oggetti ai fini della corretta eliminazione dalla memoria. Oggetti quali <strong>SPWeb</strong> o <strong>SPSite</strong> richiedono quantità di memoria elevate e per utilizzarli negli script Windows PowerShell è necessario gestire la memoria in modo appropriato. Tramite l'oggetto <strong>SPAssignment</strong> è possibile assegnare oggetti a una variabile ed eliminarli quando è necessario liberare memoria. Gli oggetti <strong>SPWeb</strong>, <strong>SPSite</strong> o <strong>SPSiteAdministration</strong> utilizzati vengono automaticamente eliminati dalla memoria se non viene utilizzato un insieme di assegnazioni o il parametro <strong>Global</strong>.</p>
<div class="alert">

> [!NOTE]
> Quando viene utilizzato il parametro <STRONG>Global</STRONG> tutti gli oggetti vengono memorizzati nell'area di archiviazione globale. Se gli oggetti non vengono utilizzati immediatamente o eliminati dalla memoria tramite il comando <STRONG>Stop-SPAssignment</STRONG>, può verificarsi una condizione di memoria insufficiente.


</div></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO-----------------

    Get-SPWOPISuppressionSetting

In questo esempio vengono restituite tutte le impostazioni di eliminazione relative alla farm di SharePoint corrente in cui viene eseguito il cmdlet. Le impostazioni di eliminazione restituite includono **DocType** e **WOPIAction**.

## Vedere anche


[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  
[Remove-SPWOPISuppressionSetting](remove-spwopisuppressionsetting.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

