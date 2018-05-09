---
title: Get-OfficeWebAppsMachine
TOCTitle: Get-OfficeWebAppsMachine
ms:assetid: 02fadf5e-0382-4e73-8d07-e67d088b1a02
ms:mtpsurl: https://technet.microsoft.com/it-it/library/JJ219432(v=office.15)
ms:contentKeyID: 49652256
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsMachine

 

_**Si applica a:**Office Web Apps Server_

_**Ultima modifica dell'argomento:**2013-12-18_

Restituisce informazioni dettagliate sul server corrente incluso in una farm di server Office Web Apps.

## Sintassi

    Get-OfficeWebAppsMachine

## Descrizione dettagliata

Il cmdlet **Get-OfficeWebAppsMachine** restituisce informazioni dettagliate sul server corrente incluso in una farm di server Office Web Apps. Tra queste informazioni dettagliate sono inclusi i ruoli e lo stato di integrità del server corrente, nonché il nome del server master della farm.

## Parametri

## Tipi di input

## Tipi restituiti

## Esempio

\------------------ESEMPIO 1---------------------

    Get-OfficeWebAppsMachine

In questo esempio vengono restituite informazioni dettagliate sul server corrente incluso in una farm di server Office Web Apps.

\------------------ESEMPIO 2---------------------

    (Get-OfficeWebAppsFarm).Machines

In questo esempio vengono restituite informazioni dettagliate su tutti i server inclusi in una farm di server Office Web Apps.

## Vedere anche


[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Distribuire l'infrastruttura: Server Office Web Apps](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

