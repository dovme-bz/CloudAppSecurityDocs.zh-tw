---
title: "從連接的應用程式匯入使用者群組 | Microsoft Docs"
description: "本主題提供將使用者群組匯入 Cloud App Security 的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 87b831ef-5977-4df8-bed3-3ee54a8adbb5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dd1263d164751133e8c50e13b003c68f43926b8d
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="import-user-groups"></a>匯入使用者群組

當您使用 API 連接器連接應用程式時，Cloud App Security 可讓您從 Office 365 及 Azure Active Directory 等等匯入使用者群組。
使用者群組有兩種類型： 
- 自動群組 </br>Cloud App Security 預設會建立自動群組。 例如，有一個名為**外部**的自動使用者群組，結合了來自組織外部且可以存取檔案，或已參與租用戶使用者活動之所有應用程式的所有使用者。
 Cloud App Security 中有下列自動群組：
  - External
  - Dropbox 系統管理員
  - Office 365 系統管理員
  - G Suite 系統管理員
  - Box 系統管理員
  - 所有的 Salesforce 標準和自訂設定檔，例如 Salesforce 系統管理員。 完整清單請參閱[這裡](https://help.salesforce.com/articleView?id=standard_profiles.htm&language=en&type=0)。

- 匯入的群組</br>您可以從連接的應用程式匯入任何群組。 例如，您可以從 Office 365 (Active Directory) 和其他連接的應用程式匯入使用者群組。 這可讓您查看特定群組來尋找組織中的威脅，不是查看整個組織或特定的使用者。 

運用匯入使用者群組的一般案例包括：您可調查人資人員查看的文件、檢查主管團隊中是否發生不尋常的情形，或管理團隊中是否有人在美國境外執行活動。 匯入使用者群組：

1. 在功能表列中，按一下設定圖示![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [使用者群組]。
2. 按一下 [匯入使用者群組]。

  ![匯入使用者群組](./media/user-groups-add.png)

3. 選取要使用者群組匯入來源的應用程式。 應用程式清單是由您部署的應用程式連接器決定。
4. 選取要匯入的群組。 可用群組清單是應用程式本身中的所有現有使用者群組清單。 如果想要新增新的群組，您必須直接在應用程式本身上執行，然後當它出現在這裡時選取它。
4. 視群組大小而定，匯入最多可能需要一小時。 您可以選取在匯入程序完成時，透過電子郵件通知的選項。
5. 按一下 [匯入]。 匯入群組後，Cloud App Security 會自動同步處理群組成員，就像 Active Directory Connect 一樣。
7. 匯入完成後，您可以在 [使用者群組] 頁面中按一下特定的群組，檢視所有群組成員的清單。 您也可以按一下任何群組成員，進一步向下切入特定帳戶的詳細資料，並檢視它們使用哪些應用程式及帳戶摘要，包括使用者圖形及其活動。

匯入群組可讓您在調查**活動記錄**和建立原則時，選取這些群組作為篩選。 

> [!NOTE]
> 只有在匯入使用者群組後執行的活動，才會標記為使用者群組成員已執行。

如需使用使用者群組篩選器的詳細資訊，請參閱[活動](activity-filters.md)。


    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  