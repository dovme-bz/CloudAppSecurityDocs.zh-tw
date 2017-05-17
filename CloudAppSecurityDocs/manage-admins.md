---
title: "管理 Cloud App Security 入口網站的管理員存取權 | Microsoft Docs"
description: "本主題提供為管理員設定 Cloud App Security 入口網站存取權的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f4d336b48dc7f3655a60d64ec4fe7e066db7f438
ms.sourcegitcommit: 50fac1cec86dfb8170ba9c63a8f58a4bf24e3c5b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2017
---
## <a name="managing-admin-access"></a>管理管理員存取權

Cloud App Security 支援角色型存取控制。 根據預設，下列 Office 365 和 Azure AD 管理員角色可以存取 Cloud App Security：

- 全域管理員和安全性系統管理員：具有 [完整存取] 的管理員在 Cloud App Security 中會擁有完整權限，可以新增管理員、新增原則和設定，上傳記錄檔及執行治理動作。

- 安全性讀取者：具有唯讀權限，而且可以管理警示。 安全性讀取者受到限制而無法執行下列動作：
      - 建立原則或編輯和變更現有原則 
      - 執行任何管理動作 
      - 上傳探索記錄
      - 禁用或核准第三方應用程式
      - 存取和檢視 IP 位址範圍設定頁面
      - 存取和檢視任何設定頁面 
      - 存取和檢視 Discovery 設定 
      - 存取和檢視 App 連線程式頁面
      - 存取和檢視管理記錄檔 
      - 存取和檢視管理快照集報告頁面 

如需詳細資訊，請參閱[在 Azure Active Directory 中指派系統管理員角色](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles)。

您也可以執行下列動作，將其他管理員新增至 Cloud App Security，而不是將使用者新增至 Azure Active Directory 系統管理角色：

1. 按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 然後按一下 [管理管理員存取權]。 

2. 新增應該可以存取 Cloud App Security 的管理員。
  
      
3. 接下來，按一下下拉式清單，設定管理員要擁有的存取類型 ([完整存取] 或 [唯讀及管理警示])。

     >[!NOTE]
      >任何具有 [唯讀及管理警示] 限制存取的管理員，若嘗試存取受限制頁面或執行受限制動作，都會收到錯誤，指出他們沒有存取頁面或執行動作的權限。

   ![管理管理員存取權](./media/manage-admin-access.png "管理管理員存取權")  

4. 按一下 **關閉**。  

   >[!NOTE]
    >只有全域管理員或安全性系統管理員可以授權其他使用者存取 Cloud App Security。
  
**覆寫管理員權限：**

如果您想從 Azure Active Directory 或 Office 365 覆寫系統管理員的權限，可以手動將使用者新增至 Cloud App Security 並指派權限給該使用者來這麼做。
例如，如果您想要指派 Stephanie (她在 Azure Active Directory 中是安全性讀取者)，而要使她在 Cloud App Security 有 [完整存取]，您可以手動將她新增至 Cloud App Security，然後指派 [完整存取] 給她以覆寫其角色，並允許她在 Cloud App Security 中所需的權限。 


將其他管理員新增至 Cloud App Security：
1. 按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 然後按一下 [管理管理員存取權]。 

2. 新增應該可以存取 Cloud App Security 的管理員，選取其存取層級，然後按一下 [關閉]。



## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  