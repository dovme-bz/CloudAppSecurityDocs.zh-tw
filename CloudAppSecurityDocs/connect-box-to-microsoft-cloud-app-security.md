---
title: "連接 Box 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Box 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b3e4713e-986f-4a5e-9fcc-f8de94dd0df7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 11716fb83acfb893dce29c7f4179788d40bef7a4
ms.sourcegitcommit: 0d4748ea2a71e6ee2b0fa1c0498d9219bfbda29a
translationtype: HT
---
# <a name="connect-box-to-microsoft-cloud-app-security"></a>將 Box 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連線程式 API，將 Cloud App Security 連接至您現有的 Box 帳戶。  
  
## <a name="how-to-connect-box-to-cloud-app-security"></a>如何將 Box 連接至 Cloud App Security  
  
> [!NOTE]  
>  使用非系統管理員帳戶的帳戶進行部署時，會導致 API 測試失敗，而且不允許 Cloud App Security 掃描 Box 的所有檔案。 如果您無法使用系統管理員帳戶，可以使用勾選了所有權限的共同管理員來部署，但這麼做 API 測試仍會失敗，亦不會掃描 Box 中其他管理員擁有的檔案。  
  
1.  如果您要限制應用程式的存取權，請遵循此步驟。 否則，請前往步驟 2。  
  
    -   在 Box Admin 主控台中，依序按一下設定圖示和 [Business settings (商務設定)]。  
  
         ![Box 商務設定](./media/box-business-settings.png "Box 商務設定")  
  
    -   按一下 [應用程式] 索引標籤。  
  
         ![Box 應用程式](./media/box-apps.png " Box應用程式")  
  
    -   如果選取 **「Unpublished Applications」** (未發行的應用程式)，請在 「Except for」 (除外) 文字方塊中，新增 Cloud App Security 的應用程式序號：`nduj1o3yavu30dii7e03c3n7p49cj2qh`，然後按一下 [儲存]。  
  
         ![Box 設定除外](./media/box-settings-except-for.png "Box 設定除外")  
  
    > [!NOTE]  
    >  如果您是現有的 Adallom 客戶，而主控台 URL 是供 Adallom 非供 Cloud App Security 使用，請使用這個應用程式序號︰bwahmilhdlpbqy2ongkl119o3lrkoshc。  
  
2.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
3.  在 [App 連線程式] 頁面中，按一下加號按鈕並選取 [Box]。  
  
     ![連接 Box](./media/connect-box.png "連接 Box")  
  
4.  在 [Box settings] (Box 設定) 快顯視窗中，按一下 [連入此連結]。  
  
5.  這會開啟 Box 的登入頁面。 輸入您的認證，允許 Cloud App Security 存取您小組的 Box 應用程式。  
  
6.  Box 會詢問您是否要允許 Cloud App Security 存取小組資訊和活動記錄檔，並允許其以任何小組成員的身分執行任何活動。 若要進行，請按一下 [允許]。  
  
7.  返回 Cloud App Security 入口網站時，您應該會收到訊息，指出已順利連接 Box。  
  
8.  按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
現在，Box 已連接到 Cloud App Security。  
 
連接 Box 之後，您會收到連線前 60 天的事件。
  
連接 Box 之後，Cloud App Security 即會執行完整掃描。 根據您擁有的檔案與使用者數量而定，完整掃描可能需要一段時間才能完成。 為了確保近即時的掃描，系統會將已偵測到活動的檔案移到掃描佇列開頭，好比說，系統會立即掃描受到編輯、更新或共用的檔案，而不會等到定期掃描程序時才進行。 如果檔案本來就沒有修改 (例如只受到檢視、預覽、列印或匯出的檔案)，則不適用此情況。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  