---
title: "Cloud App Security 網路需求 | Microsoft Docs"
description: "本主題說明要使用 Cloud App Security 時，必須開啟的 IP 位址與連接埠。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dac230e191c7c2d8159a2f373e6ef939fdd841a4
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2017
---
# <a name="network-requirements"></a>網路需求

本主題會提供一份連接埠與 IP 位址的清單，若您要使用 Cloud App Security，就必須予以允許並新增至白名單。 


## <a name="portal-access"></a>入口網站存取權

若要存取入口網站，請務必將下列 IP 位址新增至防火牆的白名單中，以提供 Cloud App Security 入口網站的存取權：  
  
104.42.231.28  


## <a name="app-connector-access"></a>應用程式連接器存取權

若要讓 Cloud App Security 存取某些協力廠商應用程式，就必須將下列 IP 位址新增至白名單，以讓 Cloud App Security 能夠收集記錄與提供 Cloud App Security 主控台的存取權：  
  
104.209.35.177  
13.91.98.185 40.118.211.172 13.93.216.68 13.91.61.249 13.93.233.42 13.64.196.27 13.64.198.97 13.64.199.41 13.64.198.19

> [!NOTE]
>因為 Cloud App Security 會從這些 IP 位址執行治理動作與掃描，所以您會在廠商的活動記錄中看到這些 IP 位址。 
  

## <a name="siem-agent-and-log-collector"></a>SIEM 代理程式與記錄收集器

若要讓 Cloud App Security 能夠連線至 SIEM，以及讓 Cloud App Security 記錄收集器能夠執行，就必須開啟：

- 輸出連接埠 443 至 104.42.231.28

## <a name="external-dlp-integration"></a>外部 DLP 整合

為了讓 Cloud App Security 透過 Stunnel 將資料傳送至 ICAP 伺服器，請使用動態來源連接埠號碼將 DMZ 防火牆開啟到 Cloud App Security 所使用的外部 IP 位址。 

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
  

   