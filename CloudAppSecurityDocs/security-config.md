---
title: 在 Cloud App Security 中取得安全性設定建議 | Microsoft Docs
description: 本文提供在與 Azure 資訊安全中心整合的情況下，如何在 Cloud App Security 中取得安全性設定建議的相關資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: c6d8f8af-867b-43ab-adee-f06520577fe7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0d21df4cac9ca31207b94061d5bb18ec857668ac
ms.sourcegitcommit: c7e4351345d55cfeb0517651446490ce5f208651
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2018
ms.locfileid: "37140766"
---
*適用於：Microsoft Cloud App Security*


# <a name="security-configuration"></a>安全性設定

Microsoft Cloud App Security 提供 Azure 環境的安全性設定評量，以及提供遺失設定和安全性控制的建議 (由 Azure 資訊安全中心提供)。 

若要使用此功能，您必須具有 Azure AD 和 Azure 入口網站中的適當權限。
 
Azure AD 全域管理員角色預設未提供 Azure 訂用帳戶存取權。 因此，您需要提高權限，以將 Azure 訂用帳戶存取權授與您自己和其他使用者。 

> [!NOTE]
> 在您完成下列程序之後，建議停用提高權限。

在 Microsoft Cloud App Security 中啟用安全性設定建議：

1. <a href="https://docs.microsoft.com/azure/security-center/security-center-management-groups" target="_blank">取得 Azure 資訊安全中心的整個租用戶可見度</a>，方法是將所有訂用帳戶的讀者角色授與您自己，以及您想要授與此頁面存取權的所有其他 Microsoft Cloud App Security 管理員，以及在 Azure 資訊安全中心內指派根管理群組的這個角色，並評估 Azure AD 全域管理員授與 Azure 訂用帳戶存取權。 

   > [!NOTE]
   > 本文描述成為安全性系統管理員的程序。 為了讓此整合運作，您需要的最小權限是讀者。

2. 請務必開啟 <a href="https://ms.portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/0" target="_blank">Azure 資訊安全中心</a>，讓變更生效。

3. 在 Microsoft Cloud App Security 入口網站中，依序前往 [調查] 和 [安全性設定]。 

   ![安全性設定功能表](./media/security-configuration-menu.png)

   > [!NOTE]
   > Microsoft Cloud App Security 只會提供前 50 個訂用帳戶的建議。
   > 最多可能需要 15 分鐘，變更才會生效。

5. 您可以依類型、資源和訂用帳戶來篩選建議。 此外，您可以按一下安全性設定圖示 ![ASC 圖示](./media/asc-icon.png) 在 Azure 資訊安全中心內開啟建議來取得詳細資訊，以及深入了解建議。 <br></br><br></br>如需如何實作安全性建議的資訊，請參閱[管理 Azure 資訊安全中心的安全性建議](https://docs.microsoft.com/azure/security-center/security-center-recommendations)。

 
   ![安全性設定](./media/security-configuration1.png)

 

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
