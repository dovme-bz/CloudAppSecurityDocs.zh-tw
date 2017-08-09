---
title: "部署 Cloud App Security Proxy | Microsoft Docs"
description: "本主題提供如何部署 Cloud App Security Proxy 的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 75094bde-e135-47fb-b5c6-7e1168919771
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 245e44cdf56b15795f67340442babcb0f688ea9d
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/03/2017
---
# <a name="deploying-the-cloud-app-security-proxy"></a>部署 Cloud App Security Proxy

> [!NOTE]
> 強烈建議您在生產環境中安裝之前，先嘗試在沙箱或測試環境中安裝。

若要部署 Cloud App Security Proxy，並啟用存取控制及工作階段控制，必須採取如下所述的步驟。

## <a name="prerequisites"></a>必要條件

-   您的雲端應用程式已設定識別提供者的工作環境。 安裝程序會牽涉到應用程式和識別提供者兩者中的組態變更。
- 請確定您可以存取識別提供者和應用程式兩者中的單一登入設定。

## <a name="deploy-the-proxy"></a>部署 Proxy

如果您要在生產環境中安裝 Proxy，我們建議您找出大部分使用者不使用應用程式的時間 (通常是半夜或週末)，並通知您的使用者可能會有短暫的應用程式停機時間。

開始進行組態變更之前，請先檢查您目前的設定可正常運作。 確認之後，請執行下列步驟。

1.  在 Cloud App Security 入口網站中，移至 [設定] 齒輪，選擇 [Proxy]。

2. 在右上角，按一下加號。

3. 在 [將應用程式新增到 Proxy] 視窗中，選取您想要新增的應用程式，然後按一下 [啟動精靈]。 

 ![將應用程式新增到 Cloud App Security Proxy](./media/proxy-add-app.png)

4. 從應用程式的單一登入設定上傳單一登入中繼資料檔案。 如果您沒有中繼資料檔案，請按一下 [手動填入資料] 並根據精靈提供要求的資料。 

 ![將單一登入中繼資料檔案新增到 Cloud App Security Proxy](./media/proxy-w-add-app.png)


5. 在您的識別提供者入口網站中，執行下列步驟。 在大部分識別提供者入口網站中，這會在 [應用程式] 下執行：

    1. 建立新的自訂 SAML 應用程式。 因為您必須變更 URL，以及新增 SAML 屬性，而這些動作無法在資源庫應用程式中進行，因此您必須建立新的自訂應用程式。
    
    2. 將單一登入組態從識別提供者清單的現有應用程式複製到新的自訂應用程式。 確定自訂應用程式中的 [識別碼] (也就是對象或實體 ID) 符合實際應用程式之單一登入設定的 [識別碼]。 如果您的識別提供者不讓您在兩個不同的應用程式使用相同的 [識別碼]，請在複製之後，變更原始應用程式的識別碼。
    
    3. 將目前指派給原始應用程式的所有使用者，指派給新的自訂應用程式。
    
    ![將單一登入中繼資料檔案新增到 Cloud App Security Proxy](./media/proxy-w-add-external-config.png)

5. 從識別提供者上傳單一登入中繼資料檔案。 如果您沒有中繼資料檔案，請按一下 [手動填入資料] 並根據精靈提供要求的資料。  

 ![將單一登入中繼資料檔案新增到 Cloud App Security Proxy](./media/proxy-w-identity-provider.png)

6. 在您的識別提供者入口網站中執行下列外部組態變更，然後在您建立的新自訂應用程式中：

    1. 複製精靈中提供的 URL。 然後，移至您的識別提供者入口網站，在您建立的新自訂 SAML 應用程式中貼上 URL 作為單一登入 URL (或回覆 URL)。
    
    2. 複製 Proxy 精靈中提供的屬性和值，並將它們新增為 SAML 自訂屬性。
    
    3. 確定您的應用程式所使用的名稱識別碼是電子郵件地址格式，Cloud App Security Proxy 才能對使用者強制執行原則。
    
    4. 儲存新自訂應用程式的設定，然後在 Proxy 精靈中按 [下一步]。
 ![在 Cloud App Security Proxy 中更新識別提供者設定](./media/proxy-w-ip-external2.png)

4.  然後，在應用程式的單一登入設定頁面上，執行下列作業：
    1. 備份目前的應用程式設定。
    
    2. 從 Proxy 精靈將 URL 複製到應用程式的 SAML 單一登入 URL。
    
    3. 下載應用程式的 Cloud App Security SAML 憑證。
    
    4. 在您建立的自訂應用程式中，上傳此 SAML 憑證來取代原始的憑證並儲存您的設定。
   
    5. 在 Proxy 精靈中，按一下 [完成]。


在幾分鐘內，對應用程式的所有要求記錄，都會透過 Cloud App Security Proxy 路由傳送。 



### <a name="test-the-configuration"></a>測試組態

1.  嘗試登入應用程式。 如果登入失敗，請確定您正確地完成所有 Proxy 精靈步驟。 

2.  在 Cloud App Security 入口網站中的 [調查] 下，選取 [活動記錄]，確定 Proxy 擷取到 [單一登入式登入] 事件。



## <a name="see-also"></a>另請參閱  
[使用 Cloud App Security Proxy](proxy-intro.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  