---
title: New-SPWOPIBinding
TOCTitle: New-SPWOPIBinding
ms:assetid: 696f01b4-a144-431b-9bae-1c3ede78609d
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219441(v=office.15)
ms:contentKeyID: 49652270
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPIBinding

 

_**Si applica a:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2015-03-09_

Crea un nuovo binding per associare estensioni di nomi di file o applicazioni ad azioni nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Sintassi

    New-SPWOPIBinding -ServerName <String> [-Action <String>] [-AllowHTTP <SwitchParameter>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-FileName <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **New-SPWOPIBinding** associa estensioni di file o applicazioni ad azioni nella farm di SharePoint corrente in cui viene eseguito il cmdlet. Ogni binding consente di utilizzare l'applicazione WOPI per visualizzare o modificare i file nella raccolta di SharePoint. Quando ad esempio un utente visualizza un documento di Word in un elenco documenti SharePoint, l'elenco SharePoint mostrerà le opzioni disponibili per la visualizzazione o la modifica del documento in base alle azioni associate a Word nella farm di SharePoint corrente.

Per utilizzare un'applicazione WOPI, ad esempio un server che esegue il server Office Web Apps, per Office Web Apps, è necessario eseguire questo cmdlet nella farm di SharePoint per poter utilizzare Office Web Apps.

Se si esegue **New-SPWOPIBinding** per un'applicazione o un'estensione di file in cui esiste già il binding (o associazione), il cmdlet avrà esito negativo.

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
<td><p><strong>ServerName</strong></p></td>
<td><p>Obbligatorio</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il nome o il nome di dominio completo (FQDN) dell'applicazione WOPI, ad esempio un server che esegue il server Office Web Apps.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'azione da associare, ad esempio &quot;view&quot;, &quot;edit&quot; ed &quot;embedview&quot;. Per un elenco di azioni supportate dall'applicazione WOPI, eseguire <strong>Get-SPWOPIBinding</strong>. Questo parametro in genere non viene utilizzato. Se si specificano alcune azioni ma non altre, è possibile che alcune caratteristiche di SharePoint non funzionino.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHTTP</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Specifica che il cmdlet può utilizzare HTTP per l'individuazione di quanto supportato dall'applicazione WOPI. Se questo parametro viene impostato su True, le informazioni per l'individuazione provenienti dall'applicazione WOPI verranno inviate su una connessione non sicura.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica le applicazioni da associare. Le applicazioni possibili sono le seguenti: &quot;Word&quot;, &quot;Excel&quot;, &quot;PowerPoint&quot; oppure &quot;OneNote&quot;. Eseguire <strong>Get-SPWOPIBinding</strong> per ottenere l'elenco completo delle applicazioni supportate dall'applicazione WOPI.</p></td>
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
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica le estensioni di file da associare. Eseguire <strong>Get-SPWOPIBinding</strong> per ottenere l'elenco delle estensioni di file supportate dall'applicazione WOPI.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileName</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il percorso del file xml contenente le informazioni per l'individuazione per l'applicazione WOPI. È possibile caricare informazioni per l'individuazione da un file xml anziché richiederle direttamente all'applicazione WOPI.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'identificatore programmatico (ProgID) di un'applicazione da associare. Eseguire <strong>Get-SPWOPIBinding</strong> per ottenere l'elenco di ProgID supportati dall'applicazione WOPI. È possibile utilizzare questo parametro solo per associare un'azione a una cartella di OneNote.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Visualizza un messaggio che illustra gli effetti del comando anziché eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO 1-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com"

In questo esempio vengono creati binding per tutte le applicazioni e le estensioni di file supportate dall'applicazione WOPI nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

\--------------ESEMPIO 2-----------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com" -Application "Excel"

In questo esempio viene associato Excel a tutte le azioni supportate dall'applicazione WOPI per Excel nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Vedere anche


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

