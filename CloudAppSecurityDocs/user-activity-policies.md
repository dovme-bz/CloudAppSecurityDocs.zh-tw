---
title: "活動原則 | Microsoft Docs"
description: "本主題提供建立及使用活動原則的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/27/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 99d5fd37-d922-4269-b557-86d7f84180eb
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9565d8a51e4c06963861d9dfaef9595944bda1ff
ms.openlocfilehash: 68961bf66a0c0bb3b668e681502ccf10bc673197


---

# <a name="activity-policies"></a>活動原則
活動原則可讓您利用應用程式提供者的 API，強制執行各種不同的自動化程序。 這些原則可讓您監視由不同使用者執行的特定活動，或是追蹤意外高比率的某種特定類型活動。  
  
設定活動偵測原則之後，就會開始產生警示 - 只有建立原則之後發生的活動才會產生警示。
  
  
## <a name="custom-alerts"></a>自訂警示  
活動原則可讓您設定要傳送的自訂警示，或偵測到使用者活動時要採取的動作。 例如，如果您想要知道每次使用者嘗試登入和一分鐘內失敗 70 次、或者使用者下載 7000 個檔案、或從阿富汗登入，您可以設定在這些事件發生時，傳送活動警示給您自己或使用者。 您甚至可以暫停使用者，直到您有時間進行調查。  
  
若要建立新的活動原則，請遵循此程序︰  
  
1.  在主控台中，依序按一下 [控制] 和 [原則]。  
  
2.  按一下 [建立原則]，然後選取 [活動原則]。  
  
     ![活動原則功能表](./media/activity-policy-menu.png "activity policy menu")  
  
3.  為您的原則命名並描述，如果希望，也可以範本為依據；如需原則範本的詳細資訊，請參閱 [Control cloud apps with policies](control-cloud-apps-with-policies.md) (使用原則控制雲端應用程式)。  
  
4.  若要設定觸發此原則的動作或其他計量，請使用 [活動篩選]。  
  
5.  在 [活動比對參數] 下，選取是單一活動符合篩選條件時觸發原則違規，還是偵測到指定數目的 [重複的活動] 時才偵測到違規。  
    若您選擇 [重複的活動]，可以設定 [每一應用程式的群組相符活動]。 僅當重複的活動發生在同一應用程式 (例如從 Box 下載 5 次) 時，才會觸發原則比對。  
  
6.  設定找到相符項目時應該採取的 [動作]。  
  
看看這些範例︰  
  
-   多次失敗的登入  
  
     您可以設定原則，以便在特定、相對短的時段內有大量的登入嘗試失敗時，收到警示。 若要設定類似的原則，請在 [新增活動原則] 頁面中選擇適當的活動篩選。  
  
     在 [活動篩選] 欄位下方，設定觸發警示的參數。  
  
     ![多個失敗登入嘗試原則範例](./media/multiple-failed-log-on-attempts-policy-example.png "multiple failed log on attempts policy example")  
  
-   高下載率  
  
     您可以設定原則，以便在非預期或無法定性層級的下載活動出現時，收到警示。 若要設定類似的原則，請在 [速率] 參數下，選擇觸發警示的參數。  
  
     ![高下載率範例](./media/high-download-rate-example.png "high download rate example")  
  
## <a name="anomaly-detection"></a>異常偵測  
在組織受到 Cloud App Security 保護之後，所有雲端活動都會根據各種預先定義的風險因素進行評分。 Cloud App Security 會查看雲端上每位使用者的工作階段，然後考量您在此處設定的風險因素以警示您有不同於組織基準的事故發生，或不同於使用者一般活動的事故發生。 異常偵測原則頁面可讓您設定及自訂風險評分程序中要考慮的風險因素系列。 原則可以針對不同的使用者、位置和組織單位以不同的方式來執行。 例如，您可以建立一項原則，在您的 IT 小組成員從辦公室外部進行活動時發出警示。  
  
設定異常偵測原則︰  
  
1.  在主控台中，依序按一下 [控制] 和 [原則]。  
  
2.  按一下 [建立原則] ，然後選取 [異常偵測] 原則。  
  
     ![異常偵測原則功能表](./media/anomaly-detection-policy-menu.png "Anomaly detection policy menu")  
  
3.  填寫該原則的名稱和描述，然後繼續填寫 [活動篩選] 欄位，這裡可以選擇您要套用原則的活動。  
  
4.  為您的原則命名並描述，如果希望，也可以範本為依據；如需原則範本的詳細資訊，請參閱 [Control cloud apps with policies](control-cloud-apps-with-policies.md) (使用原則控制雲端應用程式)。  
  
5.  若要將原則套用到雲端環境的所有活動，請選取 [所有受監視的活動]。 若要限制特定類型的活動原則，請選擇 [選取的活動]。 按一下 [新增篩選] 並設定適當的參數，藉以篩選活動。 例如，若只要針對 Salesforce 管理員所執行的活動執行原則，請選擇這個使用者標籤。  
  
6.  在此欄位下設定 [風險因素]。 您可以選擇計算風險分數時，要考慮的風險系列。 在資料列右側，您可以使用 [開啟/關閉] 按鈕來啟用和停用各種風險。 此外，為得到更細微的資料，您可以選擇對活動啟用每一個特定的風險系列。  
  
     風險因素如下︰  
  
    -   **登入失敗**︰使用者是否嘗試登入並在短時間內失敗多次？  
  
    -   **管理活動**︰管理員是否使用特殊權限帳戶從不尋常的位置或在奇怪的時間登入？  
  
    -   **非使用中帳戶**︰某個一段時間不使用的帳戶是否突然開始活動？  
  
    -   **位置**︰是否有異常、 可疑或新位置的活動？  
  
    -   **不可能的旅遊**︰是否有從丹佛登入的使用者，十分鐘後又從巴黎登入？  
  
    -   **裝置和使用者代理程式**︰是否有來自無法辨識或不受管理的裝置活動？  
  
     您可以使用這些參數來定義複雜的案例，例如，將辦公室 IP 範圍從風險因素排除不進行異常偵測，然後建立特定的 "office IP" 標籤，從考量的參數中篩選此範圍。 接著將您建立的範圍從管理活動異常偵測中排除︰  
  
    -   在 [風險類型] 內尋找 [管理活動]。  
  
    -   將 [Apply to (套用至)] 變更為 [選取的活動]。  
  
    -   在 [活動篩選] 下，將 [Apply to (套用至)] 設為 [選取的活動]，然後在 [Activities matching all of the following (與下列所有項目相符的活動)] 下，將 [系統管理活動] 選擇為 [True]。  
  
    -   按一下 **+** 圖示，然後依序選取 [IP tag does not equal (IP 標籤不等於)] 和 [Office IP] 標籤。  
  
7.  在 [敏感度] 下，選取您想要收到警示的頻率。  
  
     敏感度值會決定平均每 1000 位使用者觸發多少每週警示。  
  
     ![異常偵測 IP](./media/anomaly-detection-ips.png "anomaly detection IPs")  
  
8.  按一下 [建立]。  
 
  
## <a name="activity-policy-reference"></a>活動原則參考  
本節提供原則的參考詳細資訊，並說明每種原則類型和您可以針對每項原則設定的欄位。  
  
[活動原則] 是一種 API 型原則，可讓您將 20 多個檔案中繼資料篩選 (包括裝置類型和位置) 納入考量，藉此監視雲端中的組織活動。 系統會根據原則結果產生通知，並可能讓使用者暫停使用雲端應用程式。   
每個原則皆由下列部分組成：  
  
-   活動篩選 – 可讓您根據中繼資料建立非常細微的條件。  
  
-   活動比對參數 – 可讓您設定活動要重複幾次才會被視為符合原則的臨界值。  
  
-   動作 – 此原則提供一組可在偵測到違規時自動套用的治理動作。  
## <a name="see-also"></a>另請參閱  
[資料保護原則](data-protection-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


