---
title: "設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題說明在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/9/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9f17366c62b202432d8b0c750290b4915f64c929
ms.sourcegitcommit: b2e3af9d0a62dcb6410cc3992183c2888bdf6a2f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2017
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>設定自動記錄檔上傳以進行連續報告


記錄收集器可讓您輕鬆地從網路自動上傳記錄檔。 記錄收集器會在您的網路上執行，透過 Syslog 或 FTP 接收記錄檔。 每個記錄檔都會自動處理、壓縮和傳送至入口網站。 FTP 記錄檔在完成以 FTP 傳送至記錄收集器的作業之後，即會上傳至 Cloud App Security。  若為 Syslog，記錄收集器會將所收到的記錄檔寫入至磁碟，並在檔案大小大於 40 KB 時，將該檔案上傳至 Cloud App Security。

記錄檔上傳到 Cloud App Security 之後會移至備份目錄，其中儲存了任何指定時間的最後 20 個記錄檔。 每次有新的記錄檔抵達，就會刪除舊的記錄檔。 當記錄收集器磁碟空間已滿時，記錄收集器會在有更多可用磁碟空間之前卸除新的記錄檔。

在設定自動收集記錄檔之前，請確認您的記錄檔與預期記錄檔類型相符，以確保 Cloud App Security 可以剖析特定檔案。

> [!NOTE]
> Cloud App Security 支援將記錄檔從 SIEM 伺服器轉送到記錄檔收集器，假設記錄檔是以原始格式轉送。 不過，強烈建議您直接整合記錄收集器與防火牆及/或 Proxy。

## <a name="deployment-modes"></a>部署模式

記錄收集器支援兩種部署模式：

-   **容器** (*根據 Docker CE*)：在內部部署或 Azure 中，執行為 [Windows](discovery-docker-windows.md) 和 [Ubuntu](discovery-docker-ubuntu.md) 上的 Docker 映像。

-   **虛擬應用裝置** (*取代中*)：[執行為透過 HYPER-V 或 VMware Hypervisor 的映像](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

