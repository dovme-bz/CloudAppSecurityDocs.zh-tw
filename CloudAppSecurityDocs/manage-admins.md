---
title: 管理 Cloud App Security 入口網站的管理員存取權 | Microsoft Docs
description: 本主題提供為管理員設定 Cloud App Security 入口網站存取權的指示。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/30/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1d7d73fcc4dd31874613cb0e31e21b1bb21060db
ms.sourcegitcommit: af8fad9709171b200699ca1ed513e2831826ed7e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2018
ms.locfileid: "34568385"
---
*適用於：Microsoft Cloud App Security*


## <a name="managing-admin-access"></a>管理管理員存取權

Microsoft Cloud App Security 支援角色型存取控制。 根據預設，下列 Office 365 和 Azure AD 管理員角色可以存取 Microsoft Cloud App Security：

- 全域管理員和安全性系統管理員：具有 [完整存取] 的管理員在 Cloud App Security 中會擁有完整權限，可以新增管理員、新增原則和設定、上傳記錄檔及執行治理動作。

- 相容性 系統管理員：有唯讀權限，而且可以管理警示。 可以建立和修改檔案原則、允許檔案控管動作，以及檢視 [資料管理] 下所有的內建報表。 

- 安全性讀取者：具有唯讀權限，而且可以管理警示。 安全性讀取者受到限制而無法執行下列動作：

   - 建立原則或編輯和變更現有原則 

   - 執行任何管理動作 

   - 上傳探索記錄

   - 禁用或核准協力廠商應用程式

   - 存取和檢視 IP 位址範圍設定頁面

   - 存取和檢視任何設定頁面 

   - 存取和檢視 Discovery 設定 

   - 存取和檢視 App 連線程式頁面

   - 存取和檢視管理記錄檔 

   - 存取和檢視管理快照集報告頁面 

- 應用程式/執行個體管理員：擁有 Microsoft Cloud App Security 中所有資料的權限，可專門處理特定應用程式或此處所選取之應用程式的執行個體。 例如，如果將 Box European 執行個體的管理員權限提供給使用者，管理員就只能看見與這個應用程式執行個體相關的資料 (不論它是檔案、活動、原則或警示)，如下所示：
- 
  - 活動頁面 - 僅限於已標記實體相關的活動
  - 警示 - 僅限於與特定應用程式相關的警示
  - 原則 - 可以檢視所有的原則，但只能編輯或建立專門處理應用程式/執行個體的原則
  - 帳戶 -僅限於特定應用程式/執行個體的帳戶
  - 應用程式權限 - 僅限於特定應用程式/執行個體的權限
  - 檔案頁面 - 僅限於特定應用程式/執行個體中的檔案
  - 條件式存取應用程式控制 - 沒有權限
  - 雲端探索活動 - 沒有權限
  - 安全性延伸模組 - 僅適用於與使用者權限搭配使用之 API 權杖的權限
  - 治理動作 - 僅適用於特定應用程式/執行個體 

如需詳細資訊，請參閱[在 Azure Active Directory 中指派管理員角色](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles)。

您也可以執行下列步驟，將其他管理員新增至 Cloud App Security，而不是將使用者新增至 Azure Active Directory 系統管理角色：

1. 按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 然後按一下 [管理管理員]。 

2. 按一下 [加號] 新增應該可以存取 Cloud App Security 的管理員。
  
  ![新增管理員](./media/add-admin.png)
    
3. 接下來，按一下下拉式清單以設定管理員擁有何種角色：[全域管理員]、[安全性讀取者]、[合規性管理員] 或 [應用程式/執行個體管理員]。如果您選取 [應用程式/執行個體管理員]，請選取要讓管理員擁有權限的應用程式/執行個體。

     >[!NOTE]
      >任何存取權受限的管理員，若嘗試存取限制的頁面或執行限制的動作，都會收到錯誤，指出他們無權存取頁面或執行動作。
4. 按一下 [新增管理員]。  

   >[!NOTE]
    >只有全域管理員或安全性系統管理員可以授權其他使用者存取 Cloud App Security。
  
**覆寫管理員權限：**

如果您想從 Azure Active Directory 或 Office 365 覆寫系統管理員的權限，可以手動將使用者新增至 Cloud App Security 並指派權限給該使用者來這麼做。
例如，如果您想要指派 Stephanie (她在 Azure Active Directory 中是安全性讀取者)，而要使她在 Cloud App Security 有 [完整存取]，您可以手動將她新增至 Cloud App Security，然後指派 [完整存取] 給她以覆寫其角色，並允許她在 Cloud App Security 中所需的權限。 


將其他管理員新增至 Cloud App Security：
1. 按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 然後按一下 [管理管理員存取權]。 

2. 新增應該可以存取 Cloud App Security 的管理員。 選取其存取層級，然後按一下 [關閉]。

## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  