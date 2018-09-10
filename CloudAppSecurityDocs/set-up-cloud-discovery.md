---
title: 使用 Cloud App Security 部署 Cloud Discovery | Microsoft Docs
description: 本主題描述用來啟動 Cloud Discovery 的設定程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/15/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 805cb008b60d3ab74119d15e4e24944fe82c8bd7
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144511"
---
*適用於：Microsoft Cloud App Security*


# <a name="set-up-cloud-discovery"></a>設定 Cloud Discovery
Cloud Discovery 會依據 Microsoft Cloud App Security 雲端應用程式目錄分析您的流量記錄，此目錄內含 16,000 個以上的雲端應用程式，並會根據 70 個以上的風險因素 加以排名和評分，這可讓您持續掌握雲端使用情況、Shadow IT 以及 Shadow IT 對組織造成的風險。

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>快照集和連續風險評估報告 

您可以產生兩種類型的報告： 
- **快照集報告**提供一組手動從防火牆和 Proxy 上傳之流量記錄的臨機操作可見度。

- **連續報告**會使用 Cloud App Security 記錄收集器分析從您的網路轉寄的所有記錄。 它們提供所有資料的改良可見度，並且使用機器學習異常偵測引擎或使用您定義的自訂原則來自動找出異常使用。

## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>記錄程序流程︰從未經處理資料到風險評估  
產生風險評估的程序包含下列步驟，需時約幾分鐘到數小時，視處理的資料量而定。  

-   **上傳** – 來自您網路的 Web 流量記錄會上傳至入口網站。  

-   **剖析** – Cloud App Security 會使用針對每項資料來源的專用剖析器，剖析並擷取來自流量記錄的流量資料。  

-   **分析** – 依雲端應用程式目錄分析流量資料來識別 16,000 個以上的雲端應用程式，並評定其風險分數。 使用中的使用者和 IP 位址也會被識別為分析的一部分。  

-   **產生報告** - 產生從記錄檔擷取之資料的風險評估報告。   


>[!NOTE]
>- 連續報告資料是一天分析兩次。
>- 記錄收集器會先壓縮資料，然後再上傳。 記錄收集器的輸出流量將會是所收到流量記錄大小的 10%。 

## <a name="using-traffic-logs-for-cloud-discovery"></a>Cloud Discovery 的流量記錄使用
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
例如，**Cisco ASA 防火牆**標準記錄格式未包含**每筆交易的上傳位元組數**和**使用者名稱**，而且未包含**目標 URL** (但僅限目標 IP)。
因此，在這些記錄的 Cloud Discovery 資料中不會顯示這些屬性，而且所看到的雲端應用程式會受到限制。 對於 Cisco ASA 防火牆，需要將資訊層級設定為 6。 


為了順利產生 Cloud Discovery 報告，您的流量記錄必須符合下列條件︰
1.  支援資料來源 (請參閱下方的清單)。
2.  記錄格式符合預期的標準格式 (記錄工具會在上傳時檢查這個項目)。
3.  事件未超過 90 天。
4.  記錄檔有效，並且包含輸出流量資訊。



## 支援的防火牆和 Proxy <a name="supported-firewalls-and-proxies"></a>

- Barracuda - Web 應用程式防火牆 (W3C)
- Blue Coat Proxy SG - 存取記錄 (W3C)
- Check Point
- Cisco ASA 防火牆 (對於 Cisco ASA 防火牆，需要將資訊層級設定為 6)
- Cisco ASA with FirePOWER
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki - URL 記錄
- Clavister NGFW (Syslog)
- Dell Sonicwall
- Digital Arts i-FILTER
- Fortinet Fortigate
- iboss Secure Cloud Gateway
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto 系列防火牆
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid (一般)
- Squid (原生)
- Websense - 網站安全性解決方案 - 調查詳細資料報告 (CSV)
- Websense - 網站安全性解決方案 - 網際網路活動記錄 (CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery 支援 IPv4 和 IPv6 兩種位址。

如果您的記錄檔不受支援，請在 [資料來源] 中選取 [其他]，並指定您嘗試上傳的設備與記錄檔。 Cloud App Security 雲端分析師團隊將會檢閱您的記錄，而且會在新增您記錄類型支援時通知您。 或者，您可以定義符合您格式的自訂剖析器。 如需詳細資訊，請參閱[使用自訂記錄檔剖析器](custom-log-parser.md)。


資料屬性 (根據廠商文件)：


|                 資料來源                  |    目標應用程式 URL    |    目標應用程式 IP     |       Username       |      來源 IP       |    總流量     |    上傳的位元組    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          否          |          否          |
|                  Blue Coat                   | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Checkpoint                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> |          否          |          否          |
|              Cisco ASA (Syslog)              |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          |
|           Cisco ASA with FirePOWER           | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Cisco FWSM                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          |
|              Cisco Ironport WSA              | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Cisco Meraki                 | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |          否          |          否          |
|           Clavister NGFW (Syslog)            | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                Dell SonicWall                | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|            Digital Arts i-FILTER             | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Fortigate                   |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SRX                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Juniper SSG                  |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  McAfee SWG                  | <strong>是</strong> |          否          |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    MS TMG                    | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|              Palo Alto Networks              |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    Sophos                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          否          |
|                Squid (一般)                | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |
|                Squid (原生)                | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |
| Websense - 調查詳細資料報告 (CSV) | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|    Websense - 網際網路活動記錄 (CEF)    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                   Zscaler                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |

## <a name="see-also"></a>另請參閱

[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)