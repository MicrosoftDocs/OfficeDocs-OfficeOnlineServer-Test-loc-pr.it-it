---
title: Get-OfficeWebAppsFarm
TOCTitle: Get-OfficeWebAppsFarm
ms:assetid: 1f0704e1-a41d-40e6-a31b-08b1926ce811
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219434(v=office.15)
ms:contentKeyID: 49652258
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsFarm

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2013-12-18_

Restituisce informazioni dettagliate sull'oggetto OfficeWebAppsFarm di cui è membro il server corrente.

## Sintassi

    Get-OfficeWebAppsFarm

## Descrizione dettagliata

Il cmdlet **Get-OfficeWebAppsFarm** restituisce informazioni dettagliate sull'oggetto OfficeWebAppsFarm di cui è membro il server corrente. Questo oggetto rappresenta un gruppo di server che funzionano come singola unità per consentire la modifica e la visualizzazione di documenti di Office dal Web. Non vengono utilizzati parametri con il cmdlet **Get-OfficeWebAppsFarm**.

## Parametri

## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    Get-OfficeWebAppsFarm

In questo esempio vengono restituite informazioni dettagliate sull'oggetto OfficeWebAppsFarm.

\------------------ESEMPIO 2---------------------

    (Get-OfficeWebAppsFarm).Machines

In questo esempio vengono restituite informazioni dettagliate sui server membri della farm di server Office Web Apps. Tra queste informazioni dettagliate sono inclusi lo stato di integrità e i ruoli di ogni server.

## Vedere anche


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

