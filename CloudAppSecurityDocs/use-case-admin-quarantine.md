---
title: 如何使用系統管理隔離來調查並修復檔案違規的使用案例 | Microsoft Docs
description: 本主題描述使用系統管理隔離來控制資料違規的案例。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3fc04cfb-ad4c-4ac2-980a-ee9f4c740d88
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b61244a1c611355cf5ce9b0ca4f073c1ebccb765
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144035"
---
*適用於：Microsoft Cloud App Security*


# <a name="protecting-your-files-with-admin-quarantine"></a>使用系統管理隔離來保護您的檔案

> [!NOTE]
> 這是預覽功能。

[檔案原則](data-protection-policies.md)是尋找資訊保護原則威脅的絕佳工具；例如，尋找使用者在您雲端中儲存機密資訊、信用卡號碼和第三方 ICAP 檔案的位置。 使用 Microsoft Cloud App Security，您不僅可以偵測儲存在雲端中使您易受攻擊的垃圾檔案，還可以立即採取動作，透過追蹤並鎖定造成威脅的檔案來防止其攻擊。 使用**系統管理隔離**，您可以保護雲端中的檔案並修復問題，也可以避免未來發生外洩情形。 

>[!NOTE] 
> 如需支援系統管理隔離的應用程式清單，請參閱[治理動作](governance-actions.md)清單。
 
## <a name="how-quarantine-works"></a>隔離的運作方式 

1. 當檔案符合原則時，會為該檔案提供 [系統管理隔離] 選項。

2. 執行下列其中一項來隔離檔案：
   - 手動套用**系統管理隔離**動作：
     
     ![隔離動作](./media/quarantine-action.png)

   - 將它設定為原則中的自動化隔離動作： 

     ![自動隔離](./media/quarantine-automated.png)

3. 套用 [系統管理隔離] 時，會在幕後發生下列情況：

   1. 原始檔案會移至您設定的系統管理隔離資料夾。
   2. 原始檔案會遭到刪除。
   3. 標記檔案會上傳到原始檔案位置。
      
      ![隔離標記](./media/quarantine-tombstone.png)
      
   4. 使用者只能存取標記，他們可以在其中讀取 IT 部門所提供的自訂指引，以及用於連絡 IT 部門釋放檔案的相互關聯識別碼。

4. 當您收到已隔離檔案的警示時，請調查 Cloud App Security [警示] 頁面中的檔案：
   
   ![隔離警示](./media/quarantine-alerts.png)
   
5. 此外在 [原則報告] 的 [已隔離] 索引標籤上：
   
   ![隔離報告](./media/quarantine-report.png)
    
6. 隔離檔案之後，請使用下列程序來修復威脅情況：
    
    1. 檢查 SharePoint Online 上隔離資料夾中的檔案。
    2. 您也可以檢視稽核記錄檔，以深入探討檔案內容。
    3. 如果找到的檔案違反公司原則，請執行組織的事件回應 (IR) 程序。
    4. 如果找到的檔案無害，您可以還原隔離的檔案，此時會釋放原始檔案 (也就是複製回原始位置)、刪除標記，而且使用者可以存取檔案。
       
       ![隔離還原](./media/quarantine-restore.png)
       
7. 在您驗證原則順利執行之後，您可以使用原則中的自動化治理動作以避免未來發生外洩情形，並在符合原則時自動套用系統管理隔離。

> [!NOTE]
> 當您還原檔案時：
> - 不會還原原始共用，而是會套用預設資料夾繼承。
> - 還原的檔案只會包含最新版本。
> 
> 
> [!NOTE]
> 客戶有責任管理隔離資料夾網站存取權。

#### <a name="how-to-set-up-admin-quarantine"></a>如何設定系統管理隔離

1. 設定檔案原則以偵測違規，像是僅限中繼資料原則 (例如 SharePoint Online 中的分類標籤)、原生 DLP 原則 (例如搜尋信用卡號碼的原則) 或 ICAP 第三方原則 (例如尋找 Vontu 的原則)。

2. 設定隔離位置：
   1. 若是 Office 365 SharePoint 或商務用 OneDrive，在設定系統管理隔離之前，您無法將檔案置入系統管理隔離中作為原則的一部分：![隔離設定](./media/quarantine-warning.png)

      若要設定系統管理隔離設定，請移至設定齒輪下的 [一般設定]，然後提供隔離檔案的位置，以及使用者在其檔案遭隔離時會收到的使用者通知。 
      ![隔離設定](./media/quarantine-settings.png)

   2. 若是 Box，您無法自訂隔離資料夾位置和使用者訊息。 資料夾位置是將 Box 連線到 Cloud App Security 之系統管理員的磁碟機，而使用者訊息是：因為此檔案可能與貴組織的安全性及合規性政策相衝突，所以已隔離該檔案。 如需說明，請連絡您的 IT 系統管理員。



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  
