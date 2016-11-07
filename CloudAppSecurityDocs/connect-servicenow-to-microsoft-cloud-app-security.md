---
title: "將 ServiceNow 連接至 Microsoft Cloud App Security | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 ServiceNow 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 30ddba23a0c481cb434e9239950cce90c52efc4f


---

# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>將 ServiceNow 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連接器 API，將 Cloud App Security 連接至您現有的 ServiceNow 帳戶。  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>如何將 ServiceNow 連接至 Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security 支援 Eureka 和 Fiji 版本的 ServiceNow。 若要連接 ServiceNow 與 Cloud App Security，您必須擁有系統管理員層級權限，並確定 ServiceNow 執行個體支援 API 存取。  
  
1.  使用系統管理員帳戶登入您的 ServiceNow 帳戶。  
  
2.  建立新的 Cloud App Security 服務帳戶，並將系統管理員角色附加至新建立的帳戶。  
  
3.  確定已開啟 REST API 外掛程式。  
  
     ![servicenow 帳戶](./media/servicenow-account.png "servicenow account")  
  
4.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [獲批准的應用程式]。  
  
5.  在 ServiceNow 列中，按一下 [App 連線程式狀態] 欄位中的 [連線]，或依序按一下 [連線到應用程式] 按鈕和 [ServiceNow]。  
  
     ![連接 servicenow](./media/connect-servicenow.png "connect servicenow")  
  
6.  在 ServiceNow 設定頁面上，[API] 索引標籤的適當方塊中，加入 ServiceNow 的使用者名稱、密碼和執行個體 URL。  
  
7.  按一下 [連線] 。  
  
     ![servicenow 更新密碼](./media/servicenow-update-password.png "servicenow update password")  
  
8.  按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
連接 ServiceNow 之後，您會收到連線前 60 天的事件。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


