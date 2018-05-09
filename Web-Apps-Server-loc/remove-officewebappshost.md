---
title: Remove-OfficeWebAppsHost
TOCTitle: Remove-OfficeWebAppsHost
ms:assetid: d0f7b5c2-da0f-421a-8478-c39b247c3ac5
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219453(v=office.15)
ms:contentKeyID: 49652294
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsHost

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-09_

Rimuove un dominio host dall'elenco Consenti di una farm di server Office Web Apps.

## Sintassi

    Remove-OfficeWebAppsHost -Domain <String>

## Descrizione dettagliata

Il cmdlet **Remove-OfficeWebAppsHost** rimuove dall'elenco Consenti il dominio host specificato. Nell'elenco Consenti sono contenuti i domini host per cui server Office Web Apps consente richieste di operazioni su file.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219453.Caution(Office.15).gif" title="Attenzione" alt="Attenzione" /><strong>Attenzione:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se non sono contenuti domini nell'elenco Consenti, server Office Web Apps consentirà le richieste di file per gli host di qualsiasi dominio. Non lasciare vuoto questo elenco se la farm di server Office Web Apps è accessibile da Internet, altrimenti chiunque potrà utilizzare la farm di server Office Web Apps per visualizzare e modificare il contenuto.</td>
</tr>
</tbody>
</table>


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
<td><p><strong>Domain</strong></p></td>
<td><p>Obbligatorio</p></td>
<td><p>System.String</p></td>
<td><p>Specifica il dominio host da rimuovere dall'elenco Consenti.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    Remove-OfficeWebAppsHost -domain "contoso.com"

In questo esempio viene rimosso il dominio contoso.com dall'elenco Consenti.

## Vedere anche


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Get-OfficeWebAppsHost](get-officewebappshost.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

