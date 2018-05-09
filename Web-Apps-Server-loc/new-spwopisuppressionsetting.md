---
title: New-SPWOPISuppressionSetting
TOCTitle: New-SPWOPISuppressionSetting
ms:assetid: 7e6bb8f5-3124-4568-80c6-02cae46b803b
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219443(v=office.15)
ms:contentKeyID: 49652273
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPISuppressionSetting

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Il cmdlet **New-SPWOPISuppressionSetting** disattiva Office Web Apps per l'azione, l'estensione di file o l'identificatore programmatico specificato nella farm di SharePoint corrente.

## Sintassi

    New-SPWOPISuppressionSetting [-Action <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **New-SPWOPISuppressionSetting** disattiva Office Web Apps per l'azione, l'estensione di file o l'identificatore programmatico (ProgID) specificato nella farm di SharePoint corrente. Il cmdlet esegue questa operazione senza rimuovere le informazioni per l'individuazione o la possibilità per gli utenti di utilizzare la funzionalità di SharePoint di condivisione per collegamento per inviare un collegamento a un documento e consentire al destinatario di utilizzare Office Web Apps per tale tipo di documento. Potrebbe essere necessario utilizzare questo cmdlet se si desidera utilizzare Excel Services per visualizzare le cartelle di lavoro di Excel anziché l'applicazione WOPI, ad esempio il server Office Web Apps.

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
<td><p>Specifica l'azione da eliminare per un'estensione di file o un identificatore programmatico (ProgID) specifico, ad esempio &quot;view&quot;, &quot;edit&quot; ed &quot;embedview&quot;. Per un elenco completo di azioni, eseguire <strong>Get-SPWOPIBinding</strong>.</p></td>
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
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'estensione di file da eliminare. Eseguire Get-SPWOPIBinding per ottenere l'elenco delle estensioni di file supportate dall'applicazione WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'identificatore programmatico (ProgID) di un'applicazione da eliminare. Eseguire Get-SPWOPIBinding per ottenere l'elenco di ProgID supportati dall'applicazione WOPI.</p></td>
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

\--------------ESEMPIO 1-----------------

    New-SPWOPISuppressionSetting -Extension "XLSX" -Action "view"

    New-SPWOPISuppressionSetting -Extension "XLS" -Action "view"

In questo esempio viene disattivata la possibilità per un utente di utilizzare Office Web Apps per visualizzare le cartelle di lavoro di Excel con estensione di file "xlsx" o "xls".

## Vedere anche


[Get-SPWOPISuppressionSetting](get-spwopisuppressionsetting.md)  
[Remove-SPWOPISuppressionSetting](remove-spwopisuppressionsetting.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

