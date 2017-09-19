---
title: "Cloud App Security 網路需求 | Microsoft Docs"
description: "本主題說明要使用 Cloud App Security 時，必須開啟的 IP 位址與連接埠。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 82bdda2ab26fa1c954edb5186eeb37d909d65e64
ms.sourcegitcommit: d012fc1a099773bd9e9dc61906faab68dae0e996
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2017
---
# <a name="network-requirements"></a>網路需求

本主題會提供一份連接埠與 IP 位址的清單，若您要使用 Cloud App Security，就必須予以允許並列入白名單。 

如需如何查看要連線的目標 Cloud App Security 資料中心，請參閱 [API 權杖](api-tokens.md)



## <a name="portal-access-siem-agent-authentication-gateway-and-log-collector"></a>入口網站存取權、SIEM 代理程式、驗證閘道及記錄收集器

若要獲得入口網站及驗證閘道存取權、允許 Cloud App Security 連線到您的 SIEM，以及讓 Cloud App Security 記錄收集器執行，您必須將下列 IP 位址的**輸出連接埠 443** 新增到您的防火牆白名單中：  


> [!div class="mx-tableFixed"]
|資料中心|IP 位址|  
|----|----|
|US1|13.91.91.243<br></br>52.183.75.62|
|EU1|52.174.56.180<br></br>13.80.125.22|

## <a name="app-connector-access-and-external-dlp-integration"></a>應用程式連接器存取權及外部 DLP 整合

若要連線到協力廠商應用程式以及與外部 DLP 解決方案整合，請允許 Cloud App Security 連線到這些 IP 位址：


> [!div class="mx-tableFixed"]
|資料中心|IP 位址|  
|----|----|
|US1|104.209.35.177<br></br>13.91.98.185<br></br>40.118.211.172<br></br>13.93.216.68<br></br>13.91.61.249<br></br>13.93.233.42<br></br>13.64.196.27<br></br>13.64.198.97<br></br>13.64.199.41<br></br>13.64.198.19|
|EU1|13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|


### <a name="app-connector"></a>應用程式連接器
若要讓 Cloud App Security 存取某些協力廠商應用程式，就必須使用這些 IP 位址，讓 Cloud App Security 能夠收集記錄與提供 Cloud App Security 主控台的存取權。 

> [!NOTE]
>因為 Cloud App Security 會從這些 IP 位址執行治理動作與掃描，所以您會在廠商的活動記錄中看到這些 IP 位址。 
  

### <a name="dlp-integration"></a>DLP 整合

為了讓 Cloud App Security 透過 Stunnel 將資料傳送至 ICAP 伺服器，請使用動態來源連接埠號碼向這些 IP 位址開放您的 DMZ 防火牆。 

1.  來源位址：這些位址應該如上述列在白名單中，才能使用 API 連接器協力廠商應用程式
2.  來源 TCP 連接埠：動態
3.  目的地位址：連線至外部 ICAP 伺服器的 Stunnel 一或兩個 IP 位址
4.  目的地 TCP 連接埠：如您網路中所定義

> [!NOTE] 
> Stunnel 連接埠號碼預設為 11344。 若有必要，您可以將其變更為另一個連接埠，但請務必記下新的連接埠號碼。


    



  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  

   