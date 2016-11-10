---
title: "將 Salesforce 連接至 Microsoft Cloud App Security | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Salesforce 連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a413236b04726dddc69068e39967f6ad17218719
ms.openlocfilehash: 03dc58139a6739f5cc4294c1913ed8b6a720a9d2


---


# <a name="connect-salesforce-to-microsoft-cloud-app-security"></a>將 Salesforce 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連接程式 API，將 Cloud App Security 連接至您現有的 Salesforce 帳戶。  
  
## <a name="how-to-connect-salesforce-to-cloud-app-security"></a>如何將 Salesforce 連接至 Cloud App Security  
  
1.  建議使用 Cloud App Security 專屬的服務系統管理員帳戶。  
  
2.  驗證 REST API 已在 Salesforce 中啟用。  
  
     您的 Salesforce 帳戶必須是下列其中一個包含 REST API 支援的版本︰  
  
     **Performance**、**Enterprise**、**Unlimited** 或 **Developer**。  
  
     **Professional** 版本依預設沒有 REST API，但可以依需求新增。  
  
     請檢查您的版本有 REST API 可用且已啟用，如下所示︰  
  
    -   登入您的 Salesforce 帳戶，並移至 [設定] 頁面。  
  
    -   在 [管理使用者] 下，移至 [設定檔] 頁面。  
  
         ![salesforce 管理使用者設定檔](./media/salesforce-manageusers-profiles.png "salesforce manageusers profiles")  
  
    -   選擇您用來部署 Cloud App Security 的設定檔，然後按一下 [編輯]。  
  
         ![salesforce 編輯設定檔](./media/salesforce-edit-profile.png "salesforce edit profile")  
  
    -   請確定您已選取 [API Enabled (已啟用 API)] 核取方塊。 如果未選取，您可能需要連絡 Salesforce 以將它新增至您的帳戶。  
  
         ![salesforce api 已啟用](./media/salesforce-api-enabled.png "salesforce api enabled")  
  
3.  如果您的組織已啟用 **Salesforce CRM 內容**，請確定目前的系統管理帳戶也有啟用它。  
  
    1.  移至您的 Salesforce 設定頁面。  
  
         ![salesforce 設定](./media/salesforce-setup.png "salesforce setup")  
  
    2.  從側邊功能表上，選取 [管理使用者]，然後按一下 [使用者]。  
  
         ![salesforce 功能表使用者](./media/salesforce-menu-users.png "salesforce menu users")  
  
    3.  將目前的系統管理使用者選取為專屬的 Cloud App Security 使用者。  
  
    4.  請確定已選取 [Salesforce CRM Content User (Salesforce CRM 內容使用者)] 核取方塊。  
  
         如果未選取，請按一下 [編輯] 然後核取此核取方塊。  
  
         ![salesforce crm 內容使用者](./media/salesforce-crm-content-user.png "salesforce crm content user")  
  
    5.  按一下 **[儲存]**。  
  
4.  在 Cloud App Security 主控台中，依序按一下 [調查] 和 [獲批准的應用程式]。  
  
5.  在 Box 列中，按一下 [App 連線程式狀態] 欄位中的 [連線]，或依序按一下 [連線到應用程式] 按鈕和 [Salesforce]。  
  
     ![連接 salesforce](./media/connect-salesforce.png "connect salesforce")  
  
6.  取決於您想要安裝哪一個執行個體，在 [Salesforce 設定] 頁面的 [API] 索引標籤中，按一下 [連入此連結]。  
  
7.  這會開啟 Salesforce 登入頁面。 輸入您的認證，允許 Cloud App Security 存取您小組的 Salesforce 應用程式。  
  
     ![salesforce 登入](./media/salesforce-logon.png "salesforce logon")  
  
8.  Salesforce 會詢問您是否要允許 Cloud App Security 存取小組資訊和活動記錄檔，並允許其以任何小組成員的身分執行任何活動。 若要進行，請按一下 [允許]。  
  
9. 此時，您會收到關於部署成功或失敗的通知。 現在，Cloud App Security 已在 Salesforce.com 中獲得授權。  
  
10. 返回 Cloud App Security 主控台時，您應該會看到 Salesforce 已順利連接的訊息。  
  
11. 按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [完成]。  
  
  
連接 SalesForce 之後，您將會收到下列「事件」：自連線起的觸發程序、連線前 60 天的登入事件與設定稽核線索、EventMonitoring 30 天前或 1 天前的事件 (根據您的 SalesForce EventMonitoring 授權而定)。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


