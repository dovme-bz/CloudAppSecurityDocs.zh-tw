---
title: 威脅防護案例概觀 | Microsoft Docs
description: 本主題描述保護您的組織免受雲端環境威脅的案例。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 747199b758fb5bee40cc7ec036280c16416d0372
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


# <a name="protecting-your-organization-from-ransomware"></a>保護您的組織免受勒索軟體威脅

在最近大量的勒索軟體攻擊中，WannaCry 嚴重打擊網路世界，估計有 150 個國家/地區的 200,000 部電腦受到感染。 勒索軟體攻擊事件在過去幾年來逐漸增加，2015 年每月平均有 25,000 起攻擊事件，到了 2016 年增加到 56,000 起，這使得網路安全性變得至關重要，您必須主動確保網路和雲端沒有風險。 本文說明如何使用 Cloud App Security 監視雲端、偵測並減輕威脅，以及套用最佳做法來保護您的環境免受勒索軟體威脅。

## <a name="what-is-ransomware"></a>什麼是勒索軟體？
勒索軟體是一種網路攻擊，攻擊者會傳送您一個檔案，使您無法存取電腦及加密自己的檔案。 這些檔案有時會遭挾持要求贖金，而且您必須支付攻擊者贖金來還原電腦、檔案或重要 LOB 應用程式的存取權，才能將這些檔案解密。 勒索軟體攻擊可能會影響任何電腦、首頁、Office、網路或伺服器。 事實上，由於大型組織是由許多使用者所組成，這些使用者可能會不慎開啟檔案而將勒索軟體釋放到整個網路，因此組織更有可能被迫支付攻擊者贖金，以停止勒索軟體並還原電腦或檔案的存取權。

>[!NOTE]
> 這個使用案例適用於 Office 365、G Suite、Box 和 Dropbox。

## <a name="the-threat"></a>威脅
勒索軟體攻擊的目標是您組織中的使用者。 使用者可能在不知情的情況下開啟受感染的電子郵件，並執行勒索軟體而感染所有檔案，包括同步至雲端的檔案。

## <a name="the-solution"></a>解決方案
請建立原則在偵測到可疑活動時通知您，以偵測雲端環境中的潛在勒索軟體，並設定自動化動作，以避免將勒索軟體檔案儲存至您的雲端。

## <a name="out-of-the-box-protection"></a>預設的保護

至少將一個雲端應用程式 (Office 365、G Suite、Box 和 Dropbox) [連線](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)到 Cloud App Security。

1.  根據預設，Cloud App Security 會掃描您的網路來建立基準，藉此了解您的使用者一般會在雲端中執行哪些工作、何時執行，以及經常執行哪些工作等模式。 

2. Cloud App Security 的自動化[威脅偵測原則](anomaly-detection-policy.md)會從您連線的那一刻開始在背景中執行。 這些原則之一會搜尋勒索軟體活動，以確保防護複雜的勒索軟體攻擊涵蓋範圍完整。 使用安全性搜尋專業知識來識別可反映勒索活動的行為模式，Cloud App Security 保證可提供全面且強大的保護。 例如，若 Cloud App Security 發現有高比率的檔案上傳或檔案刪除活動，則可能代表加密程序設計不良。 這項資料會收集在從已連線應用程式 API 收到的記錄檔中，然後再和學習到的行為模式與威脅情報 (例如，已知的勒索軟體副檔名) 結合使用。 

## <a name="legacy-policy-creation"></a>建立舊版原則

2. 此外，請務必設定原則以開始監視雲端應用程式，該原則會監看雲端應用程式是否有大量下載，並在發生異常情況時發出警示：

    1. 在 [控制項] 索引標籤上，按一下 [[範本]](policy-template-reference.md)。 
   
    2. 從 [[原則範本]](policy-template-reference.md) 清單，選擇 [潛在的勒索軟體活動]。 
       ![勒索軟體範本](./media/ransomware-template.png)
    3. 此範本設計成可立即用來搜尋勒索軟體攻擊的典型活動，以及與已知勒索軟體相關的檔案和資料夾。 (選擇性) 您可以設定符合原則時所收到的警示類型 (電子郵件和簡訊)。
        ![勒索軟體範本](./media/ransomware-template-fields.png)
    4. 按一下 [建立]。 
   
     
2. 調查相符項目
    
    1. 在 [原則] 頁面上，按一下原則名稱以移至 [原則報告]，然後檢閱原則所觸發的相符項目。

    2. 您可以按一下特定相符項目來開啟活動下拉式清單，藉以調查相符項目。 在下拉式清單中，您可以查看此活動相符的其他原則。 
     
## <a name="remediating-attacks-and-preventing-risk"></a>修復攻擊並避免發生風險

在您驗證及微調原則之後，移除可能符合原則的可能誤報。 然後執行下列動作： 
1. 符合勒索軟體原則時，您可以設定自動化[治理動作](governance-actions.md)進行修復。

2. 若要防止未來遭受攻擊，請設定原則以執行自動化治理動作。 例如，在 SharePoint 和 OneDrive 中，您可以設定原則自動**暫時停止使用者的權限**。
 
 
## <a name="validating-ransomeware-protection"></a>驗證勒索軟體保護

1. 若要模擬警示，請將 30 個檔案的副檔名變更為 .wncry 並上傳到 SharePoint 網站。
3. 移至原則報告。 活動原則相符項目應該很快就會出現。 
4. 您可以按一下相符項目來查看已下載的檔案。 相符項目本身會加上遮罩以保護機密資料。 



   ## <a name="see-also"></a>另請參閱  
   [可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  