---
title: "異常偵測原則 | Microsoft Docs"
description: "本主題提供異常偵測原則的描述，並提供異常偵測原則建置組塊的參考資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 002e0b82296162ee13fa378c4641cc8f21547237
ms.openlocfilehash: ca51d36a6d899124d3d4eb84ded1972ad9c8bab4


---

# <a name="anomaly-detection-policy"></a>異常偵測原則
本文提供原則的參考詳細資訊，並說明每種原則類型和您可以針對每個原則設定的欄位。  
 
Cloud App Security 有 7 天的初始學習期間，在此期間，不會將任何新的使用者、活動、裝置或位置標記為異常。 之後，每個工作階段都會與活動進行比較，當使用者處於使用中時，會偵測到上個月的 IP 位址、裝置等以及這些活動的風險分數。 使用原則中的敏感度滑桿，來設定將觸發警示的最小風險分數。 建議您在建立異常原則時，使用預設敏感度閾值一週，在根據收到的警示數目進行變更之前，Cloud App Security 會在您變更敏感度時，將各種風險分數的更多或更少警示傳送給您。
  
![敏感度滑桿](./media/sensitivity-slider.png)
## <a name="anomaly-detection-policy-reference"></a>異常偵測原則參考  
異常偵測原則可讓您安裝和設定連續監視行為異常的使用者活動。 異常偵測是透過掃描使用者活動而完成。 風險評估是透過查看分為 6 組風險因素的 30 項不同風險指標而完成。 根據原則結果觸發安全性警示。   
每個原則皆由下列部分組成：  
  
-   活動篩選 – 可讓您選擇性地只掃描篩選出的使用者活動是否有異常。  
  
-   風險因素 – 可讓您在評估風險時選擇要包括哪些風險因素。  
  
-   敏感度 – 可讓您設定原則應觸發多少警示。  
  
### <a name="activity-filters"></a>活動篩選  
如需活動篩選清單，請參閱[在這裡輸入連結描述](activity-filters.md)。  
  
### <a name="risk-factors"></a>風險因素  
以下是評估使用者活動風險時要考量的風險因素清單。 每項風險因素都可以開啟或關閉。 每項風險因素在 [Apply to (套用至)] 欄位下都有兩個選項，決定是否於評估使用者活動風險時包含︰  
  
-   所有受監視的活動 – 通過原則活動篩選的所有使用者活動都包含它。  
  
-   選取的活動 – 使用者活動會包含它，但使用者活動必須通過原則活動篩選和出現在這個風險因素下的活動篩選。 當選取這個選項時，風險因素下就會出現活動篩選器，運作方式與原則活動篩選完全相同。  
  
當包含在風險評估中時，每項風險因素都有自己的觸發程序，會在評估的使用者活動風險中造成增幅︰  
  
-   登入失敗 – 大量的登入失敗，或整體活動造成登入失敗。  
  
-   管理活動 - 非預期使用者執行的管理活動，或從 IP、ISP 或新位置執行的管理活動，或組織中任何其他使用者未使用的管理活動。  
  
-   非使用中帳戶 - 長時間未執行活動的使用者所執行的活動。  
  
-   位置 - 從 IP、ISP 或任何其他使用者從未使用過、這個特定的使用者從未使用過、完全未使用過、或過去僅用於登入失敗的位置執行的活動。  
  
-   不可能的旅遊 - 短時間內來自遠端位置的活動。  
  
-   裝置和使用者代理程式 - 使用者利用任何其他使用者從未使用過、這個特定使用者從未使用過或完全未使用過的使用者代理程式或裝置執行的活動。  
  
### <a name="sensitivity"></a>敏感度  
您可使用下列兩種方式，來控制原則所觸發的警示數目：  
  
-   敏感度滑桿 – 選擇每 1000 名使用者每週可觸發多少警示。 具有最高風險的活動就會觸發警示。  
  
-   每日警示限制 – 限制一天當中可產生的警示數目。  
  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  



<!--HONumber=Nov16_HO5-->


