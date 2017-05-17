---
title: "了解 Cloud App Security 中可用的檔案資料和篩選 | Microsoft Docs"
description: "本參考主題提供 Cloud App Security 所使用之檔案和檔案篩選器的類型資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cadcd6db-05b2-4974-91fe-cfac3d57aecd
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 305c7ab0293e35ffbabc9b665a5b797619111131
ms.sourcegitcommit: 50fac1cec86dfb8170ba9c63a8f58a4bf24e3c5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2017
---
# <a name="files"></a>檔案


Cloud App Security 讓您可從連接的應用程式看見所有檔案，以提供資料保護。 當您使用 App 連線程式連接 Cloud App Security 與應用程式後，Cloud App Security 會掃描所有的檔案，例如，儲存在 OneDrive 和 Salesforce 的所有檔案。 然後，Cloud App Security 每次修改都會重新掃描每個檔案，修改的部分可以是內容、中繼資料或共用權限。 掃描的時間取決於儲存在應用程式中的檔案數目。 您也可以使用 [檔案] 頁面篩選檔案，調查雲端應用程式中儲存的資料類型。 

例如，您可以使用 [檔案] 頁面保護標示為**機密**的外部共用檔案，方法如下︰將應用程式連接到 Cloud App Security 之後，即可與 Azure 資訊保護整合。 然後，在 [檔案] 頁面中，篩選出標示**機密**的檔案。 如果透過篩選 [共同作業者] 篩選條件來排除網域，看到有組織外部共用的**機密**檔案，您可以建立檔案原則，偵測已套用不當存取層級的**機密**檔案，並且為它們套用自動治理動作 (例如 「Remove external collaborators」 (移除外部共同作業者) 和 「Send policy-match digest to file owner」 (將原則相符摘要傳送給擁有者))，防止組織資料遺失。

 ![機密檔案篩選器](media/file-filter-confidential.png)

以下是如何利用 [檔案] 頁面的另一個範例。 確定您的組織中沒有在過去 6 個月未修改過的公開或外部共用檔案：將應用程式連接到 Cloud App Security 之後，請在 [檔案] 頁面中篩選出檔案，而檔案的存取層級為 [外部] 或 [公開]，並將 [上次修改時間] 日期設定為 6 個月之前。 您可以建立檔案原則來偵測這些過時的公用檔案，方法是按一下 「New policy from search」 (從搜尋新增原則)，並且為它們套用自動治理動作 (例如 [移除外部使用者])，防止組織資料遺失。

 ![篩選過時外部檔案](media/file-example-stale-external.png)

基本篩選條件提供您絕佳的工具以開始篩選檔案。

 ![基本檔案記錄篩選條件](media/file-log-filter-basic.png)

若要向下鑽研更明確的檔案，您可以按一下 [進階] 展開基本篩選條件。

 ![進階檔案記錄篩選條件](media/file-log-filter-advanced.png)
 
###  <a name="Filefilters"></a>檔案篩選器 
 
Cloud App Security 可以根據 20 個以上的中繼資料篩選條件 (例如：存取層級、檔案類型) 來監視任何檔案類型。 
 
Cloud App Security 的內建 DLP 引擎可從所有常見的檔案類型 (PDF、Office 檔案、RTF、HTML、程式碼檔案等) 擷取文字以執行內容檢查。

以下是可套用的檔案篩選器清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
> [!NOTE] 
> 使用檔案原則篩選時，**Contains** 僅會搜尋**完整字組** – 以逗點、點、空格或底線分隔進行搜尋。 
> - 字組間的空格功能類似 OR，例如若您搜尋 **malware** **virus**，即會尋找所有名稱中有 malware 或 virus 的檔案，所以會同時尋找 malware-virus.exe 及 virus.exe。  
> - 如果想要搜尋字串，請用引號括住文字。 此功能類似 AND，例如：如果搜尋 **"malware"** **"virus"**，即會尋找 virus_malware_file.exe，但不會尋找 malwarevirusfile.exe 或是 malware.exe。 不過，它會搜尋完整字串。 如果搜尋 **"malware virus"**，不會尋找 **"virus"** 或 **"virus_malware"**。

>**Equals** 僅會搜尋完整字串；例如，如果您搜尋 **malware.exe**，它會找到 malware.exe，但不會找到 malware.exe.txt。 

-   存取層級 – 共用存取層級；公開、外部、內部或私人。  如需外部檔案的詳細資訊，請參閱[一般設定、設定入口網站](getting-started-with-cloud-app-security.md)。內部檔案是指您在內部網域 (透過[一般設定](General-setup.md)來設定) 內使用的任何檔案。 外部檔案是指儲存在您所設定之內部網域以外的任何檔案。 共用檔案為具有私人以上之共用層級的檔案，包括內部共用 (在您的內部網域中共用的檔案)、外部共用 (在您的內部網域之外共用的檔案)、以連結公用 (可與任何人透過連結共用的檔案) 和公用 (可在網際網路上搜尋找到的檔案) 檔案。 

> [!NOTE]
>  Cloud App Security 會以下列方式處理由外部使用者共用到您的連線儲存體應用程式中的檔案：
> - **OneDrive：** OneDrive 會將內部使用者指派為任何外部使用者所放入您 OneDrive 中之檔案的擁有者。 如此一來，系統會將這些檔案視為組織所擁有，Cloud App Security 即可掃描這些檔案並套用原則，就像 OneDrive 中的任何其他檔案一樣。
> - **Google 雲端硬碟：**Google 雲端硬碟會將這些檔案視為外部使用者擁有，既然這些檔案和資料不屬於您的組織，基於法律限制，Cloud App Security 即不能存取這些檔案。
> - **Box：**由於 Box 會將外部擁有的檔案視為私人資訊，因此 Box 全域管理員無法查看檔案的內容。 基於這個理由，Cloud App Security 並不能存取這些檔案。 
> - **Dropbox：**由於 Dropbox 會將外部擁有的檔案視為私人資訊，因此 Dropbox 全域管理員無法查看檔案的內容。 基於這個理由，Cloud App Security 並不能存取這些檔案。

-   應用程式 – 僅搜尋這些應用程式中的檔案。  
  
-   共同作業者 – 包含/排除特定的共同作業者群組。  
  
    -   網域的任何使用者 – 如果來自此網域的任何使用者皆可存取檔案，即適用此項目。  
  
    -   整個網域 – 如果整個網域皆可存取檔案，即適用此項目。  
  
    -   群組 – 如果特定群組可存取檔案，即適用此項目。 您可以從 Active Directory 與雲端應用程式匯入群組，或在服務中手動建立群組。  
  
    -   使用者 – 可存取檔案的一組特定使用者。  
  
-   建立時間 – 檔案建立時間。 篩選器可支援日期前後與日期範圍的搜尋。  
  
-   副檔名 – 著重於特定副檔名；例如，所有可執行檔案 (exe)。  
  
-   檔案識別碼 – 搜尋特定的檔案識別碼；這是一項進階功能，可讓您獨立於某些高價值檔案的擁有者/位置/名稱，來追蹤檔案。  
  
-   檔案名稱 – 雲端應用程式中定義的檔案名稱或名稱的子字串；例如，名稱中含有密碼的所有檔案。   
  
-   分類標籤 - 搜尋具有 Azure 資訊保護所設定特定標籤的檔案。 這需要與 Azure 資訊保護整合。

-   檔案類型 – Cloud App Security 會接收來自服務的兩個 MIME 類型，並掃描檔案以判斷真正的檔案類型。 請注意，這項掃描適用於資料掃描相關的檔案 (文件、影像、簡報、試算表、文字檔和 zip/封存檔)。 依據檔案/資料夾類型進行篩選，例如 ... 的所有資料夾或 ... 的所有試算表檔案。


 ![policy_file 篩選器垃圾桶](./media/policy_file-filters-trash.png "policy_file 篩選器垃圾桶")  

  
-   在垃圾桶中 – 排除/包含 Trash 資料夾中的檔案。 這些檔案可能仍受共用，並會造成風險。  
  
-   上次修改時間 – 檔案修改時間。 篩選器可支援日期之前/之後、日期範圍與相對的時間運算式；例如，前 6 個月都沒有修改過的所有檔案。  

-   相符原則 - 依據使用中 Cloud App Security 原則為相符的檔案。

-   MIME 類型 – 檔案 MIME 類型檢查，可接受任意文字。  
  
-   擁有者 – 包含/排除特定檔案擁有者；例如，追蹤由 rogue_employee_#100 共用的所有檔案。  
  
-   擁有者 OU – 包含/排除屬於特定組織群組的檔案擁有者；例如，所有公用檔案但不包括 EMEA_marketing 共用的部分。  
  
-   父資料夾 – 依據父資料夾來包含/排除項目；例如，所有公開共用的檔案但不包括此資料夾中的檔案。  
  
-   隔離 – 服務已隔離的檔案；例如，顯示所有隔離的檔案。  
  
您也可以將 **[Apply to (套用至)]** 篩選條件設為 [所有檔案]、 [選取的資料夾] 或 [All files excluding selected folders (選取的資料夾以外的所有檔案)]，然後選取相關檔案或資料夾，即可設定針對特定檔案執行原則。  
  
![套用至篩選器](./media/apply-to-filter.png "套用至篩選器")  
  
## <a name="working-with-the-file-drawer"></a>使用檔案抽屜

您可以按一下檔案記錄中的檔案本身，以檢視每個檔案的詳細資訊。 如此即可開啟檔案抽屜，其提供下列您可以對檔案執行的額外動作：

- URL：帶您前往檔案位置。
- 檔案識別碼：按一下 [檔案識別碼] 即可開啟快顯視窗，其中包含檔案的未經處理檔案詳細資料，包括檔案識別碼及加密金鑰。
- 擁有者：按一下 [擁有者] 即可檢視此檔案擁有者的使用者頁面。
- 相符的原則：按一下 [相符的原則] 連結即可查看此檔案符合的原則清單。
- 分類標籤：按一下 [分類標籤] 即可檢視此檔案中的 Azure 資訊保護分類標籤清單。 您接著可以依據符合此標籤的所有檔案進行篩選。    

隱藏式檔案選單中的欄位提供您可能想要從該隱藏式選單中直接執行的額外檔案和向下切入的內容連結。 例如，如果您將游標移到 [擁有者] 欄位旁邊，您可以使用 [新增至篩選] 圖示 ![新增至篩選](./media/add-to-filter-icon.png)，立即將擁有者新增至目前頁面的篩選中。 您也可以使用快顯的 [設定] 齒輪圖示 ![設定圖示](./media/contextual-settings-icon.png)，直接抵達修改其中一個欄位設定所需的設定頁面，例如**分類標籤**。


![隱藏式檔案選單](./media/file-drawer.png "隱藏式檔案選單")  
  
如需可用的治理動作清單，請參閱[檔案治理動作](governance-actions.md#file-governance-actions)。

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  
