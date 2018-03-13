---
title: "Cloud App Security 的新功能 | Microsoft Docs"
description: "本主題會經常更新，讓您知道最新版 Cloud App Security 的新功能。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/7/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 08a798bb20830afcbdb498c2ac72787873f72fab
ms.sourcegitcommit: 9de7ed2224aeed049fc2a87e52307988f8837eeb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2018
---
# <a name="whats-new-with-microsoft-cloud-app-security"></a>Microsoft Cloud App Security 的新功能


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
- 新的**以案例為基礎的偵測**增強了 Cloud App Security 異常偵測原則，其中案例包括不可能的旅行距離、來自可疑 IP 位址的活動，以及多次嘗試登入失敗。 新原則會自動啟用，為整個雲端環境提供立即可用的威脅偵測。 此外，新的原則會從 Cloud App Security 偵測引擎公開更多資料，以協助您加速調查程序，並遏制進行中的威脅。 如需詳細資訊，請參閱[取得即時的行為分析和異常偵測](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy)。

- 逐步推出：Cloud App Security 現在可跨 SaaS 應用程式以相互關聯使用者與其帳戶。 這可讓您輕鬆地跨越使用者所有各種相互關聯 SaaS 應用程式來調查他們的所有活動，而不論使用者所使用的應用程式或帳戶為何。  

-   逐步推出：Cloud App Security 現在支援相同已連線應用程式的多個執行個體。 例如，如果您有多個 Salesforce 的執行個體 (一個針對銷售，一個針對行銷)，則可以將兩者同時連線至 Cloud App Security 並從相同的主控台來管理，以建立更細微的原則和更深入的調查。 

- Cloud Discovery 剖析器現在支援 XML 和 KPC 兩個額外的檢查點格式。



## <a name="cloud-app-security-release-115"></a>Cloud App Security 115 版
發行日期：2018 年 1 月 21 日

-   此版本提供在檔案原則中選取特定資料夾時的增強體驗。 您現在可以輕鬆地檢視並選取多個要包含在原則中的資料夾。 
-   在 [探索到的應用程式] 頁面中： 
   - 大量標記功能可讓您套用自訂標籤 (除了獲批准的標籤和待批准的標籤)。 
   - 當您**產生 IP 位址報表**或**產生使用者報告**時，匯出的報表現在會包含流量是否來自獲批准或待批准應用程式的相關資訊。 
-   您現在可以在入口網站中的 [連線到應用程式] 頁面，直接向 Microsoft Cloud App Security 小組要求新的 API App 連線程式。 


## <a name="cloud-app-security-release-114"></a>Cloud App Security 版本 114
發行日期：2018 年 1 月 7 日

- 從 114 版開始，我們會逐漸推出在 [活動記錄] 和 [探索到的應用程式] 頁面中建立和儲存自訂查詢的功能。 自訂查詢可讓您建立篩選範本，可重複使用進行深入了解調查。 此外，已新增**建議的查詢**以提供立即可用的調查範本，篩選活動及探索到的應用程式。 **建議的查詢**包含識別風險的自訂篩選，例如模擬活動、管理員活動、危險的不相容雲端儲存體應用程式、使用弱式加密的企業應用程式，以及安全性風險。 您可以使用**建議的查詢**作為起點，在您認為合適時修改它們，然後儲存為新的查詢。 如需詳細資訊，請參閱[活動篩選與查詢](activity-filters-queries.md)和[探索到的應用程式篩選與查詢](discovered-app-queries.md)。
 
- 您現在可以前往 [status.cloudappsecurity.com](https://status.cloudappsecurity.com) 檢查目前的 Cloud App Security 服務狀態，或直接在入口網站內按一下 [說明]>[系統狀態]。 
 


## <a name="see-also"></a>另請參閱  

如需比此處所列版本更早之版本的描述，請參閱 [Microsoft Cloud App Security 的過去版本](release-note-archive.md)。

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  