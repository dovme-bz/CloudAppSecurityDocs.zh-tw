---
title: 如何使用 Cloud App Security 條件式存取應用程式控制封鎖下載敏感性資料到非受控裝置 | Microsoft Docs
description: 本主題描述使用 Azure AD 反向 Proxy 功能，保護組織不讓其從非受控裝置下載敏感性資料的案例。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 06238ebc-2088-4372-9412-96cceaf3b145
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 213a289c3a9205a9f48ee44febf4c55c146c59de
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143123"
---
*適用於：Microsoft Cloud App Security*



# <a name="blocking-downloads-of-sensitive-information-using-microsoft-cloud-app-security-conditional-access-app-control"></a>使用 Microsoft Cloud App Security 條件式存取應用程式控制封鎖下載機密資訊

>[!div class="step-by-step"]
[« 上一篇：如何建立存取原則](access-policy-aad.md)

現今的 IT 系統管理員處於進退兩難的局面：您想要讓員工更具生產力。 這表示允許員工存取應用程式，讓他們可以透過任何裝置隨時工作。 另一方面又想保護公司的資產，這包括所有權和特殊權限資訊。 您該如何讓員工存取雲端應用程式，同時又能保護資料？ **對於可以從未受管理的裝置或非公司網路位置存取企業雲端應用程式中之敏感性資料的使用者，此使用案例可讓您封鎖這些使用者的下載。**


## <a name="the-threat"></a>威脅
貴組織的帳戶管理員於週末時，想要在家用他個人的膝上型電腦檢查 Salesforce 的內容。 此 Salesforce 資料可能包括用戶端的信用卡資訊或個人資訊。 家用電腦未受管理，這表示如果其從 Salesforce 將文件下載至電腦，可能會感染惡意程式碼，或者如果電腦遺失或遭竊，可能沒有密碼保護，任何拿到電腦的人都可以存取機密資訊。 

## <a name="the-solution"></a>解決方案
請使用 Azure AD 條件式存取和 Microsoft Cloud App Security 條件式存取應用程式控制來監視及控制雲端應用程式的使用，藉以保護貴組織。  

## <a name="prerequisites"></a>必要條件

- Azure AD Premium P1 的有效授權
- 在 Azure AD 中為 SSO 設定雲端應用程式  
- 確定[應用程式部署至 Cloud App Security](proxy-deployment-aad.md)

## <a name="create-a-block-download-policy-for-unmanaged-devices"></a>建立未受管理裝置的封鎖下載原則  

Cloud App Security 工作階段原則可讓您根據裝置狀態進一步限制工作階段。 當您想要使用其裝置作為條件來控制工作階段時，您必須同時建立條件式存取原則和工作階段原則，才能達成此目的。  

### <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>步驟 1：建立 Azure AD 條件式存取原則

1. 建立已指派使用者和應用程式的 Azure AD 條件式存取原則。
2. 在條件式存取原則內的工作階段控制項下，選取 [Use Conditional Access App Control enforced restrictions] \(使用條件式存取應用程式控制強制的限制\)。   

完成這項工作之後，請進入 Cloud App Security 入口網站並建立工作階段原則，來監視和控制工作階段的檔案下載。

### <a name="step-2-create-a-session-policy"></a>步驟 2：建立工作階段原則

1. 在 Cloud App Security 入口網站中，選取 [控制]，接著選取 [原則]。 

2. 在 [原則] 頁面中，按一下 [建立原則]，接著按一下 [工作階段原則]。
 
3. 在 [建立工作階段原則] 頁面上，為您的原則提供名稱和描述。 例如，**封鎖未受管理裝置的 Salesforce 下載**。

4. 指派 [原則嚴重性] 和 [類別]。

5. 在 [工作階段控制類型] 下，選取 [控制檔案下載 (透過 DLP)]。 這能讓您監視使用者在 Salesforce 工作階段中執行的所有作業，並讓您即時控制封鎖與保護下載。

6. 在 [符合下列所有條件的活動]  區段的 [活動來源] 下，選取篩選條件： 
    
   - **裝置標籤**：選取 [不等於]，然後選取 [相容]、[已加入網域] 或 [有效的用戶端憑證]，取決於貴組織中用來識別受管理裝置的方法。 
    
   - **應用程式**：選取您想要控制的應用程式。  

   - **使用者**：選取您想要監視的使用者。  
    
7. 或者，如果您要封鎖不屬於貴公司網路位置的下載，請在 [符合下列所有條件的活動] 區段的 [活動來源] 下，設定下列篩選條件： 

   - **IP 位址**或**位置**：您可以使用這兩個參數的其中一個，來識別使用者可能嘗試從中存取敏感性資料的非公司或未知位置。

     > [!NOTE]
     > 如果您要封鎖從未受管理的裝置和非公司位置的下載，則必須建立兩個工作階段原則，一個使用位置設定 [活動來源]，另一個則將 [活動來源] 設定為未受管理的裝置。
 
   - **應用程式**：選取您想要控制的應用程式。    
   
   - **使用者**：選取您想要監視的使用者。  

8. 在 [符合下列所有條件的檔案]  區段的 [活動來源] 下，設定下列篩選條件： 
   
   - **分類標籤**：如果您使用 Azure 資訊保護分類標籤，並且想要根據特定的 Azure 資訊保護分類標籤篩選檔案。
   
   - 選取 [檔案名稱] 或 [檔案類型]，以根據這些項目套用限制。
9. 啟用 [內容檢查]，以啟用內部 DLP 來掃描檔案中是否有敏感內容。 

10. 在 [動作] 下，選取 [封鎖]。 自訂您的使用者在無法下載檔案時將收到的封鎖訊息。  

11. 設定符合原則時想要收到的警示。 您可以設定限制，以免收到過多警示，還可以選取以電子郵件訊息、簡訊或這兩者來接收警示。

12. 按一下 [建立]  
 

## <a name="validate-your-policy"></a>驗證原則 

1. 若要模擬封鎖的檔案下載，請從未受管理的裝置或非企業網路位置，登入應用程式並嘗試下載檔案。 

2. 檔案應該會被封鎖，而您應該會收到在 [自訂封鎖訊息] 下所設定的訊息。 

3. 在 Cloud App Security 入口網站中，按一下 [控制]，接著按一下 [原則]，然後按一下已建立的原則來檢視原則報告。 工作階段原則相符項目應該很快就會出現。 

4. 在原則報告中，您可以看到哪些登入已重新導向至 Microsoft Cloud App Security 進行工作階段控制，以及哪些檔案已從受監視的工作階段下載或封鎖。


>[!div class="step-by-step"]
[« 上一篇：如何建立存取原則](access-policy-aad.md)



## <a name="see-also"></a>另請參閱  
[建立工作階段原則](session-policy-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  