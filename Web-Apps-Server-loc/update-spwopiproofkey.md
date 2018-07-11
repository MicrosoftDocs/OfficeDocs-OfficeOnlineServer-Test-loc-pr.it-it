---
title: Update-SPWOPIProofKey
TOCTitle: Update-SPWOPIProofKey
ms:assetid: fe7f3a87-082e-4a43-a5f3-7be41d8e91a3
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219460(v=office.15)
ms:contentKeyID: 49652306
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Update-SPWOPIProofKey 

_**Si applica a:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013

_**Ultima modifica dell'argomento:** 2015-03-09

Aggiorna la chiave pubblica utilizzata per la connessione all'applicazione WOPI nella farm di SharePoint corrente in cui viene eseguito il cmdlet.

## Sintassi

```PowerShell
      Update-SPWOPIProofKey 
  [-AssignmentCollection <SPAssignmentCollection>] 
  [-ServerName <String>]
```

## Descrizione dettagliata

Il cmdlet **Update-SPWOPIProofKey** aggiorna la chiave pubblica utilizzata per la connessione all'applicazione WOPI (ad esempio un server che esegue il server Office Web Apps) nella farm di SharePoint corrente in cui viene eseguito il cmdlet. È possibile utilizzare il cmdlet se le chiavi tra la farm di SharePoint e l'applicazione WOPI non sono più sincronizzate. Se le chiavi non sono sincronizzate, è possibile che i documenti non vengano aperti nel browser e che nei registri ULS (Unified Logging Service) siano contenuti messaggi di firma di prova non valida per il file o per la cartella.

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

> [!NOTE]
> Quando viene utilizzato il parametro <STRONG>Global</STRONG> tutti gli oggetti vengono memorizzati nell'area di archiviazione globale. Se gli oggetti non vengono utilizzati immediatamente o eliminati dalla memoria tramite il comando <STRONG>Stop-SPAssignment</STRONG>, può verificarsi una condizione di memoria insufficiente.

</td>
</tr>
<tr class="even">
<td><p><strong>ServerName</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p>Specifica l'applicazione WOPI da cui ottenere la chiave. L'applicazione può essere un server che esegue il server Office Web Apps. Se questo parametro non viene specificato, verranno aggiornate le chiavi pubbliche per tutte le applicazioni WOPI connesse alla farm di SharePoint corrente.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\--------------ESEMPIO-----------------

```PowerShell
    Update-SPWOPIProofKey -ServerName "Server.corp.Contoso.com"
```

In questo esempio viene ottenuta la chiave pubblica corrente per l'applicazione WOPI (ad esempio un server che esegue il server Office Web Apps) e viene aggiornata la chiave archiviata nella farm di SharePoint.

## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Utilizzare Office Web Apps con SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)  
  

[](use-office-web-apps-with-sharepoint-2013.md)

