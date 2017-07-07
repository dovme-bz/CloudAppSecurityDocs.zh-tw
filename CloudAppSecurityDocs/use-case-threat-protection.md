---
title: "保護您的組織免受威脅 | Microsoft Docs"
description: "本主題描述保護您的組織免受雲端環境威脅的案例。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7bad1e1ae6196b684ac35d063558fad22bc3689f
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2017
---
# <a name="protecting-your-organization-against-threats"></a>保護您的組織免受威脅  

識別高風險使用情況和雲端安全性問題、偵測異常使用者行為，以及避免連線之雲端應用程式中的威脅。 檢視使用者和系統管理員活動，並定義原則以在出現可疑行為，或認定特定活動在獲批准環境中有風險時，自動發出警示。 擷取大量 Microsoft 威脅情報和安全性研究資料。 威脅偵測原則可協助您確保獲批准的應用程式具備所有必要的安全性控制，並協助您維持掌控這些應用程式。
 
## <a name="mass-download-by-a-single-user-data-exfiltration-by-an-insider"></a>單一使用者的大量下載 (測試人員的資料竊取)

這個使用案例適用於 Office 365、G Suite、Box、Dropbox 和 Salesforce。

### <a name="the-threat"></a>威脅
惡意測試人員可以藉由在短時間內下載或存取多個檔案，從 Office 365 或其他雲端應用程式竊取資料。

### <a name="the-solution"></a>解決方案
偵測使用者在短時間內下載或存取大量檔案的情況。

#### <a name="prerequisites"></a>必要條件

將至少一個雲端應用程式[連接](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)到 Cloud App Security。

#### <a name="setting-up-monitoring"></a>設定監視

1.  根據預設，Cloud App Security 會掃描您的網路來建立基準，藉此了解您的使用者一般會在雲端中執行哪些工作、何時執行，以及經常執行哪些工作等模式。 

2. 設定原則監看雲端應用程式是否有大量下載，並在發生異常情況時發出警示：

    1. 在 [原則] 頁面上，按一下 [[建立活動原則]](user-activity-policies.md)。 
   

    2. 在 [[原則範本]](policy-template-reference.md) 欄位中，選擇 [單一使用者大量下載]。
    
    3. (選擇性) 您可以微調重複活動篩選。
    
    4. 按一下 [建立]。 
   
     
2. 調查相符項目
    
    1. 在 [原則] 頁面上，按一下原則名稱以移至 [原則報告]，然後檢閱原則所觸發的相符項目。

    2. 您可以按一下特定相符項目來開啟活動下拉式清單，藉以調查相符項目。 在下拉式清單中，您可以查看此活動相符的其他原則。 
    
    3. 您可以檢查使用者已下載的檔案，方法是按一下**活動下拉式清單**中的活動物件，然後按一下檔案名稱，這會引導您前往檔案資料表中的檔案。 您可以在此查看檔案是否屬使用者所擁有、有誰共用檔案，您也可以判斷這些檔案是否為他們通常使用的檔案，或是不應該下載的內部 IP。
     


#### <a name="validating-your-policy"></a>驗證您的原則

1. 若要模擬警示，請根據您在原則中設定的時間範圍，在短時間內從連線的雲端應用程式下載大於所設定閾值的文件數目 (例如在 5 分鐘內下載 30 個)。
3. 移至原則報告。 活動原則相符項目應該很快就會出現。 
4. 您可以按一下相符項目來查看已下載的檔案。  

#### <a name="removing-the-risk"></a>移除風險

在您驗證並微調原則之後，請移除可能符合原則的誤判，例如正在同步檔案的服務帳戶、來自公司活動的圖片資料夾等。然後執行下列動作： 
  1. 您可以採取[治理動作](governance-actions.md)，來開啟活動下拉式清單中的活動，然後按一下 [活動物件] 下的檔案名稱。

  2. 請連絡使用者，了解他們需要電腦上有這麼多公司檔案複本的原因。

 
## <a name="admin-activity-from-outside-your-organizations-network"></a>您組織網路外部的系統管理活動

這個使用案例適用於 Office 365、G Suite、Box、Dropbox、Salesforce 和 Okta。

### <a name="the-threat"></a>威脅
系統管理員帳戶遭外部攻擊者盜用。 系統管理員帳戶由於具有最高權限並可存取您組織中的所有資訊，因此是組織中敏感性最高的帳戶。 通常，系統管理活動應該當作系統管理員工作的一部分從辦公室執行，而不是從遠端位置或無法辨識的裝置執行。

### <a name="the-solution"></a>解決方案
偵測攻擊者偽裝成系統管理員，以從外部 IP 位址連線到您的雲端應用程式並執行任何系統管理活動的情況。

#### <a name="prerequisites"></a>必要條件

- 將至少一個雲端應用程式[連接](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)到 Cloud App Security。

- 移至 [設定]  >  [IP 位址範圍]，然後新增內部子網路及其輸出公用 IP 的 IP 位址範圍，並標記為 [公司]。

#### <a name="setting-up-monitoring"></a>設定監視

1.  設定原則以開始監視雲端應用程式，該原則會監看雲端應用程式是否在網路外部有系統管理活動，並在發生異常情況時發出警示：

    1. 在 [原則] 頁面上，按一下 [[建立活動原則]](user-activity-policies.md)。 
   

    2. 在 [[原則範本]](policy-template-reference.md) 欄位中，選擇 [來自非公司 IP 位址的系統管理活動]，另外將 [活動類型] 設定為 [登入] 並依序選取 [使用者] 和 [來源群組]，然後選取您的系統管理員所屬的群組。
    
    3. 您可以微調原則，設定要視為可疑的重複活動數目。
    
    4. 按一下 [建立]。 
   
     
2. 調查相符項目
    
    1. 在 [原則] 頁面上，按一下原則名稱以移至 [原則報告]，然後檢閱原則所觸發的相符項目。

    2. 您可以按一下特定相符項目來開啟活動下拉式清單，藉以調查相符項目。 在下拉式清單中，您可以查看此活動相符的其他原則。 
     
#### <a name="validating-your-policy"></a>驗證您的原則

1. 若要模擬警示，請從具有公司網路外部 IP 位址的電腦執行系統管理活動，並確保根據您在原則中設定的時間範圍，在短時間內執行大於所設定閾值的活動數目 (例如 5 分鐘內 1 個活動)。
3. 移至原則報告。 活動原則相符項目應該很快就會出現。 
4. 您可以按一下相符項目，以查看執行了哪些活動。 

#### <a name="removing-the-risk"></a>移除風險

在您驗證及微調原則之後，移除可能符合原則的可能誤報。 然後執行下列動作： 
  1. 您可以採取[治理動作](governance-actions.md)，來開啟活動下拉式清單中的活動，然後按一下 [使用者] 的名稱。

  2. 在開啟的 [使用者] 頁面中，您會看到一個圖表，其中包含使用者過去一個月的活動、使用者過去一個月活動的位置，以及群組成員資格、應用程式活動和帳戶。 
  
  3. 如有必要，您可以按一下 [連絡] 傳送電子郵件訊息給使用者，以通知他們其帳戶遭盜用。

 ![外部自動治理](./media/auto-gov-external.png)

   2. 進行完整驗證之後，您可以設定它來執行自動治理動作。 例如，您可以 [暫時停止使用者的權限] 或 [移除使用者的共同作業]。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  