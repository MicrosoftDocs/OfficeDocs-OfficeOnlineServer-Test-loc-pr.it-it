---
title: Get-OfficeWebAppsHost
TOCTitle: Get-OfficeWebAppsHost
ms:assetid: a9b766a7-a15c-4bbf-9750-31719406d65f
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219446(v=office.15)
ms:contentKeyID: 49652281
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsHost

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2013-12-18_

Restituisce l'elenco di domini host contenuti nell'elenco Consenti di una farm di server Office Web Apps.

## Sintassi

    Get-OfficeWebAppsHost

## Descrizione dettagliata

Il cmdlet **Get-OfficeWebAppsHost** restituisce l'elenco di domini host per i quali il server Office Web Apps consente richieste di operazioni su file, ad esempio il recupero di file o metadati e le modifiche di file. Questo elenco Consenti è una funzionalità di sicurezza che impedisce a host indesiderati di connettersi a una farm di server Office Web Apps e utilizzarla per operazioni su file all'insaputa dell'utente.

Per ogni dominio contenuto nell'elenco Consenti si presuppone l'utilizzo del carattere jolly \* in modo che vengano consentite le richieste per tutti i sottodomini. Se ad esempio nell'elenco Consenti è incluso il dominio contoso.com, il server Office Web Apps consentirà le richieste anche per i domini corp.contoso.com e dev.contoso.com. Le richieste per altri domini, ad esempio fabrikam.com, non saranno consentite.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219453.Caution(Office.15).gif" title="Attenzione" alt="Attenzione" /><strong>Attenzione:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se non sono contenuti domini nell'elenco Consenti, il server Office Web Apps consentirà le richieste di file per gli host di qualsiasi dominio. Non lasciare vuoto questo elenco se la farm di server Office Web Apps è accessibile da Internet, altrimenti chiunque potrà utilizzare la farm di server Office Web Apps per visualizzare e modificare il contenuto.</td>
</tr>
</tbody>
</table>


## Parametri

## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    Get-OfficeWebAppsHost

In questo esempio vengono restituiti i domini host contenuti nell'elenco Consenti.

## Vedere anche


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

