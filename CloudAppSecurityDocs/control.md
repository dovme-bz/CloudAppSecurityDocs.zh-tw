---
title: "如何使用治理動作以控制雲端應用程式使用情況 | Microsoft Docs"
description: "本文章提供的相關資訊說明您可以在 Cloud App Security 中採取哪些治理動作，以控制組織的雲端應用程式使用方式。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 596c3436432a3183afbca37138a0f790560024b3
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2017
---
# <a name="control"></a>控制
您可將治理動作套用至整個雲端環境的使用者檔案。 在徹底調查及了解雲端之後，您可以使用治理動作來協助保護組織。  

## <a name="use-policies-to-assess-risk"></a>使用原則評估風險  
查看未解決的警示後，請移至原則中心檢閱未觸發警示的原則違規。  

-   在 Cloud App Security 儀表板中，依序按一下 **[控制]** 及 **[原則]**。  

-   選取特定的原則，查看符合原則但未觸發警示的 **[立即違規]** 清單。  

-   按一下違規，一次一個，判斷該如何處理每個違規。 如需管理動作的詳細資訊，請參閱以下圖表。  

     如果原則設定為尋找相容性缺口，而有人將信用卡號碼儲存在 OneDrive 的檔案中，原則中就會有相符項目。  

     ![PCI 相符項目](./media/pci-matches.png "PCI 相符項目")  

-   選取相符項目，查看違反原則的實際檔案。  

     ![PCI 內容相符項目](./media/pci-content-matches.png "PCI 內容相符項目")  

     您可以選取檔案本身以取得檔案的相關資訊。  

     您可以按一下 **[共同作業者]**，查看可以存取這個檔案的人員。  

     您可以按一下 **[相符項目]**，查看實際的信用卡號碼。  

     ![內容相符項目 ccn](./media/content-matches-ccn.png "內容相符項目 ccn")  

## <a name="apply-governance-actions"></a>套用治理動作  
您可以從原則內部、警示內部以及透過 **[檔案]** 記錄來套用治理動作。  

您可以隨時前往 [設定] 齒輪 ![設定圖示](./media/settings-icon.png "設定圖示")，並選擇 [治理記錄]，以檢閱並查看所有先前套用之治理動作的狀態。  

若有任何失敗的治理動作，選擇**重試**圖示 ![重試圖示](./media/retry-icon.png "重試圖示") 即可再次套用。  

不同類型的原則、違規及應用程式，可用的治理動作也各異。  

## <a name="move-from-detection-to-automatic-remediation"></a>從偵測移動到自動補救  
在您定義及自訂原則篩選後，即可選取在每次原則違規時所發生的自動治理動作。  
由於補救動作會利用雲端提供者 API，因此動作會因應用程式而異。  

> [!NOTE]  
>  當您設定治理動作時，請特別小心。 它們可能會導致遺失檔案的存取權限，且無法復原。  
> 建議您使用多個搜尋欄位，縮小篩選的範圍以明確表示您想要處理的檔案。 篩選器範圍愈小愈好。  
>   
>  如需指引，您可以使用 **[篩選]** 區段中的 **[編輯及預覽結果]** 按鈕。  

![檔案原則編輯及預覽結果](./media/file-policy-edit-and-preview-results.png "檔案原則編輯及預覽結果")  

## <a name="migration"></a>移轉  
Cloud App Security 可讓您知道組織中的使用者正在使用哪些應用程式，並提供監視新應用程式採用情況的工具，以協助您進行移轉。 其中也有相關工具讓您查看大家已在使用哪些應用程式，協助您了解可為組織提供何種類型的應用程式。  

### <a name="migrate-your-users-to-a-new-app"></a>將您的使用者移轉至新的應用程式  
假設您最近購買 Office 365，並想要讓組織中的所有使用者停用所有其他雲端儲存體應用程式，而開始使用 OneDrive。 您可能想要執行下列動作：  

1.   前往 [Cloud Discovery 儀表板]，並使用 [類別] 下方的 [雲端儲存體] 來篩選應用程式。 然後依照 [使用者] 或 [IP 位址] 排序結果，並查看哪些應用程式最受歡迎。  

2.   您可以查看哪些使用者正在使用其他應用程式。 您也可以向下鑽研這些應用程式，並通知使用者請他們移轉到 OneDrive，如下所示：

    1.  在您的 **[Cloud Discovery 儀表板]** 中，選擇 **[Dropbox]**，然後選擇 **[IP 位址]** 或 **[使用者]** 索引標籤。  

    2.  選擇箭號 ![箭號圖示](./media/arrow-icon.png "箭號圖示")，然後選擇 [匯出]。  

### <a name="find-more-secure-alternatives"></a>尋找其他更安全的選項  
Cloud App Security 服務類別目錄可協助您尋找適用於組織的替代方案，而不是使用者可能正在使用的高風險應用程式。  

假設您正在考慮購買某種生產力工具，但不確定使用者是否會善加利用。  

1.   前往 [Cloud Discovery 儀表板]。  

2.   使用 [類別] 下方的 [生產力] 來篩選應用程式。  

3.   針對每個使用中的應用程式，查看 [分數] 以了解它是否安全，以及不安全的原因。  

4.   如果您決定要為整個組織購買企業授權，建議您同時查看 **[使用者]** 資料行。 您可在做決定前，於該處查看最受您使用者歡迎的項目、其是否受信任，以及其具備哪些安全性功能。  

## <a name="see-also"></a>另請參閱  
若要了解如何使用及設定原則來控制雲端應用程式的使用情形，請參閱[使用原則控制雲端應用程式](control-cloud-apps-with-policies.md)。   
如需技術支援，請前往 [Cloud App Security 的輔助支援](http://support.microsoft.com/oas/default.aspx?prid=16031)頁面。   
頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。  
