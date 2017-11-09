---
title: "Cloud App Security 中的 API 權杖管理 | Microsoft Docs"
description: "本主題提供為 Cloud App Security 產生 API 權杖的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4f5e6b1e-6b2c-4358-98f0-945e2993d5fe
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e8e86368429fac280b5555d85a0de3ec1789effa
ms.sourcegitcommit: 2fe9475d428855a6dab6fa2edd0ccd56d66f87ec
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2017
---
# <a name="api-tokens"></a>API 權杖
    
Cloud App Security API 可利用程式設計方式透過 REST API 端點存取 Cloud App Security。 應用程式可以使用 API，在 Cloud App Security 資料和物件上執行讀取和更新作業。 例如，Cloud App Security API 支援使用者物件的下列常見作業：

- 上傳 Cloud Discovery 的記錄檔
- 產生封鎖指令碼
- 列出活動、警示和原則報告
- 關閉或解決警示

若要查看 API 的完整文件，請在 Cloud App Security 入口網站中，移至 [說明] > [API 文件]。

若要存取 API，您必須建立 API 權杖，並在軟體中使用以連線到 Cloud App Security API。

[API 權杖] 索引標籤可讓您協助管理租用戶的所有 API 權杖。 


## <a name="generate-a-token"></a>產生權杖

1. 在 [設定] 功能表上，選取 [安全性延伸模組]，然後選取 [API 權杖]。

2. 按一下加號圖示，**產生新權杖**並提供未來識別權杖的名稱，然後按一下 [下一步]。
![Cloud App Security 產生 API 權杖](./media/api-token-gen.png)

3. 複製權杖值並儲存至某處以供復原 (如果您遺失權杖，則必須重新產生權杖)。 權杖將具有發出權杖之使用者的權限。 例如，安全性讀取者無法發出可改變資料的權杖。

4. 您可以依狀態篩選權杖：[使用中]、[非使用中] 或 [已產生]。 

  - [已產生] 是從未使用過的權杖。 
  - [使用中] 是已產生且過去七天內已使用的權杖。 
  - [非使用中] 是已使用但過去七天內沒有活動的權杖。
5. 在產生新權杖之後，系統會提供您用來存取 Cloud App Security 入口網站的新 URL。 

 ![Cloud App Security API 權杖](./media/generate-api-token.png)

一般入口網站 URL 依然可用，但速度會比隨權杖提供給您的自訂 URL 慢上許多。 如果您不記得 URL，只要到功能表中的 **?** 圖示選取 [關於]，即可隨時檢視。

## <a name="api-token-management"></a>API 權杖管理

API 權杖頁面包含已產生之所有 API 權杖的資料表。

完整權限系統管理員會看到為此租用戶產生的所有權杖。 其他使用者只會看到他們自行產生的權杖。

此資料表提供有關權杖產生時間及上次使用時間的詳細資料，並可讓您撤銷權杖。 

撤銷權杖之後，權杖即從資料表中移除，而且使用該權杖的軟體在提供新權杖之前將無法進行 API 呼叫。 

> [!NOTE]
> SIEM 連接器和記錄收集器也會使用 API 權杖。 這些權杖應該從記錄收集器和 SIEM 代理程式區段進行管理，因此不會出現在此資料表中。 





## <a name="see-also"></a>另請參閱  
[針對 SIEM 整合問題進行疑難排解](troubleshooting-siem.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  \(英文\)。  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  

## <a name="check-out-this-video"></a>請觀賞這部影片！
[Microsoft Cloud App Security – REST API’s and Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens) (Microsoft Cloud App Security – REST API 和權杖)  