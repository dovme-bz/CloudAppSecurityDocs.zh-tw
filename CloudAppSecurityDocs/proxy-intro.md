---
title: "使用 Cloud App Security Proxy | Microsoft Docs"
description: "本主題提供 Cloud App Security Proxy 如何運作的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 28317b70-1851-4610-b1d6-863bc5994bb6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 82e1ee0b5161dce88db815dc8eea06340bdbc532
ms.sourcegitcommit: f9851779aa15b11f559e56ac818f1333f027c000
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2017
---
# <a name="working-with-the-cloud-app-security-proxy"></a>使用 Cloud App Security Proxy

在現今的工作地點，在事件發生之後才知道雲端環境中發生事件通常不夠，您希望在員工有意或無意讓資料與組織面臨風險之前，就能夠即時阻止入侵與洩漏。 您必須要能夠讓您組織中的使用者，充分利用雲端應用程式提供的服務和工具，並允許他們攜帶自己的裝置來工作。 同時，您還需要工具來幫助保護您的組織，防止發生資料外洩、勒索軟體攻擊以及大量資料被竊取的情況。 

## <a name="introducing-the-cloud-app-security-proxy"></a>介紹 Cloud App Security Proxy
Cloud App Security 的 Proxy 提供您執行即時監視、控制雲端環境的存取，以及控制在其中執行之活動的存取所需的工具。
您可以使用 Cloud App Security Proxy 保護您的組織：
- 在下載發生之前就加以封鎖，避免資料外洩
- 透過管理和封鎖沒有密碼保護或沒有安裝防毒軟體的未受管理裝置存取您的網路，降低受到勒索軟體侵害的風險
- 設定儲存在雲端的資料以及從雲端下載的資料，強制使用加密保護的規則
- 可以看見未受保護的端點，以便您能監視未受管理的裝置上正在進行的活動
- 控制來自高風險 IP 位址和傳統識別提供者的存取

若要啟用這些獨特功能，請使用 Proxy 提供的兩個控制層級：存取控制和工作階段控制。 這兩種類型的控制都會運用使用者資訊、位置資訊和裝置資訊 (用來識別哪些裝置是受管理的裝置和未受管理的裝置)，來決定每個應用程式的原則。

### <a name="access-control"></a>存取控制
<more information about what is access control including examples> Proxy 的存取控制可讓您為雲端應用程式建立功能強大的存取原則，並提供下列功能：

若要使用 Cloud App Security 中的存取控制，請對您現有的識別提供者組態進行一些變更來部署 Proxy，並設定原則來控制您的雲端應用程式。 

> [!NOTE]
> -  不需要變更識別提供者的現有原則。

#### <a name="supported-apps-and-identity-providers"></a>支援的應用程式和識別提供者

Proxy 的存取控制是針對支援 SAML 或 WS-同盟通訊協定的任何應用程式和任何識別提供者而設計。 Cloud App Security 小組針對領導級的識別提供者和應用程式測試存取控制功能。 不過，因為有很多識別提供者和很多雲端應用程式，所以並未針對每一種識別提供者和應用程式的組合進行測試。 我們建議您先在沙箱或測試環境中針對您的識別提供者和應用程式測試單一登入程序，再將它部署在生產環境中。

### <a name="session-control"></a>工作階段控制

工作階段控制是 Proxy 提供的額外控制層。 它可對您的雲端應用程式進行更細微而即時的控制。 您並不是設定地毯式原則以允許或封鎖特定應用程式的存取，而是可以允許存取，然後同時監視應用程式中的每個使用者工作階段，以各種方法限制存取。 例如，您可以決定針對來自特定裝置或來自特定位置的工作階段，允許使用者存取應用程式，但限制下載機密檔案。

#### <a name="supported-apps-and-flows"></a>支援的應用程式和流程

目前，工作階段控制可讓您封鎖在 Salesforce.com 中下載檔案和匯出報告。 您可以根據使用者、位置和裝置，以及根據您想要下載的內容來建立原則。

此外，此版本也支援限制使用者從瀏覽器登入的工作階段數目。 例如，如果您想要限制來自原生應用程式的工作階段存取，則必須定義存取原則來封鎖當 [使用者代理程式標籤] 篩選等於 [原生用戶端] 時的這類存取。

Salesforce 已經過所有一般流程的測試。 不過，由於 Salesforce 有許多第三方應用程式，因此可能有一些第三方應用程式並未經過測試而無法使用工作階段控制，甚至造成一些網頁無法運作。 若要驗證這確實是第三方應用程式的問題，請移除所有第三方應用程式，然後測試應用程式的工作階段控制。 如果一切運作良好，請一次新增一個第三方應用程式，直到您找出有問題的應用程式。 

## <a name="device-management"></a>裝置管理

Cloud App Security 可讓您根據裝置狀態識別並建立 Proxy 原則。 為了識別裝置是否受管理，Cloud App Security 會利用「用戶端憑證」機制，用戶端憑證都會以這個機制部署在您組織中受管理的裝置上。 使用者登入應用程式之後，需要提供安裝在裝置上的用戶端憑證。 如果提供用戶端憑證，Cloud App Security 會將裝置視為受管理。 
> [!NOTE]
>  使用者可能選擇拒絕傳送用戶端憑證，在此情況下，裝置會被視為未管理。
<好了，現在您知道裝置是否受管理，那要怎麼處理？>

### <a name="supported-browsers-and-native-apps"></a>支援的瀏覽器和原生應用程式

Cloud App Security Proxy 可讓您... 根據用戶端憑證...

用戶端憑證是瀏覽器開發人員和原生應用程式開發人員可決定是否實作的已知機制。 大部分平台上的大部分瀏覽器都支援它，但原生應用程式中的狀況則較複雜。

原生應用程式 (包括桌面應用程式和行動應用程式兩種) 的用戶端憑證支援，有時可能會根據平台，甚至是裝置的狀態而有所不同。 例如，在 Salesforce1 (Salesforce 行動應用程式) 中，用戶端憑證只有在裝置上已部署 MDM，且 Salesforce1 已設定為傳送用戶端憑證時才能運作。

用戶端憑證已在最新版本的 Windows、OSX、Android 和 iOS 上的 Internet Explorer、Edge、Chrome、Safari 和 Firefox (各有相關的瀏覽器) 上成功通過測試。

> [!NOTE]
> 在 iOS 中，只有 Safari 瀏覽器可以使用用戶端憑證。

即使在瀏覽器或原生應用程式支援用戶端憑證的情況下，也可能會發生一些使用者在提供憑證時出現問題的狀況，例如，如果使用者拒絕傳送用戶端憑證一次，瀏覽器或原生應用程式可能會記住選擇，而不再提示使用者提供憑證。 若要解決這類問題，我們建議先關閉所有開啟的瀏覽器執行個體，然後開啟新的，或清除所有 Cookie 後再試一次。

相反地，有某些瀏覽器和原生應用程式可以選擇隱藏要求用戶端憑證的快顯，而會改為自動傳送用戶端憑證。

一般而言，我們建議您測試使用者的用戶端憑證要求，但只在監視模式下才強制執行原則。 您可以建立 [僅限記錄] 原則來進行，以識別受管理的裝置。

## <a name="architecture"></a>架構

Proxy 與您的識別提供者和應用程式兩者整合，而且兩者都必須設定為將登入要求重新導向至 Proxy。

此外，為了識別受管理的裝置，Proxy 可以向受管理的裝置要求用戶端憑證。 Proxy 收到用戶端憑證之後，裝置就會被視為受管理，針對受管理的裝置和未受管理的裝置的原則才會生效。

如需有關部署程序的詳細資訊，請參閱＜部署＞一節。

![Cloud App Security Proxy 架構](./media/proxy-architecture.png)

## <a name="user-login-flow"></a>使用者登入流程

上圖說明從識別提供者開始的登入，也稱為*識別提供者起始的登入*。 如果使用者從應用程式開始，這稱為*服務提供者起始的登入*，接下來會被導向至 Cloud App Security Proxy，Cloud App Security Proxy 再將使用者導向至識別提供者，登入程序的其餘部分類似*識別提供者起始的登入*流程。

這是*識別提供者起始的登入*流程：
-   使用者傳送要求給識別提供者，並提供認證

-   如果允許存取，識別提供者會將使用者重新導向至 Cloud App Security Proxy

-   如果使用者已安裝用戶端憑證，而且有相關的原則會檢查是受管理或未受管理的裝置，則系統會提示使用者提供用戶端憑證。 無論是哪一種，都會評估存取原則

-   此時，有 3 種可能的選項：

    -   允許使用者存取應用程式

    -   封鎖使用者存取應用程式

    -   允許使用者存取應用程式，但是是在受監視的模式下

        -   在此情況下，使用者會再次被重新導向到 Cloud App Security Proxy，Cloud App Security Proxy 負責監視使用者與應用程式之間的整個工作階段

        -   監視時，Proxy 會評估工作階段原則，並據此執行封鎖動作

## <a name="how-access-control-works"></a>存取控制如何運作

在部署 Proxy 時，您必須在識別提供者和您要控制的應用程式兩者中變更組態。 這包含變更 URL，以便讓識別提供者和應用程式會將登入要求重新導向至 Proxy。 此外，如有需要，請同時取代憑證。

完成這些步驟之後，所有登入事件都會經過 Proxy，而 Proxy 可以決定是否允許這些事件存取應用程式、拒絕存取，或允許在受監視的模式下存取。 請注意在這個階段，Proxy 可以向裝置要求用戶端憑證，並使用裝置的狀態來決定原則。

## <a name="how-session-control-works"></a>工作階段控制如何運作

Proxy 的工作階段控制是以存取控制為基礎而建置。 一旦您控制應用程式的存取，就可以將 Proxy 的工作階段重新導向至其工作階段控制，以便根據存取原則來決定監視工作階段。 從此之後，使用者的要求和回應都會先經過 Proxy，而不是直接進入應用程式。

為了讓使用者留在工作階段中，Proxy 會將應用程式內所有相關的 URL、Java 指令碼和 Cookie 取代為 Proxy 中重複的頁面。 例如：如果應用程式傳回的頁面包含以 *myapp.com* 結尾的連結，Proxy 會將它們取代為以類似 *myapp.com.cas.ms* 結尾的頁面。

一旦工作階段透過 Proxy 導向，Proxy 就可以檢查流量、顯示在 Cloud App Proxy 入口網站中識別的事件，然後對工作階段強制執行原則。

## <a name="how-identifying-managed-devices-works"></a>識別受管理的裝置如何運作

Proxy 會使用用戶端憑證的機制，來識別受管理的裝置。 機制的運作方式如下：

-   如果使用者已在裝置上安裝用戶端憑證，而且有相關的原則會檢查是受管理或未受管理的裝置。

    -   當使用者在登入階段到達 Proxy 頁面時，Proxy 會向使用者的裝置要求用戶端憑證。

    -   系統會提示使用者裝置提供用戶端憑證，如果使用者核准，用戶端憑證就會傳送至 Proxy。

    -   Proxy 接著會根據管理員所提供的根憑證，驗證用戶端憑證。

    -   如果裝置所提供的用戶端憑證成功通過根憑證的驗證，裝置會被視為受管理。

-   如果未完成上述任何一個階段，則裝置會被視為未管理。



## <a name="see-also"></a>另請參閱  
[Proxy 部署](proxy-deployment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  