---
title: 設定自動記錄檔上傳以進行連續報告 | Microsoft Docs
description: 本主題說明在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/11/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: bb540bd24052d63eae44f5c936a7a6631af16986
ms.sourcegitcommit: 3177ffcbdabbddc6c758e9a1994fb21fde939ffc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2018
ms.locfileid: "35259554"
---
*適用於：Microsoft Cloud App Security*


# <a name="configure-automatic-log-upload-for-continuous-reports"></a>設定自動記錄檔上傳以進行連續報告


記錄收集器可讓您輕鬆地從網路自動上傳記錄檔。 記錄收集器會在您的網路上執行，透過 Syslog 或 FTP 接收記錄檔。 每個記錄檔都會自動處理、壓縮和傳送至入口網站。 檔案將 FTP 轉送至記錄收集器完畢後，FTP 記錄會上傳至 Microsoft Cloud App Security。  若是 Syslog 機制，記錄收集器會將接收到的記錄檔寫入磁碟，並將大小大於 40 KB 的檔案上傳至 Cloud App Security。

記錄檔上傳到 Cloud App Security 之後會移至備份目錄，其中儲存了任何指定時間的最後 20 個記錄檔。 每次有新的記錄檔抵達，就會刪除舊的記錄檔。 當記錄收集器磁碟空間已滿時，記錄收集器會在有更多可用磁碟空間之前卸除新的記錄檔。 發生這種情況時，您會在 [自動上傳記錄檔] 設定的 [記錄收集器] 索引標籤上收到警告。

在設定自動收集記錄檔之前，請確認您的記錄檔與預期記錄檔類型相符，以確保 Cloud App Security 可以剖析特定檔案。

> [!NOTE]
>-  Cloud App Security 支援將記錄檔從 SIEM 伺服器轉送到記錄檔收集器，假設記錄檔是以原始格式轉送。 不過，強烈建議您直接整合記錄收集器與防火牆及 (或) Proxy。
>- 記錄收集器會先壓縮資料，然後再上傳。 記錄收集器的輸出流量將會是所收到流量記錄大小的 10%。 

## <a name="deployment-modes"></a>部署模式

記錄收集器支援兩種部署模式：

-   **容器**：在[內部部署的 Ubuntu](discovery-docker-ubuntu.md)、[Azure 中的 Ubuntu](discovery-docker-ubuntu-azure.md) 或[內部部署的 RHEL](discovery-docker-ubuntu.md) 上以 Docker 映像的形式執行。 

-   **虛擬設備**：[在 HYPER-V 或 VMware Hypervisor 上以映像形式執行](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

