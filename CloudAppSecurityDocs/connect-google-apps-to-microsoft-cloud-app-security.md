---
title: 連接 G Suite 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs
description: 本主題提供如何使用 API 連接器將 G Suite 連接至 Cloud App Security 的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/10/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9dba7289b83397ae68224b56332baf1a59abe704
ms.sourcegitcommit: d9b65152d06b9924231b296ffe565689b44ab93e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="connect-g-suite-to-microsoft-cloud-app-security"></a>將 G Suite 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用連接器 API，將 Cloud App Security 連接至您現有的 G Suite 帳戶。
  
  
## <a name="configure-g-suite"></a>設定 G Suite  
  
1. 以 G Suite 進階管理員的身分登入 <a href="https://cloud.google.com/console/project" target="_blank">https://cloud.google.com/console/project</a>。  
  
2. 按一下 [建立專案] 開始新的專案。  
  
    ![google1](./media/google1.png "google1")  
  
3. 在 [新增專案] 畫面中，以下列名稱命名您的專案︰</br>
   Microsoft Cloud App Security**，然後按一下 [建立]**。  
          ![google2](./media/google2.png "google2")  
  
4. 建立專案後，按一下工具列的 [Google Cloud Platform]，確定在上方的下拉式清單中選取正確的專案。
       
      ![google 專案](./media/googleverify-project.png "googleverify 專案")  

5. 按一下 [API] 下方的 [Go to APIs overview] \(移至 API 概觀)。  
  
     ![google3](./media/google3.png "google3")  
  
6. 停用 [API] 下列出的所有 API。  
      
7. 按一下 [程式庫] 啟用下列 API (如果 [Popular APIs]\(熱門 API) 清單未列出 API，請使用搜尋列)：  
     
   -   管理 SDK  
  
   -   稽核 API  
  
   -   Google Drive API  
  
   -   Google Apps Marketplace API  
  
   -   Gmail API  
            
   ![Google API](./media/google4.png "google4")  
  
   > [!NOTE]  
   >  暫時忽略**認證**警告。  

8. 針對每個 API 按一下 [啟用]。
     ![啟用 Google APPI](./media/google-api.png "google-api")  
9. 您應該會有 5 個**啟用的 API**，請務必停用任何其他 API：
  
     ![Google 啟用的 API](./media/google5.png "google5")  
  
10. 按一下 [認證]，然後選取 [OAuth consent screen] \(OAuth 同意畫面) 索引標籤。
  
    - 在 [Product name shown to users (向使用者顯示的產品名稱)] 中，鍵入 **Microsoft Cloud App Security**。  
  
    - 所有其他欄位都是選擇性的。  
  
    - 按一下 **[儲存]**。  
  
      ![Google 產品名稱](./media/google6.png "google6")  
  
11. 在 [認證] 索引標籤中，按一下 [建立認證] 旁的箭號。  
  
     ![Google 認證](./media/google7.png "google7")  

12. 選取 [服務帳戶金鑰]。

     ![Google 服務帳戶金鑰](./media/google8.png "google8")  
  
13. 在 [建立服務帳戶金鑰] 下，選擇 [新增服務帳戶]，並輸入任何名稱，例如 **Service account 1**。 在 [角色] 下，選擇 [專案]，然後選擇 [編輯者]。 在 [金鑰類型] 下，選擇 [P12]，然後按一下 [建立]。 P12 憑證檔案會儲存到您的電腦。
 
     ![在 Google 中建立服務帳戶金鑰](./media/google9.png "google9")  
  
14. 請複製指派給服務的 [服務帳戶 ID]，以供稍後使用。    
        
15. 在 [認證] 畫面中，按一下最右側的 [Manage service accounts]\(管理服務帳戶)。  
     
    ![G Suite 認證服務帳戶](./media/google10.png "G Suite 認證服務帳戶")  
  
16. 按一下位於您所建立之服務帳戶右側的三個點，然後選取 [編輯]。  
  
     ![Google 編輯](./media/google11.png "Google 編輯")  
  
17. 選取 [Enable G Suite Domain-wide Delegation]\(啟用 G Suite 全網域委派) 核取方塊，然後按一下 [儲存]。  
  
     ![Google 服務帳戶識別碼](./media/google12.png "google12")  
  
18. 按一下在標題列中位於 Google Cloud Platform 旁邊的三條水平線，以開啟 Google 功能表。 按一下 **Google Cloud Platform**，然後按一下左功能表中的 [APIs and services] \(API 和服務) 索引標籤。  
    
19. 在開啟的儀表板中，向下捲動至已啟用的 API 清單，並按一下 [Google Drive API]。   
       ![選取 [Google Drive]](./media/google14.png "google14")  

20. 按一下 [Drive UI Integration] \(磁碟機 UI 整合) 索引標籤，然後填寫下列資訊：

    - **應用程式名稱**：Microsoft Cloud App Security。  
  
    - **簡短描述和完整描述** (選擇性)：Microsoft Cloud App Security 可讓您掌握雲端應用程式，協助您控制、調查和治理雲端應用程式的使用、保護公司資料，以及偵測任何雲端應用程式的可疑活動。  
  
    - Google 要求您至少上傳一個應用程式圖示。 前往 [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826) 下載包含 Cloud App Security 圖示的 zip 檔案。 然後在**應用程式圖示**下，按一下 128x128 圖片旁的 [選取]，並將其拖曳到快顯畫面。 按一下 32x32 圖片旁的 [選取]，並將其拖曳到快顯畫面。  
  
    - 向下捲動到 [Drive Integration] \(磁碟機整合) 區段，並在 [開啟 URL] 下方鍵入下列 URL：  
  
       https://portal.cloudappsecurity.com/#/services/11770?tab=files  
    
      ![編輯 Google Drive](./media/google15.png "google15")  

21. 按一下 [儲存變更]。

22. 返回 [Enabled APIs] \(啟用的 API) 清單。 按一下 [Apps Marketplace SDK]。 
      
23. 選取 [設定] 索引標籤。 
  
    -   複製上方顯示的**專案編號 (應用程式識別碼)** 以供日後使用。  
  
    -   在 [應用程式名稱] 下方，鍵入 **Microsoft Cloud App Security**。
  
         在 [應用程式描述] 中，鍵入「Microsoft Cloud App Security 可讓您掌握雲端應用程式，協助您控制、調查和治理雲端應用程式的使用、保護公司資料，以及偵測任何雲端應用程式的可疑活動。」  
  
    -   取消核取 [Enable individual install]\(啟用個別安裝) 核取方塊。  
  
    -   在 [應用程式圖示] 下設定四個必要影像。  
  
         您可於下列連結找到影像：[https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)  
  
    -   填寫下列**支援 URL**：  
  
        -   **服務條款 URL**：http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **隱私權原則 URL**：http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   在 [OAuth 2.0 範圍] 下，複製並貼上下列 URL (一次複製一個，並於貼上後按 Enter)：  
  
           https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
           https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
           https://www.googleapis.com/auth/drive  
  
           https://www.googleapis.com/auth/drive.appdata  
  
           https://www.googleapis.com/auth/drive.apps.readonly  
  
           https://www.googleapis.com/auth/drive.file  
  
           https://www.googleapis.com/auth/drive.metadata.readonly  
  
           https://www.googleapis.com/auth/drive.readonly  
  
           https://www.googleapis.com/auth/drive.scripts  
  
           https://www.googleapis.com/auth/admin.directory.user.readonly  
  
           https://www.googleapis.com/auth/admin.directory.user.security  
  
           https://www.googleapis.com/auth/admin.directory.user.alias  
  
           https://www.googleapis.com/auth/admin.directory.orgunit  
  
           https://www.googleapis.com/auth/admin.directory.notifications  
  
           https://www.googleapis.com/auth/admin.directory.group.member  
  
           https://www.googleapis.com/auth/admin.directory.group  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile  
  
           https://www.googleapis.com/auth/admin.directory.user  

    -   在 [可見度] 底下，選取 [我的網域] \(非公用)。 
    -   按一下 [儲存變更]。  
        ![google 可見性](./media/google-visibility.png "google 可見性")  
24. 請移至 [admin.google.com](https://admin.google.com/)，然後選擇 [安全性]。 
   
      ![Google Security](./media/googlesec.png "Google Security")  
 
25. 選擇 [API 參考]。  
       ![Google API 啟用](./media/googleapi.png "Google API")  
      
26. 選取 [Enable API Access (啟用 API 存取)]，然後按一下 [儲存變更]。  
  
    ![Google 參考](./media/googleapiref.png "google8")  

  
## <a name="configure-cloud-app-security"></a>設定 Cloud App Security  
  
1.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
2.  在 [連線應用程式] 頁面中，按一下加號並選取 [G Suite]。  
       
  
3.  在快顯視窗中填入下列資訊：  
  
     ![Cloud App Security 中的 G Suite 設定](./media/gsuite-config-cas.png "Cloud App Security 中的 G Suite 設定")  
  
    1.  您在步驟 13 中複製的**服務帳戶識別碼**。  
  
    2.  您在步驟 21 中複製的**專案編號 (應用程式識別碼)**。  
  
    3.  上傳您在步驟 12 中儲存的**憑證** P12。 您需要之前儲存的密碼才能執行這項操作。  
  
    4.  輸入 G Suite 系統管理員其中一個**系統管理員帳戶的電子郵件**。  
  
    5.  如果您有 G Suite 商務或企業帳戶，請選取此核取方塊。 如需適用於 G Suite 商務或企業帳戶的 Cloud App Security 可用功能的詳細資訊，請參閱[為您的應用程式提供立即可見性、保護及治理動作](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)。  
  
    6.  按一下 [儲存設定]。  
  
    7.  [連入此連結] 連接到 G Suite。 這會開啟 G Suite，且系統會要求您授與 Cloud App Security 存取權。  
         
    8.  按一下 [Test now]\(立即測試) 確定連線成功。  
  
         測試可能需要幾分鐘的時間。  
  
         收到成功通知之後，按一下 [完成] 並關閉 G Suite 頁面。  
  
  
連接 G Suite 之後，您會收到連線前 60 天的事件。
  
連接 G Suite 之後，Cloud App Security 即會執行完整掃描。 根據您擁有的檔案與使用者數量而定，完整掃描可能需要一段時間才能完成。 為了啟用近乎即時的掃描，系統會將偵測到活動的檔案移動到掃描佇列的開頭。 例如，系統會立即掃描被編輯、更新或共用的檔案。 這並不適用於實際上並未修改的檔案。 例如，已檢視、預覽、列印或匯出的檔案，會在標準掃描期間進行掃描。
  
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  