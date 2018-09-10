---
title: Cloud App Security 疑難排解原則 | Microsoft Docs
description: 本主題說明在 Cloud App Security 中建立疑難排解原則的流程。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ca7d2187ebd83c352cbbcf92efb7a30adf8debcf
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44142573"
---
*適用於：Microsoft Cloud App Security*


# <a name="troubleshooting-microsoft-cloud-app-security-policies"></a>Microsoft Cloud App Security 疑難排解原則

|錯誤|說明|解決方法|
|----|----|----|
| **原則 <policy name> 已因為設定錯誤而自動停用**|如果您在 Microsoft Cloud App Security 收到這個錯誤，表示您必須修正提及的原則設定。 當您建立 Microsoft Cloud App Security 原則時，通常會利用您在 Cloud App Security 或者安全性和合規性中心中建立的物件，像是 IP 標籤或是自訂機密類型。 如果您用於原則內的 IP 標籤或自訂機密類型後來刪除了，原則就會自動停用，而您會收到這個錯誤。 這也可能表示更常見的組態錯誤，例如太複雜的篩選。 |為了還原原則，編輯原則並修正上述每個組態錯誤。 這通常表示您必須從原則篩選器中移除任何已刪除的物件，並儲存原則。|



## <a name="see-also"></a>另請參閱
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

