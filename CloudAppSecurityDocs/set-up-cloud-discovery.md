---
title: "部署 Cloud Discovery 與 Cloud App Security | Microsoft Docs"
description: "本主題描述用來啟動 Cloud Discovery 的設定程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d12fa44f42c5545464c7e8ba9da366a2302f73c1
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: zh-TW
---
# <a name="set-up-cloud-discovery"></a>設定 Cloud Discovery
Cloud Discovery 會分析您的流量記錄，而其分析依據是根據 50 個以上屬性進行排名和評分之 13,000 個雲端應用程式的 Cloud App Security 雲端應用程式目錄，以讓您持續取得雲端使用、Shadow IT 以及 Shadow IT 對組織造成之風險的可見度。
[雲端應用程式目錄] 會依據認證法規、業界標準和最佳做法來進行雲端應用程式的風險分級。 在雲端應用程式目錄中執行四種補充程序，以保持最新資訊︰
1.    直接從雲端應用程式進行自動化資料擷取 (適用於 SOC 2 相容性這類屬性)。
2.    透過 Cloud App Security 演算法之資料的自動化進階資料擷取 (適用於 HTTP 安全性標頭這類屬性)。
3.    Cloud App Security 雲端分析師團隊進行的連續分析 (適用於靜止加密這類屬性)。
4.    客戶型修訂要求 (根據雲端應用程式目錄變更的客戶提交要求)。 所有要求都是由雲端分析師團隊所檢閱，並根據其發現的項目進行更新。
  
## <a name="cloud-discovery-data-anonymization"></a>Cloud Discovery 資料匿名

Cloud Discovery 資料匿名可讓您保護使用者隱私權。 將資料記錄檔上傳至 Cloud App Security 入口網站之後，會妥善處理記錄檔，並將所有使用者名稱資訊取代為加密使用者名稱。 如此一來，所有雲端活動都會保持匿名。 如需詳細資訊，請參閱 [Cloud Discovery 匿名](cloud-discovery-anonymizer.md)。

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>快照集和連續風險評估報告 

您可以產生兩種類型的報告： 
- **快照集報告**提供一組手動從防火牆和 Proxy 上傳之流量記錄的臨機操作可見度。
 
- **連續報告**會使用 Cloud App Security 記錄收集器分析從您的網路轉寄的所有記錄。 它們提供所有資料的改良可見度，並且使用機器學習異常偵測引擎或使用您定義的自訂原則來自動找出異常使用。
 
## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>記錄程序流程︰從未經處理資料到風險評估  
產生風險評估的程序包含下列步驟，需時約幾分鐘到數小時，視處理的資料量而定。  
  
-   **上傳** – 來自您網路的 Web 流量記錄會上傳至入口網站。  
  
-   **剖析** – Cloud App Security 會使用針對每項資料來源的專用剖析器，剖析並擷取來自流量記錄的流量資料。  
  
-   **分析** – 依 Cloud App Catalog 分析流量資料來識別超過 13,000 種的雲端應用程式，並評估其風險評分。 使用中的使用者和 IP 位址也會被識別為分析的一部分。  
  
-   **產生報告** - 產生從記錄檔擷取之資料的風險評估報告。   
 
 
>[!NOTE]
>連續報告資料是一天分析兩次。
 
## <a name="using-traffic-logs-for--cloud-discovery"></a>使用 Cloud Discovery 的流量記錄
Cloud Discovery 利用流量記錄中的資料。 記錄越詳細，可見度就越好。 Cloud Discovery 需要具有下列屬性的 Web 流量資料︰
- 交易日期
- 來源 IP
- 來源使用者 - 強烈建議
- 目的地 IP 位址
- **建議使用**目的地 URL (URL 所提供的雲端應用程式偵測正確性高於 IP 位址)
- 資料總量 (資料資訊很有價值)
- 上傳或下載的資料量 (了解雲端應用程式的使用模式)
- 採取的動作 (允許/封鎖)
 
Cloud Discovery 無法顯示或分析記錄中未包含的屬性。
例如，「Cisco ASA 防火牆」標準記錄格式未包含「每筆交易的上傳位元組數」和「使用者名稱」，而且未包含「目標 URL」 (但僅限目標 IP)。
因此，在這些記錄的 Cloud Discovery 資料中不會顯示這些屬性，而且所看到的雲端應用程式會受到限制。 對於 Cisco ASA 防火牆，需要將資訊層級設定為 6。 
 

為了順利產生 Cloud Discovery 報告，您的流量記錄必須符合下列條件︰
1.  支援資料來源 (請參閱下方的清單)。
2.  記錄格式符合預期的標準格式 (記錄工具會在上傳時檢查這個項目)。
3.  事件未超過 90 天。
4.  記錄檔有效，並且包含輸出流量資訊。
 
## <a name="supported-firewalls-and-proxies"></a>支援的防火牆和 Proxy

- Barracuda - Web 應用程式防火牆 (W3C)
- Blue Coat Proxy SG - 存取記錄 (W3C)
- Check Point
- Cisco ASA 防火牆 (對於 Cisco ASA 防火牆，需要將資訊層級設定為 6)
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki - URL 記錄
- Clavister NGFW (Syslog)
- Dell Sonicwall
- Fortinet Fortigate
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto 系列防火牆
- Sophos SG
- Sophos Cyberoam
- Squid (一般)
- Squid (原生)
- Websense - 網站安全性解決方案 - 調查詳細資料報告 (CSV)
- Websense - 網站安全性解決方案 - 網際網路活動記錄 (CEF)
- Zscaler


如果您的記錄檔不受支援，請在 [資料來源] 中選取 [其他]，並指定您嘗試上傳的設備與記錄檔。 Cloud App Security 雲端分析師團隊將會檢閱您的記錄，而且會在新增您記錄類型支援時通知您。 或者，您可以定義符合您格式的自訂剖析器。 如需詳細資訊，請參閱[使用自訂記錄檔剖析器](custom-log-parser.md)。


資料屬性 (根據廠商文件)：

|資料來源|目標應用程式 URL|目標應用程式 IP|Username|來源 IP|總流量|上傳的位元組|
|----|----|----|-----|----|----|----|
|Barracuda|**是**|**是**|**是**|**是**|否|否|
|Blue Coat|**是**|否|**是**|**是**|**是**|**是**|
|Checkpoint|否|**是**|否|**是**|否|否|
|Cisco ASA|否|**是**|否|**是**|**是**|否|
|Cisco FWSM|否|**是**|否|**是**|**是**|否|
|Cisco Ironport WSA|**是**|**是**|**是**|**是**|**是**|**是**|
|Cisco Meraki|**是**|**是**|否|**是**|否|否||Cisco Scansafe|**是**|否|**是**|**是**|**是**|**是**|
|Clavister NGFW (Syslog)|**是**|**是**|**是**|**是**|**是**|**是**|
|Dell SonicWall|**是**|**是**|否|**是**|**是**|**是**|
|Fortigate|否|**是**|否|**是**|**是**|**是**|
|Juniper SRX|否|**是**|否|**是**\**|**是**|**是**|
|Juniper SSG|否|**是**|否|**是**|**是**|**是**|
|McAfee SWG|**是**|否|否|**是**|**是**|**是**|
|MS TMG|**是**|否|**是**|**是**|**是**|**是**|
|Palo Alto Networks|**是**|**是**|**是**|**是**\*|**是**|**是**|
|Sophos|**是**|**是**|**是**|**是**|**是**|否|
|Websense - 調查詳細資料報告 (CSV)|**是**|否|否|**是**|否|否|
|Websense - 網際網路活動記錄 (CEF)|**是**|**是**|**是**|**是**|**是**|**是**|
|Zscaler|**是**|否|**是**|否|**是**|**是**|

\* Cloud Discovery 支援 IPv6。

## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)