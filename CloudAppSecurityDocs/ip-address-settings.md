---
title: "連接應用程式以取得對 Cloud App Security 的深入可見度及控制 | Microsoft Docs"
description: "本主題描述使用 API 連接器將應用程式連接到您組織的雲端應用程式之過程。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/3/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7e718d77-aae7-4a3a-8421-5ba7cee7d67c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8c9b63f4265876fc1de6a24c6576f917f9d2278
ms.sourcegitcommit: a0290ac2a662994f7771975ef6c20d0b47e9edd8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2017
---
Cloud App Security 需要如下進行存取，才能連線至您的網路。 

## <a name="cloud-app-security-system-ip-addresses"></a>Cloud App Security 系統 IP 位址

Cloud App Security 使用下列 IP 位址來連線至客戶環境。 使用 [ICAP](icap-stunnel.md) 連線時，以及連線應用程式連接器時，這是必要項目。 對於某些應用程式，可能需要將下列 IP 位址新增至白名單，讓 Cloud App Security 能收集記錄檔，並提供 Cloud App Security 主控台的存取權。 在某些應用程式中，這些 IP 位址也可以用來識別 Cloud App Security 活動，例如，在服務稽核記錄檔中。 
  
-   針對記錄檔︰  
  
    104.209.35.177  
  
    13.91.98.185
 
    40.118.211.172

    13.93.216.68

    13.91.61.249

    13.93.233.42

    13.64.196.27

    13.64.198.97

    13.64.199.41

    13.64.198.19
  
  
## <a name="cas-portal-url-and-ip-addresses"></a>CAS 入口網站 URL 和 IP 位址

Cloud App Security URL、連接埠 443 和 IP 位址是讓客戶用來存取入口網站、連線至 CAS API 時的 API 連線、記錄收集器和 SIEM 代理程式。 
  
     104.42.231.28  

 
  
> [!NOTE]  
>  若要在 URL 和 IP 位址變更時取得更新，請訂閱 RSS，如 [Office 365 URL 與 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)中所述。  
  

  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  

   