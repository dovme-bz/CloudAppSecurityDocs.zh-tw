---
title: 在 Cloud App Security 中建立原則以控制應用程式權限 | Microsoft Docs
description: 本主題提供在 Microsoft Cloud App Security 中建立和使用應用程式權限原則的指示。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9f68302c-bb3d-450c-bbf5-f8130cb163e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 02af6d6c109812156f8b8a3cf38a6f0599f2fec4
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143150"
---
*適用於：Microsoft Cloud App Security*


# <a name="app-permission-policies"></a>應用程式權限原則

除了連線至您環境中 [OAuth 應用程式的現有調查](manage-app-permissions.md)之外，您還可以設定權限原則，以在 OAuth 應用程式符合特定準則時取得自動通知。 例如，您會在應用程式需要高權限等級並由超過 50 位使用者授權時自動收到警示。 

應用程式權限原則可讓您針對 Office 365、G Suite 和 Salesforce 調查每個應用程式所要求的權限，以及授權它們的使用者。 您也可以將這些權限標示為已核准或已禁止。 將它們標示為已禁止，將會撤銷授權它之每位使用者的每個應用程式權限。 

建立新應用程式權限原則：
1. 在 [調查] 下，選取 [應用程式權限]。
2. 根據您的需求篩選應用程式，例如，您可以檢視所有可要求 [權限] 的應用程式，以**修改您信箱中的行事曆**。
3. 按一下 [從搜尋新增原則] 按鈕。 
    ![從搜尋新增原則](./media/app-permissions-filter.png)
4. 您可以使用 **Community use** 篩選，取得允許此應用程式的權限為常見、不常見還是罕見的資訊。 如果您的應用程式為罕見，並且要求具有高嚴重性層級的權限或是要求許多使用者的權限，則這可能十分有用。 

或者，您也可以按一下接著 [原則] 的 [控制項]，以建立原則。 然後按一下接著 [應用程式權限原則] 的 [建立原則]。

  
   ![新應用程式權限原則](./media/app-permissions-policy.png)



  ## <a name="see-also"></a>另請參閱  
  [資料保護原則](data-protection-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  