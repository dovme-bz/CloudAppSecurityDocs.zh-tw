---
title: "Azure 資訊保護整合 | Microsoft Docs"
description: "本文提供如何在 Cloud App Security 中使用 Azure Information Protection 標籤，提升您對組織之雲端應用程式的控制程度。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eceb326c4ab14852ecd284cfbaa0d2eb07149168
ms.openlocfilehash: bf3b2c9fcd374ee9a980d123890b9c78f6fb9e07


---

# <a name="azure-information-protection-integration"></a>Azure 資訊保護整合

Cloud App Security 讓您調查檔案，並依據 Azure Information Protection 檔案標籤設定原則，提升您監視及控制雲端上敏感性資料的能力。 若要達到此目的，請在 Cloud App Security 中設定原則，指定在掃描檔案時須啟用內容檢查功能。 此外，您可對與分類檔案相關的活動觸發警示。 Azure Information Protection 整合可以讓您：
-   量化敏感性資料在不同雲端應用程式的揭露程度。
-   針對您連線之雲端程式違規上傳機密資料的情事建立原則與警示，或隔離/封鎖敏感性資料，避免這類資料外洩。
-   調查稽核記錄，並修復違反原則的檔案 

> [!NOTE] 
> 除非有檔案原則指定在掃描檔案時，須啟用內容檢查，否則在掃描檔案時，預設只會掃描標籤。 若不要使用檔案原則，而只要掃描所有檔案中的標籤，可啟用自動掃描。

## <a name="terminology-overview"></a>術語概觀
-   Azure Information Protection 分類標籤 - 為組織中的檔案新增屬性，可以是自動新增，也可以依據原則、手動新增，或由使用者設定。
-   外部 - 由組織外部人員所設定的標籤。
-   檔案標籤 - 分類標籤在 Cloud App Security 中的表現方式。 檔案表內的每個檔案都會顯示此欄位，並可在篩選時使用。
-   檔案原則 - 一組會使用檔案篩選的規則，讓您可以利用雲端提供者的 API，施行各式各樣的自動化流程。

## <a name="license-and-tenant-creation"></a>建立授權及租用戶
若要能夠執行此功能，除了需要 Cloud App Security 授權之外，也需要 Azure Information Protection Premium P1 或 P2 的授權。 當這項兩種授權準備就緒之後，Cloud App Security 便會將組織標籤與 Azure Information Protection 服務同步：

![Azip 畫面範例](./media/azip-screen.png)

![Cas 與 Azip 的比較](./media/cas-compared-azip.png)
     
此外，經過一或多項檔案原則之內容檢查的檔案，預設也會掃描其分類標籤。

## <a name="gain-visibility"></a>增加可見度

每個檔案中經過掃瞄的檔案標籤，都會顯示在檔案抽屜中。
在 [檔案] 頁面中，按一下相關檔案檢查其中有無檔案標籤：

![檔案抽屜](./media/azip-file-drawer.png)

您可以按一下標籤檢視更多資訊，或查看完整的標籤清單：
 
![標籤清單](./media/azip-tags-list.png)

使用**檔案標籤**篩選，搜尋使用特定標籤標記的檔案：
 
![檔案標籤篩選](./media/azip-file-tags-filter.png)

或者，對於標記任何檔案標籤的檔案：

![檔案標記所有的篩選](./media/azip-file-tags-all-filter.png)

## <a name="how-it-works"></a>運作方式
您將 Cloud App Security 連接至 Azure 資訊保護後，Cloud App Security 就會如下所述掃描檔案：
1. 擷取您租用戶所使用的所有分類標籤清單。 每隔一小時會執行一次，使清單維持最新狀態。
2. 掃描檔案是否有分類標籤。 這有兩種進行方式︰a. 內容依據檔案原則需掃瞄的檔案，也將新增至分類標籤的掃描佇列。
    b. 若要將所有檔案都新增至掃瞄佇列而不設定檔案原則，請啟動自動掃描 (如下所示)，這將會掃描所有新檔案或修改過的檔案。
3. 除非您選取 [Ignore Azure Information Protection classification labels from other tenants] (略過其他租用戶的 Azure 資訊保護分類標籤) 核取方塊 (如下所示)，否則外部標籤只會在顯示於特定檔案上時，才會新增至分類標籤清單。

## <a name="enable-automatic-scan"></a>啟用自動掃描
若要在 Office 365 中自動掃描新檔案的檔案標籤：

1. 在 Office 365 中，前往 [一般設定] 頁面。
2. 在 Azure 安全性設定下，選取 [自動掃描檔案的 Azure Information Protection 分類標籤]。 啟用之後，不只是依據檔案原則需要掃描內容的檔案，所有新增到 Office 365 的檔案中都會掃描檔案標籤。

![啟用 Azure Information Protection](./media/enable-azip.png)
 

## <a name="internal-and-external-tags"></a>內部及外部標籤
Cloud App Security 預設會掃描您組織所定義的分類標籤，以及其他組織所定義的外部分類標籤。 

若要忽略分類標籤，請從 **Auzre 安全性設定**中選取 [Ignore Azure Information Protection classification labels from other tenants] (忽略其他租用戶的 Azure Information Protection 分類標籤) 。
 
![忽略標籤](./media/azip-ignore.png)

> [!Note]
> 若是使用測試租用戶工作，建議不要忽略分類標籤，如此才能測試您從其他租用戶收到的檔案。

![Cloud App Security 中的 Azure Information Protection 標籤](./media/azip-tags-in-cas.png)

## <a name="use-azure-information-protection-tags-to-apply-control"></a>使用 Azure Information Protection 標籤套用控制
在 Cloud App Security 建立檔案原則，可偵測不當共用的檔案，以及已標示標籤，但近期曾修改過的檔案。 

**原則 #1 - 在 Box 上對外共用機密資料： **

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找在 Box 上對外共用的所有機密資料：

![機密性原則](./media/azip-confidentiality-policy.png) 

**原則 #2 - 受限制的資料最近曾在 SharePoint 的 Finance 資料夾以外之處修改過：**

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找所有最近曾經修改過之受限制的資料，並在資料夾選擇選項中新增排除 Finance 資料夾： 
 
![受限制的資料原則](./media/azip-restricted-data-policy.png) 

您也可以為這些原則選擇設定警示、使用者通知或立即採取行動。
深入了解[管理動作](governance-actions.md)。

深入了解 [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection) 及查看 Azure Information Protection [ 快速入門教學課程](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial)。

  

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  



<!--HONumber=Nov16_HO5-->


