---
title: 雲端應用程式帳戶的可視性 | Microsoft Docs
description: 本主題
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/2/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: eff1d2246dc220175504911d3cadb1b5591475c5
ms.sourcegitcommit: 9d2a34a2d4145b39d855dd6f596c0fc858b92f9b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340136"
---
*適用於：Microsoft Cloud App Security*


# <a name="accounts"></a>帳戶
Microsoft Cloud App Security 可讓您從連線應用程式看見帳戶。 當您使用 App 連線程式將 Cloud App Security 連線至應用程式時，Cloud App Security 會讀取與連線應用程式建立關聯的帳戶資訊。 [帳戶] 頁面可讓您調查這些帳戶、權限、為其所屬成員的群組、其別名以及所用的應用程式。 此外，當 Cloud App Security 在其中一個連線應用程式 (例如活動或檔案共用) 中偵測到先前未看過的新帳戶時，會將此帳戶新增至該應用程式的帳戶清單。 這可讓您檢視與您的雲端應用程式互動之外部使用者的活動。

系統管理員可以搜尋特定使用者的中繼資料或使用者的活動。 [使用者及帳戶] 頁面為您提供有關從連線的雲端應用程式中提取的實體相關詳細資料。 它也提供使用者的活動歷程記錄和與使用者相關的安全性警示。

[!INCLUDE [Handle personal data](../includes/gdpr-intro-sentence.md)]


您可以篩選 [帳戶] 頁面，以尋找特定的帳戶，並深入探討不同的帳戶類型，例如，您可以篩選自去年起即未存取的所有外部帳戶。 

[帳戶] 頁面可讓您輕鬆地檢查您的帳戶是否有下列問題︰  

-   檢查是否有任何帳戶在某特定服務中長時間未使用 (您或許應該撤銷該使用者的該項服務授權)  
-   您可以篩選擁有系統管理權限的使用者清單  

-   您可以搜尋不再屬於組織但可能仍有使用中帳戶的使用者  

-   您可以對帳戶採取治理動作，例如暫停應用程式，或移至 [帳戶設定] 頁面。 如需完整的治理動作清單，請參閱[治理記錄](governance-actions.md)。
    
-   您可以查看每個使用者群組包含哪些帳戶  

-   您可以查看每個帳戶存取哪些應用程式，以及特定帳戶刪除了哪些應用程式
    

![帳戶畫面](./media/accounts-page.png)

## <a name="account-filters"></a>帳戶篩選器
以下是可套用的帳戶篩選器清單。 大部分的篩選器皆支援多個值與 NOT，以提供可在建立原則時使用的強大工具。  
  
- **帳戶名稱**︰帳戶名稱是使用者的主要別名，但也支援 Proxy 位址、別名、SID 等來自其他 Microsoft 帳戶 (Office 365 和 Azure Active Directory) 的其他識別碼，並會合併在主要別名之下。

- **聯盟**：聯盟為**內部**或**外部**。 若要設定哪些使用者及帳戶為內部，請務必在 [設定] 下設定內部組織的 [IP 位址範圍]。 如果帳戶具有系統管理員權限，則出現在 [帳戶] 資料表中的圖示會加上紅色領帶![帳戶系統管理圖示](./media/accounts-admin-icon.png)。

- **應用程式**︰您可以篩選組織中是否有帳戶正在使用任何以 API 連接的應用程式。

- **網域**︰讓您篩選特定網域中的使用者。

- **上次查看**：[上次查看] 篩選器可讓您尋找休眠，且其使用者有段時間未執行任何活動的帳戶。

- **組織/部門**︰讓您篩選連線應用程式中所定義之特定組織群組的成員。

- **使用者群組**︰讓您篩選 Cloud App Security 使用者群組的成員，包括內建的使用者群組和匯入的使用者群組。


## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  