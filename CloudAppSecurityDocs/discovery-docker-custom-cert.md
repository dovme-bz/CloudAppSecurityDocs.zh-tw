---
title: "自訂 Cloud Discovery Docker 的憑證 | Microsoft Docs"
description: "本主題說明自訂 Cloud Discovery Docker 憑證的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 26/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0e9c15d3-902b-4b8f-8dec-31953b4451e0
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6052e5b7b3db9e3f69f86fbbfe9930432ce2a30c
ms.sourcegitcommit: 473d96a6383a6e4d01ef03ed31f2e773cea82cab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2017
---
# <a name="customize-certificate-files"></a>自訂憑證檔

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
[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)  
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

