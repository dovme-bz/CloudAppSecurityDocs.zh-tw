---
title: Cloud App Security 常見問題集 | Microsoft Docs
description: 本文提供 Cloud App Security 的常見問題與解答。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b53a360b743e80c85dcced8dd2bef7eae8c60f36
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144001"
---
*適用於：Microsoft Cloud App Security*


# <a name="frequently-asked-questions"></a>常見問題集

## <a name="what-kind-of-permissions-do-i-need-to-have-in-order-to-access-cloud-app-security"></a>需要有何種權限才能存取 Cloud App Security？

您必須是 Azure Active Directory 中的全域系統管理員、合規性系統管理員或安全性系統管理員。 在 Office 365 安全與規範中心中具有這些角色是不夠的。
若要將使用者設定為 Azure Active Directory 中的全域系統管理員、合規性系統管理員或安全性系統管理員，請在 Windows PowerShell 中執行下列命令：

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 OR Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress “XX@XX.XX”

## <a name="see-also"></a>另請參閱  
若要了解如何使用及設定原則來控制雲端應用程式的使用情形，請參閱[使用原則控制雲端應用程式](control-cloud-apps-with-policies.md)。   

頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。  
