---
title: "使用 Azure AD 使用者名稱擴充 Cloud App Security 探索資料 | Microsoft Docs"
description: "本文提供如何使用 Azure AD 使用者名稱擴充 Cloud App Security 探索資料的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/19/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 909fa75c48fb9c698d083f2fb85f5f53bfadf76c
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2017
---
# <a name="cloud-discovery-enrichment"></a>Cloud Discovery 擴充

Cloud Discovery 資料現在可以使用 Azure Active Directory 使用者名稱資料進行擴充。 當您啟用這項功能時，探索流量記錄檔中收到的使用者名稱會經過比對，並取代為 Azure AD 使用者名稱以啟用下列新功能：
-   您可以調查 Azure Active Directory 使用者的影子 IT 使用方式。
-   您可以將探索到的雲端應用程式使用與 API 收集的活動相互關聯。
-   然後，您可以建立以 Azure AD 使用者群組為基礎的自訂記錄檔。 例如，特定行銷部門的影子 IT 報告。


## <a name="prerequisites"></a>先決條件：
- 資料來源必須提供使用者名稱資訊
- Office 365 應用程式連接器已連線

## <a name="enabling-user-data-enrichment"></a>啟用使用者資料擴充 
    
1. 在 [設定] 齒輪下，選取 [Cloud Discovery 設定]。
     
2. 在 [使用者擴充] 索引標籤中，若要允許 Cloud App Security 預設使用 Azure Active Directory 資料擴充使用者名稱，請選取 [使用 Azure Active Directory 使用者名稱，擴充探索到的使用者識別碼]。

3. 按一下 **[儲存]**。
 
![使用 Azure AD 使用者名稱擴充 Cloud App Security 探索](./media/discovery-enrichment.png)
  

  
      
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
    
      
  