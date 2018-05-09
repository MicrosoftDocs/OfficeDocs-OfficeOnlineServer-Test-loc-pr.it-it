---
title: Get-SPWOPIBinding
TOCTitle: Get-SPWOPIBinding
ms:assetid: b757301b-f6c5-43a5-a8ca-2ef33ede0ae8
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219450(v=office.15)
ms:contentKeyID: 49652287
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIBinding

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Restituisce un elenco di binding creati utilizzando **New-SPWOPIBinding** nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Sintassi

    Get-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WOPIZone <String>]

## Descrizione dettagliata

**Get-SPWOPIBinding** restituisce un elenco di binding creati utilizzando **New-SPWOPIBinding** nella farm di SharePoint corrente in cui viene eseguito il cmdlet. Tra i risultati sono inclusi tipi di file, azioni, applicazioni e aree configurati per un'applicazione WOPI, ad esempio un server Office Web Apps.

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
<td><p><strong>Action</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'azione per cui restituire i binding.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'applicazione per cui restituire i binding.</p></td>
</tr>
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
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'estensione di file per cui restituire i binding.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'identificatore programmatico (ProgID) di un'applicazione per la quale restituire i binding.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il nome dell'applicazione WOPI per la quale restituire i binding, ad esempio un server Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'area per cui restituire i binding.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO 1-----------------

    Get-SPWOPIBinding -Server "Server.corp.Contoso.com"

In questo esempio viene restituito un elenco di binding creati nella farm di SharePoint corrente in cui viene eseguito il cmdlet per l'applicazione WOPI "Server.corp.Contoso.com". L'applicazione WOPI può essere il server Office Web Apps.

\--------------ESEMPIO 2-----------------

    Get-SPWOPIZone | Get-SPWOPIBinding

In questo esempio viene restituito un elenco di binding creati nella farm di SharePoint corrente in cui viene eseguito il cmdlet per l'area configurata per l'applicazione WOPI.

## Vedere anche


[New-SPWOPIBinding](new-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

