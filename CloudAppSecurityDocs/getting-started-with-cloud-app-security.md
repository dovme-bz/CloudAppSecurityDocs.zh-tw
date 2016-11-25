---
title: "開始使用 Cloud App Security | Microsoft Docs"
description: "本主題概述啟動並執行 Cloud App Security 的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 224c7039ecb7200ad951774ac5fb76202543a35c
ms.openlocfilehash: 2e9307b5166566efa65f4766c0331c6aa15118e9


---

# <a name="getting-started-with-cloud-app-security"></a>開始使用 Cloud App Security
Cloud App Security 可協助您充分利用雲端應用程式的優點，同時維持對公司資源的控制。 其運作方式為改善雲端活動的可見度，並協助提升對公司資料的保護。 本主題會逐步引導您設定及使用 Cloud App Security 的步驟。  

組織必須擁有授權才能使用 Cloud App Security。 如需詳細資訊，請參閱[如何購買 Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security) 中的＜授權資源＞一節。  

>[!NOTE]
>您無須具備 Office 365 授權，也可使用 Cloud App Security。  

## <a name="get-started-quickly-with-cloud-app-security"></a>快速開始使用 Cloud App Security  

|您應該執行的動作|工作|必要？|如何進行|描述|  
|-------------------------|----------|---------------|-------------|-----------------|  
|步驟 1. [設定 Cloud Discovery](set-up-cloud-discovery.md)。|上傳流量記錄|必要|**建立 Cloud Discovery 持續報告**<br /><br /> 1.移至 [設定]  >  [Cloud Discovery 設定]。<br /><br /> 2.選擇 **[自動上傳記錄]**。<br /><br /> 3.在 **[資料來源]** 索引標籤上，新增您的來源。<br /><br /> 4.在 **[記錄收集器]** 索引標籤上，設定記錄收集器。<br /><br /> **建立 Cloud Discovery 快照集報告**<br /><br /> 1.移至 **[探索]** > **[建立新的快照集報告]**，並遵循顯示的步驟。|**為什麼應該設定 Cloud Discovery 報告？**<br /> 取得組織中影子 IT 的可見度非常重要。 <br />分析記錄之後，您可以輕易找出哪些人員在哪些裝置上使用哪些雲端應用程式。|
|步驟 2. [為您的應用程式設定立即可見度、保護及治理動作](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)。|連線應用程式|必要|1.移至 [設定] > [獲批准的應用程式]。<br /><br /> 2.選擇 **[連接應用程式]** 並選取應用程式。<br /><br /> 3.請遵循下列設定步驟，以連線應用程式。|**為什麼要連線應用程式？**<br />連接應用程式後，您就可以取得更深入的可見度，進而得以替雲端環境中的應用程式調查活動、檔案及帳戶。|
|步驟 3. [使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)。|建立原則|必要|**建立原則**<br /><br /> 1.移至 [控制] > [範本]。<br /><br /> 2.從清單中選取原則範本，然後選擇 (+) **[建立原則]**。<br /><br /> 3.自訂原則 (選取篩選、動作及其他設定)，然後選擇 **[建立]**。<br /><br /> 4.在 **[原則]** 索引標籤中，選擇原則以查看相關的相符項目 (活動、檔案、警示等)。<br /><br /> 提示：為每個 **[風險類別]** 建立原則，以涵蓋雲端環境的所有安全性案例。|**原則對組織有何幫助？**<br />您可使用原則來協助您監視趨勢、查看安全性威脅，並產生自訂的報告及警示。 使用原則時，您可以建立治理動作並設定資料外洩防護及檔案共用的控制項。|
|步驟 4. [個人化您的體驗](general-setup.md#Adallom_mailsettings)。|新增組織詳細資料|建議|**輸入電子郵件設定**<br /><br /> 1.移至 [設定] > [郵件設定]。<br /><br /> 2.在 **[電子郵件寄件者身分識別]** 下方，輸入電子郵件地址及顯示名稱。<br /><br /> 3.在 **[電子郵件設計]** 下方，上傳組織的電子郵件範本。<br /><br /> **設定管理通知**<br /><br /> 1.在導覽列中，選擇您的使用者名稱，然後移至 **[使用者設定]**。<br /><br /> 2.在 **[通知]** 下方，設定您想要設定的系統通知方法。<br /><br /> 3.選擇 **[儲存]**。<br /><br /> **自訂分數計量**<br /><br /> 1.移至 [設定]  >  [Cloud Discovery 設定]。<br /><br /> 2.在 **[Score metric configuration (分數計量設定)]** 下方，設定各種風險值的重要性。<br /><br /> 3.選擇 **[儲存]**。<br /><br /> 現在，系統即會根據您的組織需求和優先順序，精確地針對找到的應用程式設定風險分數。|**為什麼個人化您的環境？**<br />有些功能在針對您的需求進行自訂時才能發揮最大的效益。 <br />您可以使用自己的電子郵件範本，為使用者提供更好的體驗，也可以決定要接收何種通知，並自訂風險分數計量以符合組織的喜好設定。|
|步驟 5. [根據您的需求組織資料](general-setup.md#IPtagsandRanges)。|進行重要的設定|建議|**建立 IP 位址標記**<br /><br /> 1.移至 [設定]  >  [IP 位址標記]。<br /><br /> 2.選擇 (+) **新增 IP 位址範圍]**。<br /><br /> 3.輸入 IP 範圍 **[詳細資料]**、**[位置]**、**[標記]** 及 **[類別]**。<br /><br /> 4.選擇 **[建立]**。<br /><br /> 現在您可以在建立原則及篩選與建立資料檢視時，使用 IP 標記。<br /><br /> **建立檢視**<br /><br /> 1.移至 [設定]  >  [Cloud Discovery 設定]。<br /><br /> 2.在 **[資料檢視]** 下方，選擇 (+) **[Add data view]** (新增資料檢視)。<br /><br /> 3.請遵循下列設定步驟。<br /><br /> 4.選擇 **[建立]**。<br /><br /> 現在，您可以依據自己的喜好設定來檢視找到的資料，例如業務單位或 IP 範圍。<br /><br /> **新增網域**<br /><br /> 1.移至 [設定] > [一般設定]。<br /><br /> 2.在 **[組織詳細資料]** 下方，新增組織的內部網域。<br /><br /> 3.選擇 **[儲存]**。|**為什麼要進行這些設定？**<br />這些設定可協助您更充分掌控主控台的功能。 使用 IP 標記，可讓您輕鬆建立符合需求的原則、正確篩選資料等等。 您可以使用 [資料檢視]，將資料歸類於不同邏輯類別。|  

## <a name="see-also"></a>另請參閱

在[開始使用 Cloud App Security](getting-started-with-cloud-app-security.md) 中了解基本概念。    
如需技術支援，請前往 [Cloud App Security 的輔助支援](http://support.microsoft.com/oas/default.aspx?prid=16031)頁面。   
頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。   



<!--HONumber=Nov16_HO3-->


