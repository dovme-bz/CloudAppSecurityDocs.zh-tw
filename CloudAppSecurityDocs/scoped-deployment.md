---
title: 限定 Microsoft Cloud App Security 部署範圍 | Microsoft Docs
description: 本文提供有關如何限定 Cloud App Security 部署範圍的相關資訊，包含和排除特定使用者或群組。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: fe2ce27b-1020-45e9-ad72-fad93d197169
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4e97155b07dfc1e7f360eb798961406c36f85003
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143746"
---
*適用於：Microsoft Cloud App Security*


# 限定範圍的部署 <a name="scoped-deployment"></a> 

Microsoft Cloud App Security 可讓您限定部署的範圍，就能只監視特定使用者群組，或能將特定使用者群組從監視中排除。

您可能不想針對組織中的所有使用者使用 Microsoft Cloud App Security。 當您由於授權限制而想要限制部署時，或者因為合規性規定可能要求您不要監視來自特定國家/地區的使用者時，此功能特別有用。 例如，使用限定範圍的部署可以僅監視美國員工，或者避免為您的德國使用者顯示任何活動。 

- 若要限定部署的範圍，您必須先[將使用者群組匯入](user-groups.md)到 Microsoft Cloud App Security。 根據預設，您會看到**應用程式**使用者群組。這是一個內建群組，可讓您查看由 Office 365 和 Azure AD 應用程式以及**外部使用者**群組執行的活動。如此可合併不在您為組織所設定 [IP 位址範圍](ip-tags.md)內的所有使用者。
- 設定包含規則將自動排除不在包含群組內的所有群組。 例如，如果您將規則設定為包含美國辦公室群組的所有成員，則不會監視不屬於該群組的任何群組。
- 排除的使用者群組會覆寫包含的使用者群組。 這表示如果您包含「英國員工」使用者群組但排除「行銷」，即使他們是**英國員工**群組的成員，英國的行銷成員也不會受到監視。

1. 在功能表列中，按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [限定範圍的部署]。  

2. 為了限定您的部署範圍包含或排除特定群組，您必須先[將使用者群組匯入](user-groups.md) Microsoft Cloud App Security。 

3. 若要設定要由 Microsoft Cloud App Security 監視的特定群組，請在 [包含] 索引標籤上按一下加號 ![圖示](./media/plus-icon.png)。 <br>在 [建立新包含規則] 對話方塊中，執行下列步驟：

    1. 在 [類型規則名稱] 下，為該規則指定一個描述性名稱。
    2. 在 [選取使用者群組] 下，選取您想要使用 Cloud App Security 監視的所有群組。
    3. 選取是否要將此規則套用於已連線的所有應用程式，還是僅套用於**特定應用程式**。 如果您選取 [特定應用程式]，該規則只會影響您所選取應用程式的監視。 也就是說，如果您選取 [英國使用者] 群組和 [Box]，則 Cloud App Security 將只監視英國使用者的 Box 活動，而對於所有其他應用程式，Cloud App Security 會監視所有使用者的所有活動。
     
     ![包括規則](./media/include-rule.png)

4. 若要設定從監視中排除特定群組，請在 [排除] 標籤上按一下加號![圖示](./media/plus-icon.png)。 <br>在 [建立新排除規則] 對話方塊中，設定下列參數：

    1. 在 [類型規則名稱] 下，為該規則指定一個描述性名稱。
    在 [選取使用者群組] 下，選取您不想要使用 Cloud App Security 監視的所有群組。
    2. 選取是否要將此規則套用於已連線的所有應用程式，還是僅套用於**特定應用程式**。 如果您選取 [特定應用程式]，Cloud App Security 將停止監視您針對所選取應用程式而選取的唯一群組。 也就是說，如果您選取 [德國使用者] 群組和 [Active Directory]，Cloud App Security 將監視所有使用者活動，但排除德國使用者執行的 Active Directory 活動。
    
    ![排除規則](./media/exclude-rule.png)

您所建立的包含和排除規則可共同運作，以限定由 Microsoft Cloud App Security 執行的整體監視範圍。

以下是您可以建立的包含和排除規則的範例，以及在執行這些規則之後，Microsoft Cloud App Security 所監視之項目的最終結果。

如果您建立下列規則：

- 排除使用者群組「德國所有使用者」
- 針對使用者群組「全球銷售」僅包含 Office 365 活動
- 針對使用者群組「銷售經理」僅包含 Power BI 活動
- Salesforce 已連線至 Microsoft Cloud App Security，且其未設有任何規則

下列使用者的活動會受到監視：

|使用者|群組成員資格|監視的活動|
|----|----|----|
|Adriana|德國所有使用者<br>全球銷售<br>銷售經理|無|
|Alain|全球銷售|Office 365 和所有子應用程式 (除 Power BI 以外)|
|Cornel|全球銷售<br>銷售經理|Office 365 和所有子應用程式|
|Raymond|銷售經理|僅限 Power BI|

> [!NOTE] 
> 其他應用程式不會受到這些規則中的群組範圍限定影響。
> 在範例中，針對 Salesforce，會監視所有使用者群組的所有活動。

  
    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  
