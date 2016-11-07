---
title: "控制 | Microsoft Docs"
description: "本文章提供的相關資訊說明您可以在 Cloud App Security 中採取哪些治理動作，以控制組織的雲端應用程式使用方式。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9dc74c35f32c9a3dff251d6e0ac6b35a3591f4b9


---

# <a name="control"></a>控制
您可將治理動作套用至整個雲端環境的使用者檔案。 在徹底調查和了解雲端之後，您可以使用治理動作來保護組織。  
  
## <a name="applying-governance-actions"></a>套用治理動作  
您可以從原則內部、警示內部以及透過 [檔案] 記錄來套用治理動作。  
  
您可以隨時前往 [設定] 齒輪 ![設定圖示](./media/settings-icon.png "settings icon")，按一下 [治理記錄]，以檢閱並查看所有先前套用之治理動作的狀態。  
  
若有任何失敗的治理動作，按一下重試圖示 ![重試圖示](./media/retry-icon.png "retry icon") 即可再次套用。  
  
不同類型的原則、違規及應用程式，可用的治理動作也各異。  
  
## <a name="moving-from-detection-to-automatic-remediation"></a>從偵測移動到自動補救  
在您定義和自訂原則篩選器之後，即可選取在每次原則違規時要採取的自動治理動作。  
由於補救動作會利用雲端提供者 API，因此動作會因應用程式而異。  
  
> [!NOTE]  
>  設定治理動作時請特別小心，因為它們可能會導致無法恢復的檔案存取權限遺失。  
> 建議您使用多個搜尋欄位，縮小篩選的範圍以明確表示您想要處理的檔案。 篩選器範圍愈小愈好。  
>   
>  如需指引，您可以使用 [篩選器] 區段中的 [Edit and preview results (編輯和預覽結果)] 按鈕。  
  
![檔案原則編輯和預覽結果](./media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
## <a name="migration"></a>移轉  
Cloud App Security 可讓您知道組織中的使用者正在使用哪些應用程式，並提供監視新應用程式採用情況的工具，以協助您進行移轉。 其中也有相關工具讓您查看大家已在使用哪些應用程式，協助您了解可為組織提供何種類型的應用程式。  
  
### <a name="how-to-migrate-your-users-to-a-new-app"></a>如何將您的使用者移轉至新的應用程式  
假設您最近購買 Office 365，並想要讓組織中的所有使用者停用所有其他雲端儲存體應用程式，而開始使用 OneDrive。 您可能想要執行下列動作：  
  
-   前往 [Cloud Discovery 儀表板]，並使用 [類別] 下方的 [雲端儲存體] 來篩選應用程式。 然後依照 [使用者] 或 [IP 位址] 排序結果，並查看哪些應用程式最受歡迎。  
  
-   您可以查看哪些使用者正在使用其他應用程式。  
  
     您也可以向下鑽研這些應用程式，並通知使用這些應用程式的相關人員，請他們移轉到 OneDrive，如下所示：  
  
    1.  在您的 [Cloud Discovery 儀表板] 中，按一下 [Dropbox]，然後按一下 [IP 位址] 或 [使用者] 索引標籤。  
  
    2.  按一下箭號 ![箭號圖示](./media/arrow-icon.png "arrow icon")，然後選取 [匯出]。  
  
### <a name="find-more-secure-alternatives"></a>尋找其他更安全的選項  
Cloud App Security 服務類別目錄可協助您尋找適用於組織的替代方案，而不是使用者可能正在使用的高風險應用程式。  
  
假設您正在考慮購買某種生產力工具，但不確定使用者是否會善加利用。  
  
-   前往 [Cloud Discovery 儀表板]。  
  
-   使用 [類別] 下方的 [生產力] 來篩選應用程式。  
  
-   針對每個使用中的應用程式，查看 [分數] 以了解它是否安全，以及不安全的原因。  
  
-   如果您決定要為整個組織購買企業授權，也可以查看 [使用者] 欄位，以了解使用者最喜歡哪些應用程式、這些應用程式是否值得信任，以及其中具有哪些安全性功能，再做決定。  
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請瀏覽 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


