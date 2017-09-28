---
title: "設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題說明在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的流程。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f0f6f0de46e8833b4f4ffb6bd31c7c46eeacac9a
ms.sourcegitcommit: 13148ac82e496e8d4e0d10851e5d6e4f231229e4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2017
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>設定自動記錄檔上傳以進行連續報告


記錄收集器可讓您輕鬆地從網路自動上傳記錄檔。 記錄收集器會在您的網路上執行，透過 Syslog 或 FTP 接收記錄檔。 每個記錄檔都會自動處理、壓縮和傳送至入口網站。 檔案將 FTP 轉送至記錄收集器完畢後，FTP 記錄會上傳至 Cloud App Security。  若是 Syslog 機制，記錄收集器會將接收到的記錄檔寫入磁碟，並將大小大於 40 KB 的檔案上傳至 Cloud App Security。

記錄檔上傳到 Cloud App Security 之後會移至備份目錄，其中儲存了任何指定時間的最後 20 個記錄檔。 每次有新的記錄檔抵達，就會刪除舊的記錄檔。 當記錄收集器磁碟空間已滿時，記錄收集器會在有更多可用磁碟空間之前卸除新的記錄檔。 發生這種情況時，您會在 [自動上傳記錄檔] 設定的 [記錄收集器] 索引標籤上收到警告。

在設定自動收集記錄檔之前，請確認您的記錄檔與預期記錄檔類型相符，以確保 Cloud App Security 可以剖析特定檔案。

> [!NOTE]
>-  Cloud App Security 支援將記錄檔從 SIEM 伺服器轉送到記錄檔收集器，假設記錄檔是以原始格式轉送。 不過，強烈建議您直接整合記錄收集器與防火牆及 (或) Proxy。
>- 記錄收集器會先壓縮資料，然後再上傳。 記錄收集器的輸出流量將會是所收到流量記錄大小的 10%。 

## <a name="deployment-modes"></a>部署模式

記錄收集器支援兩種部署模式：

-   **容器**(*預覽*)：在 [Windows](discovery-docker-windows.md) 和 [Ubuntu](discovery-docker-ubuntu.md) 上，在內部部署或在 Azure 以 Docker 映像形式執行。 



-   **虛擬設備**：[在 HYPER-V 或 VMware Hypervisor 上以映像形式執行](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

