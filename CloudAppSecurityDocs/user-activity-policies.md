---
title: "在 Cloud App Security 中建立原則以控制活動 | Microsoft Docs"
description: "本主題提供建立及使用活動原則的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 99d5fd37-d922-4269-b557-86d7f84180eb
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0e771330feb92833e77c0699d33851d7d52d82ef
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="activity-policies"></a>活動原則
活動原則可讓您利用應用程式提供者的 API，強制執行各種不同的自動化程序。 這些原則可讓您監視由不同使用者執行的特定活動，或是追蹤意外高比率的某種特定類型活動。  
  
設定活動偵測原則之後，就會開始產生警示 - 只有建立原則之後發生的活動才會產生警示。
  
  
## <a name="custom-alerts"></a>自訂警示  
活動原則可讓您設定要傳送的自訂警示，或偵測到使用者活動時要採取的動作。 例如，如果您想要知道每次使用者嘗試登入和一分鐘內失敗 70 次、或者使用者下載 7000 個檔案、或從阿富汗登入，您可以設定在這些事件發生時，傳送活動警示給您自己或使用者。 您甚至可以暫停使用者，直到您有時間進行調查。  
  
若要建立新的活動原則，請遵循此程序︰  
  
1.  在主控台中，依序按一下 [控制] 和 [原則]。  
  
2.  按一下 [建立原則]，然後選取 [活動原則]。  
  
     ![活動原則功能表](./media/activity-policy-menu.png "活動原則功能表")  
  
3.  為您的原則命名並描述，如果希望，也可以範本為依據；如需原則範本的詳細資訊，請參閱 [Control cloud apps with policies](control-cloud-apps-with-policies.md) (使用原則控制雲端應用程式)。  
  
4.  若要設定觸發此原則的動作或其他計量，請使用 [活動篩選]。  
  
5.  在 [活動比對參數] 下，選取是單一活動符合篩選條件時觸發原則違規，還是偵測到指定數目的 [重複的活動] 時才偵測到違規。  
    若您選擇 [重複的活動]，可以設定 [每一應用程式的群組相符活動]。 僅當重複的活動發生在同一應用程式 (例如從 Box 下載 5 次) 時，才會觸發原則比對。  
  
6.  設定找到相符項目時應該採取的 [動作]。  
  
看看這些範例︰  
  
-   多次失敗的登入  
  
     您可以設定原則，以便在特定、相對短的時段內有大量的登入嘗試失敗時，收到警示。 若要設定類似的原則，請在 [新增活動原則] 頁面中選擇適當的活動篩選。  
  
     在 [活動篩選] 欄位下方，設定觸發警示的參數。  
  
     ![多個失敗登入嘗試原則範例](./media/multiple-failed-log-on-attempts-policy-example.png "多個失敗登入嘗試原則範例")  
  
-   高下載率  
  
     您可以設定原則，以便在非預期或無法定性層級的下載活動出現時，收到警示。 若要設定類似的原則，請在 [速率] 參數下，選擇觸發警示的參數。  
  
     ![高下載率範例](./media/high-download-rate-example.png "高下載率範例")  
  
  
## <a name="activity-policy-reference"></a>活動原則參考  
本節提供原則的參考詳細資訊，並說明每種原則類型和您可以針對每項原則設定的欄位。  
  
[活動原則] 是一種 API 型原則，可讓您將 20 多個檔案中繼資料篩選 (包括裝置類型和位置) 納入考量，藉此監視雲端中的組織活動。 系統會根據原則結果產生通知，並可能讓使用者暫停使用雲端應用程式。   
每個原則皆由下列部分組成：  
  
-   活動篩選 – 可讓您根據中繼資料建立非常細微的條件。  
  
-   活動比對參數 – 可讓您設定活動要重複幾次才會被視為符合原則的臨界值。  指定將活動視為符合原則前的必要重複次數；例如，您可設定原則，以在使用者於 2 分鐘的時間範圍內執行 10 次失敗登入時提出警示。  「Activity match parameters」(活動比對參數) 預設會在單一活動符合所有活動篩選時引發相符事件。   
您可使用 [重複的活動] 來設定重複的活動數量、計算活動數量的時間範圍，甚至可以指定相同的使用者和相同雲端應用程式內應該執行的所有活動。  
  
  
-   動作 – 此原則提供一組可在偵測到違規時自動套用的治理動作。  
## <a name="see-also"></a>另請參閱  
[資料保護原則](data-protection-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  