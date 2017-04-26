---
title: "雲端應用程式帳戶的可視性 | Microsoft Docs"
description: "本主題"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5d5ccc55fe0d9c3fea93446daebfcbd5bbed8c8d
ms.sourcegitcommit: fd3b6c04cec30f7c9300cc02d29d562d17bf43ea
translationtype: HT
---
# <a name="accounts"></a>帳戶
Cloud App Security 可讓您從連接的應用程式看見所有帳戶。 當您連接 Cloud App Security 與使用 App 連線程式的應用程式後，Cloud App Security 會掃描所有與應用程式建立關聯的帳戶。 [帳戶] 頁面可讓您調查這些帳戶、其為所屬成員的群組、其別名以及所用的應用程式。 


您可以篩選 [帳戶] 記錄，以尋找特定的帳戶，並深入探討不同的帳戶類型，例如，您可以篩選自去年起即未存取的所有外部帳戶。 您可以根據帳戶建立原則，然後定義想要收到的警示項目並採取動作。 

[帳戶] 頁面可讓您輕鬆地檢查您的帳戶是否有下列問題︰  

-   檢查是否有任何帳戶在某特定服務中長時間未使用 (您或許應該撤銷該使用者的該項服務授權)  
-   您可以篩選擁有系統管理權限的使用者清單  

-   您可以檢視哪些帳戶為使用中，但屬於貴組織已離職的使用者  

-   您可以撤銷使用者的特定應用程式權限 (視應用程式而定)，或需要特定使用者執行多重要素驗證
    
-   您可以查看每個使用者群組包含哪些帳戶  

-   您可以查看每個帳戶存取哪些應用程式，以及特定帳戶刪除了哪些應用程式
    
-   您可以向下切入至使用者帳戶並選取相關的管理動作，例如 [暫時停止使用者的權限] 或 [移除使用者的共同作業]。 如果使用者是從 Azure Active Directory 匯入，您也可以按一下 [Azure AD 帳戶設定] 輕鬆存取進階使用者管理功能，例如群組管理、多重要素驗證、使用者登入的詳細資料，以及封鎖登入的能力。

![帳戶畫面](./media/accounts-page.png)

## <a name="account-filters"></a>帳戶篩選器
以下是可套用的帳戶篩選器清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
- **帳戶名稱**︰帳戶名稱是使用者的主要別名，但也支援 Proxy 位址、別名、SID 等來自其他 Microsoft 帳戶 (Office 365 和 Azure Active Directory) 的其他識別碼，並會合併在主要別名之下。

- **聯盟**：聯盟會是**內部**或**外部**。 若要設定哪些使用者及帳戶為內部，請務必在 [設定] 下設定內部組織的 [IP 位址範圍]。 如果帳戶具有系統管理員權限，則出現在 [帳戶] 資料表中的圖示會加上![帳戶系統管理圖示](./media/accounts-admin-icon.png)的紅色結。

- **應用程式**︰您可以篩選組織中是否有帳戶正在使用任何以 API 連接的應用程式。

- **網域**︰讓您篩選特定網域中的使用者。

- **上次查看**：[上次查看] 篩選器可讓您尋找休眠，且其使用者有段時間未執行任何活動的帳戶。

- **組織/部門**︰讓您篩選特定 Azure Active Directory 或 Office 365 組織群組的成員。

- **使用者群組**︰讓您篩選 Cloud App Security 使用者群組的成員，包括內建的使用者群組和匯入的使用者群組。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  