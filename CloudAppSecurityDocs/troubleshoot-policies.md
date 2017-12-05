---
title: "Cloud App Security 疑難排解原則 | Microsoft Docs"
description: "本主題說明在 Cloud App Security 中建立疑難排解原則的流程。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 29/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6c8cbfa8899a6cfa66f6fc2a9ec9ff75375acecb
ms.sourcegitcommit: f4ec7f2cb81c9d83bb7f406ddcca91ab07790a98
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-cloud-app-security-policies"></a>Cloud App Security 疑難排解原則

|錯誤|描述|解決方法|
|----|----|----|
| **原則<policy name>已因為組態錯誤而自動停用。**|如果您在 Cloud App Security 收到這項錯誤，表示您必須修正提及的原則組態。 當您建立 Cloud App Security 原則時，您通常會利用您在 Cloud App Security 中建立的物件，像是 IP 標籤或者是 IP 範圍篩選。 如果您用於原則內的 IP 標籤或範圍後來刪除了，原則就會自動停用，而您會收到這項錯誤。 |若要還原原則，請編輯原則並從其篩選中移除任何已刪除的物件，再儲存原則。|



## <a name="see-also"></a>另請參閱
[使用原則控制雲端應用程式](control-cloud-apps-with-policies.md)
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

