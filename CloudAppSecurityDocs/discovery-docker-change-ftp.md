---
title: "修改 Cloud Discovery Docker 的 ftp 密碼 | Microsoft Docs"
description: "本主題說明修改 Cloud Discovery ftp 密碼的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 26/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 91411653b36cc5119b1c8e85ceac79c34386482f
ms.sourcegitcommit: 473d96a6383a6e4d01ef03ed31f2e773cea82cab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/27/2017
---
# <a name="changing-the-ftp-password"></a>變更 FTP 密碼


1. 連線至記錄收集器主機。

2.  執行 `docker exec -it <collector name> pure-pw passwd <ftp user>`

    1. 輸入新密碼。
    2. 再次輸入新密碼以便確認。
 
3.  執行 `docker exec -it <collector name> pure-pw mkdb` 以套用變更。


  ![變更 ftp 密碼](./media/ftp-connect.png)

## <a name="see-also"></a>另請參閱
[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)  
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

