---
title: "連接 Google Apps | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Google Apps 連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/19/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2997a79f2e0fd730302be2602b6aee6ec56999db
ms.openlocfilehash: 7734badea1da58b839d23842b73e9be57fe43be3


---

# <a name="connect-google-apps-to-microsoft-cloud-app-security"></a>將 Google Apps 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用連接器 API，將 Cloud App Security 連接至您現有的 Google Apps 帳戶。

  
  
## <a name="configure-google-apps"></a>設定 Google Apps  
  
1.  以 Google Apps 超級管理員身分登入 [https://cloud.google.com/console/project](https://cloud.google.com/console/project)。  
  
2.  按一下 [Create an empty project (建立空白專案)] 啟動新的專案。  
  
     ![google1](./media/google1.png "google1")  
  
3.  在 [新增專案] 畫面中︰  
  
    1.  如下命名您的專案︰</br>
    **Cloud App Security for Google** 
  
    2.  選取是否要訂閱更新。  
  
    3.  檢閱並核准服務條款。  
  
    4.  按一下 [建立]。  
  
         ![google2](./media/google2.png "google2")  
  
4.  在建立專案之後，按一下 [Enable and manage APIs (啟用和管理 API)]。  
  
     ![google3](./media/google3.png "google3")  
  
5.  按一下 [Enabled APIs (啟用的 API)] 索引標籤，停用所有列出的 API。  
  
     ![google5](./media/google5.png "google5")  
  
6.  按一下 [Google API] 索引標籤，啟用下列 API (如果 「Popular APIs」 (熱門 API) 清單未列出 API，請使用搜尋列)：  
  
     ![google8](./media/google8.png "google8")  
  
    > [!NOTE]  
    >  暫時忽略**認證**警告。  
  
    -   管理 SDK  
  
    -   稽核 API  
  
    -   磁碟機 API  
  
    -   Google Apps Marketplace SDK  
  
    -   Gmail API  
  
         ![google11 警告](./media/google11-warning.png "google11 警告")  
  
7.  您應該會有 5 個 [Enabled APIs (啟用的 API)]：  
  
     ![google15](./media/google15.png "google15")  
  
8.  依序按一下 [認證] 和 [OAuth consent (OAuth 同意)]  
  
    -   在 [Product name shown to users (向使用者顯示的產品名稱)] 中輸入 **Cloud App Security for Google**。  
  
    -   所有其他欄位都是選擇性的。  
  
    -   按一下 **[儲存]**。  
  
     ![google16](./media/google16.png "google16")  
  
9. 在 [認證] 索引標籤上，按一下 [建立認證] 旁的箭號，然後選取 [服務帳戶金鑰]。  
  
     ![google17](./media/google17.png "google17")  
  
10. 在 [服務帳戶] 中選擇 [New service account (新的服務帳戶)]，並輸入任何名稱，例如**服務帳戶 1**。  
  
     ![google19](./media/google19.png "google19")  
  
     在 [金鑰類型] 下選擇 [P12]，然後按一下 [建立]。  
  
     即會下載 P12 憑證檔案。 儲存憑證以供後用。  
  
     ![google20](./media/google20.png "google20")  
  
11. 在 [認證] 索引標籤上，按一下最右側的 [管理服務帳戶]。  
  
     ![Google Apps 認證服務帳戶](./media/google-apps-credentials-service-account.png "Google Apps 認證服務帳戶")  
  
12. 按一下所建服務帳戶右側的 3 個點，然後選取 [編輯]。  
  
     ![google22](./media/google22.png "google22")  
  
13. 選取 「Enable Google Apps Domain-wide Delegation」 (啟用 Google Apps 全網域委派) 核取方塊，然後按一下 [儲存]。  
  
     ![google24](./media/google24.png "google24")  
  
14. 將指派給服務的**電子郵件地址**複製下來，以供稍後使用。  
  
     ![google25](./media/google25.png "google25")  
  
15. 按一下 Google 雲端平台旁邊的三條水平線來開啟 Google 功能表，然後選取 [API manager (API 管理員)]。  
  
     ![Google 功能表](./media/google-menu.png "Google 功能表")  
  
     選取 [Enabled APIs (啟用的 API)]。  
  
     ![google27](./media/google27.png "google27")  
  
16. 按一下 [Drive API (磁碟機 API)] 旁邊的設定齒輪，並在 [Drive UI Integration (磁碟機 UI 整合)] 下填入下列內容︰  
  
    -   **應用程式名稱**：Cloud App Security for Google。  
  
    -   **簡短描述和完整描述**：Microsoft Cloud App Security 可讓您掌握雲端應用程式，協助您控制、調查和管理雲端應用程式使用，保護公司資料，以及偵測任何雲端應用程式的可疑活動。  
  
    -   在**應用程式圖示**下上傳 128x128 和 32x32 影像。  
  
         影像位於︰[https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
    -   在 [開啟 URL] 下輸入下列資訊：  
  
         https://portal.cloudappsecurity.com/#/services/11770?tab=files  
  
    -   按一下 [儲存變更]。  
  
         ![google29](./media/google29.png "google29")  
  
17. 在 **「Enabled APIs」** (啟用的 API) 清單中，按一下 [Google Apps Marketplace SDK] 旁邊的設定齒輪，然後選取 [設定] 索引標籤。  
  
    -   複製上方顯示的**專案編號 (應用程式識別碼)** 以供日後使用。  
  
    -   **應用程式名稱**：Cloud App Security for Google。  
  
         在 [應用程式描述] 欄位中填入「Microsoft Cloud App Security 可讓您掌握雲端應用程式，協助您控制、調查和管理雲端應用程式使用，保護公司資料，以及偵測任何雲端應用程式的可疑活動。」  
  
    -   取消核取 [Enable individual install (啟用個別安裝)] 核取方塊。  
  
    -   在**應用程式圖示**下設定 4 個必要影像。  
  
         影像位於︰[https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
         ![google31](./media/google31.png "google31")  
  
    -   填寫下列**支援 URL**：  
  
        -   **服務條款 URL**：http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **隱私權原則 URL**：http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   在 [OAuth 2.0 scopes (OAuth 2.0 範圍)] 下方，輸入下列項目 (每行 1 項， 並按 Enter 確認)：  
  
        -   https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
        -   https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
        -   https://www.googleapis.com/auth/drive  
  
        -   https://www.googleapis.com/auth/drive.appdata  
  
        -   https://www.googleapis.com/auth/drive.apps.readonly  
  
        -   https://www.googleapis.com/auth/drive.file  
  
        -   https://www.googleapis.com/auth/drive.metadata.readonly  
  
        -   https://www.googleapis.com/auth/drive.readonly  
  
        -   https://www.googleapis.com/auth/drive.scripts  
  
        -   https://www.googleapis.com/auth/admin.directory.user.readonly  
  
        -   https://www.googleapis.com/auth/admin.directory.user.security  
  
        -   https://www.googleapis.com/auth/admin.directory.user.alias  
  
        -   https://www.googleapis.com/auth/admin.directory.orgunit  
  
        -   https://www.googleapis.com/auth/admin.directory.notifications  
  
        -   https://www.googleapis.com/auth/admin.directory.group.member  
  
        -   https://www.googleapis.com/auth/admin.directory.group  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile  
  
        -   https://www.googleapis.com/auth/admin.directory.user  
  
    -   按一下 [儲存變更]。  
  
18. 從控制項清單選取 [安全性]。 如果沒看到這個選項，請從頁面底部的灰色列中選取 [其他控制項]，然後選取 [安全性]。  
  
     ![Google Apps 安全性](./media/google-apps-security.png "Google Apps 安全性")  
  
19. 選擇 [API 參考]。  
  
     ![google api ref](./media/google-api-ref.png "google api ref")  
  
20. 選取 [Enable API Access (啟用 API 存取)]，然後按一下 [儲存變更]。  
  
     ![google api access](./media/google-api-access.png "google api access")  
  
## <a name="configure-cloud-app-security"></a>設定 Cloud App Security  
  
1.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
2.  在 [連線應用程式] 頁面中，按一下加號並選取 [Google Apps]。  
  
     ![連接 Google Apps](./media/connect-google-apps.png "連接 Google Apps")  
  
3.  在快顯畫面填寫下列內容：  
  
     ![Cloud App Security 中的 Google Apps 設定](./media/google-apps-configuration-in-cloud-app-security.png "Cloud App Security 中的 Google Apps 設定")  
  
    1.  您在步驟 14 中複製的 **Google 服務帳戶電子郵件地址**。  
  
    2.  您在步驟 17 中複製的 **Google 專案編號 (應用程式識別碼)**。  
  
    3.  上傳您在步驟 10 中儲存的 **Google 憑證** P12。  
  
    4.  輸入其中一個 Google Apps 管理員的**管理員電子郵件**。  
  
    5.  如果您有 Google Apps Unlimited 帳戶，請核取這個核取方塊。 如需適用於 Google Apps Unlimited 的 Cloud App Security 可用功能資訊，請參閱[為您的應用程式提供立即可見度、保護及治理動作](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)。  
  
    6.  按一下 [儲存設定]。  
  
    7.  [連入此連結] 連接到 Google Apps。 這會開啟 Google Apps，並要求您授與 Cloud App Security 存取權。  
  
         ![Google Apps 授權要求](./media/google-apps-authorization-request.png "Google Apps 授權要求")  
  
    8.  按一下 [測試 API] 確定連線成功。  
  
         測試可能需要幾分鐘的時間。  
  
         收到成功通知之後，按一下 [完成] 並關閉 Google Apps 頁面。  
  
  
連接 Google Apps 之後，您會收到連線前 60 天的事件。
  
連接 Google Apps 之後，Cloud App Security 即會執行完整掃描。 根據您擁有的檔案與使用者數量而定，完整掃描可能需要一段時間才能完成。 為了確保近即時的掃描，系統會將已偵測到活動的檔案移到掃描佇列開頭，好比說，系統會立即掃描受到編輯、更新或共用的檔案，而不會等到定期掃描程序時才進行。 如果檔案本來就沒有修改 (例如只受到檢視、預覽、列印或匯出的檔案)，則不適用此情況。
  
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO3-->


