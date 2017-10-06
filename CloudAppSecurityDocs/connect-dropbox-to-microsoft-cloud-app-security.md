---
title: "連接 Dropbox 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Dropbox 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4acd93f4-b885-4e1f-a385-43b5db02a3ee
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 56195253a603671d2f273616b652f5d821e80a51
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2017
---
# <a name="connect-dropbox-to-microsoft-cloud-app-security"></a>將 Dropbox 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用連接器 API，將 Cloud App Security 連接至您現有的 Dropbox 帳戶。  
 
 
由於 Dropbox 可讓您透過共用連結存取檔案而不需登入，因此 Cloud App Security 會將這些使用者註冊為「未驗證的使用者」。 若您看到未驗證的 Dropbox 使用者，可能表示使用者不是來自您的組織，也可能是來自組織內未登入但可辨識的使用者。

## <a name="how-to-connect-dropbox-to-cloud-app-security"></a>如何將 Dropbox 連接至 Cloud App Security  
  
1.  在 Cloud App Security 主控台中，依序按一下 [調查] 和 [連線應用程式]。  
  
2.  在 [App 連線程式] 頁面中，依序按一下加號按鈕及 [Dropbox]。  
  
     ![連接 Dropbox](./media/connect-dropbox.png "連接 Dropbox")  
  
3.  在快顯視窗中，輸入系統管理員帳戶的電子郵件地址。  
  
4.  按一下 [產生連結]。  
  
5.  按一下 [連入此連結]。  
  
     Dropbox 的登入頁面隨即開啟。 輸入您的認證，允許 Cloud App Security 存取您小組的 Dropbox 執行個體。  
  
6.  Dropbox 會詢問您是否要允許 Cloud App Security 存取小組資訊及活動記錄檔，並以小組成員的身分執行活動。 若要進行，請按一下 [允許]。  
  
7.  返回 Cloud App Security 主控台時，您應該會收到訊息，指出已順利連接 Dropbox。  
  
8.  按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
連接 Dropbox 之後，您會收到連線前 60 天的事件。

> [!NOTE] 
> Cloud App Security 會將任何 Dropbox 的新增檔案事件顯示為「上傳檔案」，以與連線至 Cloud App Security 的其他所有應用程式保持一致。 
 
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  \(英文\)。  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  