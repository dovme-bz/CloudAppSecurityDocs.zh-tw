---
title: "連接 Box 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Box 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/3/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b3e4713e-986f-4a5e-9fcc-f8de94dd0df7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 2b9239b43d2f104f6e54c519ba089346c7672456
ms.sourcegitcommit: c5533d66b8e037d6221c48bdbad81574f25f2817
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2018
---
# <a name="connect-box-to-microsoft-cloud-app-security"></a>將 Box 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連線程式 API，將 Cloud App Security 連接至您現有的 Box 帳戶。  
  
## <a name="how-to-connect-box-to-cloud-app-security"></a>如何將 Box 連接至 Cloud App Security  
  
> [!NOTE]  
>  使用非系統管理員帳戶的帳戶進行部署時，會導致 API 測試失敗，並會使 Cloud App Security 無法掃描 Box 中的所有檔案。 如果您無法使用系統管理員帳戶，可以使用勾選了所有權限的共同管理員來部署，但這麼做 API 測試仍會失敗，亦不會掃描 Box 中其他管理員擁有的檔案。  
  
1.  如果您要限制應用程式的存取權，請遵循此步驟。 否則，請前往步驟 2。  
  
    -   在 [Box Admin] 主控台中，按一下 [Business settings] \(商務設定\) 或 [Enterprise settings] \(企業設定\) 之後的設定圖示。  
  
         ![Box 商務設定](./media/box-business-settings.png "Box 商務設定")  
  
    -   按一下 [應用程式] 索引標籤。  
  
         ![Box 應用程式](./media/box-apps.png " Box應用程式")  
  
    -   如果選取 [Unpublished Applications] \(未發行的應用程式\)，請在 [Except for] \(除外\) 文字方塊中，新增 Cloud App Security 應用程式序號：<br></br>US1 資料中心：`nduj1o3yavu30dii7e03c3n7p49cj2qh` <br></br>US2 資料中心：`w0ouf1apiii9z8o0r6kpr4nu1pvyec75`<br></br>EU1 資料中心：`me9cm6n7kr4mfz135yt0ab9f5k4ze8qp`<br></br>然後按一下 [儲存]。 如需如何查看要連線的目標 Cloud App Security 資料中心，請參閱 [API 權杖](api-tokens.md)。 
  
         ![Box 設定除外](./media/box-settings-except-for.png "Box 設定除外")  
  
    > [!NOTE]  
    >  如果您是現有的 Adallom 客戶，而主控台 URL 是供 Adallom 非供 Cloud App Security 使用，請使用這個應用程式序號︰bwahmilhdlpbqy2ongkl119o3lrkoshc。  
  
2.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
3.  在 [App 連線程式] 頁面中，按一下加號按鈕並選取 [Box]。  
  
     ![連接 Box](./media/connect-box.png "連接 Box")  
  
4.  在 [Box settings]\(Box 設定) 快顯視窗中，按一下 [連入此連結]。  
  
5.  Box 的登入頁面隨即開啟。 輸入您的認證，允許 Cloud App Security 存取您小組的 Box 應用程式。  
  
6.  Box 會詢問您是否要允許 Cloud App Security 存取小組資訊及活動記錄檔，並以小組成員的身分執行活動。 若要進行，請按一下 [允許]。  
  
7.  返回 Cloud App Security 入口網站時，您應該會收到訊息，指出已順利連接 Box。  
  
8.  按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
現在，Box 已連接到 Cloud App Security。  
 
連接 Box 之後，您會收到連線前 60 天的事件。
  
連接 Box 之後，Cloud App Security 即會執行完整掃描。 根據您擁有的檔案與使用者數量而定，完整掃描可能需要一段時間才能完成。 為了啟用近乎即時的掃描，系統會將偵測到活動的檔案移動到掃描佇列的開頭。 例如，系統會立即掃描被編輯、更新或共用的檔案，這些檔案並不需要等待標準的掃描流程。 近乎即時的掃描並不適用於實際上並未修改的檔案。 例如，已檢視、預覽、列印或匯出的檔案，會依標準的掃描排程進行掃描。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  