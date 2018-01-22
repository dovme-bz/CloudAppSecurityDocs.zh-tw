---
title: "為 Cloud Discovery Docker 部署進行疑難排解 | Microsoft Docs"
description: "本主題說明修改 Cloud App Security Cloud Discovery Docker 組態的流程。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b994661f0f875db100a0aa2eb293b88e637b89cb
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-the-cloud-app-security-cloud-discovery-docker"></a>為 Cloud App Security Cloud Discovery Docker 進行疑難排解

## <a name="changing-the-ftp-password"></a>變更 FTP 密碼


1. 連線至記錄收集器主機。

2.  執行 `docker exec -it <collector name> pure-pw passwd <ftp user>`

    1. 輸入新密碼。
    2. 再次輸入新密碼以便確認。
 
3.  執行 `docker exec -it <collector name> pure-pw mkdb` 以套用變更。


  ![變更 ftp 密碼](./media/ftp-connect.png)

## <a name="customize-certificate-files"></a>自訂憑證檔

針對 Cloud Discovery Docker 的安全連線，請遵循此程序來自訂用於安全連線的憑證檔。

1.  開啟 FTP 用戶端，並連線到記錄收集器。

  ![連線到 ftp 用戶端](./media/ftp-connect.png)

2.  瀏覽至 `ssl_update` 目錄。
3.  將新的憑證檔上傳至 `ssl_update` 目錄 (為強制名稱)。

    ![變更 ftp 密碼](./media/new-certs.png)

    1.  對於 FTP：只需要一個檔案，其中依序包含金鑰與憑證資料，檔案名稱為 **pure-ftpd.pem**。
    
    2.  對於 Syslog：需要三個檔案：**ca.pem**、**server-key.pem** 與 **server-cert.pem**。 若遺漏其中任何一個檔案，就不會進行更新。

4.  在終端機中執行：`docker exec -t <collector name> update_certs`。 如此應產生如下列畫面所示的類似輸出。

    ![變更 ftp 密碼](./media/update-certs.png)

## <a name="see-also"></a>另請參閱
[部署 Cloud Discovery](set-up-cloud-discovery.md)

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

