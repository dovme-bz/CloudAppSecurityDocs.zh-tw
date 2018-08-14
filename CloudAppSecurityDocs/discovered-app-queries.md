---
title: 使用 Cloud App Security 探索到的應用程式篩選與查詢 | Microsoft Docs
description: 本主題提供 Cloud App Security 探索到的應用程式篩選與查詢清單，並說明如何使用它們。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 1a2d3aeb-4e28-4c73-804b-95e862b08e43
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a2b5ec778ef7e9cd5968353b247f117f3019d3be
ms.sourcegitcommit: 96f82381a17b89f9aef384f760ebf142695a6051
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653276"
---
*適用於：Microsoft Cloud App Security*

# <a name="discovered-app-filters-and-queries"></a>探索到的應用程式篩選與查詢

## <a name="discovered-app-filters"></a>探索到的應用程式篩選

探索到的應用程式篩選分為基本和進階。 若要取得複雜的篩選 (如以上範例所示)，請使用包括下列所有篩選的進階選項：

![探索到的應用程式](./media/discovered-apps.png)  


- **應用程式標籤**：選擇應用程式為獲批准、待批准或未標記。 此外，您可以為應用程式建立自訂標籤，然後使用此標籤來篩選特定應用程式類型。 
- **應用程式與網域**：可讓您搜尋特定應用程式或用於特定網域的應用程式。 
- **類別**：類別篩選位於頁面左邊，可讓您根據應用程式類別搜尋不同類型的應用程式，例如社交網路應用程式、雲端儲存體應用程式等。您可以一次選取多個類別或單一類別，然後將基本和進階篩選套用其上。
- **合規性風險因素**：可讓您搜尋應用程式可能符合的特定標準、認證與規範 (HIPAA、ISO 27001、SOC 2、PCI-DSS 等)。
- **一般風險因素**：可讓您搜尋一般風險因素，例如消費者歡迎程度、資料中心地區設定等。
- **風險分數**：可讓您依風險分數篩選應用程式，以便專注在只檢閱高風險的應用程式。 您也可以覆寫 Cloud App Security 所設定的風險分數。 如需詳細資訊，請參閱[使用風險分數](risk-score.md)。
- **安全性風險因素**：可讓您根據特定安全措施 (例如待用資料加密、多重要素驗證等) 進行篩選。
- **使用量**：可讓您根據此應用程式的使用量統計資料進行篩選，例如具有小於或大於指定**資料上傳**數目的應用程式，以及具有大於或小於指定**使用者**數目的應用程式。
- **法務法務風險因素**：讓您根據所有適用法規與原則進行篩選，以確保應用程式使用者的資料保護與隱私權，例如 GDPR 就緒的雲端應用程式、DMCA 與資料保留原則。

### <a name="creating-and-managing-custom-app-tags"></a>建立及管理自訂應用程式標籤

您可以建立自訂應用程式標籤。 接著可以使用這些標籤作為篩選，以深入探討您想要調查的特定應用程式類型。 例如，自訂監看清單、給特定業務單位的指派，或自訂核准，例如 "approved by legal"。

建立自訂應用程式標籤：

1. 從**設定**齒輪選取 [Cloud Discovery]，然後在 [Manage app tags]\(管理應用程式標籤\) 索引標籤中，按一下圖示 ![加號圖示](./media/plus-icon.png)。 

![建立自訂應用程式標籤](./media/create-app-tag.png)

2. 您可以使用 [Manage app tags]\(管理應用程式標籤) 資料表，檢視每個應用程式標籤目前標記的應用程式，而且您可以刪除未使用的應用程式標籤。

3. 若要套用應用程式標籤，請在 [探索到的應用程式] 索引標籤中，按一下資料表最右側的三個點，然後選取要套用的應用程式標籤。 

> [!NOTE]
>您也可以直接在 [探索到的應用程式] 資料表中建立新的應用程式標籤，方法是在選取任何所選應用程式右側的三個點之後，按一下 [Create app tag]\(建立應用程式標籤)。 您也可以按一下 [Create app tag]\(建立應用程式標籤) 快顯視窗角落的連結，來存取 [Manage app tags]\(管理應用程式標籤) 畫面。

## <a name="discovered-app-queries"></a>探索到的應用程式查詢

為更簡化調查，您現在可以建立自訂的查詢，並儲存以供日後使用。 

1. 如有需要，在 [探索到的應用程式] 頁面中，使用上文描述的篩選向下鑽研至您的應用程式。 

2. 得到所要的結果之後，請按一下篩選器右上角的 [另存新檔] 按鈕。 

3. 在 [儲存查詢] 快顯視窗中命名您的查詢。

   ![新增查詢](./media/new-query.png)

4. 日後若要再次使用這項查詢，請在 [查詢] 下向下捲動至 [儲存查詢]，並選取您的查詢。 

   ![開啟查詢](./media/discovered-app-query.png)


Cloud App Security 也會提供您**建議的查詢**，讓您儲存經常使用的自訂查詢。 建議的查詢提供調查途徑建議，使用下列選用建議查詢篩選探索到的應用程式：

 - 允許匿名使用的雲端應用程式 - 會篩選所有探索到的應用程式，只顯示有安全性風險的應用程式，因為它們不需要使用者驗證，而且允許使用者上傳資料。

 - 經 CSA STAR 認證的雲端應用程式 - 會篩選所有探索到的應用程式，只顯示具有 CSA STAR 認證的應用程式 (透過自我評定、認證、證明或持續監視)。

 - 符合 FedRAMP 規範的雲端應用程式 - 會篩選所有探索到的應用程式，只顯示 FedRAMP 合規性風險因素為高、中或低的應用程式。 

 - 擁有使用者資料的雲端儲存體和共同作業應用程式 - 會篩選所有探索到的應用程式，只顯示有風險的應用程式，因為它們不允許您有自己資料的擁有權，但它們卻要保留您的資料。

 - 有風險且不相容的雲端儲存體應用程式 - 會篩選所有探索到的應用程式，只顯示與 SOC 2 或 HIPAA 不相容的應用程式，它們不支援 PCI DSS 版本，風險分數為 5 或更低。

 - 具有弱式驗證的企業雲端應用程式 - 會篩選所有探索到的應用程式，只顯示不支援 SAML、沒有密碼原則且未啟用 MFA 的應用程式。

 - 具有弱式加密的企業雲端應用程式 - 會篩選所有探索到的應用程式，只顯示有風險的應用程式，因為它們不會加密待用資料，而且不支援任何加密通訊協定。

- GDPR 就緒雲端應用程式：篩選您探索到的所有應用程式，只顯示 GDPR 就緒的應用程式。 因為 GDPR 合規性是最高優先事項，所以此查詢有助於輕鬆地找出 GDPR 就緒的應用程式，並藉由評定未經評定的風險來降低威脅。
 
![查詢探索到的應用程式](./media/queries-discovered-apps.png)

 
此外，您可以使用建議的查詢，作為新查詢的起點。 首先，選取其中一個建議的查詢。 然後，視需要進行變更，最後按一下 [另存新檔] 建立新的 [已儲存的查詢]。


## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

