---
title: "使用錯誤訊息為 App 連線程式疑難排解 | Microsoft Docs"
description: "本主題提供 API App 連線程式的錯誤訊息清單，及各項錯誤的解決方法建議。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/27/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9565d8a51e4c06963861d9dfaef9595944bda1ff
ms.openlocfilehash: 71e2a213ddf6f625037b11373e55aa270c3b1785


---


# <a name="troubleshooting-app-connectors-using-error-messages"></a>使用錯誤訊息為 App 連線程式疑難排解

嘗試使用 API App 連線程式連接雲端應用程式後，App 連線程式的對話方塊中會出現 App 連線程式的錯誤。


|錯誤訊息|相關應用程式|描述|解決方法|
|----|----|----|------------|
|HttpRequestFailure: 伺服器傳回: 400 錯誤的要求: {"error":{"code":"AF20012","message":"系統中不正確地設定所指定的租用戶識別碼 (這裡是 Tenant_ID)。"|Office 365 |找不到指派的 Office 365 授權。 |將至少一個 Office 365 授權指派給您的租用戶。| 
|AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"重新整理權杖無效"}|方塊|Box 重新整理權杖無效|再次遵循將 Box 連線至 Cloud App Security 的程序。|
|BoxRestException︰ 無法剖析回應。|方塊|內部錯誤|再按一下 [立即測試] 連結，以測試與 Box 的連線。|
|ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"重新整理權杖無效"}'|方塊|Box 重新整理權杖無效|再次遵循將 Box 連線至 Cloud App Security 的程序。|
|BoxServerException︰使用者沒有企業，就無法存取這項功能|方塊|Box 帳戶不是企業版帳戶。|將 Box 授權升級至 Box 企業版，並再次遵循將 Box 連線至 Cloud App Security 的程序。|
|BoxServerException: 未經授權 - 無法向此服務授權|方塊|Box 管理員已在 Box 中刪除 Cloud App Security 應用程式。|再次遵循將 Box 連線至 Cloud App Security 的程序。|
|HttpRequestFailure: 伺服器傳回: 401 未經授權|Okta|Okta 權杖無效。|再次遵循將 Okta 連線至 Cloud App Security 的程序。|
|IOException:|Okta|內部錯誤|請連絡支援部門|
|HttpRequestFailure: 伺服器傳回: 404 找不到|Okta|內部錯誤|請連絡支援部門|
|SocketTimeoutException: 讀取逾時|Salesforce|內部錯誤|再按一下 [立即測試] 連結，以測試與 Salesforce 的連線。|
|HttpRequestFailure: 伺服器傳回: 400 錯誤的要求|Salesforce|與 Salesforce 的連線未完成或過期。|再次遵循將 Salesforce 連線至 Cloud App Security 的程序。|
|HttpRequestFailure: 伺服器傳回: 401 未經授權|Office 365|內部問題|再按一下 [立即測試] 連結|
|TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: 驗證認證時發生錯誤。 AADSTS70008: 提供的授權碼或重新整理權杖過期。 傳送此使用者和資源的新互動式授權要求。|Office 365|權杖過期|再次遵循將 Office 365 連線至 Cloud App Security 的程序。|
|SocketTimeoutException: 讀取逾時|Office 365|內部錯誤|再按一下 [立即測試] 連結|
|NullPointerException|Office 365|內部錯誤|請連絡支援部門|
|IgniteException|Office 365|網域或使用者無效|重設設定，並再次遵循將 Office 365 連線至 Cloud App Security 的程序。|
|ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: 驗證認證時發生錯誤。 AADSTS70008: 提供的授權碼或重新整理權杖過期。 傳送此使用者和資源的新互動式授權要求。|Office 365|網域或使用者無效|重設設定，並再次遵循將 Office 365 連線至 Cloud App Security 的程序。|
|HttpRequestFailure: 伺服器傳回: 400 錯誤的要求|Office 365|內部錯誤|在幾分鐘內再按一下 [立即測試] 連結，如果它未運作，請再次遵循將 Office 365 連線至 Cloud App Security 的程序。|
|GoogleJsonResponseException: 401 未經授權|Google Apps|拒絕存取。 您未獲授權，無法讀取活動記錄。 您用來登入 Google Apps 的使用者必須是管理使用者。|再次遵循使用管理員帳戶將 Google Apps 連線至 Cloud App Security 的程序。|
|GoogleJsonResponseException: 403 已禁止|Google Apps|執行 Google Apps API 時發生問題。|如果您才剛部署 Google Apps 的 Cloud App Security App 連線程式，請檢查下列項目︰如果您已按一下 [無限制]，請確定您的 Google Apps 帳戶真正無限制。 否則，請重新執行 App 連接程式，然後取消選取無限制帳戶的選項。 檢查您在安裝期間所定義的範圍正確。 如果這不是新的部署，並看到此錯誤，則您今天可能已達到 API 限制，明天將會更新 Google Apps 事件。|
|TokenResponseException: 400 錯誤的要求|Google Apps|與 Google Apps 的連線未完成或過期。|再次遵循將 Google Apps 連線至 Cloud App Security 的程序。|
|RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: 伺服器傳回: 403 已禁止|ServiceNow|權限不正確|再次遵循使用管理員帳戶將 ServiceNow 連線至 Cloud App Security 的程序。|
|HttpRequestFailure: 伺服器傳回: 401 未經授權|Exchange Online|使用者或密碼不正確|請確定使用者名稱和密碼正確，並再次遵循將 Exchange Online 連線至 Cloud App Security 的程序。|
|HttpRequestFailure: 伺服器傳回: 404 找不到|Exchange Online|您用來登入 Exchange Online 的使用者在 Exchange Online 中沒有主要信箱 (例如，不存在於 Azure AD 的使用者或存在於 Azure AD 的使用者，但沒有 Exchange Online 授權)。|再次遵循使用新管理員帳戶將 Exchange Online 連線至 Cloud App Security 的程序。|
|NullPointerException|AWS|內部錯誤|請連絡支援部門|
|HttpRequestFailure: 伺服器傳回: 500 內部伺服器錯誤|所有應用程式|應用程式發生錯誤。|檢查應用程式的狀態|
|服務逾時|所有應用程式|在 Cloud App Security 與應用程式之間的連接中偵測到逾時。 原因可能是應用程式發生問題。|請稍後再試。|

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


