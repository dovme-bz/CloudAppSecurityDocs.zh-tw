---
title: 在 Cloud App Security 中建立 Cloud Discovery 應用程式原則 | Microsoft Docs
description: 本主題提供如何使用 Cloud Discovery 原則的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 45446111-ed1a-4699-9df5-840cc6664a6b
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 983a4af689351fe9c71d1971f16b858a577a31ae
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


# <a name="cloud-discovery-policies"></a>Cloud Discovery 原則
    
## <a name="creating-an-app-discovery-policy"></a>建立應用程式探索原則  
探索原則可讓您設定警示，在您的組織內偵測到新的應用程式時通知您。  
  
1.  在主控台中，依序按一下 [控制] 和 [原則]。  
  
2.  按一下 [建立原則]，然後選取 [應用程式探索原則]。  
  
     ![應用程式探索原則功能表](./media/app-discovery-policy-menu.png "應用程式探索原則功能表")  
  
3.  為您的原則命名並描述，如果希望，也可以範本為依據；如需原則範本的詳細資訊，請參閱 [Control cloud apps with policies](control-cloud-apps-with-policies.md) (使用原則控制雲端應用程式)。  
  
4.  設定原則的 [嚴重性]。

5. 若要設定有哪些已探索到的應用程式會觸發此原則，請新增篩選。  
  
6.  您可以設定原則敏感度的閾值。 啟用 [同一天發生下列所有情況時，觸發原則比對] 之後，您可以設定 [使用者數目]、[IP 位址數目]、[每日流量]、[下載的資料]、[上傳的資料] 和 [交易數目] 的最小值，應用程式必須符合這些值才能比對原則。  
  
7.  設定 [每日警示限制]，然後選取要以電子郵件還是簡訊 (或兩者皆是) 來傳送警示，並視需要提供詳細資料。 您可以按一下 [Save alert settings to default (將警示設定儲存為預設值)]，讓未來的原則能將這些警示設定，包括電話號碼和電子郵件地址，儲存為預設值。  
  
8. 選取當應用程式符合此原則時所要套用的可能**治理**動作。 它可能會將原則自動標記為 [獲批准] 或 [待批准] 

8.  按一下 [建立]。  
  
例如，如果您想要探索雲端環境中高風險的主控應用程式，請如下所示設定您的原則︰  
  
設定原則篩選，探索在 [主控服務] 類別中找到且分數低的任何服務，這表示它們具有高風險。   
   
您可在底部設定要針對特定已探索應用程式觸發警示的閾值；只有在環境中有超過 100 個使用者使用該應用程式，且只有在他們從服務下載特定資料量的情況下，才觸發警示。   
此外，您可以設定想要接收的每日警示限制。  
  
![應用程式探索原則範例](./media/app-discovery-policy-example.png "應用程式探索原則範例")  
  
## <a name="cloud-discovery-anomaly-detection"></a>Cloud Discovery 異常偵測  
Cloud App Security 會搜尋 Cloud Discovery 的所有記錄檔是否有異常。 例如，某位使用者從未使用過 Dropbox，突然上傳 600 GB 到 Dropbox，或是在特定應用程式上的交易比起平日超出許多。 異常偵測原則預設為已啟用，所以不需要設定新的原則即可正常運作，但您可以在預設原則中微調想要收到警示的異常類型。  
  
1.  在主控台中，依序按一下 [控制] 和 [原則]。  
  
2.  按一下 [建立原則] ，然後選取 [Cloud Discovery 異常偵測原則]。  
  
     ![Cloud Discovery 異常偵測原則功能表](./media/cloud-discovery-anomaly-detection-policy-menu.png "Cloud Discovery 異常偵測原則功能表")  
  
3.  為您的原則命名並描述，如果希望，也可以範本為依據；如需原則範本的詳細資訊，請參閱 [Control cloud apps with policies](control-cloud-apps-with-policies.md) (使用原則控制雲端應用程式)。  
  
4.  若要設定有哪些已探索到的應用程式會觸發此原則，請按一下 [新增篩選]。  
  
     篩選是從篩選快顯畫面的頁面左側選擇。 可以依 [服務名稱]、[網域]、[風險因素]、[風險分數] 和 [類別] 來篩選。 頁面的右側會顯示來自目前服務類別目錄之所選篩選的結果。 選擇篩選之後，請儲存並確定適當的標記顯示在 [篩選] 方塊中。  
  
5.  在 [Apply to (套用至)] 下選擇它適用於 [所有資料檢視] 還是 [特定資料檢視]，以及它適用於 [使用者]、[IP 位址] 還是兩者都適用。  
  
6.  在 [只對下列日期以後發生的可疑活動引發警示] 下選取發生異常活動的日期，來觸發警示。  
  
7.  在 [警示] 下，您可以從低到高設定異常偵測敏感度，以設定您想要收到警示的頻率。  
設定 [每日警示限制]，然後選取要以電子郵件還是簡訊 (或兩者皆是) 來傳送警示，並視需要提供詳細資料。 您可以按一下 [Save alert settings to default (將警示設定儲存為預設值)]，讓未來的原則能將這些警示設定，包括電話號碼和電子郵件地址，儲存為預設值。 您也可以按一下 [Use organization defaults (使用組織的預設值)] 來根據您組織的預設值設定這些設定。  
  
9. 按一下 [建立]。  
  
![新的探索異常原則](./media/new-discovery-anomaly-policy.png "新的探索異常原則")  
  
## <a name="see-also"></a>另請參閱  
[使用者活動原則](user-activity-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  