---
title: "活動 | Microsoft Docs"
description: "本主題提供可套用至活動原則的活動、篩選和比對參數清單。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 401801da8a4439b3dc0cf5c2f150c72e169a6d16


---

# <a name="activities"></a>活動
以下是可套用的活動篩選清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
-   活動 – 僅搜尋特定活動；例如，所有的檔案上傳、從新的裝置登入和失敗的登入。  
  
-   活動識別碼 - 依據識別碼，僅搜尋特定活動。 若您要將 MCAS 連接到 SIEM (使用 SIEM 代理程式)，並進一步調查 MCAS 入口網站中的警示時，就非常適合使用此篩選。  
  
-   系統管理活動 – 僅搜尋管理活動。  
  
-   模擬活動 – 僅搜尋以其他使用者名稱所執行的活動。  
  
-   應用程式 – 只搜尋特定應用程式內的活動。  
  
-   日期 – 活動發生的日期。 篩選可支援日期前後與日期範圍的搜尋。  
  
-   使用者 – 執行活動的使用者。 若要篩選不具特定使用者的活動，您可以使用 ‘is not set’ 運算子。  
  
     ![活動 ref1](./media/activity-ref1.png "activity ref1")  
  
-   IP 位址 – 執行活動的來源 IP 位址。  
  
-   IP 類別 – 執行活動的來源 IP 位址類別；例如，來自系統管理 IP 位址範圍的所有活動。 如需 IP 類別的詳細資訊，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。  
  
-   IP 標記 - 執行活動的來源 IP 位址標記；例如，來自匿名 Proxy IP 位址的所有活動。 如需 IP 標籤的詳細資訊，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。  
  
-   位置 – 執行活動的來源國家/地區。  
  
-   已註冊的 ISP – 執行活動的來源 ISP。  
  
     ![活動原則 ref2](./media/activity-policy-ref2.png "activity policy ref2")  
  
-   裝置類型 - 僅搜尋使用特定裝置類型所執行的活動；例如，來自行動裝置的所有活動。  
  
-   使用者代理程式 – 執行活動的來源使用者代理程式。  
  
-   使用者代理程式標記 – 內建的使用者代理程式標記；例如，來自過期瀏覽器或過期作業系統的所有活動。  
  
-   使用者組織 – 執行活動之使用者所屬的組織單位，例如 EMEA_marketing 使用者所執行的所有活動。  
  
- 目標物件 - 可讓您選取特定檔案。 

-   使用者群組 – MCAS 自動從雲端應用程式匯入的特定使用者群組，例如 Office 365 系統管理員所執行的所有活動。  
  
-   描述 – 活動描述的特定關鍵字；例如，描述中包括**使用者**字串的所有活動。  
  
-   相符的原則 – 搜尋與入口網站所設定之特定原則相符的活動。  
  
     ![活動原則 ref3](./media/activity-policy-ref3.png "Activity policy ref3")  
  
## <a name="activity-match-parameters"></a>活動比對參數  
指定將活動視為符合原則前的必要重複次數；例如，您可設定原則，以在使用者於 2 分鐘的時間範圍內執行 10 次失敗登入時提出警示。  
[活動比對參數] 是預設設定，其會在單一活動符合所有活動篩選條件時引發相符事件。   
您可使用 [重複的活動] 來設定重複的活動數量、計算活動數量的時間範圍，甚至可以指定相同的使用者和相同雲端應用程式內應該執行的所有活動。  
  
### <a name="actions"></a>[動作]  
通知  
  
-   警示 – 系統可以觸發警示，並根據嚴重性層級，透過電子郵件和文字訊息來傳播警示。  
  
-   使用者電子郵件通知 – 您可自訂電子郵件訊息，並將其傳送給所有違規的檔案擁有者。  
  
-   CC 管理員 – 也可以根據使用者的目錄整合，將電子郵件通知傳送給違反原則之人員的管理員。  
  
-   通知其他使用者 – 將接收這些通知的電子郵件地址特定清單。  
  
應用程式中的治理動作  
  
-   每個應用程式皆可強制執行細微的動作；特定動作視應用程式的術語而異。  
  
-   暫時停止使用者的權限 – 暫時停止使用者的應用程式權限。  
  
-   撤銷密碼 – 撤銷使用者的密碼，並強制使用者在下次登入時設定新密碼。  
  
     ![活動原則 ref6](./media/activity-policy-ref6.png "activity policy ref6")  
  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


