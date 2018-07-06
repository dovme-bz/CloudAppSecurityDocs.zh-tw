---
title: Cloud App Security 的新功能 | Microsoft Docs
description: 本主題會經常更新，讓您知道最新版 Cloud App Security 的新功能。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/24/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: bec87e3db09ee14320371cfbffba0d3d9a2cd55a
ms.sourcegitcommit: 49a06f2169af74304eef0288e31783c06ccd3b74
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2018
ms.locfileid: "36747046"
---
*適用於：Microsoft Cloud App Security*


# <a name="whats-new-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的新功能


## <a name="cloud-app-security-release-126"></a>Cloud App Security 版本 126

發行日期：2018 年 6 月 24 日

-   **條件式存取應用程式控制已正式運作**<br>Microsoft Cloud App Security 的條件式存取應用程式控制 (反向 Proxy) 現已正式運作，可供任何 SAML 應用程式使用。 條件式存取應用程式控制直接與您的 Azure AD 條件式存取原則整合，以**即時監視及控制您使用者的工作階段**，同時讓他們提高產能。 從首次預覽功能起，就提供許多功能和改善，包括： 
    -   除了為瀏覽器流量建立工作階段原則之外，還有建立[存取原則](access-policy-aad.md)的功能，可管理原生用戶端對相同應用程式的存取。
    -   簡化了應用程式上架程序，以支援組織中的自訂 SAML 應用程式。
    -   作為 Azure 全球網路的一部分，已改進整合和介面，以為世界各地的使用者提供無縫體驗。
 

-   **使用 Microsoft 資料分類服務檢查內容已正式運作**<br>Microsoft Cloud App Security 與 Microsoft 資料分類服務的整合現已正式運作。 這項整合可讓您原生利用 Microsoft 資料分類服務，以分類雲端應用程式中的檔案。 如需詳細資訊，請參閱 [Microsoft 資料分類服務整合](dcs-inspection.md)。

- **Cloud Discovery 執行報告**<br>Microsoft Cloud App Security 正逐步推出產生 Cloud Discovery 執行 PDF 報告的功能。 此報告概述在您組織中找到的影子 IT 使用，特別說明整體使用上和主要類別中前幾名的應用程式和使用者，並著重影子 IT 對組織造成的風險。 此外，其亦提供建議清單，說明如何改進和控制組織中影子 IT 的可見度。 使用此報告可確保移除潛在風險和威脅，以及確保您的組織保持安全。

-   **惡意程式碼偵測**<br>我們正逐漸推出惡意程式碼偵測功能，這可**自動偵測您雲端儲存體中的惡意檔案**，不論檔案類型為何。 Microsoft Cloud App Security 使用 Microsoft 的威脅情報辨識出某些檔案是否與已知的惡意程式碼攻擊有關，或是否可能為惡意檔案。 如需詳細資訊，請參閱[異常偵測原則](anomaly-detection-policy.md)。
 
-   **可疑活動的自動化補救**<br>您現在可以為異常偵測原則觸發的可疑工作階段設定自動補救動作。 這項增強功能可讓您在缺口發生時，立即收到警示，並**自動套用管理動作**，例如將使用者暫時停權。 如需詳細資訊，請參閱[異常偵測原則](anomaly-detection-policy.md#adp-automated-gov)。 
 
-   **Azure 的安全性設定評定**<br>Microsoft Cloud App Security 正逐步推出取得您 Azure 環境安全性設定評定的功能，以及提供遺失設定和安全性控制的建議。 例如，它可讓您知道您是否缺少系統管理使用者的 MFA。 如需詳細資訊，請參閱[雲端安全性狀態管理整合](security-config.md)。  
  
-   **自動偵測具風險的 OAuth 應用程式**<br>除了連線到您環境之 OAuth 應用程式的現有調查，Microsoft Cloud App Security 亦在逐步推出設定自動化通知的功能，以讓您知道 OAuth 應用程式何時符合特定準則。 例如，您可在應用程式需要高權限層級，並已獲 50 位以上的使用者授權時，自動收到警示。 如需詳細資訊，請參閱[應用程式權限原則](app-permission-policy.md)。
 
-   **受控安全性服務提供者管理 (MSSP) 支援**<br>Microsoft Cloud App Security 現可提供較好的 MSSP 管理體驗。 您現在可將外部使用者設定為系統管理員，並予以指派 [Microsoft Cloud App Security 中目前可用的任何角色](manage-admins.md)。 此外，若要讓 MSSP 跨多個客戶租用戶提供服務，具有多個租用戶存取權的系統管理員現在可以在入口網站內輕鬆切換租用戶。 如需管理系統管理員的資訊，請參閱[管理系統管理員](manage-admins.md)。
  
-   **與外部 DLP 整合已正式運作**<br>Microsoft Cloud App Security 可讓您[運用協力廠商分類系統中的現有投資](icap-stunnel.md) (例如資料外洩防護 (DLP) 解決方案)，且可讓您使用環境中執行的現有部署，掃描雲端應用程式的內容。 如需詳細資訊，請參閱[外部 DLP 整合](icap-stunnel.md)。


## <a name="cloud-app-security-release-125"></a>Cloud App Security 版本 125

發行日期：2018 年 6 月 10 日


- **新的調查功能 (依前幾名使用者)：**<br>
Microsoft Cloud App Security 在儀表板上新增了新的調查功能小工具，可根據開啟威脅偵測警示的數目來顯示排名在前幾位的使用者。 這個調查小工具可讓您將威脅調查專注於擁有最大可疑工作階段數目的使用者。

- **AWS S3 儲存貯體的支援：**<br>
Microsoft Cloud App Security 現在可以偵測 AWS S3 貯體及其共用層級。 如此對於可公開存取的 AWS 貯體可提供警示與可見度。 這也讓您可根據貯體來建立原則，以及套用自動治理。 此外，還有稱為**可公開存取的 S3 貯體 (AWS)** 的新原則範本，可用來輕鬆地建立原則來治理您的 AWS 儲存體。 為了啟用這些新功能，請務必如[連線 AWS](connect-aws-to-microsoft-cloud-app-security.md) 中所述來新增新的權限，以確認更新了連線到 AWS 的應用程式。

- **依使用者群組設定的系統管理權限**：您現在可以根據使用者群組設定 Microsoft Cloud App Security 系統管理員的系統管理權限。 例如，您可以僅針對在德國的使用者，將特定的使用者設定為系統管理員。 這樣只有該使用者能夠針對使用者群組 [德國 - 所有使用者] 以檢視和修改 Microsoft Cloud App Security 中的資訊。 如需詳細資訊，請參閱[管理管理員存取權](manage-admins.md)。


## <a name="cloud-app-security-release-124"></a>Cloud App Security 版本 124

發行日期：2018 年 5 月 27 日

-   **新增至雲端應用程式類別目錄的 GDPR 風險評估**<br>
Microsoft Cloud App Security 新增了 13 個新的風險因素。 這些風險因素遵循 GDPR 架構檢查清單，可讓您根據 GDPR 規定評估雲端應用程式類別目錄中的應用程式。

-   **與 Microsoft 資料分類服務整合**<br>
現在，Microsoft Cloud App Security 讓您能夠以原生方式利用 Microsoft 資料分類服務，以便對雲端應用程式中的檔案進行分類。 <br>
Microsoft 資料分類服務為 Office 365、Azure 資訊保護和 Microsoft Cloud App Security 提供統一的資訊保護體驗。 它允許您將相同的資料分類架構延伸到受 Microsoft Cloud App Security 保護的協力廠商雲端應用程式，利用您在眾多應用程式中做出的決策。 

-   **連線到 Microsoft Azure** (逐步推出)<br>
Microsoft Cloud App Security 正在將其 IaaS 監視功能延伸到 Amazon Web Services 之外，且現在支援 Microsoft Azure。 這可讓您使用 Cloud App Security 順暢地連線及監視所有 Azure 訂用帳戶。 此連線會為您提供一組強大的工具來保護您的 Azure 環境，其中包括： 

       -    透過入口網站所執行全部活動的可見度

       -    能夠建立自訂原則以警示不想要的行為，以及能夠將潛在高風險使用者暫停或強制再次登入以自動保護這些使用者。

       -    Azure 的所有活動均由我們的異常偵測引擎涵蓋，並會自動警示 Azure 入口網站中任何可疑的行為，例如不可能的移動、可疑的群體活動以及來自新國家/地區的活動。<br>

  如需詳細資訊，請參閱[將 Azure 連線至 Microsoft Cloud App Security](connect-azure-to-microsoft-cloud-app-security.md)。
 
-   **限定範圍的部署** (逐步推出) <br>
Microsoft Cloud App Security 為企業提供根據群組成員資格，精細判斷他們想要監視及保護哪些使用者的功能。 此功能可讓您選取不會針對任何受保護的應用程式顯示活動的使用者。 限定範圍的監視功能特別適用於： 

    -   合規性 - 如果您的標準規定要求您根據當地法規不要監視特定國家/地區的使用者。

       -    授權 - 如果您希望監視較少的使用者，以維持在您的 Microsoft Cloud App Security 授權限制內。
   如需詳細資訊，請參閱[限定範圍的部署](scoped-deployment.md)。

-   **探索到的應用程式之安全性缺口應用程式警示**<br>
 我們現在有一個內建警示，會在發現任何租用戶探索到的應用程式遭到入侵時通知您。 警示將提供有關入侵的日期和時間資訊，哪些使用者使用該應用程式，並將連結至公開可用的來源，以提供有關安全性缺口的資訊。

-   **新的郵件伺服器**<br>
 Cloud App Security 的郵件伺服器已變更，並使用不同的 IP 位址範圍。 為確保您可以收到通知，請將新的 IP 位址加入您的反垃圾郵件白名單。 針對自訂通知的使用者，Microsoft Cloud App Security 可使用 MailChimp® (一種協力廠商電子郵件服務) 為您啟用。 如需郵件伺服器 IP 位址清單以及如何使用 MailChimp 的指示，請參閱[網路需求](https://docs.microsoft.com/cloud-app-security/network-requirements#email-server)和[郵件設定](mail-settings.md)。


## <a name="cloud-app-security-release-123"></a>Cloud App Security 版本 123

發行日期：2018 年 5 月 13 日

- **異常偵測原則範圍設定**：<br>
異常偵測原則現在可以設定範圍。 這可讓您設定每個異常偵測原則以只包含特定使用者或群組，並排除特定使用者或群組。 例如，您可以設定來自非經常性國家/地區活動的偵測，以忽略經常出差的特定使用者。 


## <a name="cloud-app-security-release-122"></a>Cloud App Security 版本 122
發行日期：2018 年 4 月 29 日

-   逐步推出：您現在可以**為每個應用程式的 Microsoft Cloud App Security 管理員設定系統管理權限**。 例如，您可以將特定使用者設為僅限於 G Suite 的管理員。 這可讓使用者檢視並修改 Microsoft Cloud App Security 中只與 G Suite 相關的資訊。 如需詳細資訊，請參閱[管理管理員存取權](manage-admins.md)。
- 逐步推出：**Okta 管理員角色現在可以於 Microsoft Cloud App Security 中看見**，而且可在 [設定] > [使用者群組] 下供每個角色使用作為標記。


## <a name="cloud-app-security-release-121"></a>Cloud App Security 121 版
發行日期：2018 年 4 月 22 日

-   **條件式存取應用程式控制 (先前稱為 Cloud App Security Proxy)** 的公開預覽版已透過可更深入掌握情況且可控制不同應用程式的功能增強。 您現在可以使用「活動類型」篩選來建立工作階段原則，以監視及封鎖各種不同的應用程式特定活動。 這個新篩選可加強現有的檔案下載控制功能，讓您可以全面控制組織中的應用程式，並和 Azure Active Directory 條件式存取一起使用，即時掌握及控制有風險的使用者工作階段，例如 B2B 共同作業使用者或來自非受控裝置的使用者執行的工作階段。 如需詳細資訊，請參閱[工作階段原則](session-policy-aad.md)。
-   逐步推出：Cloud App Security 的**異常偵測原則已經改善**，包括兩種新的威脅偵測類型：勒索軟體活動與離職使用者活動。 Cloud App Security 透過異常偵測來延伸其勒索軟體偵測功能，以確保防護複雜的勒索軟體攻擊涵蓋範圍更全面。 Cloud App Security 使用安全性研究專業知識來識別可反映勒索軟體活動的行為模式，進而保證可提供全面且強大的保護。 離職使用者活動可讓您監視離職使用者的帳戶，其帳戶可能已從公司應用程式解除佈建，但在許多情況下，仍會留有特定公司資源的存取權。 如需詳細資訊，請參閱[取得即時的行為分析和異常偵測](anomaly-detection-policy.md)。


## <a name="cloud-app-security-release-120"></a>Cloud App Security 版本 120
發行日期：2018 年 4 月 8 日

-   對於 Office 365 與 Azure AD，我們正在逐步推出一項功能，能夠在 Office 365 及 Azure AD 應用程式 (內外部應用程式皆適用) 執行使用者帳戶活動時，偵測到內部應用程式。 這使您得以建立警示原則，在應用程式執行未預期與未經授權的活動時向您發出警示。 
-   在將應用程式權限清單匯出至 csv 時，也包括了發行者、權限等級及社群使用方式等其他欄位，這有助於合規性與調查程序的進行。
-   改善已連線 ServiceNow 的應用程式，使內部服務活動不會再註記為「已經過來賓執行」，並且不會再觸發誤判警示。 這些活動現在會以其他已連線應用程式慣用的 N/A 表示。


## <a name="cloud-app-security-release-119"></a>Cloud App Security 版本 119
發行日期：2018 年 3 月 18 日

-   [IP 位址範圍] 頁面包括 Cloud App Security 探索到的內建 IP 位址。 其中有已識別的雲端服務 (例如 Azure 和 Office 365) IP 位址，還有威脅情報摘要，會自動為 IP 位址補充已知的具風險 IP 位址相關資訊。 
-   當 Cloud App Security 嘗試對檔案執行治理動作，但因檔案已鎖定而失敗時，現在會自動重試治理動作。 

## <a name="cloud-app-security-release-118"></a>Cloud App Security 118 版
發行日期：2018 年 3 月 4 日

- 您現在可針對自己專屬的自訂應用程式，以善用 Microsoft Cloud App Security 的影子 IT 探索和監視功能。 新增自訂應用程式到 Cloud Discovery 的新功能，可讓您監視應用程式的使用方式，並在使用模式變更時獲得警示。 如需詳細資訊，請參閱[保護自訂應用程式](cloud-discovery-custom-apps.md)。 這項功能正逐步推出。

- Cloud App Security 入口網站的 [設定] 頁面已重新設計。 新設計合併了所有設定頁面，提供搜尋功能和改良的設計。 

- Cloud Discovery 現在支援 Barracuda F-Series 防火牆和 Barracuda F-Series 防火牆 Web 記錄串流。

- 在 [使用者] 和 [IP 位址] 頁面的搜尋功能現在可自動完成，讓您更輕鬆地找到想要的項目。

- 您現在可在 [排除實體] 和 [排除 IP 位址設定] 頁面執行大量動作。 這可讓您更輕鬆地選取多個使用者和群組或 IP 位址，並將它們從您組織的 Cloud Discovery 監視當中排除。 

## <a name="cloud-app-security-release-117"></a>Cloud App Security 117 版
發行日期：2018 年 2 月 20 日

-   Cloud App Security 現在深入整合了 Azure 資訊保護，讓您可以保護 G Suite 中的檔案。 此公開預覽功能可讓您掃描與分類 G Suite 中的檔案，並自動套用 Azure 資訊保護標籤的保護。 如需詳細資訊，請參閱 [Azure 資訊保護整合](azip-integration.md)。

-   Cloud Discovery 現在支援 [Digital Arts i-FILTER](http://www.daj.jp/en/products/if/) \(英文\)。

-   SIEM 代理程式資料表現在包含更多詳細資料，以便於輕鬆管理。

## <a name="cloud-app-security-release-116"></a>Cloud App Security 版本 116
發行於 2018 年 2 月 4 日
- 新的**以案例為基礎的偵測**增強了 Cloud App Security 異常偵測原則，其中案例包括不可能的移動、來自可疑 IP 位址的活動，以及多次嘗試登入失敗。 新原則會自動啟用，為整個雲端環境提供立即可用的威脅偵測。 此外，新的原則會從 Cloud App Security 偵測引擎公開更多資料，以協助您加速調查程序，並遏制進行中的威脅。 如需詳細資訊，請參閱[取得即時的行為分析和異常偵測](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy)。

- 逐步推出：Cloud App Security 現在可跨 SaaS 應用程式以相互關聯使用者與其帳戶。 這可讓您輕鬆地跨越使用者所有各種相互關聯 SaaS 應用程式來調查他們的所有活動，而不論使用者所使用的應用程式或帳戶為何。  

-   逐步推出：Cloud App Security 現在支援相同已連線應用程式的多個執行個體。 例如，如果您有多個 Salesforce 的執行個體 (一個針對銷售，一個針對行銷)，則可以將兩者同時連線至 Cloud App Security 並從相同的主控台來管理，以建立更細微的原則和更深入的調查。 

- Cloud Discovery 剖析器現在支援 XML 和 KPC 兩個額外的檢查點格式。



## <a name="cloud-app-security-release-115"></a>Cloud App Security 115 版
發行日期：2018 年 1 月 21 日

- 此版本提供在檔案原則中選取特定資料夾時的增強體驗。 您現在可以輕鬆地檢視並選取多個要包含在原則中的資料夾。 
- 在 [探索到的應用程式] 頁面中： 
  - 大量標記功能可讓您套用自訂標籤 (除了獲批准的標籤和待批准的標籤)。 
  - 當您**產生 IP 位址報表**或**產生使用者報告**時，匯出的報表現在會包含流量是否來自獲批准或待批准應用程式的相關資訊。 
- 您現在可以在入口網站中的 [連線到應用程式] 頁面，直接向 Microsoft Cloud App Security 小組要求新的 API App 連線程式。 


## <a name="cloud-app-security-release-114"></a>Cloud App Security 版本 114
發行日期：2018 年 1 月 7 日

- 從 114 版開始，我們會逐漸推出在 [活動記錄] 和 [探索到的應用程式] 頁面中建立和儲存自訂查詢的功能。 自訂查詢可讓您建立篩選範本，可重複使用進行深入了解調查。 此外，已新增**建議的查詢**以提供立即可用的調查範本，篩選活動及探索到的應用程式。 **建議的查詢**包含識別風險的自訂篩選，例如模擬活動、管理員活動、危險的不相容雲端儲存體應用程式、使用弱式加密的企業應用程式，以及安全性風險。 您可以使用**建議的查詢**作為起點，在您認為合適時修改它們，然後儲存為新的查詢。 如需詳細資訊，請參閱[活動篩選與查詢](activity-filters-queries.md)和[探索到的應用程式篩選與查詢](discovered-app-queries.md)。
 
- 您現在可以前往 [status.cloudappsecurity.com](https://status.cloudappsecurity.com) 檢查目前的 Cloud App Security 服務狀態，或直接在入口網站內按一下 [說明]>[系統狀態]。 
 


## <a name="see-also"></a>另請參閱  

如需比此處所列版本更早之版本的描述，請參閱 [Microsoft Cloud App Security 的過去版本](release-note-archive.md)。

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  