---
title: New-OfficeWebAppsHost
TOCTitle: New-OfficeWebAppsHost
ms:assetid: f1d523ab-45c6-4e3c-b274-22c0d229a6a0
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219459(v=office.15)
ms:contentKeyID: 49652305
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsHost

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2015-03-09_

Aggiunge un dominio host all'elenco Consenti di una farm di server Office Web Apps.

## Sintassi

    New-OfficeWebAppsHost -Domain <String>

## Descrizione dettagliata

Il cmdlet **New-OfficeWebAppsHost** aggiunge un dominio host all'elenco di domini host a cui server Office Web Apps consente richieste di operazioni su file, ad esempio il recupero di file o metadati e le modifiche di file. Questo elenco Consenti è una funzionalità di sicurezza che impedisce a host indesiderati di connettersi a una farm di server Office Web Apps e utilizzarla per operazioni su file all'insaputa dell'utente.

<table>
<thead>
<tr class="header">
<th><img src="images/JJ219455.tip(Office.15).gif" title="Suggerimento" alt="Suggerimento" /><strong>Suggerimento:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>È possibile utilizzare qualsiasi tipo di dominio, inclusi i nomi di dominio Public, Pool, Farm e Active Directory. È opportuno assicurarsi che il dominio a cui si consente l'accesso soddisfi i requisiti di sicurezza specifici.</td>
</tr>
</tbody>
</table>


Per ogni dominio aggiunto all'elenco Consenti si presuppone l'utilizzo del carattere jolly \* in modo che vengano consentite le richieste per tutti i sottodomini. Se ad esempio si aggiunge all'elenco Consenti il dominio contoso.com, server Office Web Apps consentirà le richieste anche per i domini corp.contoso.com e dev.contoso.com. Le richieste per altri domini, ad esempio fabrikam.com, non saranno consentite.

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
<td><p>Specifica il dominio da aggiungere all'elenco Consenti. Non specificare un asterisco né iniziare con un punto.</p></td>
</tr>
</tbody>
</table>


## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    New-OfficeWebAppsHost -domain "contoso.com"

In questo esempio viene aggiunto il dominio contoso.com all'elenco Consenti.


> [!NOTE]
> Non è possibile aggiungere più domini host tutti contemporaneamente all'elenco Consenti. È necessario eseguire il cmdlet New-OfficeWebAppsHost per ogni dominio host da aggiungere all'elenco Consenti.



## Vedere anche


[Get-OfficeWebAppsHost](get-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

