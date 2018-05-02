---
title: 自動套用 Azure 資訊保護分類標籤 | Microsoft Docs
description: 本主題描述要在 Microsoft Cloud App Security 中自動套用 Azure 資訊保護分類標籤的程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b4d507b5fb3a646b31ba3c380b170c2abca18ddf
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*



# <a name="automatically-apply-azure-information-protection-classification-labels"></a>自動套用 Azure 資訊保護分類標籤  

在理想的世界中，您的所有員工都了解資訊保護的重要性，並遵守您的規定。 但在真實世界中，處理帳戶的合作夥伴可能會以錯誤的權限將文件上傳到您的 Box 存放庫，而一週後您意識到貴企業的機密資訊已外洩給您的競爭對手。 

Microsoft Cloud App Security 可協助您在遭受這種嚴重損壞之前避免其發生。

Microsoft Cloud App Security 確認對 Box 帳戶中儲存的文件具有公用權限，而且會使用分類引擎來確認公開共用的文件內含機密資訊。 Cloud App Security 會傳送警示，讓您知道發生這個問題；此外，它會自動套用 Azure 資訊保護的**機密**分類標籤，為檔案提供額外的加密。 

>[!NOTE]
> - 套用 Azure 資訊保護標籤是許多可用[治理動作](governance-actions.md)的其中之一。
> - 這項功能適用於 Box、SharePoint 和商務用 OneDrive。

### <a name="enhanced-data-level-encryption-protection"></a>增強的資料層級加密保護

Cloud App Security 與 Azure 資訊保護的整合可自動將檔案加密，以啟用多一層的保護。 例如，當 Azure 資訊保護將檔案加密時，支援 Azure 資訊保護的應用程式 (例如 Office 365) 就會知道如何開啟檔案，並接受分類標籤中設定的權限。 您可以使用標籤來套用特定的保護規則。 例如，您可以設定檔案，使其能夠開啟但無法共用、列印、轉寄或編輯。 

這種強大的保護層級會跟著檔案移動 - 如果您傳送檔案、複製檔案、將檔案儲存在線上儲存體應用程式，檔案仍受到保護。 如果您的其中一位員工遺失了內含檔案的隨身碟，則會鎖定檔案，如果有人嘗試開啟它，檔案擁有者將會收到警示。 使用 Cloud App Security，您可以自動套用保護。 例如，具有信用卡號碼或由財務部門上傳並於外部共用的所有檔案，都可以設定為使用分類標籤自動保護。 

## <a name="the-threat"></a>威脅 
貴組織中的使用者會將機密客戶資訊檔案儲存到 Box，並將它設定為在組織中與所有人共用。 該使用者並不了解除了他們的直屬小組外，全體支援人員都能存取該 Box 帳戶，這包括廠商、合作夥伴以及偶然進入辦公室的訪客。 能夠存取您組織 Box 帳戶的任何人，現在都會有該資訊的存取權。 這不僅對貴組織來說很危險，也可能會違反許多國家的 PII 規定，造成潛在的法律問題。

## <a name="the-solution"></a>解決方案
搭配使用 Cloud App Security 與 Azure 資訊保護來內嵌分類和保護資訊，以進行跟隨資料的持續保護—不論儲存的位置為何或共用的對象是誰，確保資料仍受到保護。 這也可讓您與同事以及您的客戶和合作夥伴安全地共用資料。 除了 Cloud App Security 所支援的其他[治理動作](governance-actions.md) (例如移除共同作業者和移除共用功能)　之外，還定義誰可以存取資料，以及他們可以使用它來做什麼 (例如允許使用者檢視並編輯檔案，但不能列印或轉寄)。

## <a name="prerequisites"></a>必要條件

- 為您的租用戶[啟用 Cloud App Security 和 Azure 資訊保護](azip-integration.md)。
- [將 Box 連線至 Cloud App Security](connect-box-to-microsoft-cloud-app-security.md)。

## <a name="setting-up-data-protection"></a>設定資料保護

讓我們設定尋找儲存在 Box 帳戶中之檔案信用卡號碼的原則，找到後自動套用 Azure 資訊保護標籤，然後使用該標籤控制所有檔案的情況。

1. 設定會對儲存在 Box 中的任何敏感性資料加密的原則，以開始保護您儲存在 Box 中的資料：

    1. 在 [控制] 索引標籤上，[按一下 [原則]](control-cloud-apps-with-policies.md)。 
    
    2. 按一下 [建立原則]，然後選取 [檔案原則]。
    
    3. 將原則命名為 *Box data protection*。
    
    4. 在 [為套用這項原則的檔案建立篩選] 下，將目標設為專屬與敏感性資料。<br></br>
    例如，選取 [父資料夾] 等同選取 Box 中的 [客戶資料]，而選取 [擁有者] 則等同選取財務小組。
    
    4. 在該資料夾內，尋找包含信用卡資訊的檔案，如下所示：在 [內容檢查方法] 下，選取 [內建 DLP]，然後選取 [包含符合預設運算式的檔案] 並選取 [所有國家/地區:財務:信用卡號碼]。
    
    5. 在 [治理] 下，開啟 [Box] 區段，然後選取 [套用分類標籤] 並選取您要套用的標籤。
    
    6. 因為 [Cloud App Security 已與 Azure 資訊保護整合](azip-integration.md)，所以您可以從現有的分類標籤清單中選取要用於保護資料的標籤。
 
    7. 按一下 [建立]。 
   
   ![將分類標籤新增至原則](./media/aip-auto-policy.png)
     
2. 調查相符項目
    
    1. 在 [原則] 頁面上，按一下原則名稱以移至 [原則報告]，然後檢閱原則所觸發的相符項目。

    2. 您可以按一下特定相符項目來開啟隱藏式檔案選單，藉以調查相符項目。 在下拉式清單中，您可以看到此檔案符合的其他原則。 
     
## <a name="validating-your-policy"></a>驗證您的原則

1. 若要模擬警示，請前往您的 Box 帳戶然後嘗試存取 [客戶資料] 資料夾中的檔案。
3. 移至原則報告。 檔案原則相符項目應該很快就會出現。 
4. 您可以按一下相符項目來查看有哪些檔案受到保護。 相符項目本身會加上遮罩以保護機密資料。 

>[!NOTE]
> - Cloud App Security 目前支援對 Box、SharePoint 和商務用 OneDrive 自動套用 Azure 資訊保護標籤。
> - 當文件使用 Cloud App Security 來加上標籤時，視覺標記不會立即套用，而會在文件於 Office 應用程式中開啟，並初次儲存後才套用。 如需詳細資訊，請參閱[如何為 Azure 資訊保護的標籤設定視覺標記](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-markings#when-visual-markings-are-applied)。

 ## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  