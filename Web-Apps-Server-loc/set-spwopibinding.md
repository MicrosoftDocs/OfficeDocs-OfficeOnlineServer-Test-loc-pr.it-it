---
title: Set-SPWOPIBinding
TOCTitle: Set-SPWOPIBinding
ms:assetid: e373528f-e69b-4e25-9df4-3a5f80ab64ac
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219454(v=office.15)
ms:contentKeyID: 49652296
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIBinding

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Aggiorna l'azione di clic predefinita per un binding di applicazione o di estensione di nome di file.

## Sintassi

    Set-SPWOPIBinding [-Identity] <SPWopiBindingPipeBind> -DefaultAction <SwitchParameter> [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Set-SPWOPIBinding** aggiorna l'azione di clic predefinita per un binding di applicazione o di estensione di file. È ad esempio possibile impostare l'azione di clic predefinita per la visualizzazione di un documento di Word in una raccolta di SharePoint. A tale scopo, impostare l'azione predefinita su true per i binding "view"-"Word".

In genere, è possibile utilizzare l'output del comando **Get-SPWOPIBinding** come valore per la proprietà -Identity del comando. Per ulteriori informazioni, vedere [Get-SPWOPIBinding](get-spwopibinding.md)

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>È possibile impostare binding creati utilizzando il comando <strong>New-SPWOPIBinding</strong>. Per sovrascrivere un binding integrato, ad esempio l'azione eseguita durante la visualizzazione di un documento di Word in una raccolta SharePoint, creare un nuovo binding, utilizzando <strong>New-SPWOPIBinding</strong>, e assegnare un'azione diversa. Per ulteriori informazioni, vedere <a href="new-spwopibinding.md">New-SPWOPIBinding</a>.</td>
</tr>
</tbody>
</table>


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
<td><p><strong>Identity</strong></p></td>
<td><p>Obbligatorio</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Specifica il binding. In genere, è possibile utilizzare l'output del comando <strong>Get-SPWOPIBinding</strong> come valore per la proprietà –Identity.</p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>Obbligatorio</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Specifica se il binding deve essere impostato come azione di clic predefinita per un'applicazione o un'estensione di file nel binding.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Consente di gestire gli oggetti ai fini della corretta eliminazione dalla memoria. Oggetti quali <strong>SPWeb</strong> o <strong>SPSite</strong> richiedono quantità di memoria elevate e per utilizzarli negli script Windows PowerShell è necessario gestire la memoria in modo appropriato. Tramite l'oggetto <strong>SPAssignment</strong> è possibile assegnare oggetti a una variabile ed eliminarli quando è necessario liberare memoria. Gli oggetti <strong>SPWeb</strong>, <strong>SPSite</strong> o <strong>SPSiteAdministration</strong> utilizzati vengono automaticamente eliminati dalla memoria se non viene utilizzato un insieme di assegnazioni o il parametro <strong>Global</strong>.</p>
<div class="alert">

> [!NOTE]
> Quando viene utilizzato il parametro <STRONG>Global</STRONG> tutti gli oggetti vengono memorizzati nell'area di archiviazione globale. Se gli oggetti non vengono utilizzati immediatamente o eliminati dalla memoria tramite il comando <STRONG>Stop-SPAssignment</STRONG>, può verificarsi una condizione di memoria insufficiente.


</div>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
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

    Get-SPWOPIBinding -Action "view" -Application "Word"| Set-SPWOPIBinding -DefaultAction

In questo esempio viene impostata l'azione di clic predefinita per la visualizzazione di un documento di Word in una raccolta di SharePoint. È possibile verificare che l'azione di clic predefinita sia impostata per Word eseguendo il cmdlet **Get-SPWOPIBinding -Action "view" -Application "Word"**. Il valore **IsDefaultAction** è impostato su "True".

## Vedere anche


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  
[New-SPWOPIBinding](new-spwopibinding.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

