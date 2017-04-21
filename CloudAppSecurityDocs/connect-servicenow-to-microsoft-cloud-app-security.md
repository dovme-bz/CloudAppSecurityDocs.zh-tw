---
title: "連接 ServiceNow 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 ServiceNow 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f4fd428f762bcbe1fb2a26bf44268cf985fbd4f
ms.sourcegitcommit: c79c405a1277c5fcebbc245fa12ff8feb53248d5
translationtype: HT
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>將 ServiceNow 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連接器 API，將 Cloud App Security 連接至您現有的 ServiceNow 帳戶。  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>如何將 ServiceNow 連接至 Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security 支援 Eureka、Fiji、Geneva、Helsinki 和 Istanbul 版本的 ServiceNow。 若要連接 ServiceNow 與 Cloud App Security，您必須擁有**系統管理員**角色，並確定 ServiceNow 執行個體支援 API 存取。  如需詳細資訊，請參閱 [ServiceNow 產品文件](http://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0)。
  
1.  使用系統管理員帳戶登入您的 ServiceNow 帳戶。  
  
2.  在 [Filter navigator] (篩選導覽) 搜尋列中，鍵入 **OAuth** 並選取 [Application Registry] (應用程式登錄)。

3. 在 [Application Registry] (應用程式登錄) 功能表列中，按一下 [新增] 建立新的 OAuth 設定檔。

   ![ServiceNow 的新 OAuth 設定檔](./media/servicenow-app-registry.png)

4. 在 [What kind of OAuth application?] (OAuth 應用程式種類為何?) 下，按一下 [Create an OAuth API endpoint for external clients] (建立外部用戶端的 OAuth API 端點)。

   ![ServiceNow OAuth 類型](./media/servicenow-oauth-app-type.png)

5. 在 [Application Registries New record] (應用程式登錄新增記錄) 填入下列內容︰
    
    - [名稱] 欄位中請填入新的 OAuth 設定檔名稱，例如 CloudAppSecurity。 
    
    - [用戶端識別碼] 會自動產生。 您需要複製此識別碼，並將它貼入 Cloud App Security 以完成連線。
    
    - 在 [Client Secret] (用戶端密碼) 欄位中輸入字串。 如果空白，就會自動產生隨機密碼。 複製並儲存以供稍後使用。 
    
    - 將 [Access Token Lifespan] (存取權杖使用時間) 增加到至少 3,600。
    
    - 按一下 [提交] 。

   ![ServiceNow 設定檔識別碼](./media/servicenow-profile-ids.png)

6.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
7.  在 [App 連線程式] 頁面中，依序按一下加號按鈕及 [ServiceNow]。  
  
     ![連線 ServiceNow](./media/connect-servicenow.png "連線 ServiceNow")  
  
8.  在快顯中，於適當的方塊內新增您的 ServiceNow 使用者名稱、密碼、執行個體 URL 及用戶端識別碼。  
  
9.  按一下 [連線] 。  
  
     ![ServiceNow 連線到 CAS](./media/servicenow-portal-connect.png "在入口網站連線到 ServiceNow")  
  
10.  按一下 [Test now] (立即測試) 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
連接 ServiceNow 之後，您會收到連線前 60 天的事件。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
