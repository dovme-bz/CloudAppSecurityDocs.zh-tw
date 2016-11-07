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
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 8b454edde557c408b644c9bff6f7bf6136ba9819


---

# <a name="getting-started-with-cloud-app-security"></a>開始使用 Cloud App Security
Cloud App Security 協助客戶利用雲端應用程式的優勢，同時透過改良的活動可見度與加強的保護，來控管公司的重要資料。  本文件將逐步引導您完成下列 Cloud App Security 使用步驟。  
  
組織必須擁有 Cloud App Security 的授權，才能使用該產品。 如需詳細資訊，請參閱[如何購買 Cloud App Security](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) 並查看[授權資源](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx)。  
  
>[!NOTE]
>Cloud App Security 不需要 Office 365 授權。  
  
## <a name="get-started-quickly-with-cloud-app-security"></a>快速開始使用 Cloud App Security  
  
|您應該執行什麼動作：|工作|必要？|作法：|描述|  
|-------------------------|----------|---------------|-------------|-----------------|  
|步驟 1： [設定 Cloud Discovery](set-up-cloud-discovery.md)。|上傳流量記錄|必要|**建立 Cloud Discovery 連續報告**<br /><br /> 1. 移至 [設定] -> [Cloud Discovery 設定]。<br /><br /> 2.  按一下 [Upload log automatically (自動上傳記錄)]。<br /><br /> 3. 在 [資料來源] 索引標籤下方，新增您的資料來源。<br /><br /> 4.  在 [記錄收集器] 索引標籤下方，設定記錄收集器。<br /><br /> 建立 Cloud Discovery 快照集報告<br /><br /> 1.  移至 [探索] -> [建立新的快照集報告]，並遵循步驟|**為什麼應該設定 Cloud Discovery 報告？** 取得組織中陰影 IT 的可見度非常重要。  <br />分析記錄之後，您可以輕易找出哪些人、在哪些裝置上、使用哪些雲端應用程式。|  
|步驟 2： [為您的應用程式提供立即可見度、保護及治理動作](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)。|連線應用程式|必要|1. 移至 [設定] -> [獲批准的應用程式]。<br /><br /> 2.按一下 [連線應用程式]，然後選擇應用程式。<br /><br /> 3.請遵循下列設定步驟，以連線應用程式。|**為什麼要連線應用程式？**<br /><br /> 只有在連線應用程式之後，您才能取得更深入的可見度，以便調查雲端應用程式中雲端環境的活動、檔案和帳戶。|  
|步驟 3： [使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)。|建立原則|必要|**建立原則**<br /><br /> 1.移至 [控制] -> [範本]。<br /><br /> 2.  從清單中選取原則範本，然後按一下 (+) [建立原則]。<br /><br /> 3.依據您的需求自訂原則 (選取篩選、動作和其他設定)，然後按一下 [建立]。<br /><br /> 4.  在 [原則] 索引標籤中，按一下您建立的原則以查看相關的相符項目 (活動、檔案、警示等)。<br /><br /> 提示 - 您可針對每個原則建立 [風險類別]，以涵蓋雲端環境的所有安全性案例。|**原則對組織有何幫助？**<br /><br /> 原則提供相關工具，可讓您監視趨勢、查看安全性威脅，並產生自訂的報告和警示。 使用原則時，您可以建立各種治理動作、DLP 以及檔案共用的控制項。|  
|步驟 4： [個人化您的體驗](general-setup.md#Adallom_mailsettings)。|新增組織詳細資料|建議|**輸入電子郵件設定**<br /><br /> 1.移至 [設定] -> [郵件設定]。<br /><br /> 2. 在 [電子郵件寄件者身分識別] 下方，輸入電子郵件地址和顯示名稱。<br /><br /> 3.在 [電子郵件設計] 下方，上傳組織的電子郵件範本。<br /><br /> **設定管理通知**<br /><br /> 1.  按一下導覽列中的使用者名稱，並前往 [使用者設定]。<br /><br /> 2.  在 [通知] 下方，設定您想要設定的系統通知方法。<br /><br /> 3.按一下 **[儲存]**。<br /><br /> **自訂分數計量**<br /><br /> 1.移至 [設定] -> [Cloud Discovery 設定]。<br /><br /> 2.  在 [Score metric configuration (分數計量設定)] 下方，設定各種風險值的重要性。<br /><br /> 3.  按一下 **[儲存]**。<br /><br /> 現在，系統即會根據您的組織需求和優先順序，精確地針對找到的應用程式設定風險分數。|**為什麼個人化您的環境？**<br /><br /> 有些功能在針對您的需求進行自訂時才能發揮最大的效益。  <br />您可以使用自己的電子郵件範本，為使用者提供更好的體驗，也可以決定要接收何種通知，並自訂風險分數計量以符合組織的喜好設定。|  
|步驟 5： [根據您的需求組織資料](general-setup.md#IPtagsandRanges)。|進行重要的設定|建議|**建立 IP 位址標記**<br /><br /> 1. 移至 [設定]  ->  [IP 位址標記]。<br /><br /> 2.按一下 (+) [新增 IP 位址範圍]。<br /><br /> 3.  輸入的 IP 範圍的 [詳細資料]、[位置]、[標記] 和 [類別]。<br /><br /> 4.按一下 [建立]。<br /><br /> 現在，當您要篩選和建立資料檢視以及建立原則時，皆可使用 IP 標籤。<br /><br /> **建立檢視**<br /><br /> 1.移至 [設定]  ->  [Cloud Discovery 設定]。<br /><br /> 2.  在 [資料檢視] 下方，按一下 (+) [Add data view] (新增資料檢視)。<br /><br /> 3.請遵循下列設定步驟。<br /><br /> 4.按一下 [建立]。<br /><br /> 現在，您可以依據自己的喜好設定來檢視找到的資料，例如業務單位或 IP 範圍。<br /><br /> **新增網域**<br /><br /> 1.  移至 [設定] -> [一般設定]。<br /><br /> 2.  在 [組織詳細資料] 下方，新增組織的內部網域。<br /><br /> 3.按一下 **[儲存]**。|**為什麼要進行這些設定？**<br /><br /> 這些設定可讓您更妥善、輕鬆地在主控台中控制各種功能。 使用 IP 標籤，可讓您輕鬆建立符合需求的原則、正確篩選資料等等。 您可以使用 [資料檢視]，將資料歸類於不同邏輯類別。|  
  
## <a name="see-also"></a>另請參閱  
[一般設定](general-setup.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


