---
title: Set-OfficeWebAppsMachine
TOCTitle: Set-OfficeWebAppsMachine
ms:assetid: aeba2638-be88-4030-80fe-7e4bcd30309b
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219448(v=office.15)
ms:contentKeyID: 49652285
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsMachine

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-09_

Modifica le impostazioni del server corrente di una farm di server Office Web Apps.

## Sintassi

    Set-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-Master <String>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Set-OfficeWebAppsMachine** modifica le impostazioni del server corrente di una farm di server Office Web Apps. Tra le impostazioni sono inclusi i ruoli del server corrente e il server master designato per la farm.

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
<td><p><strong>Confirm</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Richiede la conferma prima di eseguire il comando. Per ulteriori informazioni, digitare il comando seguente: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Master</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String</p></td>
<td><p></p>
<p>Specifica il server in cui vengono archiviati i file di configurazione della farm master.</p>
<p>Se si imposta il server locale come master, sarà necessario eseguire <strong>Set-OfficeWebAppsMachine -Master</strong> in tutti i server restanti della farm di server Office Web Apps in modo che puntino al nuovo master.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roles</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.String[]</p></td>
<td><p>Specifica l'elenco di ruoli del server da assegnare al server locale, separati da virgole.</p>
<p>I tipi di ruoli sono i seguenti:</p>
<p><strong>All</strong></p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/JJ219448.important(Office.15).gif" title="Importante" alt="Importante" /><strong>Importante:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>È consigliabile che in tutti i server di una farm di server Office Web Apps vengano eseguiti tutti i ruoli. L'assegnazione di ruoli non si rivela utile finché nella farm di server Office Web Apps non sono contenuti circa 50 server.</td>
</tr>
</tbody>
</table>

</div></td>
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

\------------------ESEMPIO 1---------------------

    (Get-OfficeWebAppsFarm).Machines

In questo esempio vengono mostrati i ruoli di ogni server della farm di server Office Web Apps.

\------------------ESEMPIO 2---------------------

    Set-OfficeWebAppsMachine -Roles FrontEnd

In questo esempio il server corrente viene configurato come server front-end.

\------------------ESEMPIO 3---------------------

    Set-OfficeWebAppsMachine -Roles All

In questo esempio il server corrente viene configurato in modo da ospitare tutti i ruoli.

## Vedere anche


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

