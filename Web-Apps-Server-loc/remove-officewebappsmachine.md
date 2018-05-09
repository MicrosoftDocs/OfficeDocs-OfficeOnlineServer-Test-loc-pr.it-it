---
title: Remove-OfficeWebAppsMachine
TOCTitle: Remove-OfficeWebAppsMachine
ms:assetid: 5ad806f2-67c6-41ed-a708-69db800f492a
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219440(v=office.15)
ms:contentKeyID: 49652269
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsMachine

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-09_

Rimuove il server corrente dalla farm di server Office Web Apps.

## Sintassi

    Remove-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Descrizione dettagliata

Il cmdlet **Remove-OfficeWebAppsMachine** rimuove il server corrente dalla farm di server Office Web Apps. Nell'ambito di questo processo il cmdlet rimuove le applicazioni Web e arresta i servizi correlati a server Office Web Apps. Se non è possibile eseguire il cmdlet **Remove-OfficeWebAppsMachine** dal server che si desidera rimuovere, utilizzare il cmdlet **Repair-OfficeWebAppsFarm** da qualsiasi altro server della farm di Office Web Apps.


> [!NOTE]
> Se il server locale è designato come server master nella farm di server Office Web Apps, non è possibile rimuoverlo dalla farm finché non viene assegnato un altro server come master utilizzando il cmdlet <STRONG>Set-OfficeWebAppsMachine</STRONG> oppure finché non vengono rimossi tutti gli altri server dalla farm.



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

    Remove-OfficeWebAppsMachine

In questo esempio viene rimosso il server corrente dalla farm di server Office Web Apps.

## Vedere anche


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

