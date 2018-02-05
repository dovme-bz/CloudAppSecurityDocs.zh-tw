---
title: "如何使用 Cloud App Security Proxy 封鎖下載敏感性資料到未受管理的裝置 | Microsoft Docs"
description: "本主題描述使用 Azure AD Proxy 功能，保護組織不讓其從未受管理的裝置下載敏感性資料的案例。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 06238ebc-2088-4372-9412-96cceaf3b145
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fd3d2abe04206926ec86f05a21f3bc0ecbe13728
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="blocking-downloads-of-sensitive-information-using-the-microsoft-cloud-app-security-proxy"></a>使用 Microsoft Cloud App Security Proxy 封鎖下載機密資訊


現今的 IT 系統管理員處於進退兩難的局面：您想要讓員工更具生產力。 這表示允許員工存取應用程式，讓他們可以透過任何裝置隨時工作。 另一方面又想保護公司的資產，這包括所有權和特殊權限資訊。 您該如何讓員工存取雲端應用程式，同時又能保護資料？ **對於可以從未受管理的裝置或非公司網路位置存取企業雲端應用程式中之敏感性資料的使用者，此使用案例可讓您封鎖這些使用者的下載。**


## <a name="the-threat"></a>威脅
貴組織的帳戶管理員於週末時，想要在家用他個人的膝上型電腦檢查 Salesforce 的內容。 此 Salesforce 資料可能包括用戶端的信用卡資訊或個人資訊。 家用電腦未受管理，這表示如果其從 Salesforce 將文件下載至電腦，可能會感染惡意程式碼，或者如果電腦遺失或遭竊，可能沒有密碼保護，任何拿到電腦的人都可以存取機密資訊。 

## <a name="the-solution"></a>解決方案
請使用 Azure AD 條件式存取和 Cloud App Security Proxy 來監視及控制雲端應用程式的使用，藉以保護貴組織。  

## <a name="prerequisites"></a>必要條件

- Azure AD Premium P2 的有效授權
- 在 Azure AD 中為 SSO 設定雲端應用程式  
- 確定[應用程式部署至 Cloud App Security](proxy-deployment-aad.md)

## <a name="create-a-block-download-policy-for-unmanaged-devices"></a>建立未受管理裝置的封鎖下載原則  

Cloud App Security 工作階段原則可讓您根據裝置狀態進一步限制工作階段。 當您想要使用其裝置作為條件來控制工作階段時，您必須同時建立條件式存取原則和工作階段原則，才能達成此目的。  

### <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>步驟 1：建立 Azure AD 條件式存取原則

1. 建立已指派使用者和應用程式的 Azure AD 條件式存取原則。
2. 在條件式存取原則內的工作階段控制項下，選取 [使用 Proxy 強制的限制]。   

 ![Azure AD 條件式存取](./media/proxy-deploy-restrictions-aad.png)

完成這項工作之後，請進入 Cloud App Security 入口網站並建立工作階段原則，來監視和控制工作階段的檔案下載。

### <a name="step-2-create-a-session-policy"></a>步驟 2：建立工作階段原則

1. 在 Cloud App Security 入口網站中，選取 [控制]，接著選取 [原則]。 

2. 在 [原則] 頁面中，按一下 [建立原則]，接著按一下 [工作階段原則]。
 
 ![建立工作階段原則](./media/create-session-policy.png)

2. 在 [建立工作階段原則] 頁面上，為您的原則提供名稱和描述。 例如，**封鎖未受管理裝置的 Salesforce 下載**。

3. 指派 [原則嚴重性] 和 [類別]。

 ![新的工作階段原則](./media/new-session-policy.png)

4. 在 [工作階段控制項類型] 下，選取 [Monitor all activities and control file download] \(監視所有活動及控制檔案下載)。 這能讓您監視使用者在 Salesforce 工作階段中執行的所有作業，並讓您即時控制封鎖與保護下載。

 ![工作階段原則控制類型](./media/session-policy-control-type.png)

5.  在 [符合下列所有條件的活動]  區段的 [活動來源] 下，選取篩選條件： 
    
    - **裝置標籤**：選取 [不等於]，然後選取 [相容]、[已加入網域] 或 [有效的用戶端憑證]，取決於貴組織中用來識別受管理裝置的方法。 
    
    - **應用程式**：選取您想要控制的應用程式。  

    - **使用者**：選取您想要監視的使用者。  
    
7. 或者，如果您要封鎖不屬於貴公司網路位置的下載，請在 [符合下列所有條件的活動] 區段的 [活動來源] 下，設定下列篩選條件： 

  - **IP 位址**或**位置**：您可以使用這兩個參數的其中一個，來識別使用者可能嘗試從中存取敏感性資料的非公司或未知位置。

     > [!NOTE]
     > 如果您要封鎖從未受管理的裝置和非公司位置的下載，則必須建立兩個工作階段原則，一個使用位置設定 [活動來源]，另一個則將 [活動來源] 設定為未受管理的裝置。
 
   - **應用程式**：選取您想要控制的應用程式。    
   
   - **使用者**：選取您想要監視的使用者。  

6. 在 [符合下列所有條件的檔案]  區段的 [活動來源] 下，設定下列篩選條件： 
   
    - **分類標籤**：如果您使用 Azure 資訊保護分類標籤，並且想要根據特定的 Azure 資訊保護分類標籤篩選檔案。
   
    - 選取 [檔案名稱] 或 [檔案類型]，以根據這些項目套用限制。
 
     ![工作階段原則檔案篩選條件](./media/session-policy-file-filters.png)

7. 啟用 [內容檢查]，以啟用內部 DLP 來掃描檔案中是否有敏感內容。 

 ![工作階段原則內容檢查](./media/session-policy-content-inspection.png)

8. 在 [動作] 下，選取 [封鎖]。 自訂您的使用者在無法下載檔案時將收到的封鎖訊息。  

 ![工作階段原則動作](./media/session-policy-actions.png)

9. 設定符合原則時想要收到的警示。 您可以設定限制，以免收到過多警示，還可以選取以電子郵件訊息、簡訊或這兩者來接收警示。

 ![工作階段原則警示](./media/session-policy-alert.png)


10. 按一下 [建立]  
 

## <a name="validate-your-policy"></a>驗證原則 

1. 若要模擬封鎖的檔案下載，請從未受管理的裝置或非企業網路位置，登入應用程式並嘗試下載檔案。 

2. 檔案應該會被封鎖，而您應該會收到在 [自訂封鎖訊息] 下所設定的訊息。 

  ![封鎖下載訊息](./media/block-download-message.png)

3. 在 Cloud App Security 入口網站中，按一下 [控制]，接著按一下 [原則]，然後按一下已建立的原則來檢視原則報告。 工作階段原則相符項目應該很快就會出現。 
 
  ![工作階段原則報告](./media/session-policy-report.png)

4. 在原則報告中，您可以看到哪些登入已重新導向至 Proxy 進行工作階段控制，以及哪些檔案已從受監視的工作階段下載或封鎖。




## <a name="see-also"></a>另請參閱  
[建立工作階段原則](session-policy-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  