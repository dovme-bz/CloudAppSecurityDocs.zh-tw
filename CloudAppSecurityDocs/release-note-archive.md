---
title: "Cloud App Security 過去更新的封存 | Microsoft Docs"
description: "本主題為描述 Cloud App Security 過去版本所做更新的封存。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/7/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 185c3a46-ede8-4d58-b232-111807845c8f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: eccb23c10641517090c9fead2231eb5ebceb2000
ms.sourcegitcommit: 9de7ed2224aeed049fc2a87e52307988f8837eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2018
---
# <a name="past-release-archive-of-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的過去版本封存

若要查看最新功能清單，請參閱 [Cloud App Security 新功能](release-notes.md)。



## <a name="updates-made-in-2017"></a>2017 年所做的更新

### <a name="cloud-app-security-release-113"></a>Cloud App Security 版本 113
發行日期：2017 年 12 月 25 日

-   我們很高興宣佈 Cloud App Security 現在支援與 Azure 資訊保護的深度整合。 此公用預覽功能可讓您掃描與分類雲端應用程式中的檔案，自動套用 Azure 資訊保護標籤的保護。 這項功能適用於 Box、SharePoint 和 OneDrive。 如需詳細資訊，請參閱 [Azure 資訊保護整合](azip-integration.md)。

-   Cloud Discovery 記錄檔剖析器現可支援一般格式：LEEF、CEF 和 W3C。


### <a name="cloud-app-security-release-112"></a>Cloud App Security 版本 112
發行日期：2017 年 12 月 10 日

-   您現在可以在活動記錄中按一下使用者名稱或 IP 位址，以存取相關的隱藏式深入解析選單。 
-   在調查活動時，只要按一下時鐘圖示，就能在隱藏式深入解析選單內輕鬆地檢視所有相同時段的活動，讓您可以針對正在檢視的活動，查看其 48 小時內執行的所有活動。
-   已改善適用於 Juniper SRX 的 Cloud Discovery 記錄檔剖析器。
-   針對由 Proxy 監視的活動，**活動物件**已擴充為包含 DLP 掃描的相關資訊，而符合的原則也擴充為包含 DLP 違規 (若存在)。


### <a name="cloud-app-security-release-111"></a>Cloud App Security 版本 111
發行日期 2017 年 11 月 26 日

-   探索原則現在支援應用程式標記做為條件以及治理動作。 這可讓您使用自訂標籤 (像是 **熱門應用程式**) 來自動標記新發現的應用程式。 您也可以使用應用程式標記做為篩選條件，例如，「當觀察清單中的應用程式在一天有超過 100 個以上的使用者時向我發出警示」。

-   **時間**篩選已改善，讓使用者更容易使用。

-   內容檢查現在可區分內容、中繼資料和檔案名稱，讓您可以選取想要檢查的項目。

-   為 G Suite 新增了新的治理動作。 您現在可以對共用檔案**減少公用存取**。 讓您將可公開取得的檔案設定為只能透過共用連結來取得。

-   對於其他應用程式的所有 OKTA 登入活動現在會顯示在 Cloud App Security 中，並註明來源為 OKTA。 您可以在活動的**活動物件**欄位中，根據執行登入的目標應用程式來檢視和篩選。


### <a name="cloud-app-security-release-110"></a>Cloud App Security 版本 110
發行日期 2017 年 11 月 12 日
 
-   現在已正式運作：我們將開始推出記錄收集器的新部署模式。 除了目前以虛擬設備為基礎的部署之外，新的以 Docker (容器) 為基礎的記錄收集器可以在內部部署和 Azure 中的 [Ubuntu 電腦](discovery-docker.md)上安裝為套件。 使用 Docker 時，可自由修補和監視裝載電腦的客戶即擁有該裝載電腦。
-   從入口網站的頁面內，您可以使用位於角落的新藍色問號來存取 docs.microsoft.com 上的相關 Cloud App Security 文件頁面。 每個連結都具有內容相關性，並會根據您所在的頁面將您引導至所需的資訊。
-   您現在可以從 Cloud App Security 入口網站的每個頁面傳送意見反應。 這可讓您直接向 Cloud App Security 小組回報錯誤、要求新功能，以及分享您的體驗。
-   針對深入調查組織的雲端使用方式，已改進識別子網域的雲端探索能力。 如需詳細資訊，請參閱[使用探索到的應用程式](discovered-apps.md)。

### <a name="cloud-app-security-release-109"></a>Cloud App Security 版本 109
發行日期：2017 年 10 月 29 日 

- 開始推出 Microsoft Cloud App Security Proxy 功能。 Microsoft Cloud App Security 的 Proxy 提供您所需的工具，讓您取得在雲端環境內所執行之存取與活動的即時可見性與控制權。 例如：
    -   在下載前即予以封鎖，避免資料外洩。
    -   設定儲存在雲端的資料以及從雲端下載的資料，強制使用加密保護的規則。
    -   可以看見未受保護的端點，以便您能監視未受管理的裝置上正在進行的活動。
    -   控制來自非企業網路或高風險 IP 位址的存取。
  
  如需詳細資訊，請參閱[使用 Proxy 保護應用程式](proxy-intro-aad.md)。

-   我們會逐漸推出根據特定服務活動名稱篩選的功能。 這個新的活動類型篩選更精細，可讓您監視特定的應用程式活動，而不是較籠統的活動類型。 例如，以前可能是篩選**執行命令**，現在則可以篩選特定的 EXO Cmdlet。 活動名稱也會出現在 [Type (in app)] (類型 (依應用程式)) 下的活動下拉式清單中。 這項功能最終會取代活動類型篩選。  

-   Cloud Discovery 現在支援 Cisco ASA with FirePOWER。 

-   已強化 [Discovery User and IP] (Discovery 使用者和 IP) 頁面的效能，以改善使用者體驗。


### <a name="cloud-app-security-releases-105-106-107-108"></a>Cloud App Security 版本 105、106、107、108
發行日期：2017 年 9 月/10 月
 
-   Cloud App Security 現在包含位於歐盟的資料中心。 我們除了美國的資料中心之外，歐盟地區的資料中心可讓 Cloud App Security 客戶完全符合新的和即將公布的歐洲標準及法規。 
-   新的篩選已新增至 [App 連線程式] 頁面，提供您更簡便的篩選和其他深入解析。
-   已改善僅包含目的地 IP 資訊的記錄檔雲端探索。
 

### <a name="cloud-app-security-release-104"></a>Cloud App Security 版本 104 
發行日期：2017 年 8 月 27 日

-   您現在可以藉由使用 **IP 位址範圍 API** 來建立指令碼，以便大量新增 IP 範圍。在 Cloud App Security 入口網站功能表列中，依序按一下問號、[API 文件]，便能找到此 API。 
-   Cloud Discovery 現在會同時顯示總交易數與封鎖的交易數，讓您能夠更清楚看到封鎖的交易數。
-   您現在可以依據雲端應用程式是否經過 **ISO 27017** 認證來加以篩選。 這個新的 Cloud App Catalog 風險因素會判斷應用程式提供者是否具有此憑證，能夠制定一套大眾均可接受的措施與準則，以及用於處理及保護公用雲端計算環境中的使用者資訊。
- 為了讓您針對 GDPR 合規性做準備，我們會從「雲端應用程式類別目錄」中的雲端應用程式收集 GDPR 整備聲明。 它還不會影響應用程式的風險分數，而只是提供應用程式發行者 GDPR 整備頁面 (當應用程式發行者提供此頁面時) 的連結。 Microsoft 尚未驗證此內容，對其有效性不負責任。


### <a name="cloud-app-security-release-103"></a>Cloud App Security 版本 103 
發行日期：2017 年 8 月 13 日

- Cloud App Security 已針對下列 Office 檔案新增 Azure 資訊保護原生保護支援：.docm、.docx、.dotm、.dotx、.xlam、.xlsb、.xlsm、.xlsx、.xltx、.xps、.potm、.potx、.ppsx、.ppsm、.pptm、.pptx、.thmx、.vsdx、.vsdm、.vssx、.vssm、.vstx、.vstm (取代一般保護)。

- 任何 Azure Active Directory 相容性系統管理員都會自動獲授與類似 Cloud App Security 的權限，包括唯讀及管理警示、建立和修改檔案原則、允許檔案治理動作，以及檢視 [資料管理] 下的所有內建報表。 

- 我們將 DLP 違規內容從 40 個字元擴充到 100 個字元，以協助您更清楚違規的內容。

- Cloud Discovery 自訂記錄檔上傳程式的詳細錯誤訊息，能讓您輕鬆地為上傳記錄檔中的錯誤進行疑難排解。

- 擴充 Cloud Discovery 封鎖指令碼以支援 Zscaler 格式。

- 新的雲端應用程式目錄風險因素：帳戶終止之後保留資料。 這可讓您在終止雲端應用程式內的帳戶之後，確定您的資料已完全移除。


### <a name="cloud-app-security-release-102"></a>Cloud App Security 版本 102 
發行日期：2017 年 7 月 30 日
 
-   因為 IP 位址資訊對幾乎所有調查都非常重要，所以您現在可以在 [活動] 下拉式清單中檢視 IP 位址的詳細資訊。 在特定活動中，您現在可以按一下 IP 位址索引標籤，檢視 IP 位址的相關彙總資料，包括特定 IP 位址的未解決警示數目、最近活動的趨勢圖形，以及位置地圖。 如此將有助於深入調查，例如當調查不可能的旅遊警示時，您可以輕鬆地了解使用的 IP 位址位置，以及它是否涉及可疑活動。 您也可以直接在 [IP 位址] 下拉式清單中執行動作，讓您將某個 IP 位址標記為有風險、VPN 或公司，以便未來進行調查和建立原則。 如需詳細資訊，請參閱 [IP 位址深入解析](activity-filters.md#ip-address-insights)

-   在 Cloud Discovery 中，您現在也可以使用[自訂記錄檔格式](custom-log-parser.md)來進行[自動記錄上傳](discovery-docker.md)。 這可讓您輕鬆地從您的 SIEM (例如 Splunk 伺服器或任何其他不受支援的格式) 自動上傳記錄檔。 
 
-   新的使用者調查動作可以對使用者進行更深層級的調查。 您現在可以從 [調查] 頁面，以滑鼠右鍵按一下活動、使用者或帳戶，並套用下列其中一個新篩選來進行進階的調查和過濾：[檢視相關的活動]、[檢視相關的治理]、[檢視相關的警示]、[檢視擁有的檔案]、[檢視與此使用者共用的檔案]。

-   雲端應用程式目錄現在包含新的欄位，供帳戶終止之後保留資料之用。 此風險因素可讓您在終止雲端應用程式內的帳戶之後，確定您的資料已完全移除。

-   Cloud App Security 現在已經增強與 Salesforce 物件 (例如潛在客戶、帳戶、活動、機會、設定檔與案例) 相關活動的可見性。 例如，帳戶頁面存取的可見性可讓您設定原則，以便在使用者檢視異常多的帳戶頁面時發出警示。 若您在 Salesforce 中啟用 Salesforce 事件監視 (Salesforce Shield 的一部分)，可透過 Salesforce 應用程式連接器使用。

- 私人預覽版客戶現在已可使用「不要追蹤」功能！ 您現在可以控制處理哪些使用者的活動資料。 這可讓您在 Cloud App Security 中將特定群組設定為 「不要追蹤」。 例如，您現在可以決定不要處理位於德國，或位於不受特定合規性法律之任何國家/地區的任何使用者活動資料。 這在 Cloud App Security 中可以跨所有應用程式、針對特定的應用程式，或甚至針對特定子應用程式實作。 此外，還可以利用這項功能來漸進推出 Cloud App Security。 如需此功能的詳細資訊，或加入私人預覽，請連絡支援部門或您的帳戶代表。 



### <a name="cloud-app-security-release-100"></a>Cloud App Security 版本 100 
發行日期：2017 年 7 月 3 日
 

#### <a name="new-features"></a>新功能
-   **安全性延伸模組**：[安全性延伸模組] 是新的儀表板，可集中化管理 Cloud App Security 的所有安全性延伸模組，包括 API 權杖管理、SIEM 代理程式和外部 DLP 連接器。 Cloud App Security 的 [設定] 下提供這個新的儀表板。 
    - API 權杖 – 產生和管理您自己的 [API 權杖](api-tokens.md)，以使用 RESTful API 來整合 Cloud App Security 與協力廠商軟體。 
    - SIEM 代理程式 – [SIEM 整合](siem.md) 之前直接位在 [設定] 下方，現在則提供為 [安全性延伸模組] 中的索引標籤。
    - 外部 DLP (預覽) – Cloud App Security 可讓您[運用協力廠商分類系統中的現有投資](icap-stunnel.md) (例如資料外洩防護 (DLP) 解決方案)，且可讓您使用環境中執行的現有部署來掃描雲端應用程式的內容。 請連絡您的帳戶管理員，以加入預覽。 
-   **自動批准/不批准：**新的應用程式偵測原則讓 Cloud Discovery 可以自動設定應用程式具有 [批准/不批准] 標籤。 這可讓您自動找出違反組織原則和規定的應用程式，並將其新增至產生的封鎖指令碼。
-   **Cloud App Security 檔案標籤**：您現在可以套用 Cloud App Security 檔案標籤，以深入了解它所掃描的檔案。 針對 Cloud App Security DLP 所掃描的每個檔案，您現在可以知道檔案是否因為加密或損毀而無法檢查。 例如，您可以設定原則，針對外部共用的受密碼保護檔案發出警示並予以隔離。 這項功能適用於 2017 年 7 月 3 日之後所掃描的檔案。

    您可以使用篩選 [分類標籤] > [Cloud App Security] 來篩選這些檔案： 
    - **已加密 Azure RMS** - 這些檔案由於已設定 Azure RMS 加密，因此不會檢查其內容。
    - **已加密密碼** - 這些檔案由於受使用者密碼保護，因此不會檢查其內容。
    - **損毀的檔案** - 這些檔案由於無法讀取其內容，因此不會檢查其內容。
-   **使用者深入解析**：已升級調查體驗，啟用目前使用者的預設深入解析。 現在，您只要按一下就可以從 [活動] 下拉式清單中看到使用者的完整概觀，包括它們從中連線的位置、與它們有關的未解決警示數目，以及其中繼資料資訊。
-   **App 連線程式深入解析**：在 [App 連線程式] 中，每個連線的應用程式現在都會在表格中包括應用程式下拉式清單，更輕鬆地向下切入到其狀態。 所提供的詳細資料包括 App 連線程式的連線時間，以及連線程式的最後一個健全狀況檢查。 您也可以監視每個應用程式的 DLP 掃描狀態：DLP 所檢查的檔案總數，以及即時掃描狀態 (所要求的掃描與實際掃描)。 您可以得知 Cloud App Security 即時掃描檔案的速率是否低於所要求的數目，以及您的租用戶是否可能超過其容量並在 DLP 結果中發生延遲。
-   **雲端應用程式目錄自訂：** 
    - **應用程式標籤**：您現在可以建立應用程式的自訂標籤。 接著可以使用這些標籤作為篩選，以深入探討您想要調查的特定應用程式類型。 例如，自訂監看清單、給特定業務單位的指派，或自訂核准，例如 "approved by legal"。
    - **自訂附註**：當您檢閱和評估跨環境探索到的不同應用程式時，現在可以將結論和深入解析儲存至「附註」。
    - **自訂風險分數**：您現在可以覆寫應用程式的風險分數。 例如，如果應用程式的風險分數為 8，而且它是您組織中批准的應用程式，則可以將您組織的風險分數變更為 10。 您也可以新增附註，以在任何人檢閱應用程式時清楚變更理由。
-   **新的記錄收集器部署模式：**我們將開始推出記錄收集器目前的新部署模式。 除了以目前虛擬設備為基礎的部署之外，新的以 Docker (容器) 為基礎的記錄收集器可以在內部部署和 Azure 中的 Windows 和 Ubuntu 電腦上安裝為套件。 使用 Docker 時，可自由修補和監視裝載電腦的客戶即擁有該裝載電腦。

#### <a name="announcements"></a>宣告： 
-   雲端應用程式目錄現在支援超過 15,000 個可探索的應用程式
-   合規性：Cloud App Security 通過 Azure 的 SOC1/2/3 官方認證。 如需完整的認證清單，請參閱[合規性供應項目](https://www.microsoft.com/trustcenter/compliance/complianceofferings) \(英文\) 並篩選 Cloud App Security 的結果。

#### <a name="other-improvements"></a>其他改進： 
-   **改進的剖析：**已改進 Cloud Discovery 記錄剖析機制。 內部錯誤極不可能發生。
-   **預期的記錄格式：**Cloud Discovery 記錄的預期記錄格式現在提供 Syslog 格式和 FTP 格式的範例。
-   **記錄收集器上傳狀態：**您現在可以在入口網站中查看記錄收集器狀態，並使用入口網站內狀態通知和系統警示對錯誤進行更快速地疑難排解。


### <a name="cloud-app-security-release-99"></a>Cloud App Security 版本 99 
發行日期：2017 年 6 月 18 日

#### <a name="new-features"></a>新功能

-   您現在可以要求使用者重新登入所有 Office 365 和 Azure AD 應用程式，以快速有效地修復可疑的使用者活動警示及遭盜用的帳戶。 您可以在 [原則設定] 和 [警示] 頁面的 [暫停使用者] 選項旁邊找到新的治理動作。
-   您現在可以篩選活動記錄中的 [Add impersonation role assignment (新增模擬角色指派)] 活動。 此活動可讓您使用 Cmdlet **New-ManagementRoleAssignment**來偵測系統管理員何時將 [應用程式模擬] 角色授與任何使用者或系統帳戶。 這個角色允許模擬者使用與已模擬帳戶建立關聯的權限來執行作業，而不是使用與模擬者帳戶建立關聯的權限。
Cloud Discovery 改進：
-   Cloud Discovery 資料現在可以使用 Azure Active Directory 使用者名稱資料進行擴充。 當您啟用這項功能時，探索流量記錄檔中收到的使用者名稱會經過比對，並取代為 Azure AD 使用者名稱以啟用下列新功能：
  - 您可以調查 Azure Active Directory 使用者的影子 IT 使用方式。
  - 您可以將探索到的雲端應用程式使用與 API 收集的活動相互關聯。
  - 然後，您可以建立以 Azure AD 使用者群組為基礎的自訂記錄檔。 例如，特定行銷部門的影子 IT 報告。
-   已改進 Juniper syslog 剖析器。 它現在支援 welf 和 sd syslog 格式。
-   改進 Palo Alto 剖析器，可進行更好的應用程式探索。
-   若要確認已成功上載記錄檔，您現在可以在 Cloud App Security 入口網站中看到記錄收集器的狀態。 

#### <a name="general-improvements"></a>一般改進：
-   內建 IP 位址標籤和自訂 IP 標籤現在會依階層考量，其中自訂 IP 標籤優先於內建 IP 標籤。 例如，如果根據威脅情報將 IP 位址標籤為 [具風險]，但有自訂 IP 標籤將其識別為 [公司]，則會優先使用自訂類別和標籤。


### <a name="cloud-app-security-release-98"></a>Cloud App Security 版本 98 
發行日期：2017 年 6 月 4 日
 
Cloud Discovery 更新：
-   使用者現在可以對探索到的應用程式執行進階篩選，以讓您執行深入調查，例如根據使用量來篩選應用程式：有多少上傳流量來自特定類型的探索到應用程式、有多少使用者使用特定類別的探索到應用程式。 您也可以執行左面板中的複選來選取多個類別。 
-   已開始推出根據常用搜尋的新 Cloud Discovery 範本，例如 "non-compliant cloud storage app"。 這些基本篩選可以用作對探索到的應用程式執行分析的範本。
-   為了方便使用，您現在可以執行動作，例如透過一個動作批准和不批准多個應用程式。
-   我們現在將推出根據 Azure Active Directory 使用者群組建立自訂探索報告的功能。 例如，如果您想要查看行銷部門的雲端使用情況，您可以使用 [匯入使用者群組] 功能匯入行銷群組，然後為此群組建立自訂報告。

新功能：
-   安全性讀取者的 RBAC 已完成推出。這項功能可讓您管理授與 Cloud App Security 主控台內系統管理員的權限。 根據預設，所有的 Azure Active Directory 和 Office 365 全域管理員及安全性管理員在入口網站中都有完整的權限，而 Azure Active Directory 和 Office 365 中的所有安全性讀取者在 Cloud App Security 中只有唯讀權限。 您可以新增其他系統管理員，或覆寫使用 [管理存取] 選項的權限。 如需詳細資訊，請參閱[管理管理員權限](manage-admins.md)。
-   我們現在將推出 Microsoft 智慧型安全性圖表偵測到之具風險 IP 位址的詳細威脅智慧報告：殭屍網路執行活動時，會看到殭屍網路名稱 (可用時) 與特定殭屍網路的詳細報告連結。
 
### <a name="cloud-app-security-release-97"></a>Cloud App Security 版本 97
發行日期：2017 年 5 月 24 日

#### <a name="new-features"></a>新功能
-   調查檔案和原則違規：您現在可以在 [檔案] 頁面中看到所有原則相符項目。 此外，已改進您的 [File Alert (檔案警示)] 頁面，現在包括特定檔案之 [歷程記錄] 的不同索引標籤，可讓您向下切入到特定檔案之所有原則的違規歷程記錄。 每個「歷程記錄」事件都會在警示時包括檔案的快照。 它會指出刪除還是隔離檔案。
-   Office 365 SharePoint 和商務用 OneDrive 檔案現在提供[系統管理隔離](use-case-admin-quarantine.md)，其為私人預覽版本。 這項功能可讓您隔離符合原則的檔案，或設定要隔離它們的自動化動作，並從使用者的 SharePoint 目錄中移除它們，以及將原始檔案複製至您選擇的系統管理隔離位置。
        
#### <a name="cloud-discovery-improvements"></a>Cloud Discovery 改進

-   已改進 Cloud Discovery 對 Cisco Meraki 記錄檔的支援。
-   向 Cloud Discovery 建議改進的選項現在可讓您建議新的風險因素。
-   已改進自訂記錄剖析器，可區隔日期和時間設定來支援記錄格式，並可讓您選擇設定時間戳記。
-   開始推出根據 Azure Active Directory 使用者群組建立自訂探索報告的功能。 例如，如果您想要查看行銷部門的雲端使用情況，您可以使用 [匯入使用者群組] 功能匯入行銷群組，然後為此群組建立自訂報告。

**其他更新**

-   Cloud App Security 現在支援 Office 365 稽核記錄中所支援的 Microsoft Power BI 活動。 這項功能正逐步推出。 請注意，您需要[在 Power BI 入口網站中啟用這項功能](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/)。
-   在活動原則中，您現在可以設定要對所有已連線應用程式之使用者採取的通知和暫停動作。 例如，您可以設定原則，一律通知使用者的管理員，並在使用者具有任何已連線應用程式中的多次失敗登入時立即暫停使用者。
 
### <a name="oob-release"></a>OOB 版本
-   為了快速反應横掃全球的勒索軟體，在星期日，Cloud App Security 團隊已將新的[潛在的勒索軟體活動偵測原則](use-case-ransomware.md)範本新增至包括 WannaCrypt 簽章延伸模組的入口網站。 建議您立即設定此原則。

### <a name="cloud-app-security-release-96"></a>Cloud App Security 96 版
發行日期：2017 年 5 月 8 日

新功能：

-   持續逐步推出「安全性讀取者」權限，可讓您管理授與給系統管理員在 Cloud App Security 主控台中的權限。 根據預設，所有的 Azure Active Directory 和 Office 365 全域管理員及安全性管理員在入口網站中都有完整的權限，而 Azure Active Directory 和 Office 365 中的所有安全性讀取者在 Cloud App Security 中只有唯讀權限。 如需詳細資訊，請參閱[管理管理員權限](manage-admins.md)。
-   已完成推出 Cloud Discovery 針對 CSV 記錄檔的使用者定義記錄檔剖析器支援。 Cloud App Security 可提供工具來描述與特定資料相關聯的資料行，讓您針對先前不支援的設備來設定剖析器。 如需詳細資訊，請參閱[自訂記錄檔剖析器](custom-log-parser.md)。

改善：

-   Cloud Discovery 現在支援 Juniper SSG 設備。
-   Cloud Discovery 對 Cisco ASA 記錄檔的支援已改進以獲得更好的可見度。
-   您現在可以在 Cloud App Security 入口網站資料表中更輕鬆地執行大量動作和選取多個記錄：頁面長度已增加以改善大量作業。
-   「域外共用 (依網域)」和「共用檔案的擁有者」內建報告現在可以針對 Salesforce 資料執行。
-   我們已開始推出其他的 Salesforce 活動，讓您能夠追蹤從活動資料所擷取的有趣資訊。 這些活動包括檢視和編輯帳戶、潛在客戶、商機以及各種其他有趣的 Salesforce 物件。
-   新的活動已新增到 Exchange，讓您可監視已授與哪些權限給使用者信箱或信箱資料夾。 這些活動包括：
    -   新增收件者權限
    -   移除收件者權限
    -   新增信箱資料夾權限
    -   移除信箱資料夾權限
    -   設定信箱資料夾權限

    例如，您現在可監視已授與其他使用者信箱 **SendAs** 權限，因此能以其名稱傳送電子郵件的使用者。


### <a name="cloud-app-security-release-95"></a>Cloud App Security 版本 95
發行日期：2017 年 4 月 24 日

**更新**
- [帳戶] 頁面已使用改進功能更新，讓風險偵測變得更容易。 您現在會更容易篩選內部和外部帳戶，看一眼就知道使用者是否擁有系統管理權限，而且可以只對每個帳戶依應用程式執行動作 (例如移除權限、移除使用者的共同作業、暫時停止使用者的權限)。 此外，還會顯示每個帳戶的已匯入[使用者群組](user-groups.md)。 

- 針對 Microsoft 工作帳戶 (Office 365 和 Azure Active Directory)，Cloud App Security 會將不同的使用者識別碼 (例如 Proxy 位址、別名、SID 等) 分組在單一帳戶之下。 所有與帳戶相關的別名都會出現在主要電子郵件地址下。 以使用者識別碼清單為基礎，凡執行者為使用者識別碼的活動，其執行者會顯示為主要使用者名稱 UPN (使用者主體名稱)。 根據 UPN 指派群組並套用原則。 這會改善調查活動，並將所有相關的活動融合到異常和群組原則的相同工作階段。 這項功能會在下個月陸續推出。

- 傀儡程式標記已新增為瀏覽器利用內建報告的可能風險因素。 現在，除了瀏覽器利用被標記為過時，您還可以看到傀儡程式何時執行瀏覽器利用。 深入了解[內建報告](built-in-report-reference.md)。

- 現在在建立內容檢查檔案原則時，您可以設定篩選器只包含至少有 50 個符合項目的檔案。



### <a name="cloud-app-security-release-94"></a>Cloud App Security 版本 94
發行日期：2017 年 4 月 2 日

**新功能：**
-   Cloud App Security 現在已與 Azure RMS 整合。 您可以直接從 Cloud App Security 入口網站中，利用 Microsoft Rights Management 來保護 Office 365 OneDrive 和 Sharepoint Online 中的檔案。 這可以從 [檔案] 頁面完成。 如需詳細資訊，請參閱[與 Azure 資訊保護整合](azip-integration.md)。 未來版本中將提供對其他應用程式的支援。
-   到目前為止，當您的網路中發生傀儡程式和編目程式活動時，尤其難以辨識，因為這類活動不是由使用者在您的網路上所執行。 Bot 和編目程式可以在您不知情的狀況下，於您的電腦上執行惡意的工具。 現在，Cloud App Security 提供工具，讓您能夠在傀儡程式和編目程式於您的網路上執行時進行查看。 您可以使用新的使用者代理程式標記來篩選活動記錄中的活動。 使用者代理程式標記可讓您篩選傀儡程式所執行的所有活動，而您可以使用它來建立原則，以便每次偵測到這種類型的活動時警示您。 若未來版本以將這個有風險的活動內嵌到異常偵測警示的形式來包含它時，將為您提供最新訊息。 
-   新的統一應用程式權限頁面可讓您更輕鬆地調查已授與使用者對協力廠商應用程式的權限。 按一下 [調查] > [應用程式權限]，您現在可以透過每個已連接應用程式之應用程式權限的頁面，來檢視已授與使用者對協力廠商應用程式的所有權限清單，此頁面讓您能夠在各種應用程式與已授與的權限間進行比較。  如需詳細資訊，請參閱[管理應用程式權限](manage-app-permissions.md)。
-   您可以從隱藏式表格選單中篩選資料，更容易進行調查。
在 [活動記錄] 中，[檔案] 表格和 [應用程式權限] 頁面現已增強且具有新的內容動作，讓您在調查過程中進行樞紐分析時能夠輕鬆許多。 我們也新增了設定頁面的快速連結，以及按一下就能複製資料的功能。 如需詳細資訊，請參閱[使用隱藏式檔案與活動選單](file-filters.md)的相關資訊。
-   已完成對 Microsoft Teams 推出 Microsoft Office 365 活動記錄及警示的支援。
 



### <a name="cloud-app-security-release-93"></a>Cloud App Security 版本 93
發行日期：2017 年 3 月 20 日

**新功能：**
-   您現在可以套用原則以包含或排除匯入的使用者群組。 
-   Cloud App Security Anonymization 現在可讓您設定自訂的加密金鑰。 如需詳細資訊，請參閱 [Cloud Discovery 匿名](cloud-discovery-anonymizer.md)。
-   為了更充分掌控使用者與帳戶管理，您現在可以從 [帳戶] 頁面內按一下每個使用者旁的齒輪，直接存取每個使用者的 Azure AD 帳戶設定。 這可以方便存取進階使用者管理功能群組管理、MFA 設定、使用者登入相關詳細資訊，以及提供封鎖登入的能力。 
-   您現在可以透過 Cloud App Security API，匯出待批准應用程式的封鎖指令碼。 深入了解 Cloud App Security 入口網站中的 API，方法是按一下功能表列中的問號，隨即出現 [API 文件]。
-   適用於 ServiceNow 的 Cloud App Security App 連線程式已擴展為包含 OAuth 權杖的支援 (如 Geneva、Helsinki、Istanbul 中所引進)。 這提供 ServiceNow 更健全的 API 連線，不需要仰賴部署使用者。 如需詳細資訊，請參閱[將 ServiceNow 連接至 Microsoft Cloud App Security](connect-servicenow-to-microsoft-cloud-app-security.md)。 現有的客戶可在 [ServiceNow App 連線程式] 頁面中更新其設定。
-   如果您已設定其他第三方 DLP 掃描器，DLP 掃描狀態現在將會顯示個別連線程式的狀態，以改善可見性。
-   Cloud App Security 現在支援 Office 365 稽核記錄檔中所支援的 Microsoft Teams 活動。 這項功能正逐步推出。
-   針對 Exchange Online 模擬事件，您現在可依使用的權限層級 (委派、系統管理員或委派的系統管理員) 來篩選。您現在可以在 [活動記錄] 中搜尋您感興趣之顯示模擬層級的事件，方法是搜尋 [活動物件] > [項目]。
-   在 Office 365 應用程式的 [應用程式權限] 索引標籤上的應用程式下拉式清單中，您現在可以看到每個應用程式的 [發行者]。 您也可以使用 [發行者] 做為篩選條件，調查來自相同發行者的其他應用程式。
-   「有風險的 IP 位址」現在會顯示為獨立的風險因素，而非在 [位置] 風險因素下加權。 
-   當停用檔案上的 Azure 資訊保護標籤時，停用的標籤在 Cloud App Security 中會顯示為「已停用」。 已刪除的標籤則不會顯示。
 
**其他 Salesforce 的支援︰**
-   您現在可在 Cloud App Security 中暫停或恢復 Salesforce 使用者的權限。 這可在 Salesforce 連線程式的 [帳戶] 索引標籤中完成，方法是按一下特定使用者資料列結尾的齒輪，然後選取 [暫時停權] 或 [恢復權限]，而且還能夠在原則中當作治理動作套用。 在 Cloud App Security 中採取的所有暫時停權與恢復權限的動作，都會記錄在[治理記錄](governance-actions.md)中。 
-   提高 Salesforce 內容共用可見度：您現在可以看到共用檔案的共用對象，包括公開共用的檔案、與群組共用的檔案，以及與整個 Salesforce 網域共用的檔案。 提高可見度將回溯推出至新的與目前的已連線 Salesforce 應用程式，第一次更新時可能需要一些時間。
-   我們改善了下列 Salesforce 事件的涵蓋範圍，並將它們與 [管理使用者] 活動區隔： 
    - 編輯權限
    - 建立使用者
    - 變更角色
    - 重設密碼

### <a name="cloud-app-security-release-90-91-92"></a>Cloud App Security 版本 90、91、92
發行於 2017 年 2 月

**特殊公告**

Cloud App Security 現已通過 Microsoft Compliance 的官方認證，符合 ISO、HIPAA、CSA STAR、歐盟示範條款 (EU Model Clauses) 等。 請前往 [Microsoft Compliance Offerings (Microsoft 合規性供應項目)](https://www.microsoft.com/trustcenter/compliance/complianceofferings) 並選取 [Cloud App Security]，以查看完整的憑證清單。

**新功能**

-  **匯入使用者群組 (預覽)**   現在當您使用 API 連接器連接應用程式時，Cloud App Security 可讓您從 Office 365 及 Azure Active Directory 匯入使用者群組。 運用匯入使用者群組的一般案例包括：調查人資人員查看的文件、檢查主管團隊中是否發生不尋常的情形，或管理團隊中是否有人在美國境外執行活動。 如需詳細資料和指示，請參閱[匯入使用者群組](user-groups.md)。

-  您現在可以在活動記錄中篩選使用者及群組中的使用者，以顯示特定使用者是哪些活動的執行者和執行對象。 舉例來說，您可以調查使用者模擬其他人的活動，以及其他人模仿該使用者的活動。 如需詳細資訊，請參閱[活動](activity-filters.md)。

- 在 [檔案] 頁面調查檔案時，如果您向下鑽研特定檔案的 [共同作業者]，您現在可以看到共同作業者的詳細資訊，包括他們在內部或外部、是寫入者或讀取者 (檔案權限)，而且在檔案與群組共用時，您現在可以看到身為群組成員的所有使用者。 這可讓您知道群組成員是否為外部使用者。

-  現在所有設備均有 IPv6 支援。

-   Cloud Discovery 現在支援 Baracuda 設備。

-   Cloud App Security 系統警示線在涵蓋了 SIEM 連線錯誤。 如需詳細資訊，請參閱 [SIEM 整合](siem.md)。

-   Cloud App Security 現在包括下列活動的支援：

     **Office 365、SharePoint/OneDrive**：更新應用程式設定、從群組中移除擁有者、刪除網站、建立資料夾

     **Dropbox**︰將成員新增到群組、從群組中移除成員、建立群組、為群組重新命名、變更團隊成員名稱

     **Box**：從群組中移除項目、更新項目共用、將使用者新增到群組、從群組中移除使用者


### <a name="cloud-app-security-release-89"></a>Cloud App Security 版本 89
發行日期：2017 年 1 月 22 日

**新功能**
-   我們將開始推出在 Cloud App Security 中檢視 Office 365 安全與規範中心 DLP 事件的功能。 如果您已在 Office 365 安全與規範中心中設定 DLP 原則，則偵測到原則相符項目時，將可以在 Cloud App Security 活動記錄檔中看到它們。 活動記錄檔中的資訊將包括已觸發相符項目的檔案或電子郵件，以及相符的原則或警示。 「安全性事件」活動可讓您在 Cloud App Security 活動記錄檔中檢視 Office 365 DLP 原則相符項目。 您可以使用這項功能︰
    -   查看來自 Office 365 DLP 引擎的所有 DLP 相符項目。
    -   警示發現特定檔案、SharePoint 網站或原則之 Office 365 DLP 原則相符項目。
    -   調查內容較廣的 DLP 相符項目，例如，存取或下載已觸發 DLP 原則相符項目之檔案的外部使用者。
 
-   已改善活動描述的明確性和一致性。 每個活動現在都提供意見反應按鈕，因此，如果您有不了解的地方或有任何問題，請讓我們知道。 
 
**改善**  
-   已為 Office 365 新增治理動作，可讓您移除檔案的所有外部使用者。 例如，這可讓您實作原則，而這些原則會**從僅限內部分類的檔案中移除外部共用**。
-   改善外部使用者在 SharePoint 中的線上識別。 篩選「外部使用者」群組時，將不會顯示 app@sharepoint 系統帳戶。



### <a name="cloud-app-security-release-88"></a>Cloud App Security 88 版
發行日期：2017 年 1 月 8 日
 
**新功能**
- 將 SIEM 連接至 Cloud App Security。 您現在可以設定 SIEM 代理程式，以將警示和活動自動傳送到您所選擇的 SIEM。 現在已提供進行公開預覽。  如需完整文件和詳細資料，請查看＜與 SIEM 整合＞。
- Cloud Discovery 現在支援 IPv6。 我們已支援 Palo Alto 和 Juniper，未來的版本將會推出更多設備。
 
**改善**
- Cloud App Catalog 中有一個新的風險因素。 您現在可以根據是否需要使用者驗證，以對應用程式進行評分。 強制執行驗證且不允許使用匿名的應用程式，將會收到較健全的風險分數。
- 我們將會推出更實用且一致的新活動描述。 搜尋活動將不會受到這個項目的影響。
- 我們已加入改善的使用者裝置識別，讓 Cloud App Security 利用裝置資訊來豐富大量事件。

## <a name="updates-made-in-2016"></a>2016 年所做的更新
 
### <a name="cloud-app-security-release-87"></a>Cloud App Security 版本 87
發行日期：2016 年 12 月 25 日

**新功能**
-   我們正在推出[資料匿名](cloud-discovery-anonymizer.md)，讓您可以享受 Cloud Discovery，同時保護使用者隱私權。 資料匿名是透過加密使用者名稱資訊來執行。
-   我們正在推出將封鎖指令碼從 Cloud App Security 匯出到其他應用裝置的能力。 這個指令碼可讓您透過封鎖流向待批准應用程式的流量，輕鬆地減少影子 IT。 下列項目現在可以使用這個選項： 
    -   BlueCoat ProxySG
    -   Cisco ASA
    -   Fortinet
    -   Juniper SRX
    -   Palo Alto
    -   Websense
-   已新增檔案治理動作，可讓您刪除已針對檔案或資料夾所設定的任何唯一權限，來強制檔案繼承父系的權限。 這個檔案治理動作可讓您變更檔案或資料夾的權限繼承自父資料夾。 
-   已新增稱為「外部」的使用者群組。 這是 Cloud App Security 預先設定的預設使用者群組，內含不屬於您內部網域的所有使用者。 您可以使用這個使用者群組作為篩選條件，例如，您可以找到外部使用者所執行的活動。
-   Cloud Discovery 功能現在支援 Sophos Cyberoam 應用裝置。
 
**錯誤修正**
-   SharePoint Online 和商務用 OneDrive 檔案已透過「內部」而非「私人」形式顯示在 [檔案] 原則報告和 [檔案] 頁面中。 這已更正。
 


### <a name="cloud-app-security-release-86"></a>Cloud App Security 版本 86
發行日期：2016 年 12 月 13 日

**新功能**
- 所有 Cloud App Security 獨立授權都可讓您透過一般設定來啟用 Azure 資訊保護掃描，而不需要建立原則。 
 
**改善**
- 您現在可以在檔案篩選中將 "or" 用於檔案名稱，並在 MIME 類型篩選中用於檔案和原則。 這會啟用這類案例：使用 PII 建立原則時，輸入 “passport” 或 “driver” 這個字，它將會比對檔名中具有 “passport” 或 “driver” 的任何檔案。 
- 根據預設，執行 DLP 內容檢查原則時，會遮罩所產生違規中的資料。 您現在可以取消遮罩違規的最後 4 個字元。 

**微幅改善**
- 新 Office 365 (Exchange) 信箱相關事件必須處理轉送規則，以及新增和移除委派信箱權限。
- 新事件，可在 Azure Active Directory 中稽核將同意授與新的應用程式。 




### <a name="cloud-app-security-release-85"></a>Cloud App Security 版本 85
發行日期 2016 年 11 月 27 日

**新功能**
- 已區別獲批准應用程式及連線應用程式。 「獲批准」及「待批准」現在是標籤，可套用至探索到的應用程式及應用程式目錄中的任何應用程式。 連線應用程式是您使用 API 連接器連線的應用程式，以便有更深入的可見度及控制。 您現在可以將應用程式標記為「獲批准」或「待批准」，或在可用的情況下使用 App 連線程式將其連線。 
 
- 作為此變更的一部份，[獲批准的應用程式] 頁面已由重新設計過的 [連線應用程式] 頁面取代，顯現出關於連接器的狀態資料。 
 
- 記錄檔收集器在 [來源] 下的 [設定] 功能表內的線路中更容易存取。 
- 建立活動原則篩選時，您可以藉由在相同使用者對相同目標物件執行時選擇忽略重複的活動以減少誤判，例如，相同人員多次嘗試下載相同的檔案將不會觸發警示。 
- 已改善 [活動] 下拉式清單。 現在，當您按一下 [活動] 下拉式清單中的 [活動物件] 時，您可以向下切入以取得更多資訊。

**改善**
- 已改善異常偵測引擎，包括不可能的移動警示，且現在可以在警示描述中看到 IP 資訊。
- 已改善複雜的篩選，能夠多次新增相同的篩選來微調篩選的結果。 
- 已分隔 Dropbox 中的檔案及資料夾活動，使可見度更佳。 
  
**錯誤修正**
- 已修正系統警示機制中會建立誤判的 Bug。

### <a name="cloud-app-security-release-84"></a>Cloud App Security 版本 84
發行日期 2016 年 11 月 13 日

**新功能**
-   Cloud App Security 現可支援 Microsoft Azure 資訊保護，包括強化的整合及自動佈建。 您可以使用 [標記安全分類] 篩選檔案及設定檔案原則，然後設定您想要檢視的分類標籤。 標籤也會指出類別是由貴組織的人員還是其他租用戶 (外部) 的人員所設定。 您也可以根據 Azure 資訊保護分類標籤設定活動原則，並啟用自動掃描 Office 365 的分類標籤。 如需如何利用此絕佳新功能的詳細資訊，請參閱[與 Azure 資訊保護整合](azip-integration.md)。
 
**改善**
-   已改善 Cloud App Security 的活動記錄︰ 
   -    安全性與相容性中心內的 Office 365 事件現已與 Cloud App Security 整合，且會出現在 **[活動記錄]** 中。
   -    Cloud App Security 的所有活動都在 Cloud App Security 活動記錄中作為管理活動註冊。
-   為了協助您調查與檔案相關的警示，如今您可在每個源自檔案原則的警示中，檢視相符檔案所執行的活動清單。
-   異常偵測引擎中的不可能移動演算法已有改善，可替小型的租用戶提供更佳的支援。 
 
**微幅改善**
-   **活動匯出限制**提升至 10,000。 
-   如今您會在 Cloud Discovery 手動記錄上傳程序中建立**快照集報告**時，接收到精確的處理記錄所需時間預估。 
-   在檔案原則中，**[移除共同作業者]** 治理動作現可在群組中使用。
-   **[應用程式權限]** 頁面有微幅改善。 
-   超過 10,000 個使用者授與連接至 Office 365 的應用程式權限時，清單載入速度即會變慢。 此問題已修正。
-   已將其他屬性新增至與付款卡片產業相關的**應用程式目錄**。


### <a name="cloud-app-security-release-83"></a>Cloud App Security 版本 83
發行日期：2016 年 10 月 30 日

**新功能**
-   為了簡化[活動記錄](activity-filters.md)和[檔案記錄](file-filters.md)中的篩選功能，而合併了相似的篩選條件。 使用活動篩選條件：[活動物件]、[IP 位址] 和 [使用者]。 使用檔案篩選條件 [共同作業者] 準確尋找您需要的內容。
-   從活動記錄下拉式清單中，在 [來源] 下按一下 [檢視未經處理資料] 的連結，下載用來產生活動記錄的未經處理資料，以更進一步向下切入應用程式事件。 
-   新增 Okta 中額外登入活動的支援。 [私人預覽]
-   新增 Salesforce 中額外登入活動的支援。 

**改善**
-   改進 Cloud Discovery 快照集報告的可用性及疑難排解。
-   改進警示清單中，對多個應用程式發出的警示可見度。
-   改進建立新 Cloud Discovery 連續報告時的可用性。
-   改進治理記錄的可用性。



### <a name="cloud-app-security-release-82"></a>Cloud App Security 版本 82
發行日期：2016 年 10 月 9 日

**改善**

- **變更電子郵件**和**變更密碼**活動現在與 Salesforce 中的泛型**管理使用者**活動無關。
- 已新增 SMS 每日警示限制的釐清。 每個電話號碼每天 (UTC) 最多傳送 10 則訊息。
- 已將新的憑證新增至已取代 Safe Harbor 之「隱私盾」的 Cloud Discovery 屬性 (僅與美國廠商有關)。
- 已新增 API 連接器失敗訊息的疑難排解，讓您更輕鬆地修復問題。
- 已改善 Office 365 協力廠商應用程式掃描的更新頻率。
- 已改善 Cloud Discovery 儀表板。
- 已改善 Checkpoint Syslog 剖析器。
- 改善治理記錄中的禁止和取消禁止協力廠商應用程式。
 
**錯誤修正**
 
- 改善標誌上傳程序。
 
### <a name="cloud-app-security-release-81"></a>Cloud App Security 版本 81
發行日期：2016 年 9 月 18 日

**改善**
- Cloud App Security 現在是 Office 365 中的第一方應用程式！ 從現在起，只要按一下，就可以將 Office 365 連線至 Cloud App Security。

- 治理記錄的新外觀 - 現在已升級成與活動記錄和檔案資料表相同的實用外觀。 使用新的篩選，輕鬆找出您的需求以及監視您的治理動作。 
- 已改善異常偵測引擎的多次失敗登入和其他風險因子。
- 已改善 Cloud Discovery 快照集報告。
- 已改善活動記錄中的管理活動；變更密碼、更新使用者、重設密碼現在指出活動是否執行為管理活動。
- 已改善系統警示的警示篩選。 
- 警示內原則的標籤現在連結回原則報告。
- 如果未指定 Dropbox 檔案的擁有者，則會將通知電子郵件訊息傳送給您設定的收件者。 
- Cloud App Security 支援額外的 24 種語言，以將我們的支援擴充到共 41 種語言。  


### <a name="cloud-app-security-release-80"></a>Cloud App Security 版本 80
發行日期：2016 年 9 月 4 日 

**改善**
- DLP 掃描失敗時，會提供 Cloud App Security 為何無法掃描檔案的解釋。 如需詳細資訊，請參閱[內容檢查](https://aka.ms/aka.ms/cas-contentinspection)。
- 已改善異常偵測引擎，包括改善不可能的旅遊警示。
- 改善關閉警示經驗，您也可以新增意見反應，讓 Cloud App Security 團隊知道警示是否有趣，以及為什麼您的意見反應可以用來改善 Cloud App Security 偵測。
- 已增強 Cisco ASA Cloud Discovery 剖析器。
- 現在，Cloud Discovery 記錄手動上傳完成時，即可收到電子郵件通知。
   



### <a name="cloud-app-security-release-79"></a>Cloud App Security 版本 79
發行日期：2016 年 8 月 21 日 

**新功能**

- **新的 Cloud Discovery 儀表板**  
提供全新 Cloud Discovery 儀表板，設計目的是讓您深入了解如何在組織中使用雲端應用程式。 它概述正在使用的應用程式種類、未解決的警示以及組織中應用程式的風險層級。 它也可讓您知道誰是組織中的最上層應用程式使用者，並提供 App Headquarter 位置圖。
新的「儀表板」具有多個用於篩選資料的選項，可讓您根據最感興趣的項目來產生特定檢視，並且提供容易了解的圖形，讓您一目瞭然。

- **新的 Cloud Discovery 報告** 若要檢視 Cloud Discovery 結果，您現在可以產生兩種類型的報告：快照集報告和連續報告。
快照集報告提供一組手動從防火牆和 Proxy 上傳之流量記錄的臨機操作可見度。 連續報告顯示使用 Cloud App Security 的記錄收集器從您的網路轉寄的所有記錄結果。 這些新的報告提供所有資料的改良可見度、自動識別 Cloud App Security 機器學習異常偵測引擎所識別的異常使用，以及識別您使用強固且更細微原則引擎所定義的異常使用。 如需詳細資訊，請參閱[設定 Cloud Discovery](set-up-cloud-discovery.md)。
 
**改善**
- 改善下列頁面中的一般使用性︰原則頁面、一般設定、郵件設定。
- 在 [警示] 表格中，現在較容易區分讀取與未讀取警示。 讀取警示的左邊會有藍色線並呈現灰色，表示您已讀取過它們。
- 已更新活動原則**重複活動**參數。 
- 在 [帳戶] 頁面中，已新增使用者**類型**資料行，因此，您現在可以看到每個使用者所具有的使用者帳戶類型。 使用者類型是應用程式特有的。 
- 在 OneDrive 和 SharePoint 中，已新增檔案相關活動的近乎即時支援。 檔案變更時，Cloud App Security 幾乎會立即觸發掃描。


### <a name="cloud-app-security-release-78"></a>Cloud App Security 版本 78
發行日期：2016 年 8 月 7 日

**改善**
- 從特定檔案中，您現在可以按一下滑鼠右鍵，並 [尋找相關內容]。 從活動記錄中，您可以使用目標物件篩選，然後選取特定檔案。

- 改善 Cloud Discovery 記錄檔剖析器 (包括新增 Juniper 和 Cisco ASA)。
- 現在，當您關閉警示時，Cloud App Security 可讓您提供改善警示的意見。 讓我們知道為什麼關閉警示 (例如，不有趣、收到許多類似警示、實際嚴重性應該更低、警示不精確)，就可以協助改善 Cloud App Security 警示品質。
-在 [檔案原則] 檢視中，或檢視檔案時，如果您開啟檔案抽屜，則已新增 [相符的原則] 的新連結。 當您按一下它時，即可檢視所有相符項目，您現在已可以關閉全部。 
- 使用者所屬的組織單位現在新增至所有相關警示。
- 現在，要讓您知道手動上傳記錄檔的處理完成時會傳送電子郵件通知。


### <a name="cloud-app-security-release-77"></a>Cloud App Security 版本 77
發行日期：2016 年 7 月 24 日

**改善：**
- 已改善 Cloud Discovery [匯出] 按鈕圖示的使用性。
- 調查活動時，如果尚未剖析使用者代理程式，則您現在可以看到原始資料。
- 異常偵測引擎中已新增兩個新的風險因素︰ 
    - Cloud App Security 現在將殭屍網路相關 IP 位址標記和匿名 IP 位址當成風險計算的一部分。 
    - 現在會監視 Office 365 活動是否具有高下載率。 如果 Office 365 下載率遠大於您組織 (或特定使用者) 的一般下載率，則會觸發「異常偵測」警示。 
- Cloud App Security 現在已與新的 Dropbox [安全共用功能](https://blogs.dropbox.com/dropbox/2016/06/new-dropbox-productivity-tools/) API 相容。 
- 已改善將詳細資料新增至 Discovery 記錄剖析錯誤，包括：沒有雲端相關交易、所有事件都已過時、檔案損毀、記錄格式不相符。
- 已改善活動記錄日期篩選；它現在包含依時間進行篩選的能力。
- 已改善 IP 位址範圍頁面的使用性。
- Cloud App Security 現在支援 Microsoft Azure 資訊保護 (預覽版本)。 您可以使用標記安全分類來篩選檔案以及設定檔案原則，然後設定您想要檢視的分類標籤層級。 標籤也會指出您的組織或另一個租用戶 (外部) 中是否有人已設定分類。 



### <a name="cloud-app-security-release-76"></a>Cloud App Security 版本 76
發行日期：2016 年 7 月 10 日

**改善：**

- 現在可以匯出內建報告中的使用者清單。
- 改善彙總活動原則的使用性。
- 改善 TMG W3C 防火牆記錄訊息剖析器的支援。
- 檔案治理動作的改良使用性下降，現在已分成共同作業、安全性和調查動作。
- 改善 Exchange Online 活動的不可能旅遊偵測︰傳送郵件。
- 新的標題 (軌跡) 清單已新增至 [警示] 和 [原則] 頁面頂端，方便進行瀏覽。

**錯誤修正：**
- 檔案原則 DLP 設定中之信用卡的預設運算式已變更為「全部︰財務︰信用卡」。


### <a name="cloud-app-security-release-75"></a>Cloud App Security 版本 75
發行日期：2016 年 6 月 27 日


**新功能：**
* 新的新增項目已新增至不斷成長的支援 Salesforce 事件清單，包含了解報告、共用連結、內容發佈、模擬登入等事件。
* Cloud App Security 儀表板上的已連線應用程式圖示狀態，會與儀表板上所顯示以反映最近 30 天的應用程式狀態一致。
* 全螢幕支援。


**錯誤修正：**
* SMS 警示電話號碼現在會在插入時進行驗證。

### <a name="cloud-app-security-release-74"></a>Cloud App Security 版本 74
發行日期：2016 年 6 月 13 日
* [警示] 畫面已更新，為您提供更多資訊的概觀，包括能夠快速查看所有使用者活動、活動對應、相關的使用者治理記錄檔、觸發警示的原因描述，以及使用者頁面中的其他圖形和對應。 
* Cloud App Security 產生的事件現在包括事件類型、格式、群組原則、相關的物件和描述。
* 針對 Office 365 ProPlus、OneNote、Office Online 和 Exchange Online Protection 新增了新的 IP 位址標記。
* 您現在可以選擇從主要探索功能表上傳記錄檔。
* IP 位址類別篩選已獲得改善。 Null 的 IP 位址類別現在稱為未分類，並且新增了稱為「沒有值」的新類別，以包含沒有 IP 位址資料的所有活動。
* Cloud App Security 中的安全性群組現在稱為使用者群組，以避免和 Active Directory 安全性群組混淆。
* 現在可以針對每個 IP 位址篩選，和篩選掉不含 IP 位址的事件。 
* 在活動原則與檔案原則中偵測到相符項目時，傳送通知電子郵件的設定已變更。 您現在可以為您想要寄送通知副本的收件者新增電子郵件地址。


### <a name="cloud-app-security-release-73"></a>Cloud App Security 版本 73
發行日期：2016 年 5 月 29 日

* 更新警示功能︰現已可為每項原則設定警示，透過電子郵件傳送或傳送簡訊。
* 警示頁面︰已改善了設計，更可運用進階的解決方法選項及事件管理。
* 調整原則︰您現已可利用警示，直接從警示解決方法選項移到 [原則設定] 頁面，以便更容易依警示加以調整。
* 根據客戶的意見，改善了異常偵測風險分數的計算，且降低了誤判率。
* 活動記錄匯出現已包含事件識別碼、事件分類與事件類型名稱。
* 已改善建立原則治理動作的外觀與可用性。
* 已簡化 Office 365 的調查與控制 - 選擇使用 Office 365 會自動選取隸屬於 Office 365 套件的所有應用程式。
* 通知現已會傳送到連線的應用程式中所設定之電子郵件地址。 
* 發生連線錯誤時，雲端應用程式現已可提供有關錯誤的詳細說明。
* 當檔案符合原則時，現已於檔案抽屜中提供用於存取檔案的 URL。
* 活動原則或異常偵測原則觸發警示時，會傳送新的詳細通知，提供符合項目的相關資訊。 
* 中斷應用程式連接器的連線時，就會觸發自動化系統警示。
* 您現已可關閉及解決單一警示，或從 [警示] 頁面選取大範圍的警示。

### <a name="cloud-app-security-release-72"></a>Cloud App Security 版本 72
發行日期：2016 年 5 月 15 日

*  已改善一般外觀與基礎結構，包括：
    * 有新的圖表可提供 Cloud Discovery 手動記錄上傳程序的更多協助。
    * 已改善更新無法辨識 (「其他」) 的記錄檔之程序，包括讓您知道檔案需要其他檢閱的快顯視窗，而且會在資料可使用時通知您。
    * 調查活動與過時瀏覽器和作業系統的檔案記錄時，可反白顯示更多活動及檔案違規。
* 已改善 Cloud Discovery 記錄檔剖析器，包括加入 Cisco ASA、Cisco FWSM、Cisco Meraki 與 W3C。
* 改善 Cloud Discovery 已知問題。
* 已為擁有者的網域與內部/外部聯盟加入了新的活動篩選器。
* 已加入新的篩選器，您可用以搜尋任何 Office 365 物件 (檔案、資料夾、URL)。
* 已加入一項功能，可設定異常偵測原則的最低風險分數。
* 當您設定在違反原則時要傳送警示，現已可設定您要接到警示的最低嚴重性等級。 您可以選擇為此使用貴組織的預設值，您可以設定特定的警示設定作為您組織的預設值。

### <a name="see-also"></a>另請參閱  

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  