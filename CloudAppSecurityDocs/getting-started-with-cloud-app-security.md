---
title: "部署 Cloud App Security 讓雲端應用程式使用洞察力和控制 | Microsoft Docs"
description: "本主題概述啟動並執行 Cloud App Security 的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/30/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 148c9b275ce77a963dc27c77be791d5dcd37379a
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/03/2017
---
# <a name="deploy-cloud-app-security"></a>部署 Cloud App Security
Cloud App Security 可協助您充分利用雲端應用程式的優點，同時維持對公司資源的控制。 其運作方式為改善雲端活動的可見度，並協助提升對公司資料的保護。 本主題會逐步引導您設定及使用 Cloud App Security 的步驟。  

組織必須擁有授權才能使用 Cloud App Security。 如需詳細資訊，請參閱[如何購買 Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security) 中的＜授權資源＞一節。  

>[!NOTE]
>您無須具備 Office 365 授權，也可使用 Cloud App Security。  

## <a name="prerequisites"></a>必要條件  
  
-   組織必須擁有 Cloud App Security 的授權，才能使用該產品。 如需詳細資訊，請參閱[如何購買 Cloud App Security](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) 並查看[授權資源](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx)。  
  
     如需租用戶啟用支援，請參閱[連絡商務用 Office 365 支援人員 - 系統管理協助](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。  
  
> [!NOTE] 
> Cloud App Security 不需要 Office 365 授權。  
  
-   您購買 Cloud App Security 授權之後，會收到一封電子郵件，其中附有啟用資訊和 Cloud App Security 入口網站的連結。  
  
-   若要設定 Cloud App Security，您必須是 Azure Active Directory 或 Office 365 的全域管理員、規範管理員或安全性系統管理員。 請務必了解，獲指派系統管理員角色的使用者將會在您組織已訂閱的所有雲端應用程式都擁有相同的權限，而不論您是在 Office 365 入口網站、Azure 傳統入口網站，還是使用適用於 [Windows PowerShell](https://technet.microsoft.com/library/mt736914.aspx) 的 Azure AD 模組來指派角色。 如需詳細資訊，請參閱[在 Office 365 中指派管理員角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[在 Azure Active Directory 中指派管理員角色](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/)。  
  
-   若要執行 Cloud App Security 入口網站，請使用 Internet Explorer 11、Microsoft Edge (最新)、Google Chrome (最新)、Mozilla Firefox (最新) 或 Apple Safari (最新)。  

## <a name="to-access-the-portal"></a>存取入口網站

若要存取 Cloud App Security 入口網站，請前往 [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)。  
  
或者，您可以透過 **Office 365 系統管理中心**存取入口網站，方法是依序按一下系統管理中心圖示 ![O365 系統管理中心圖示](./media/o365-admin-centers-icon.png "O365 系統管理中心圖示") 和 [Cloud App Security]。  
  
![從 O365 存取](./media/access-from-o365.png "從 O365 存取")  
  



## <a name="get-started-quickly-with-cloud-app-security"></a>快速開始使用 Cloud App Security  

 

### <a name="step-1-set-up-cloud-discoveryset-up-cloud-discoverymd"></a>步驟 1. [設定 Cloud Discovery](set-up-cloud-discovery.md)。
必要工作︰上傳流量記錄**以建立連續的 Cloud Discovery 報告**

 1. 移至 [設定]  >  [Cloud Discovery 設定]。
 2. 選擇 **[自動上傳記錄]**。
 3. 在 **[資料來源]** 索引標籤上，新增您的來源。
 4. 在 **[記錄收集器]** 索引標籤上，設定記錄收集器。
 
**建立 Cloud Discovery 快照集報告**

 1. 移至 **[探索]** > **[建立新的快照集報告]**，並遵循顯示的步驟。

**為什麼應該設定 Cloud Discovery 報告？**
取得組織中影子 IT 的可見度非常重要。
分析記錄之後，您可以輕易找出哪些人員在哪些裝置上使用哪些雲端應用程式。


### <a name="step-2-set-instant-visibility-protection-and-governance-actions-for-your-appsenable-instant-visibility-protection-and-governance-actions-for-your-appsmd"></a>步驟 2. [為您的應用程式設定立即可見度、保護及治理動作](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)。
必要工作︰連接應用程式

1. 移至 [設定] > [App 連線程式]。
2. 選擇 **[連接應用程式]** 並選取應用程式。
3. 請遵循下列設定步驟，以連線應用程式。

**為什麼要連線應用程式？**
連接應用程式後，您就可以取得更深入的可見度，進而得以替雲端環境中的應用程式調查活動、檔案及帳戶。


### <a name="step-3-control-cloud-apps-with-policiescontrol-cloud-apps-with-policiesmd"></a>步驟 3. [使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)。
必要工作︰建立原則

**建立原則**

1. 移至 [控制] > [範本]。
2. 從清單中選取原則範本，然後選擇 (+) **[建立原則]**。
3. 自訂原則 (選取篩選、動作及其他設定)，然後選擇 **[建立]**。
4. 在 **[原則]** 索引標籤中，選擇原則以查看相關的相符項目 (活動、檔案、警示等)。
 提示：為每個 **[風險類別]** 建立原則，以涵蓋雲端環境的所有安全性案例。

**原則對組織有何幫助？**
您可使用原則來協助您監視趨勢、查看安全性威脅，並產生自訂的報告及警示。 使用原則時，您可以建立治理動作並設定資料外洩防護及檔案共用的控制項。


### <a name="step-4-personalize-your-experiencemail-settingsmd"></a>步驟 4. [個人化您的體驗](mail-settings.md)。
建議工作：新增您的組織詳細資料

**輸入電子郵件設定**

1. 移至 [設定] > [郵件設定]。
2. 在 **[電子郵件寄件者身分識別]** 下方，輸入電子郵件地址及顯示名稱。
3. 在 **[電子郵件設計]** 下方，上傳組織的電子郵件範本。

**設定管理通知**

1. 在導覽列中，選擇您的使用者名稱，然後移至 **[使用者設定]**。
2. 在 **[通知]** 下方，設定您想要設定的系統通知方法。
3. 選擇 **[儲存]**。

**自訂分數計量**

1. 移至 [設定]  >  [Cloud Discovery 設定]。
2. 在 **[Score metric configuration (分數計量設定)]** 下方，設定各種風險值的重要性。
3. 選擇 **[儲存]**。

現在，系統即會根據您的組織需求和優先順序，精確地針對找到的應用程式設定風險分數。

**為什麼個人化您的環境？**
有些功能在針對您的需求進行自訂時才能發揮最大的效益。 您可以使用自己的電子郵件範本，為使用者提供更好的體驗，也可以決定要接收何種通知，並自訂風險分數計量以符合組織的喜好設定。


### <a name="step-5-organize-the-data-according-to-your-needsip-tagsmd"></a>步驟 5. [根據您的需求組織資料](ip-tags.md)。
建議工作：設定重要的設定

**建立 IP 位址標記**

1. 移至 [設定]  >  [IP 位址標記]。
2. 選擇 (+) **新增 IP 位址範圍**。
3. 輸入 IP 範圍 **[詳細資料]**、**[位置]**、**[標記]** 及 **[類別]**。
4. 選擇 **[建立]**。

 現在您可以在建立原則及篩選與建立連續報告時，使用 IP 標記。

**建立連續報告**

1. 移至 [設定]  >  [Cloud Discovery 設定]。
2. 在 [管理連續報告] 下，選擇 [建立報告]。
3. 請遵循下列設定步驟。
4. 選擇 **[建立]**。

現在，您可以依據自己的喜好設定來檢視找到的資料，例如業務單位或 IP 範圍。

**新增網域**

1. 移至 [設定] > [一般設定]。
2. 在 **[組織詳細資料]** 下方，新增組織的內部網域。
3. 選擇 **[儲存]**。

**為什麼要進行這些設定？**
這些設定可協助您更充分掌控主控台的功能。 使用 IP 標記，可讓您輕鬆建立符合需求的原則、正確篩選資料等等。 您可以使用 [資料檢視]，將資料歸類於不同邏輯類別。
  

## <a name="see-also"></a>另請參閱

設定原則[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)。    
如需技術支援，請前往 [Cloud App Security 的輔助支援](http://support.microsoft.com/oas/default.aspx?prid=16031)頁面。   
頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。   
