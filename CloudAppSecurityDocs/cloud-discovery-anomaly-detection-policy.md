---
title: "Cloud Discovery 異常偵測原則 | Microsoft Docs"
description: "此主題提供如何使用 Cloud Discovery 異常偵測原則的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 400741713d40422a3b1c7680663a572d18e9c692
ms.openlocfilehash: 132b4d296b26dd187418734b40d08ecb243692da


---

# <a name="cloud-discovery-anomaly-detection-policy"></a>Cloud Discovery 異常偵測原則
本文提供原則的參考詳細資訊，並說明每種原則類型和您可以針對每個原則設定的欄位。  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>Cloud Discovery 異常偵測原則參考  
Cloud Discovery 異常偵測原則可讓您進行設定，以持續監視雲端應用程式使用量的不尋常增加。 其中，每個雲端應用程式的下載資料、上傳資料、交易數目和使用者數目的增加都會納入考量。 系統會將每次的增加量和應用程式的標準使用模式 (從過去使用量學習而得) 進行比較。 最極端的增加量會觸發安全性警示。  
  
每個原則皆由下列部分組成：  
  
-   篩選 – 可讓您根據應用程式篩選條件、選取的資料檢視和選取的開始日期，選擇性地監視應用程式使用量。  
  
-   敏感度 – 可讓您設定原則應觸發多少警示。  
  
### <a name="activity-filters"></a>活動篩選  
如需活動篩選條件清單，請參閱[活動](activity-filters.md)。  
  
### <a name="apply-to"></a>套用到  
您可使用下列兩種不同方式，篩選受監視的使用量：  
  
-   資料檢視 – 選擇監視所有的資料檢視 (預設)，或選擇監視特定的資料檢視。  
  
    -   選取 [所有資料檢視] 時，系統會將每次的增加量和標準使用模式 (從所有資料檢視學習而得) 進行比較。  
  
    -   選取特定的資料檢視時，系統會將每次的增加量和標準使用模式 (從相同資料檢視中觀察到的增加量學習而得) 進行比較。  
  
-   使用者和 IP 位址 – 已與每個雲端應用程式使用量建立關聯的使用者、IP 位址，或兩者。  
  
    -   選取 [使用者] 時，將會忽略已與應用程式使用量建立關聯的 IP 位址 (若有的話)。  
  
    -   選取 [IP 位址] 時，將會忽略已與應用程式使用量建立關聯的使用者 (若有的話)。  
  
    -   選取 [使用者與 IP 位址] 時，將會考慮這兩種關聯，但若使用者與 IP 位址之間有緊密的對應性，則可能會產生重複警示。  
  
只對下列日期以後發生的可疑活動引發警示 – 任何在選取的日期之前發生的應用程式使用量增加情況皆會被忽略。 不過，系統會從所選日期之前開始的活動進行學習，藉此建立標準使用模式。  
  
### <a name="sensitivity"></a>敏感度  
您可使用下列兩種方式，來控制原則所觸發的警示數目：  
  
-   敏感度滑桿 – 選擇每 1000 名使用者每週可觸發多少警示。 具有最高風險的活動就會觸發警示。  
  
-   每日警示限制 – 限制一天當中可產生的警示數目。  
  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


