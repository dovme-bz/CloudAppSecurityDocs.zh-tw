---
title: 使用 Cloud App Security 活動篩選與查詢 | Microsoft Docs
description: 本主題提供 Cloud App Security 活動篩選與查詢清單，並說明如何使用它們。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9ba5c7d3-c733-4048-9b99-bf41a0f46695
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6d8eb8dd128645df1811ab8125096c7ddf77e0a1
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144086"
---
*適用於：Microsoft Cloud App Security*


# <a name="activity-filters-and-queries"></a>活動篩選與查詢

## <a name="activity-filters"></a>活動篩選

以下是可套用的活動篩選清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
- 活動識別碼 - 依據識別碼，僅搜尋特定活動。 若您要將 Cloud App Security 連線到 SIEM (使用 SIEM 代理程式)，並進一步調查 Microsoft Cloud App Security 入口網站中的警示時，就非常適合使用此篩選。  
  
- 活動物件 – 搜尋活動執行對象物件。 此篩選器適用於檔案、資料夾、使用者或應用程式物件。 
  - 活動物件識別碼 - 物件 (檔案、資料夾、使用者或應用程式識別碼) 的識別碼。
  - 檔案、資料夾或網站 URL - 讓您能夠選取開頭為特定字串的檔案、資料夾和 URL。
  - 目標物件 (檔案/資料夾) - 可讓您選取特定檔案或資料夾。 
  - 項目 - 可讓您依任何活動物件 (例如︰使用者名稱、檔案、參數、網站) 的名稱或識別碼搜尋。 針對 [活動物件項目] 篩選條件，您可以選取是否想要篩選「包含」、「等於」或「開頭為」指定項目的項目。
    
- 活動類型 - 搜尋應用程式活動。

- 系統管理活動 – 僅搜尋管理活動。  
  
- 警示識別碼 - 依警示識別碼搜尋。

- 應用程式 – 只搜尋特定應用程式內的活動。  
  
- 套用的動作 - 依套用的治理動作搜尋：封鎖、旁路 Proxy、解密、加密、加密失敗、無動作。

- 日期 – 活動發生的日期。 篩選器可支援日期前後與日期範圍的搜尋。  
  
- 描述 – 活動描述的特定關鍵字；例如，描述中包括**使用者**字串的所有活動。  
  
- 裝置標記 - 依相容、受管理獲通過驗證的裝置搜尋。

- 裝置類型 - 僅搜尋使用特定裝置類型所執行的活動；例如，來自行動裝置、電腦或平板電腦的所有活動。  
  
- IP 位址 - 執行活動來源的原始 IP 位址、類別或標記。  
  - 原始 IP 位址 - 可讓您搜尋在原始 IP 位址上執行或由其執行的活動，條件包括等於、不等於或開頭是否為特定順序，或是否為經過設定的原始 IP 位址。 
  - IP 類別 - 執行活動的來源 IP 位址類別；例如，來自系統管理 IP 位址範圍的所有活動。 類別需要設定成包含相關 IP 位址，但 "Risky" 類別除外，這種類別是預先設定的類別，並且包含兩個 IP 標記 - 匿名 Proxy 和 Tor。 若要了解如何設定 IP 類別，請參閱[依據需求來組織資料](ip-tags.md)。  
  - IP 標記 - 執行活動的來源 IP 位址標記；例如，來自匿名 Proxy IP 位址的所有活動。 Cloud App Security 建立一組不可設定的內建 IP 標記。 此外，您可以設定專屬 IP 標記。 如需設定專屬 IP 標記的詳細資訊，請參閱[依據需求來組織資料](ip-tags.md)。
  內建 IP 標記包含：
  - Microsoft 應用程式 (其中的 14 個)
  - 匿名 Proxy
  - 殭屍網路 (您可以使用可深入了解特定殭屍網路的連結，來查看疆屍網路已執行活動)
  - Darknet 掃描 IP
  - 惡意程式碼 C&C 伺服器
  - Remote Connectivity Analyzer
  - 衛星提供者
  - 智慧型 Proxy 和存取 Proxy (故意省略)
  - Tor 結束節點
  - Zscaler


- 模擬活動 – 僅搜尋以其他使用者名稱所執行的活動。  

- 位置 – 執行活動的來源國家/地區。  

- 相符的原則 – 搜尋與入口網站所設定之特定原則相符的活動。  

- 已註冊的 ISP – 執行活動的來源 ISP。   

- 來源 - 依據偵測到其中有活動的來源進行搜尋。 來源可以是下列任一項：
  - App 連線程式 - 直接來自應用程式 API 連接器之記錄。
  - App 連線程式分析 - 以 API 連接器所掃描到之資訊為基礎的 Cloud App Security 額外功能。
  

- 使用者 - 執行活動的使用者，可使用網域、群組、名稱或組織進行篩選。 若要篩選不具特定使用者的活動，您可以使用 ‘is not set’ 運算子。  
  - 使用者網域 - 搜尋特定使用者網域。
  - 使用者組織 – 執行活動之使用者所屬的組織單位，例如 EMEA_marketing 使用者所執行的所有活動。  
  - 使用者群組 - 可從連線應用程式匯入的特定使用者群組，例如 Office 365 管理員。  
  - 使用者名稱 - 搜尋特定的使用者名稱。 若要查看特定使用者群組中的使用者清單，請在 [活動] 選單中按一下使用者群組的名稱。 這會帶您前往 [帳戶] 頁面，其中列出群組中的所有使用者。 您可以從該處向下鑽研群組中特定使用者的帳戶詳細資料。
    -  您可以使用 [作為] 篩選並選取使用者角色，進一步篩選 [使用者群組] 和 [使用者名稱] 篩選。角色可以是下列任一項：
        - 僅活動對象 - 這表示選取的使用者或使用者群組未執行待查明的活動，他們是活動的對象
        - 僅活動執行者 - 這表示使用者或使用者群組執行了活動
        - 任何角色 - 這表示使用者或使用者群組與活動有關，而可能是執行活動的人或活動的對象

- 使用者代理程式 – 執行活動的來源使用者代理程式。  
  
- 使用者代理程式標記 - 內建的使用者代理程式標記；例如，來自過期瀏覽器或過期作業系統的所有活動。  
    
>[!NOTE]
> 每當您想要清除篩選時，您可以按一下清除篩選圖示 ![清除篩選圖示](./media/clear-filters.png) 來執行這個動作。


## <a name="activity-queries"></a>活動查詢

為更簡化調查，您現在可以建立自訂的查詢，並儲存以供日後使用。 

1. 如有需要，在 [活動記錄] 頁面中，使用上文描述的篩選向下鑽研至您的應用程式。 

2. 得到所要的結果之後，請按一下篩選器右上角的 [另存新檔] 按鈕。 

3. 在 [儲存查詢] 快顯視窗中命名您的查詢。

   ![新增查詢](./media/new-activity-query.png)

4. 日後若要再次使用這項查詢，請在 [查詢] 下向下捲動至 [儲存查詢]，並選取您的查詢。 

   ![開啟查詢](./media/select-activity-query.png)


Cloud App Security 也會提供您**建議的查詢**，讓您儲存經常使用的自訂查詢。 建議的查詢提供調查的建議途徑，其使用下列選用建議查詢來篩選活動：

 - 管理活動 - 篩選所有活動，只顯示與管理員有關的活動。

 - 下載活動 - 篩選所有活動，只顯示下載活動的活動，包括將使用者清單下載為 .csv 檔、下載共用內容和下載資料夾。

 - 失敗的登入 - 篩選所有活動，只顯示登入失敗和透過 SSO 的簽入失敗 

 - 檔案及資料夾活動 - 篩選所有活動，只顯示與檔案和資料夾有關的活動，包括上傳和下載資料夾；存取資料夾；建立、刪除、上傳、下載、隔離及存取檔案；以及傳送內容。 

 - 模擬活動 - 篩選所有活動，只顯示模擬活動。

 - 信箱活動 - 篩選所有活動，只顯示 Microsoft Exchange Online 的活動，例如建立項目、清除信箱的訊息、使用 [傳送為] 權限 (模擬) 來更新訊息和傳送訊息。

 - 密碼變更與重設要求 - 篩選所有活動，只顯示與密碼重設、變更密碼有關的活動，並強制使用者在下次登入時變更密碼。

 - 安全性風險 - 篩選所有活動，只顯示符合 DLP 原則的活動。

 - 共用活動 - 篩選所有活動，只顯示與共用資料夾和檔案有關的活動，包括建立公司連結、建立匿名連結，以及授與讀取/寫入權限。

 - 成功登入 - 篩選所有活動，只顯示與成功登入有關的活動，包括模擬動作、模擬登入、單一登入的登入，以及從新裝置登入。

![查詢活動](./media/queries-activity.png)
 
此外，您可以使用建議的查詢，作為新查詢的起點。 首先，選取其中一個建議的查詢。 然後，視需要進行變更，最後按一下 [另存新檔] 建立新的 [已儲存的查詢]。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  