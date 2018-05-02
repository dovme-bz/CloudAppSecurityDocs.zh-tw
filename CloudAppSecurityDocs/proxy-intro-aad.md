---
title: 使用 Microsoft Cloud App Security Proxy 防護 | Microsoft Docs
description: 本主題提供 Cloud App Security Proxy 如何運作的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 35a43120-bf67-4cf9-9b48-ebe157dbbd18
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 94e92c75aab62216d8eb374d584ff369e7cb6a2f
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


# <a name="protect-apps-with-microsoft-cloud-app-security-proxy"></a>使用 Microsoft Cloud App Security Proxy 防護應用程式

> [!NOTE]
> 這是預覽功能。


在現今的工作地點，在事件發生之後才知道雲端環境中發生事件通常不夠，您希望在員工有意或無意讓資料與組織面臨風險之前，就能夠即時阻止入侵與洩漏。 讓組織中的使用者充分利用雲端應用程式提供的服務和工具，並可攜帶自己的裝置來工作，極其重要。 同時，您還需要有工具幫助您保護組織，即時防止發生資料外洩以及資料遭竊的情況。 搭配 Azure Active Directory，Microsoft Cloud App Security Proxy 讓您體驗這些功能的全面整合。

## <a name="how-it-works"></a>運作方式

Cloud App Security Proxy 整合了 Azure AD 條件式存取。 Azure AD 條件式存取可讓您根據特定條件，強制執行對組織中應用程式的存取控制。 這些條件會定義條件式存取原則套用的「對象」(例如使用者或使用者群組)、「內容」(哪些雲端應用程式) 和「位置」 (哪些位置和網路)。 決定條件之後，您可以將使用者路由至可套用存取和工作階段控制的 Cloud App Security Proxy。

在使用者路由至 Cloud App Security Proxy 之後，即可根據存取和工作階段原則即時監視與控制他們的應用程式存取和工作階段。 Cloud App Security 入口網站內使用存取和工作段原則來進一步細化篩選並設定要對使用者採取的動作。 使用存取和工作階段原則，您可以：

-   **封鎖下載**：您可以封鎖下載機密文件。 例如，未受管理的裝置。

-   **保護下載**：不封鎖下載機密文件，但可要求加密下載以保護文件。 這樣可以在資料下載至不受信任的裝置時，確保文件受到保護並驗證使用者的存取權。 

-   **限制非企業網路的使用者工作階段**：使用者可以從不屬於公司網路的位置存取受保護的應用程式，但限制其存取，並封鎖或保護下載敏感性資料。

-   **監視低度信任使用者工作階段**：當高風險的使用者登入應用程式時會受到監視，其在工作階段中的動作也會予以記錄。 您可以調查及分析使用者的行為，以了解未來應該在什麼位置及什麼情況下套用工作階段原則。 

- **封鎖存取**：您可以完全封鎖來自不受控裝置或來自非企業網路的使用者，使其無法存取特定的應用程式。


### <a name="how-session-control-works"></a>工作階段控制如何運作

Proxy 工作階段控制的建置基礎是條件式存取。 控制應用程式存取之後，您可以將使用者工作階段重新導向至 Proxy 的工作階段控制，而不是直接導向至應用程式。 從此之後，使用者的要求和回應都會先經過 Proxy，而不是直接進入應用程式。

為了讓使用者留在工作階段中，Proxy 會使用 Proxy URL 取代應用程式工作階段內所有相關的 URL、Java 指令碼和 Cookie。 例如：如果應用程式傳回的頁面包含以 myapp.com 結尾的網域連結，Proxy 就會使用以類似 myapp.com.cas.ms 結尾的網域取代這些連結 

這個方法不需要在裝置上安裝任何項目。 這非常適合用來監視未受管理裝置的工作階段。 

透過 Proxy 導向工作階段之後，Proxy 就可以執行下列作業：
1. 檢查使用者活動的流量
3. 在雲端應用程式 Proxy 入口網站中顯示已識別的活動
2. 儲存與分析流量記錄
3. 讓管理員匯出流量記錄
4. 對工作階段強制執行原則

## <a name="managed-device-identification"></a>識別受管理的裝置

Proxy 可讓您建立能夠考量裝置是否受管理的原則。 為識別裝置是否受管理，Proxy 會利用：

-   相容的裝置 
-   已加入網域的裝置 
-   用戶端憑證部署
 
 
### <a name="compliant-and-domain-joined-devices"></a>相容且加入網域的裝置
Azure AD 條件式存取可以直接將相容且加入網域的裝置資訊傳遞至 Cloud App Security Proxy。 此時，可使用裝置狀態作為篩選，開發存取原則或工作階段原則。
如需詳細資訊，請參閱 [Azure Active Directory 中的裝置管理簡介](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。 

### <a name="client-certificate-authenticated-devices"></a>使用用戶端憑證驗證的裝置

Proxy 裝置識別機制可要求使用用戶端憑證驗證相關裝置。 這可讓您利用組織中已部署的現有用戶端憑證，或推出受管理裝置的新用戶端憑證，然後使用這些憑證設定存取與工作階段原則。 如需如何部署用戶端憑證的資訊，請參閱[部署 Azure AD 應用程式的 Proxy](proxy-deployment-aad.md)。
 
## <a name="supported-apps-and-clients"></a>支援的應用程式和用戶端

Proxy 目前支援在 Azure AD 中設定使用 SAML 單一登入的應用程式。 

> [!NOTE]
> - Proxy 也支援使用識別提供者所設定的應用程式，不是私人預覽之 Azure AD 設定的應用程式。 如需私人預覽的詳細資訊，請傳送電子郵件至 mcaspreview@microsoft.com。
> - Office 365 應用程式不設定使用 SAML，所以目前不受支援。

所有主要平台上的任何瀏覽器都能使用工作階段控制項 (目前不支援行動應用程式及桌面應用程式)。 因為是以 Azure AD 原生規格整合到 AD，所以可以支援所有在 Azure AD 中設定了 SAML 單一登入的應用程式，包括下列精選應用程式：

-   Salesforce

-   方塊

-   G Suite

-   Workday

-   Slack

-   Workplace by Facebook

-   ServiceNow

-   JIRA/Confluence

-   AWS

-   Workiva

-   CornerStone on Demand

-   DocuSign

-   HighQ 

工作階段控制項將陸續支援更多的應用程式。 若您要使用的應用程式不在上列支援對象之中，您可以[將應用程式的詳細資料傳送給我們](mailto:casfeedback@microsoft.com)，並附上相關使用案例，我們會將該應用程式加入支援之列。




## <a name="see-also"></a>另請參閱  
[部署 Cloud App Security Proxy](proxy-deployment-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  


