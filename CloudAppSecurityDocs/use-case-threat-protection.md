---
title: "威脅防護案例概觀 | Microsoft Docs"
description: "本主題描述保護您的組織免受雲端環境威脅的案例。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/30/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fcc793f0fea71ef0666a7c99034185c5cd5fd894
ms.sourcegitcommit: 7e9ae94cb4f90fbccaa84f19bdebb4652a425e45
translationtype: HT
---
# <a name="controlling-and-protecting-your-files"></a>控制和保護您的檔案  

識別高風險使用情況和雲端安全性問題、偵測異常使用者行為，以及避免獲批准雲端應用程式中的威脅。 檢視使用者和系統管理員活動，並定義原則以在出現可疑行為，或認定特定活動在獲批准環境中有風險時，自動發出警示。 擷取大量 Microsoft 威脅情報和安全性研究資料。 威脅偵測原則可協助您確保獲批准的應用程式具備所有必要的安全性控制，並協助您維持掌控這些應用程式。
 
## <a name="massive-quantities-of-files-are-being-downloaded-insider-data-exfiltration"></a>下載數量龐大的檔案 (測試人員資料竊取)

這個使用案例適用於 Office 365、Google Apps、Box、Dropbox、Salesforce。

### <a name="the-threat"></a>威脅
遭盜用的帳戶攻擊者可以藉由下載或存取多個檔案，從 Office 365 或其他雲端應用程式竊取資料。

### <a name="the-solution"></a>解決方案
偵測使用者在短時間內下載或存取大量檔案的情況。

#### <a name="prerequisites"></a>必要條件

將至少一個雲端應用程式[連接](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)到 Cloud App Security。

#### <a name="setting-up-monitoring"></a>設定監視

1.    根據預設，Cloud App Security 會掃描您的網路來建立基準，藉此了解您的使用者一般會在雲端中執行哪些工作、何時執行，以及經常執行哪些工作等模式。 

2. 此外，請務必設定原則以開始監視雲端應用程式，該原則會監看雲端應用程式是否有大量下載，並在發生異常情況時發出警示：

    1. 在 [原則] 頁面上，按一下 [[建立活動原則]](user-activity-policies.md)。 
    ![建立活動原則](./media/create-activity-policy.png)

    2. 在 [[原則範本]](policy-template-reference.md) 欄位中，選擇 [單一使用者大量下載]。
    
    3. (選擇性) 您可以微調重複活動篩選。
    
    4. 按一下 [套用範本]。 
    ![活動原則範本](./media/activity-policy-template.png)
     
2. 調查相符項目
    
    1. 在 [原則] 頁面上，按一下原則名稱以移至 [原則報告]，然後檢閱原則所觸發的相符項目。

    2. 您可以按一下特定相符項目來開啟活動下拉式清單，藉以調查相符項目。 在下拉式清單中，您可以查看此活動相符的其他原則。 
     


#### <a name="validating-your-policy"></a>驗證您的原則

1. 若要模擬警示，請依照原則設定中的定義，在短時間內，從雲端連線應用程式多次下載多份文件 (例如在不到 30 分鐘內下載 10 次)。
3. 移至原則報告。 活動原則相符項目應該很快就會出現。 
4. 您可以按一下相符項目來查看已下載的檔案。 相符項目本身會加上遮罩以保護機密資料。 

#### <a name="removing-the-risk"></a>移除風險

在您驗證及微調原則之後，移除可能符合原則的可能誤報。 然後執行下列動作： 
  1. 您可以立即採取[治理動作](governance-actions.md)，方法是按一下資料列結尾的三個點，然後選取相關的治理動作，例如**將使用者置入隔離中**。

 ![外部自動治理](./media/auto-gov-external.png)

   2. 進行完整驗證之後，您可以設定它來執行自動治理動作。 例如，在 SharePoint 和 OneDrive 中，您可以**移除外部使用者**或**置入使用者隔離中**，而針對 G Suite 和 Box，您可以**移除外部使用者**和**移除公用存取權**。

  ![套用自動治理動作](./media/apply-automatic-gov-actions.png)



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  