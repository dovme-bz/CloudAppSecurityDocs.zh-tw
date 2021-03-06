---
title: Cloud App Security 網路需求 | Microsoft Docs
description: 本主題說明要使用 Cloud App Security 時，必須開啟的 IP 位址與連接埠。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9bc1064b28a8d7781718f121a0f64bd9cfa97395
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144307"
---
*適用於：Microsoft Cloud App Security*


# <a name="network-requirements"></a>網路需求

本主題會提供一份連接埠與 IP 位址的清單，若您要使用 Microsoft Cloud App Security，就必須予以允許並列入允許清單。 


## <a name="view-your-data-center"></a>檢視您的資料中心

以下某些需求會隨您連接的資料中心而異。 

查看您連接的資料中心：

1. 在 Cloud App Security 入口網站中，按一下 **?** 再選取 [關於]。 

    ![按一下 [關於]](./media/about-menu.png)

2. 您可以在 Cloud App Security 的版本畫面中看到地區及資料中心。

    ![檢視您的資料中心](./media/data-center.png)

## <a name="portal-access"></a>入口網站存取權

如要存取 Cloud App Security 入口網站，請將下列 IP 位址和 DNS 名稱的**輸出連接埠 443**新增到您的防火牆允許清單：  


> [!div class="mx-tableFixed"]
> 
> |資料中心|IP 位址|DNS 名稱|
> |----|----|----|
> |美國|13.80.125.22<br></br>52.183.75.62<br></br>13.91.91.243|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.us.portal.cloudappsecurity.com<br></br>cdn.cloudappsecurity.com|
> |US2|13.80.125.22<br></br>52.183.75.62<br></br>52.184.165.82|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.us2.portal.cloudappsecurity.com<br></br>cdn.cloudappsecurity.com|
> |US3|13.80.125.22<br></br>52.183.75.62<br></br>40.90.218.198<br></br>40.90.218.196|portal.cloudappsecurity.com<br></br>*.portal.cloudappsecurity.com <br></br>*.us3.portal.cloudappsecurity.com<br></br>cdn.cloudappsecurity.com|
> |EU|13.80.125.22<br></br>52.183.75.62<br></br>52.174.56.180|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.eu.portal.cloudappsecurity.com<br></br>cdn.cloudappsecurity.com|
> |EU2|13.80.125.22<br></br>52.183.75.62<br></br>40.81.156.154<br></br>40.81.156.156|portal.cloudappsecurity.com<br></br>*.portal.cloudappsecurity.com <br></br>*.eu2.portal.cloudappsecurity.com<br></br>cdn.cloudappsecurity.com|


> 
> [!NOTE]
> 而不是只能開啟您特定租用戶 URL 的萬用字元 (\*)；例如，根據上文中的螢幕擷取畫面，您可以開啟：mod244533.us.portal.cloudappsecurity.com

## <a name="siem-agent-connection"></a>SIEM 代理程式連線

若要讓 Cloud App Security 連線到 SIEM，請將下列 IP 位址的**輸出連接埠 443**新增到您的防火牆允許清單：  


> [!div class="mx-tableFixed"]
> 
> |資料中心|IP 位址|  
> |----|----|
> |美國|13.91.91.243|
> |US2|52.184.165.82|
> |US3|40.90.218.198<br>40.90.218.196|
> |EU|52.174.56.180|
> |EU2|40.81.156.154<br>40.81.156.156|

## <a name="app-connector"></a>應用程式連接器

若要讓 Cloud App Security 存取某些協力廠商應用程式，就必須使用這些 IP 位址，讓 Cloud App Security 能夠收集記錄與提供 Cloud App Security 主控台的存取權。 

> [!NOTE]
>因為 Cloud App Security 會從這些 IP 位址執行治理動作與掃描，所以您會在廠商的活動記錄中看到這些 IP 位址。 

若要連線到協力廠商應用程式，請允許 Cloud App Security 從這些 IP 位址進行連線：


> [!div class="mx-tableFixed"]
> 
> |資料中心|IP 位址|  
> |----|----|
> |美國|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|


## <a name="third-party-dlp-integration"></a>協力廠商的 DLP 整合

為了讓 Cloud App Security 透過 Stunnel 將資料傳送至 ICAP 伺服器，請使用動態來源連接埠號碼向這些 IP 位址開放您的 DMZ 防火牆。 

1.  來源位址：這些位址應該如上述列在允許清單中，才能使用 API 連接器協力廠商應用程式
2.  來源 TCP 連接埠：動態
3.  目的地位址：連線至外部 ICAP 伺服器的 Stunnel 一或兩個 IP 位址
4.  目的地 TCP 連接埠：如您網路中所定義

> [!NOTE] 
> -  Stunnel 連接埠號碼預設為 11344。 若有必要，您可以將其變更為另一個連接埠，但請務必記下新的連接埠號碼。
> - 因為 Cloud App Security 會從這些 IP 位址執行治理動作與掃描，所以您會在廠商的活動記錄中看到這些 IP 位址。 

若要連線到協力廠商應用程式與外部 DLP 解決方案整合，請允許 Cloud App Security 從這些 IP 位址進行連線：

> [!div class="mx-tableFixed"]
> 
> |資料中心|IP 位址|  
> |----|----|
> |美國|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|

## <a name="mail-server"></a>郵件伺服器

若要透過預設範本和設定傳送通知，請將這些 IP 位址新增至您的反垃圾郵件允許清單。 Cloud App Security 的專用電子郵件 IP 位址為： 

- 65.55.234.192/26
- 207.46.200.0/27
- 65.55.52.224/27
- 94.245.112.0/27
- 111.221.26.0/27
- 207.46.50.192/26

如果您想要自訂電子郵件寄件者身分識別，Microsoft Cloud App Security 可讓您使用 MailChimp® (協力廠商電子郵件服務) 進行此作業。 若要進行此作業，請在 Microsoft Cloud App Security 入口網站的 [設定] 下，選取 [郵件設定]，並檢閱 MailChimp 的服務條款及隱私權聲明，然後提供允許 Microsoft 代表您使用 MailChimp 的權限。

如果您不這樣做，您的電子郵件通知將使用所有預設設定傳送。

若要使用 MailChimp，請將此 IP 位址加入至您的反垃圾郵件白名單以啟用傳送通知：198.2.134.139 (mail1.cloudappsecurity.com)


## <a name="log-collector"></a>記錄收集器 

若要啟用使用記錄收集器的 Cloud Discovery 功能並偵測組織中的影子 IT，必須開啟下列項目：

- 允許記錄收集器接收輸入的 FTP 和 Syslog 流量。
- 允許記錄收集器起始輸出流量至連接埠 443 上的入口網站 (例如 contoso.cloudappsecurity.com)。
- 允許記錄收集器在連接埠 80 和 443 上初始化往 Azure Blob 儲存體的輸出流量：


  | 資料中心 |                        URL                        |
  |-------------|---------------------------------------------------|
  |     美國      |   https://adaprodconsole.blob.core.windows.net/   |
  |     US2     | https://prod03use2console1.blob.core.windows.net/ |
  |     US3     |https://prod5usw2console1.blob.core.windows.net/   |
  |     EU      | https://prod02euwconsole1.blob.core.windows.net/  |
  |     EU2     |https://prod4uksconsole1.blob.core.windows.net/    |

> [!NOTE]
> - 如果您的防火牆要求靜態 IP 位址存取清單，且不支援以 URL 為基礎的允許清單，請允許記錄收集器在連接埠 443 上初始化針對 [Microsoft Azure 資料中心 IP 範圍](https://www.microsoft.com/download/details.aspx?id=41653)的輸出流量。
>- 允許記錄收集器初始化 Cloud App Security 入口網站的輸出流量。



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  

