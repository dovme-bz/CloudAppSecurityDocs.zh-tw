---
title: 在 Cloud App Security 中建立 Cloud Discovery 異常偵測原則 | Microsoft Docs
description: 此主題提供如何使用 Cloud Discovery 異常偵測原則的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 49e7dadb3d179e70c04decccdc8ab11aeefc3241
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


# <a name="cloud-discovery-anomaly-detection-policy"></a>Cloud Discovery 異常偵測原則
本文提供原則的參考詳細資訊，並說明每種原則類型和您可以針對每個原則設定的欄位。  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>Cloud Discovery 異常偵測原則參考  
Cloud Discovery 異常偵測原則可讓您進行設定，以持續監視雲端應用程式使用量的不尋常增加。 其中，每個雲端應用程式的下載資料、上傳資料、交易數目和使用者數目的增加都會納入考量。 系統會將每次的增加量和應用程式的標準使用模式 (從過去使用量學習而得) 進行比較。 最極端的增加量會觸發安全性警示。  
  
針對每個原則，您可以設定篩選條件，以根據應用程式篩選條件、選取的資料檢視和選取的開始日期，選擇性地監視應用程式使用量。 您也可以設定敏感度，以讓您設定原則應觸發多少警示。  

針對每個原則，請設定下列參數：

1. 決定是否要根據範本來建立原則，相關的原則範本為 [探索到之使用者中的異常行為] 範本，此範本可在探索到之使用者和應用程式中偵測到異常行為時發出警示，例如：與其他使用者相較之下的異常大量上傳資料，或是與使用者歷程記錄相較之下的異常大型使用者交易。 您也可以選取 「Anomalous behavior of discovered IP addresses」 (探索到之 IP 位址的異常行為) 範本，可在探索到之 IP 位址和應用程式中偵測到異常行為時發出警示，例如：與其他 IP 位址相較之下的大量上傳資料、與 IP 位址歷程記錄相較之下的大型應用程式交易。 
 
2. 提供 [原則名稱] 和 [描述]。  

3. 按一下 [新增篩選]，為您想要監視的應用程式建立篩選條件。 
   您可以選取特定的應用程式、應用程式「類別」，或依 [名稱]、[網域] 和 [風險因素]<strong>**</strong> 進行篩選，然後按一下 [儲存]。

4. 在 [套用至] 下，設定您想要如何篩選使用量。 您可使用下列兩種不同方式，篩選受監視的使用量：  
  
    -   連續報告 – 選擇是否監視 「All continuous reports」 (所有連續報告) (預設值)，或選擇監視 「Specific continuous reports」 (特定連續報告)。  
  
        -   選取 「All continuous reports」 (所有連續報告) 時，系統會將每個增加的使用量和一般使用模式 (從所有資料檢視學習而得) 進行比較。  
  
        -   選取 「Specific continuous reports」 (特定連續報告) 時，系統會將每個增加的使用量和一般使用模式 (從相同資料檢視中觀察到的增加量學習而得) 進行比較。  
  
    -   **Users and IP addresses (使用者和 IP 位址)** – 已與每個雲端應用程式使用量建立關聯的使用者、IP 位址，或兩者。  
  
        -   選取 [使用者] 會忽略應用程式使用量和 IP 位址之間的關聯 (若有的話)。  
  
        -   選取 [IP 位址] 會忽略應用程式使用量和使用者之間的關聯 (若有的話)。  
  
        -   選取 [使用者與 IP 位址] (預設值) 會考慮這兩種關聯，但在使用者與 IP 位址之間有緊密對應性的情況下，可能會產生重複警示。
    -   只對特定日期以後發生的可疑活動觸發警示，任何在選取的日期之前所發生的應用程式使用量增加情況皆會被忽略。 不過，系統會根據所選日期之前的活動進行學習，藉此建立標準使用模式。  
  
5. 在 [警示] 下，您可以設定警示敏感度。 您可以使用多種方式來控制原則所觸發的警示數目：  
  
    -   「Select anomaly detection sensitivity」 (選取異常偵測敏感度) 滑桿 – 針對每週每 1,000 位使用者的前 X 個異常活動觸發警示。 系統會針對具有最高風險的活動觸發警示。  
  
    -   **Daily alert limit (每日警示限制)** – 限制一天當中可產生的警示數目。 您可以選擇 「Send alert as email」 (將警示傳送為電子郵件)、「Send alert as text message」 (將警示傳送為簡訊) 或兩者。 針對 UTC 時區，透過簡訊所傳送的訊息將會有每天 10 則的限制，這表示系統會在 UTC 時區午夜重設 10 則訊息的限制。

    - 您也可以選取 「Use your organization's default settings」 (使用組織的預設設定) 選項，這個選項會填入組織預設設定的 「Daily alert limit」 (每日警示限制)、電子郵件和簡訊設定。 若要設定預設值，請填寫 「Alert configuration」 (警示設定) 設定，然後按一下 「Save these alert settings as the default for your organization」 (將這些警示設定儲存為組織的預設值)。

6. 按一下 [建立]。

7. 與所有原則相同，您可以按一下 [原則] 頁面中資料列結尾的三個點，來 [編輯]、[停用] 和 [啟用] 原則。 原則預設會在建立之後予以啟用。

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  