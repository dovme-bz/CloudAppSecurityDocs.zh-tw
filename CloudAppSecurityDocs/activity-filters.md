---
title: "雲端應用程式活動的可視性 | Microsoft Docs"
description: "本主題提供可套用至活動原則的活動、篩選和比對參數清單。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/2/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8f22fc1c949a265b3a53cc4a534550be9601d10
ms.sourcegitcommit: 661f4ce41262e8462c90fd2a4f1232e2154d5113
translationtype: HT
---
# <a name="activities"></a>活動
Cloud App Security 可讓您從連接的應用程式看見所有活動。 Cloud App Security 連接到使用 App 連線程式的應用程式後，Cloud App Security 會掃描發生的所有活動 (每個應用程式的追溯掃描時段都不相同)，再以新的活動不斷更新。 

> [!NOTE] 
> 如需 Cloud App Security 所監視的 Office 365 活動完整清單，請參閱[搜尋 Office 365 安全與規範中心的稽核記錄](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)

您可以篩選 [活動記錄]，進而找到特定活動。 您可以根據活動建立原則，然後定義想要收到的警示項目並採取動作。 您也可以搜尋對特定檔案執行的活動。 我們取得之每項活動的活動與資訊類型，都是取決於應用程式以及應用程式可提供的資料種類。 

例如，您可以使用 [活動記錄] 尋找組織中使用過期作業系統或瀏覽器的使用者，方法如下：當您在 [活動記錄] 頁面上將應用程式連接到 Cloud App Security 之後，請使用進階篩選，並選取 [User agent tag]\(使用者代理程式標記)。 然後選取 [過期的瀏覽器] 或 [過期的作業系統]。

 ![過期的瀏覽器活動範例](media/activity-example-outdated.png)

如果您想要檢查是否有在組織外部存取的**機密**檔案，請設定 [Activity object]\(活動物件) 篩選條件來搜尋 [Classification label]\(分類標籤)，然後選取 [機密] 標籤。 設定 [IP 位址] 篩選條件來搜尋 [類別]，並排除正式 IP 位址 (您可以在 [設定] 功能表中設定 IP 類別)。 您可以按一下 [New policy from search]\(從搜尋新增原則)，根據您所定義的篩選條件來建立活動原則，並自動通知使用者。

 ![活動機密檔案外部範例](media/activity-example-ip.png)

 
基本篩選條件提供您絕佳的工具以開始篩選活動。

 ![基本活動記錄篩選條件](media/activity-log-filter-basic.png)

若要向下鑽研更明確的活動，您可以按一下 [進階] 展開基本篩選條件。

 ![進階活動記錄篩選條件](media/activity-log-filter-advanced.png)

## <a name="activity-filters"></a>活動篩選
以下是可套用的活動篩選清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
-   活動識別碼 - 依據識別碼，僅搜尋特定活動。 若您要將 Cloud App Security 連線到 SIEM (使用 SIEM 代理程式)，並進一步調查 Cloud App Security 入口網站中的警示時，就非常適合使用此篩選。  
  
-   活動物件 – 搜尋活動執行對象物件。 此篩選器適用於檔案、資料夾、使用者或應用程式物件。 
    - 活動物件識別碼 - 物件 (檔案、資料夾、使用者或應用程式識別碼) 的識別碼。
    - 檔案、資料夾或網站 URL - 讓您能夠選取開頭為特定字串的檔案、資料夾和 URL。
    - 目標物件 (檔案/資料夾) - 可讓您選取特定檔案或資料夾。 
    - 項目 - 可讓您依任何活動物件 (例如︰使用者名稱、檔案、參數、網站) 的名稱或識別碼搜尋。 針對 [活動物件項目] 篩選條件，您可以選取是否想要篩選「包含」、「等於」或「開頭為」指定項目的項目。
    
-   活動類型 - 搜尋應用程式活動。

-   系統管理活動 – 僅搜尋管理活動。  
  
-   警示識別碼 - 依警示識別碼搜尋。

-   應用程式 – 只搜尋特定應用程式內的活動。  
  
-   套用的動作 - 依套用的治理動作搜尋：封鎖、旁路 Proxy、解密、加密、加密失敗、無動作。

-   日期 – 活動發生的日期。 篩選器可支援日期前後與日期範圍的搜尋。  
  
-   描述 – 活動描述的特定關鍵字；例如，描述中包括**使用者**字串的所有活動。  
  
-   裝置標記 - 依相容、受管理獲通過驗證的裝置搜尋。

-   裝置類型 - 僅搜尋使用特定裝置類型所執行的活動；例如，來自行動裝置、電腦或平板電腦的所有活動。  
  
-   IP 位址 - 執行活動來源的原始 IP 位址、類別或標記。  
    - 原始 IP 位址 - 可讓您搜尋在原始 IP 位址上執行或由其執行的活動，條件包括等於、不等於或開頭是否為特定順序，或是否為經過設定的原始 IP 位址。 
    - IP 類別 - 執行活動的來源 IP 位址類別；例如，來自系統管理 IP 位址範圍的所有活動。 類別需要設定成包含相關 IP 位址，但 "Risky" 類別除外，這種類別是預先設定的類別，並且包含兩個 IP 標記 - 匿名 Proxy 和 Tor。 若要了解如何設定 IP 類別，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。  
    - IP 標記 - 執行活動的來源 IP 位址標記；例如，來自匿名 Proxy IP 位址的所有活動。 Cloud App Security 建立一組不可設定的內建 IP 標記。 此外，您可以設定專屬 IP 標記。 如需設定專屬 IP 標記的詳細資訊，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。
   內建 IP 標記包含：
    - Microsoft 應用程式 (其中的 14 個)
    - 匿名 Proxy
    - 殭屍網路
    - Darknet 掃描 IP
    - 惡意程式碼 C&C 伺服器
    - Remote Connectivity Analyzer
    - 衛星提供者
    - 智慧型 Proxy 和存取 Proxy (故意省略)
    - Tor 結束節點
    - Zscaler


-   模擬活動 – 僅搜尋以其他使用者名稱所執行的活動。  

-   位置 – 執行活動的來源國家/地區。  

-   相符的原則 – 搜尋與入口網站所設定之特定原則相符的活動。  

-   已註冊的 ISP – 執行活動的來源 ISP。   

-  來源 - 依據偵測到其中有活動的來源進行搜尋。 來源可以是下列任一項：
  -    App 連線程式 - 直接來自應用程式 API 連接器之記錄。
  -    App 連線程式分析 - 以 API 連接器所掃描到之資訊為基礎的 Cloud App Security 額外功能。
  

-   使用者 - 執行活動的使用者，可使用網域、群組、名稱或組織進行篩選。 若要篩選不具特定使用者的活動，您可以使用 ‘is not set’ 運算子。  
    -   使用者網域 - 搜尋特定使用者網域。
    -   使用者組織 – 執行活動之使用者所屬的組織單位，例如 EMEA_marketing 使用者所執行的所有活動。  
    -   使用者群組 - 可從連線應用程式匯入的特定使用者群組，例如 Office 365 管理員。  
    -   使用者名稱 - 搜尋特定的使用者名稱。 若要查看特定使用者群組中的使用者清單，請在 [活動] 選單中按一下使用者群組的名稱。 這會帶您前往 [帳戶] 頁面，其中列出群組中的所有使用者。 您可以從該處向下鑽研群組中特定使用者的帳戶詳細資料。
       -  您可以使用 [作為] 篩選並選取使用者角色，進一步篩選 [使用者群組] 和 [使用者名稱] 篩選。角色可以是下列任一項：
            - 僅活動對象 - 這表示選取的使用者或使用者群組未執行待查明的活動，他們是活動的對象
            - 僅活動執行者 - 這表示使用者或使用者群組執行了活動
            - 任何角色 - 這表示使用者或使用者群組與活動有關，而可能是執行活動的人或活動的對象

-   使用者代理程式 – 執行活動的來源使用者代理程式。  
  
-   使用者代理程式標記 - 內建的使用者代理程式標記；例如，來自過期瀏覽器或過期作業系統的所有活動。  
    
  
## <a name="working-with-the-activity-drawer"></a>使用 [活動] 下拉式清單

您可以檢視各項活動的詳細資訊，方法是在活動記錄中按一下活動本身。 如此即開啟 [活動] 下拉式清單，其中提供下列您可以對檔案執行的額外動作：

- 相符原則：按一下 [相符原則] 連結以查看此活動符合的原則清單。
- 檢視原始資料︰按一下 [檢視原始資料] 以查看從應用程式收到的實際資料。
- 使用者：按一下使用者檢視活動執行使用者的使用者頁面。 
- 裝置類型：按一下裝置類型檢視未經處理的使用者代理程式資料。 
- 位置：按一下位置用 Bing 地圖服務檢視位置。
- IP 位址類別與標記：按一下 IP 標記以檢視在此活動中找到的 IP 標記清單。 您接著可以依據符合此標記的所有活動進行篩選。    

隱藏式活動選單中的欄位提供您可能想要從該隱藏式選單中直接執行的額外活動和向下切入的內容連結。 例如，如果您將游標移到 IP 位址類別旁邊，您可以使用 [新增至篩選] 圖示 ![新增至篩選](./media/add-to-filter-icon.png)，立即將 IP 位址新增至目前頁面的篩選中。 您也可以使用快顯的 [設定] 齒輪圖示 ![設定圖示](./media/contextual-settings-icon.png)，直接抵達修改其中一個欄位設定所需的設定頁面，例如**使用者群組**。


![隱藏式活動選單](./media/activity-drawer.png "隱藏式活動選單")  
  
如需可用的治理動作清單，請參閱[活動治理動作](governance-actions.md#activity-governance-actions)。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  