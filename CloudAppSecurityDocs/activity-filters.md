---
title: "活動 | Microsoft Docs"
description: "本主題提供可套用至活動原則的活動、篩選和比對參數清單。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 156dccf0c77bf7e46c0328ebf6bd1e0ad9609845
ms.openlocfilehash: f1dc1e39309cfe06037a13da55d92935786bed81


---
# <a name="activities"></a>活動
Cloud App Security 為提供資料保護，讓您可從連接的應用程式看見所有活動。 Cloud App Security 連接到使用 App 連線程式的應用程式後，Cloud App Security 會掃描發生的所有活動 (每個應用程式的追溯掃描時段都不相同)，再以新的活動不斷更新。 您可以根據活動建立原則，然後定義想要收到的警示項目。 您也可以搜尋對特定檔案執行的活動。 我們取得的每項活動的活動與資訊類型，是根據應用程式和應用程式可以提供的資料種類而定。 

例如，您可以使用**活動**記錄尋找貴組織中使用過期作業系統或瀏覽器的使用者，方法如下：當您在 [活動記錄] 頁面上將 Office 365、Google Apps、Box、Dropbox、Okta、Amazon Web Services 或 Salesforce 連接到 Cloud App Security 之後，請使用進階篩選器並選取 [使用者代理程式標籤]。 然後選取 [過期的瀏覽器] 或 [過期的作業系統]。 如果看到有組織外部共用的**機密**檔案，您可以按一下 [從搜尋新增原則] 建立活動原則，偵測過期的瀏覽器與作業系統並自動通知使用者。

 ![過期的瀏覽器活動範例](media/activity-outdated-example.png)

 

您可以篩選活動記錄，進而找到特定活動。 基本篩選條件提供您絕佳的工具以開始篩選活動。

 ![基本活動記錄篩選條件](media/activity-log-filter-basic.png)

若要向下鑽研更明確的活動，您可以按一下 [進階] 展開基本篩選條件。

 ![進階活動記錄篩選條件](media/activity-log-filter-advanced.png)

## <a name="activity-filters"></a>活動篩選
以下是可套用的活動篩選清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
-   活動識別碼 - 依據識別碼，僅搜尋特定活動。 若您要將 MCAS 連接到 SIEM (使用 SIEM 代理程式)，並進一步調查 MCAS 入口網站中的警示時，就非常適合使用此篩選。  
  
-   活動物件 – 搜尋活動執行對象物件。 此篩選器適用於檔案、資料夾、使用者或應用程式物件。
    - 活動物件識別碼 - 物件 (檔案、資料夾、使用者或應用程式識別碼) 的識別碼。
    - 檔案、資料夾或網站 URL - 讓您能夠選取開頭為特定字串的檔案、資料夾和 URL。
    - 目標物件 (檔案/資料夾) - 可讓您選取特定檔案或資料夾。 
    
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
    - IP 類別 - 執行活動的來源 IP 位址類別；例如，來自系統管理 IP 位址範圍的所有活動。 如需 IP 類別的詳細資訊，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。  
    - IP 標記 - 執行活動的來源 IP 位址標記；例如，來自匿名 Proxy IP 位址的所有活動。 如需 IP 標籤的詳細資訊，請參閱[依據需求來組織資料](general-setup.md#IPtagsandRanges)。
  
-   模擬活動 – 僅搜尋以其他使用者名稱所執行的活動。  

-   位置 – 執行活動的來源國家/地區。  

-   相符的原則 – 搜尋與入口網站所設定之特定原則相符的活動。  

-   已註冊的 ISP – 執行活動的來源 ISP。   

-  來源 - 依據偵測到其中有活動的來源進行搜尋。 來源可以是下列任一項：
  - App 連線程式 - 直接來自應用程式 API 連接器之記錄。
  - App 連線程式分析 - 以 API 連接器所掃描到之資訊為基礎的 Cloud App Security 額外功能。
  

-   使用者 - 執行活動的使用者，可使用網域、群組、名稱或組織進行篩選。 若要篩選不具特定使用者的活動，您可以使用 ‘is not set’ 運算子。  
    -   使用者網域 - 搜尋特定使用者網域。
    -   使用者群組 - Cloud App Security 自動從雲端應用程式匯入的特定使用者群組，例如 Office 365 系統管理員所執行的所有活動。
    -   使用者名稱 - 搜尋特定的使用者名稱。
    -   使用者組織 – 執行活動之使用者所屬的組織單位，例如 EMEA_marketing 使用者所執行的所有活動。  

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

![隱藏式活動選單](./media/activity-drawer.png "隱藏式活動選單")  
  
如需可用的治理動作清單，請參閱[活動比對參數](governance-actions.md#activity-match-parameters)。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO2-->


