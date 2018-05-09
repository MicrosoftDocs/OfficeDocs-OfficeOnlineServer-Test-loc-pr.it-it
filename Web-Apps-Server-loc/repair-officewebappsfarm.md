---
title: Repair-OfficeWebAppsFarm
TOCTitle: Repair-OfficeWebAppsFarm
ms:assetid: 083d8e25-ce82-4884-9bbc-06375185011c
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219433(v=office.15)
ms:contentKeyID: 49652257
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Repair-OfficeWebAppsFarm

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-09_

Rimuove da una farm di server Office Web Apps tutti i server contrassegnati come non integri.

## Sintassi

    Repair-OfficeWebAppsFarm [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Repair-OfficeWebAppsFarm** rimuove da una farm di server Office Web Apps tutti i server contrassegnati come non integri. Questo cmdlet aggiorna la topologia della farm, ma non elimina i servizi e le applicazioni Web dei server che vengono rimossi. Per questo motivo è consigliabile eseguire il cmdlet **Remove-OfficeWebAppsMachine** dai server non integri, in modo che vengano rimossi correttamente dalla farm. Utilizzare il cmdlet **Repair-OfficeWebAppsFarm** solo in caso di errore dei server non integri e qualora sia impossibile eseguire il cmdlet **Remove-OfficeWebAppsMachine** direttamente da tali server.

Se sono presenti più server non integri, verrà visualizzata una richiesta prima della rimozione di ogni server. Se invece non vi sono server non integri, questo cmdlet non eseguirà alcuna azione.

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
<td><p><strong>Force</strong></p></td>
<td><p>Facoltativo</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Presuppone che la risposta a qualsiasi richiesta utente sia affermativa.</p></td>
</tr>
<tr class="odd">
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

In questo esempio viene visualizzato lo stato di integrità di tutti i server della farm di server Office Web Apps.

\------------------ESEMPIO 2---------------------

    Repair-OfficeWebAppsFarm

In questo esempio vengono rimossi dalla farm di server Office Web Apps tutti i server non integri.

## Vedere anche


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

