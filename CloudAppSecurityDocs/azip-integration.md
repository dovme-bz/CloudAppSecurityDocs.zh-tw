---
title: 整合 Azure Information Protection 與 Cloud App Security | Microsoft Docs
description: 本文提供如何在 Cloud App Security 中使用 Azure Information Protection 標籤，提升您對組織之雲端應用程式的控制程度。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/16/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: abca47db7d4c3aa2db69bca2219e742af96b040e
ms.sourcegitcommit: b439f29dc1d0aa8eec783ba45e3d517722a5ebe0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2018
ms.locfileid: "43016936"
---
*適用於：Microsoft Cloud App Security*


# <a name="azure-information-protection-integration"></a>Azure 資訊保護整合

無論是否受保護，Microsoft Cloud App Security 可讓您將 Azure 資訊保護分類標籤自動套用至檔案，當作檔案原則治理動作。 您也可以在 Cloud App Security 入口網站中篩選套用的分類標籤，以調查檔案。 這可讓您對雲端的敏感性資料有更大的可見性與掌控度。 整合 Azure Information Protection 與 Cloud App Security 就像選取一個單一核取方塊一樣簡單。 

將 Azure Information Protection 整合到 Cloud App Security，即可利用這兩個服務的完整功能，以及保護雲端中的檔案，包括︰
- 能夠對符合特定原則的檔案套用分類標籤當作治理動作
- 在集中位置檢視所有分類檔案的能力
- 根據分類層級執行調查以及量化雲端應用程式上敏感性資料暴露的能力
- 建立原則以確認正確處理分類檔案的能力


> [!NOTE] 
> 若要能夠執行此功能，除了需要 Cloud App Security 授權之外，也需要 Azure 資訊保護 Premium P1 的授權。 當這項兩種授權準備就緒之後，Cloud App Security 便會從 Azure 資訊保護服務同步組織標籤。


## <a name="prerequisites"></a>必要條件

- 若要使用 Azure 資訊保護整合，您必須啟用 [Office 365 應用程式連接器](connect-office-365-to-microsoft-cloud-app-security.md)。

Cloud App Security 目前支援下列檔案類型套用 Azure 資訊保護分類標籤：

- Word：docm、docx、dotm、dotx
- Excel：xlam、xlsm、xlsx、xltx
- PowerPoint：potm、potx、ppsx、ppsm、pptm、pptx
- 未來的版本將提供 PDF 

此功能目前適用於儲存於 Box、SharePoint Online 和商務用 OneDrive 中的檔案。 未來版本中將支援更多雲端應用程式。

Cloud App Security 目前無法掃描或變更標示為不受 Cloud App Security 保護的檔案。 標示為 Cloud App Security 外部 (不受保護) 的檔案可以掃描，而且 Cloud App Security 可套用依 Cloud App Security 原則定義的不同標籤 (無論是否受保護)。


## <a name="how-it-works"></a>運作方式
您可能熟悉 [Azure Information Protection](https://docs.microsoft.com/information-protection/) 中的檔案分類標籤。 您可以在 Cloud App Security 中查看 Azure Information Protection 分類標記。 整合 Cloud App Security 與 Azure Information Protection 之後，Cloud App Security 就會如下所述掃描檔案：

1. Cloud App Security 會擷取您租用戶所使用的所有分類標籤清單。 每隔一小時會執行一次，使清單維持最新狀態。

2. Cloud App Security 接著會掃描檔案是否有分類標籤，如下所示：

   1. 若您啟用自動掃描 (如下方所示)，所有新增或已修改的檔案就都會加到掃描佇列中，而系統會掃描、分類及保護所有現有檔案及存放庫。
   2. 如果您設定檔案原則 (請參閱後文) 以搜尋分類標籤，則會將這些檔案新增至分類標籤的掃描佇列。

3. 如上所述，這些掃描是針對 Cloud App Security 執行初始掃描時所發現的分類標籤，以查看租用戶所使用的分類標籤。 外部標籤 (租用戶外部人員所設定的分類標籤) 會新增至分類標籤清單。 若不想掃描，請選取 [Only scan files for Azure Information Protection classification labels from this tenant] (只掃描此租用戶的 Azure 資訊保護分類標籤) 核取方塊 (請參閱下文)。

4. 在 Cloud App Security 上啟用 Azure Information Protection 之後，也會掃描所有已新增至 Office 365 的新檔案是否有分類標籤。

5. 您可以在 Cloud App Security 中建立自動套用分類標籤的新原則。

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>如何整合 Azure Information Protection 與 Cloud App Security
  
### <a name="enable-azure-information-protection"></a>啟用 Azure Information Protection

整合 Azure Information Protection 與 Cloud App Security 時，您只需要：啟用自動掃描以在 Office 365 檔案搜尋 Azure Information Protection 分類標籤，而不需要建立一個原則。 啟用這項功能之後，如果您有雲端環境中標上 Azure Information Protection 分類標籤的檔案，則會在 Cloud App Security 中看到它們。

讓 Cloud App Security 掃描已啟用分類標籤內容檢查的檔案：

1. 在 Cloud App Security 的 [設定] 齒輪下，選取 [一般設定] 頁面。
2. 在 Azure 資訊保護下，選取 「Automatically scan files for Azure Information Protection classification labels」 (自動掃描檔案尋找 Azure 資訊保護分類標籤)。 

啟用 Azure Information Protection 之後，就可以在 Cloud App Security 中查看具有分類標籤的檔案以及根據標籤進行篩選。 Cloud App Security 連線到雲端應用程式之後，您就能夠使用 Cloud App Security Azure 資訊保護整合功能，將 Azure 資訊保護標籤直接新增至檔案或設定自動套用分類標籤當作治理動作的檔案原則，直接在 Cloud App Security 入口網站中套用 Azure 資訊保護標籤 (無論是否受保護)。


 ![啟用 Azure Information Protection](./media/enable-azip.png)

> [!NOTE] 
> 自動掃描不會掃描現有的檔案，直到這些檔案經過修改為止。 若要掃描現有檔案是否有 Azure 資訊保護分類標籤，您至少要有一項**內容檢查檔案原則**。 如果完全沒有的話，請建立新的**檔案原則**、刪除所有預設篩選，並選取 [內容檢查] 選項。 接著在 [內容檢查] 下，按一下 [Include files that match a preset expression (包含符合預設運算式的檔案)] 並選取任何預先定義的值，然後儲存原則。 如此便可啟用內容檢查，以自動偵測 Azure 資訊保護分類標籤。

#### <a name="set-internal-and-external-tags"></a>設定內部和外部標記
Cloud App Security 預設會掃描組織中所定義的分類標籤，以及其他組織所定義的外部分類標籤。 


若要忽略在組織外部設定的分類標籤，請在 Cloud App Security 入口網站，從 [一般設定] 的 [Auzre 安全性設定] 下，選取 [Ignore Azure Information Protection classification labels from other tenants]\(忽略其他租用戶的 Azure Information Protection 分類標籤)。
 
![忽略標籤](./media/azip-ignore.png)

### <a name="apply-labels-directly-to-files"></a>直接將標籤套用至檔案

1. 從 [檔案] 頁面上，選取您要保護的檔案，然後按一下檔案資料列結尾的三個點，接著選擇 [套用分類標籤]。

   ![保護應用程式](./media/protect-app.png)
  
   >[!NOTE]
   > Cloud App Security 可以在最高達 50 MB 的檔案上套用 Azure 資訊保護。  

2. 系統會要求您選擇組織分類標籤的其中之一，套用至檔案，並按一下 [套用]。 
   ![保護分類標籤](./media/protect-template.png)

3. 當您選擇分類標籤並按一下 [套用] 之後，Cloud App Security 會將分類標籤套用至原始檔案。

4. 您也可以選擇 [移除分類標籤] 選項移除分類標籤。 


如需 Cloud App Security 與 Azure 資訊保護如何搭配使用的詳細資訊，請參閱[保護資料不受使用者錯誤影響](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)。

### <a name="automatically-label-files"></a>自動為檔案貼上標籤

您可以建立檔案原則，並將 [套用分類標籤] 設定為治理動作，將分類標籤自動套用到檔案。

請遵循下列指示建立檔案原則：

1. 建立檔案原則。
2. 設定原則包含您想要偵測的檔案類型，例如，[存取層級] 不等於 [內部] 以及 [擁有者 OU] 等於您財務小組的所有檔案。 
3. 在相關應用程式的治理動作下，[套用分類標籤] 然後選取標籤類型。

   ![套用標籤](./media/aip-gov-action.png)

> [!NOTE]
> 能夠透過檔案原則自動套用 Azure 資訊保護標籤是強大的功能。 為了避免客戶意外地將標籤套用至大量檔案，因此每個租用戶對每個應用程式有 100 個 [套用標籤] 動作的每日限制作為安全預防措施。 達到每日限制之後，套用標籤動作會暫時暫停，並會於隔天 (12:00 UTC 之後) 自動繼續。 若要提高您的租用戶之限制，請[連絡 Cloud App Security 支援](mailto:cascoresupport@microsoft.com)。

### <a name="control-file-exposure"></a>控制檔案暴露

- 如果這是您貼上 Azure 資訊保護分類標籤的文件︰

   ![Azure 資訊保護範例畫面](./media/azip-screen.png)

- 篩選分類標籤之後，即可在 Cloud App Security 的 [檔案] 頁面中看到此檔案︰

   ![Cloud App Security 與 Azure 資訊保護的比較](./media/cas-compared-azip.png)

- 您可以在 [檔案] 頁面中按一下相關的檔案，於檔案抽屜中取得這些檔案及其分類標籤的詳細資訊，並檢查是否有分類標籤：

   ![檔案抽屜](./media/azip-file-drawer.png)

- 接著，您可以在 Cloud App Security 建立檔案原則，以控制不當共用的檔案，以及找到已標示標籤但近期曾修改過的檔案。
- 此外，您可對與分類檔案相關的活動觸發警示。

  ![Cloud App Security 中的 Azure 資訊保護標籤](./media/azip-tags-in-cas.png)

- 您也可以建立原則，將分類標籤自動套用至特定的檔案。


> [!Note]
> 當停用檔案上的 Azure Identity Protection 標籤時，停用的標籤在 Cloud App Security 中會顯示為「已停用」。 已刪除的標籤則不會顯示。


**原則範例 - 在 Box 上對外共用機密資料：**

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找在 Box 上對外共用的所有機密資料：

![機密性原則](./media/azip-confidentiality-policy.png) 

**原則範例 - 受限制的資料最近曾在 SharePoint 的 Finance 資料夾以外之處修改過：**

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找所有最近曾經修改過之受限制的資料，並在資料夾選擇選項中新增排除 Finance 資料夾： 
 
![受限制的資料原則](./media/azip-restricted-data-policy.png) 

您也可以為這些原則選擇設定警示、使用者通知或立即採取行動。
深入了解[管理動作](governance-actions.md)。

深入了解 [Azure 資訊保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)及查看 Azure 資訊保護[快速入門教學課程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。


 
## <a name="related-videos"></a>相關影片  
[Cloud App Security 與 Azure 資訊保護的整合](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
