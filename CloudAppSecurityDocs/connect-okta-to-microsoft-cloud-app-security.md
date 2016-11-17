---
title: "將 Okta 連接至 Microsoft Cloud App Security | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Okta 連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 759692e7b270d87dc1becf88453d095f2382c411
ms.openlocfilehash: 3fd8ada1ce622da339368c64ecc8b1d319b9c333


---

# <a name="connect-okta-to-microsoft-cloud-app-security"></a>將 Okta 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用連接器 API，將 Cloud App Security 連接至您現有的 Okta 帳戶。  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>如何將 Okta 連接至 Cloud App Security  
  
1.  建議您在 Okta 中為 Cloud App Security 建立系統管理服務帳戶。  
  
     確定您使用具有進階管理員權限的帳戶。  
  
     確定您的 Okta 帳戶已驗證。  
  
2.  在 Okta 主控台中，按一下 [系統管理]。  
  
    -   按一下 [安全性]，然後按一下 [API]。  
  
         ![okta api](./media/okta-api.png "okta api")  
  
    -   按一下 [建立權杖]。  
  
         ![okta createtoken](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   在 [建立權杖] 快顯視窗中，命名您的 Cloud App Security 權杖，然後按一下 [建立權杖]。  
  
         ![okta 權杖快顯視窗](./media/okta-token-popup.png "okta token popup")  
  
    -   在 [Token created successfully (已成功建立權杖)] 快顯視窗中，複製 [Token value (權杖值)]。  
  
         ![okta 權杖值](./media/okta-token-value.png "okta token value")  
  
3.  在 Cloud App Security 主控台中，依序按一下 [調查] 和 [獲批准的應用程式]。  
  
4.  在 Okta 列中，按一下 [App 連線程式狀態] 欄位中的 [連線]，或按一下 [連線到應用程式] 按鈕，然後按一下 [Okta]。  
  
     ![連接 okta](./media/connect-okta.png "connect okta")  
  
5.  在 [API] 頁面的 [網域] 欄位中，輸入您的 Okta 網域並將權杖貼到 [權杖] 欄位。  
  
6.  按一下 [連線] 在 Cloud App Security 中建立 Okta 的權杖。  
  
7.  按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
連接 Okta 之後，您會收到連線前 60 天的事件。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO3-->


