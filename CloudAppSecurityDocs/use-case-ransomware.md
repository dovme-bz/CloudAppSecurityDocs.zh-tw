---
title: 威脅防護案例概觀 | Microsoft Docs
description: 本主題描述保護您的組織免受雲端環境威脅的案例。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5fd6cf54012d148261e98f0058109420cb55e9fa
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143865"
---
*適用於：Microsoft Cloud App Security*


# <a name="protecting-your-organization-from-ransomware"></a>保護您的組織免受勒索軟體威脅

在最近大量的勒索軟體攻擊中，WannaCry 嚴重打擊網路世界，估計有 150 個國家/地區的 200,000 部電腦受到感染。 勒索軟體攻擊事件在過去幾年來逐漸增加，2015 年每月平均有 25,000 起攻擊事件，到了 2016 年增加到 56,000 起，這使得網路安全性變得至關重要，您必須主動確保網路和雲端沒有風險。 本文說明如何使用 Cloud App Security 監視雲端、偵測並減輕威脅，以及套用最佳做法來保護您的環境免受勒索軟體威脅。

## <a name="what-is-ransomware"></a>什麼是勒索軟體？
勒索軟體是一種網路攻擊，攻擊者會傳送您一個檔案，使您無法存取電腦及加密自己的檔案。 這些檔案有時會遭挾持要求贖金，而且您必須支付攻擊者贖金來還原電腦、檔案或重要 LOB 應用程式的存取權，才能將這些檔案解密。 勒索軟體攻擊可能會影響任何電腦、首頁、Office、網路或伺服器。 事實上，由於大型組織是由許多使用者所組成，這些使用者可能會不慎開啟檔案而將勒索軟體釋放到整個網路，因此組織更有可能被迫支付攻擊者贖金，以停止勒索軟體並還原電腦或檔案的存取權。

>[!NOTE]
> 這個使用案例適用於 Office 365、G Suite、Box 和 Dropbox。

## <a name="the-threat"></a>威脅
勒索軟體攻擊的目標是您組織中的使用者。 使用者可能在不知情的情況下開啟受感染的電子郵件，並執行勒索軟體而感染所有檔案，包括同步至雲端的檔案。

## <a name="the-solution"></a>解決方案
請建立原則在偵測到可疑活動時通知您，以偵測雲端環境中的潛在勒索軟體，並設定自動化動作，以避免將勒索軟體檔案儲存至您的雲端。

## <a name="out-of-the-box-protection"></a>預設的保護

至少將一個雲端應用程式 (Office 365、G Suite、Box 和 Dropbox) [連線](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)到 Cloud App Security。

1.  根據預設，Cloud App Security 會掃描您的網路來建立基準，藉此了解您的使用者一般會在雲端中執行哪些工作、何時執行，以及經常執行哪些工作等模式。 

2. Cloud App Security 的自動化[威脅偵測原則](anomaly-detection-policy.md)會從您連線的那一刻開始在背景中執行。 這些原則之一會搜尋勒索軟體活動，以確保防護複雜的勒索軟體攻擊涵蓋範圍完整。 使用安全性搜尋專業知識來識別可反映勒索活動的行為模式，Cloud App Security 保證可提供全面且強大的保護。 例如，若 Cloud App Security 發現有高比率的檔案上傳或檔案刪除活動，則可能代表加密程序設計不良。 這項資料會收集在從已連線應用程式 API 收到的記錄檔中，然後再和學習到的行為模式與威脅情報 (例如，已知的勒索軟體副檔名) 結合使用。 




   ## <a name="see-also"></a>另請參閱  
   [可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  