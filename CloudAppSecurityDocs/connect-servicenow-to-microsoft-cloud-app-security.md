---
title: "連接 ServiceNow 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 ServiceNow 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/21/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9988a610e9768173f0c89458974997647cabceaa
ms.sourcegitcommit: 4aaa8abdaaf5f2515f504b08c550c7987b6bc7be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2018
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>將 ServiceNow 連接至 Microsoft Cloud App Security

本節提供的指示說明如何使用 App 連接器 API，將 Cloud App Security 連接至您現有的 ServiceNow 帳戶。 

 >  [!NOTE]
>  建議使用適用於 Fuji 和更新版本的 OAuth 應用程式權杖，來部署 ServiceNow (請參閱相關的 [ServiceNow 文件](http://wiki.servicenow.com/index.php?title=OAuth_Applications#gsc.tab=0)。 針對舊版，則會根據使用者/密碼提供[舊版連線模式](#legacy-servicenow-connection)。

 > [!NOTE]  
>  Cloud App Security 支援 Eureka、Fiji、Geneva、Helsinki 和 Istanbul 版本的 ServiceNow。 若要連接 ServiceNow 與 Cloud App Security，您必須擁有**系統管理員**角色，並確定 ServiceNow 執行個體支援 API 存取。  如需詳細資訊，請參閱 [ServiceNow 產品文件](http://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0)。
  
## <a name="how-to-connect-servicenow-to-cloud-app-security-using-oauth"></a>如何使用 OAuth 將 ServiceNow 連線至 Cloud App Security
  
  
1.  使用系統管理員帳戶登入您的 ServiceNow 帳戶。  
  
2.  在 [Filter navigator]\(篩選導覽) 搜尋列中，鍵入 **OAuth** 並選取 [Application Registry]\(應用程式登錄)。

3. 在 [Application Registry]\(應用程式登錄) 功能表列中，按一下 [新增] 建立新的 OAuth 設定檔。

   ![ServiceNow 的新 OAuth 設定檔](./media/servicenow-app-registry.png)

4. 在 [What kind of OAuth application?] \(OAuth 應用程式種類為何?) 下，按一下 [Create an OAuth API endpoint for external clients] \(建立外部用戶端的 OAuth API 端點)。

   ![ServiceNow OAuth 類型](./media/servicenow-oauth-app-type.png)

5. 在 [Application Registry 新增記錄] 下填入下列欄位︰
    
    - [名稱] 欄位中請填入新的 OAuth 設定檔名稱，例如 CloudAppSecurity。 
    
    - [用戶端識別碼] 會自動產生。 您需要複製此識別碼，並將其貼入 Cloud App Security 以完成連線。
    
    - 在 [Client Secret]\(用戶端密碼) 欄位中輸入字串。 如果保留空白，則會自動產生隨機祕密。 複製並儲存以供稍後使用。 
    
    - 將 [Access Token Lifespan]\(存取權杖使用時間) 增加到至少 3,600。
    
    - 按一下 [提交] 。

   ![ServiceNow 設定檔識別碼](./media/servicenow-profile-ids.png)

6.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
7.  在 [App 連線程式] 頁面中，依序按一下加號按鈕及 [ServiceNow]。  
  
     ![連線 ServiceNow](./media/connect-servicenow.png "連線 ServiceNow")  
  
8.  在快顯中，於適當的方塊中新增您的 ServiceNow 使用者識別碼、密碼、執行個體 URL、用戶端識別碼及用戶端密碼。 若要尋找您的 ServiceNow 使用者識別碼，請在 ServiceNow 入口網站中，移至 [使用者] 並在資料表中找出您的名稱。名稱會顯示在使用者識別碼旁邊。

    ![ServiceNow 使用者識別碼](./media/servicenow-userid.png)
  
9.  按一下 [連線] 。  
  
     ![ServiceNow 連線到 CAS](./media/servicenow-portal-connect.png "在入口網站連線到 ServiceNow")  
  
10.  按一下 [Test now]\(立即測試) 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
連接 ServiceNow 之後，您會收到連線前 60 天的事件。
  
## <a name="legacy-servicenow-connection"></a>舊版 ServiceNow 連線

若要連接 ServiceNow 與 Cloud App Security，您必須擁有系統管理員層級權限，並確定 ServiceNow 執行個體支援 API 存取。   

1.  使用系統管理員帳戶登入您的 ServiceNow 帳戶。   

2.  建立新的 Cloud App Security 服務帳戶，並將系統管理員角色附加至新建立的帳戶。   

3.  確定已開啟 REST API 外掛程式。   

    ![ServiceNow 帳戶](./media/servicenow-account.png "ServiceNow 帳戶")   

4.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [獲批准的應用程式]。   

5.  在 ServiceNow 列中，按一下 [App 連線程式狀態] 欄位中的 [連線]，或依序按一下 [連線到應用程式] 按鈕和 [ServiceNow]。   

    ![連線 ServiceNow](./media/connect-servicenow.png "連線 ServiceNow")   

6.  在 ServiceNow 設定頁面上，於 [API] 索引標籤的適當方塊中，新增您的 ServiceNow 使用者識別碼、密碼和執行個體 URL。   

7.  按一下 [連線] 。   

   ![ServiceNow 更新密碼](./media/servicenow-update-password.png "ServiceNow 更新密碼")   

8.  按一下 [測試 API] 確定連線成功。   
  
   測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。    
 連接 ServiceNow 之後，您會收到連線前 60 天的事件。 


## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
