---
title: Remove-SPWOPIBinding
TOCTitle: Remove-SPWOPIBinding
ms:assetid: 52855c21-ee2c-497a-b308-bf5eeabe4bbe
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219438(v=office.15)
ms:contentKeyID: 49652266
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPIBinding

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Rimuove i binding per le applicazioni, le estensioni dei nomi di file e le relative azioni nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Sintassi

    Remove-SPWOPIBinding [[-Identity] <SPWopiBindingPipeBind>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WhatIf [<SwitchParameter>]] [-WOPIZone <String>]

    Remove-SPWOPIBinding [-All <SwitchParameter>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Remove-SPWOPIBinding** rimuove i binding per le applicazioni, le estensioni di file e le relative azioni nella farm di SharePoint corrente in cui viene eseguito. Dopo aver eseguito questo cmdlet, è possibile utilizzare **New-SPWOPIBinding** per creare nuovamente i binding in base alle esigenze. Se si rimuovono tutti i binding di un'applicazione, gli utenti non potranno utilizzare Office Web Apps o la funzionalità di SharePoint di condivisione per collegamento per l'applicazione. Se si rimuovono tutti i binding nella farm di SharePoint in cui viene eseguito il cmdlet, gli utenti non potranno utilizzare Office Web Apps o la funzionalità di SharePoint di condivisione per collegamento per alcuna applicazione della raccolta di SharePoint.

Utilizzare invece il cmdlet **New-SPWOPISuppression** se si desidera smettere di utilizzare Office Web Apps per i clic predefiniti, mantenendo però le informazioni per l'individuazione dei binding e la possibilità per gli utenti di utilizzare la funzionalità di SharePoint di condivisione per collegamento per l'invio di un collegamento a un documento e consentendo al destinatario di utilizzare Office Web Apps per il tipo di documento.

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
<td><p>Facoltativo</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Specifica il binding.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'azione per cui rimuovere i binding, ad esempio &quot;view&quot;, &quot;edit&quot; ed &quot;embedview&quot;. Per un elenco di azioni, eseguire <strong>Get-SPWOPIBinding</strong>. Questo parametro in genere non viene utilizzato. Se si specificano alcune azioni ma non altre, è possibile che alcune caratteristiche di SharePoint non funzionino.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Rimuove tutti i binding.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'applicazione per cui rimuovere i binding. Le applicazioni possibili sono le seguenti: &quot;Word&quot;, &quot;Excel&quot;, &quot;PowerPoint&quot; oppure &quot;OneNote&quot;. Eseguire <strong>Get-SPWOPIBinding</strong> per visualizzare l'elenco delle applicazioni.</p></td>
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
<td><p><strong>Confirm</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica le estensioni di file per cui rimuovere i binding. Eseguire <strong>Get-SPWOPIBinding</strong> per ottenere l'elenco delle estensioni di file.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'identificatore programmatico (ProgID) di un'applicazione per la quale rimuovere i binding. Eseguire <strong>Get-SPWOPIBinding</strong> per visualizzare l'elenco dei ProgID. È possibile utilizzare questo parametro solo per rimuovere i binding per OneNote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il nome dell'applicazione WOPI (ad esempio il server Office Web Apps) per la quale rimuovere i binding.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Visualizza un messaggio che illustra gli effetti del comando anziché eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'area per cui rimuovere i binding.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO 1-----------------

    Remove-SPWOPIBinding -Application "Excel"

In questo esempio vengono rimossi tutti i binding per Excel nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

\--------------ESEMPIO 2-----------------

    Remove-SPWOPIBinding -All:$true

In questo esempio vengono rimossi tutti i binding nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

\--------------ESEMPIO 3-----------------

    Get-SPWOPIBinding -Action "MobileView" | Remove-SPWOPIBinding

In questo esempio vengono rimossi tutti i binding per Office Mobile Web Apps nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Vedere anche


[New-SPWOPIBinding](new-spwopibinding.md)  
[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

