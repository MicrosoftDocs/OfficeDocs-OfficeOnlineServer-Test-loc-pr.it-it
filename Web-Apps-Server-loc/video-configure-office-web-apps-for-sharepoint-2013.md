---
title: 'Video: Configurare Office Web Apps per SharePoint 2013'
TOCTitle: 'Video: Configurare Office Web Apps per SharePoint 2013'
ms:assetid: 0c02633f-3839-448b-ae83-24f24c254179
ms:mtpsurl: https://technet.microsoft.com/it-it/library/Dn455088(v=office.15)
ms:contentKeyID: 59152168
ms.date: 12/23/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Video: Configurare Office Web Apps per SharePoint 2013

 

_**Si applica a:**Office Web Apps, Office Web Apps Server, SharePoint Foundation 2013, SharePoint Server 2013_

_**Ultima modifica dell'argomento:**2016-12-16_

**Riepilogo:** illustra nel dettaglio i nove passaggi principali da eseguire per configurare una farm di server di Office Web Apps che funzioni con SharePoint 2013.

Configurare Office Web Apps per SharePoint 2013 è piuttosto semplice. Questo video illustra come impostare il server Office Web Apps e configurare SharePoint 2013 per l'uso del server Office Web Apps in un ambiente di testing.


**Guardare il video sulla configurazione di Office Web Apps per SharePoint 2013.**

> [!VIDEO https://www.microsoft.com/it-it/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

Il video illustra procedure che vengono eseguite in due server: il server che esegue il server Office Web Apps e quello che esegue SharePoint 2013. Devono sempre essere due server distinti, come illustrato in [Software, hardware, and configuration requirements for Office Web Apps Server](plan-office-web-apps-server.md).

**Nel server che esegue server Office Web Apps il video mostra come:**

1\. Aprire il prompt dei comandi di Windows PowerShell e installare i ruoli e i servizi necessari per server Office Web Apps. Vedere [Prepare servers to run Office Web Apps Server](deploy-office-web-apps-server.md). Questa operazione è necessaria perché server Office Web Apps non verrà installato se i ruoli e i servizi richiesti non sono presenti.  
2\. Installare il software server Office Web Apps dal [Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/p/?linkid=256561). Per scaricare server Office Web Apps è necessario disporre di una licenza nell'ambito di un contratto multilicenza per Office Professional Plus 2013, Office Standard 2013 o Office per Mac 2011. L'opzione di download è disponibile sotto questi prodotti di Office nel portale VLSC.  
3\. Creare la farm di server Office Web Apps usando [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).  
4\. Verificare che la farm di server Office Web Apps sia stata creata correttamente aprendo una finestra del browser e accedendo alla pagina http://*ServerName*/hosting/discovery.

**Nel server che esegue SharePoint 2013 il video mostra come:**

5\. Aprire la Shell di gestione di SharePoint 2013.  
6\. Creare il binding tra il server Office Web Apps e SharePoint 2013 usando [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps). Questo consente di stabilire la comunicazione tra il server che esegue SharePoint 2013 e quello che esegue il server Office Web Apps.  
7\. Visualizzare l'area WOPI di SharePoint 2013 usando [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps). Questo passaggio evidenzia il fatto che i due server usano aree WOPI diverse: SharePoint 2013 usa internal-https, mentre il server Office Web Apps usa internal-http. Per il funzionamento corretto di Office Web Apps, l'area deve corrispondere.  
8\. Modificare l'area WOPI per SharePoint 2013 usando [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps) per cambiare l'area WOPI in internal-http.  
9\. Verificare il funzionamento corretto di Office Web Apps aprendo un documento di Office in una raccolta documenti di SharePoint 2013.

Per altre informazioni sui singoli passaggi, vedere le sezioni seguenti negli articoli [Distribuire il server Office Web Apps](deploy-office-web-apps-server.md) e [Configurare Office Web Apps per l'uso con SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

  - [Prepare servers to run Office Web Apps Server](deploy-office-web-apps-server.md)

  - [Deploy a single-server Office Web Apps Server farm that uses HTTP](deploy-office-web-apps-server.md)

  - [Before you configure SharePoint 2013 to use Office Web Apps Server](configure-office-web-apps-for-sharepoint-2013.md)

  - [In a test environment that uses HTTP](configure-office-web-apps-for-sharepoint-2013.md)

## Vedere anche


[Guida di orientamento al contenuto per il server Office Web Apps](content-roadmap-for-office-web-apps-server.md)  
[Pianificare Office Web Apps (utilizzato con SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
[Funzionamento di Office Web Apps in locale con SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

