---
title: "可保護雲端環境的日常活動 | Microsoft Docs"
description: "本文提供您必須在 Cloud App Security 中定期執行的作業基礎資訊，以監視組織中使用的雲端應用程式。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a835fa24-15c5-4bbb-a25a-688444040f1f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9565d8a51e4c06963861d9dfaef9595944bda1ff
ms.openlocfilehash: f4cf027220a7f4329a72d662f6ccf4d9ab02ede4


---

# <a name="daily-activities-to-protect-your-cloud-environment"></a>可保護雲端環境的日常活動
啟動並執行 Cloud App Security 後，您將需設定資料流、批准您想要讓人員使用的應用程式，以及設定原則監視雲端環境。 接著就可以使用 Cloud App Security 來控制及保護您的雲端並管理風險。  

本主題說明您每日應該搭配 Cloud App Security 執行的工作。  

## <a name="check-the-dashboard"></a>檢查儀表板  
Cloud App Security 儀表板提供您活動及功能的概觀，包括︰

- 開啟警示。
- 活動違規。
- 內容違規。
- 繪製使用者活動來源的活動圖。
- 您雲端環境中的已連接應用程式使用方式趨勢。  

建議您每日檢查儀表板，查看被觸發的新警示。 這也是監督雲端環境健全狀況並了解整個雲端環境的好位置。  

![Cloud App Security 儀表板](./media/dashboard.png "dashboard")  

## <a name="handle-your-alerts"></a>處理警示  
警示是更深入了解雲端環境的切入點。 建議您根據您的發現建立新原則。 例如，您可能會看到系統管理員從格陵蘭登入，而您組織中從未有人曾從格陵蘭登入。 您可以建立一項原則，在系統管理員帳戶用來從該位置登入時，自動加以暫時停權。  

建議您檢閱所有的警示，並將其作為修改原則的工具。 如果無害事件視為對現有原則的違規，則請精簡原則，以降低收到不必要警示的機率。  

1.   按一下 [Open alerts (未解決的警示)] 下的 [檢視所有警示]。  

     儀表板的本區段提供完整的可見度，讓您掌握任何可疑的活動或違反您所建立原則的情形， 並可協助保護您為雲端環境所定義的安全性狀態。  

     ![警示](./media/alerts.png "alerts")  

2.   您必須調查每個警示，並判斷違規的性質和所需之回應。  

     您可依據 [警示類型] 或 [嚴重性] 來篩選警示，以便優先處理最重要的警示。  

     選取特定警示。 視警示類型而定，您可在解決警示前查看各種可採取的動作。  

     有三種類型的違規，您必須在調查警示時處理︰  

    #### <a name="serious-violations"></a>嚴重違規
     嚴重違規需要立即回應。

         Examples:  

         For a suspicious activity alert, you might want to suspend the account until the user changes their password.  

         For a data leak you might want to restrict permissions or quarantine the file.  

         If a new app is discovered, you might want to block access to the service on your proxy or firewall.  

    #### <a name="questionable-violations"></a>可疑的違規
    可疑違規需要進一步調查。  

         You can contact the  user or the user's manager about the nature of the activity.  

         Leave the activity open until you have more information.  

 #### <a name="authorized-violations-or-anomalous-behavior"></a>授權的違規或異常行為
 授權違規或異常行為可能源於合法使用。  

         Dismiss the alert.  

3.   當您完成此程序時，請將警示標示為已解決。  

下表提供會觸發的警示類型清單，及建議的解決方法。  

|警示類型|描述|建議的解決方法|  
|----------------|-----------------|----------------------------|  
|活動原則違規|這類警示是您建立的原則結果。|若要大量使用這類警示，建議您在原則中心內使用以減少警示。<br /><br /> 新增更多篩選及更細微的控制來微調原則，以排除雜訊太多的實體。<br /><br /> 如果原則精確且應該有警示，而它又是您想要立即停止的違規，請考慮在原則中新增自動補救。|  
|檔案原則違規|這類警示是您建立的原則結果。| 若要大量使用這類警示，建議您在原則中心內使用以減少警示。<br /><br /> 新增更多篩選及更細微的控制來微調原則，以排除雜訊太多的實體。<br /><br /> 如果原則精確且應該有警示，而它又是您想要立即停止的違規，請考慮在原則中新增自動補救。|  
|遭盜用的帳戶|當 Cloud App Security 識別到帳戶遭盜用 (意即帳戶有極高的可能遭到未經授權的使用) 時，即會觸發這類警示。|建議您將帳戶暫時停權，直到您能連絡到使用者，並確認他們變更密碼。|  
|非使用中帳戶|若您其中一個連接的雲端應用程式中有連續 60 天未使用的帳戶，即會觸發此警示。|請連絡使用者及使用者的管理員，以判斷帳戶是否仍在使用中。 如果不是，請暫停使用者並終止應用程式授權。|  
|新增管理使用者|當特殊權限帳戶出現連接的應用程式異動時，即會觸發此警示。|確認使用者實際上需要新的系統管理員權限。 如果不需要，建議您撤銷系統管理員權限以降低風險。|  
|新增管理員位置|當特殊權限帳戶出現連接的應用程式異動時，即會觸發此警示。|確認從這個異常位置登入合法。 如果不是，建議您撤銷系統管理員權限或將帳戶暫時停權以降低風險。|  
|新增位置|此類警示是通知您從新的位置存取連接的應用程式，每個國家 (地區) 只觸發一次。|調查特定使用者的活動。|  
|新探索到的服務|這是影子 IT 的相關警示--Cloud Discovery 偵測到新的應用程式。|<ul><li>根據應用程式目錄評估服務風險。</li><li>向下切入至活動以了解使用模式和普遍性。</li><li>決定是否要批准該應用程式。</li><br /></ul>針對未經批准的應用程式︰<br /><br /><ul><li>您可能想要在 Proxy 或防火牆中封鎖使用。</li><li>如果您在相同類別中有未經批准及批准的應用程式，您可以匯出未經批准的應用程式使用者清單，連絡他們遷移到批准的應用程式。</li></ul></li>|  
|可疑的活動|此警示可讓您知道已偵測到異常活動，它不符合預期的活動或貴組織的使用者。|調查行為並向使用者確認。<br /><br /> 這類警示是開始深入了解環境及使用這些警示來建立新原則的最佳位置。 例如，如果有人突然上傳大量的資料到您某個連接的應用程式，您可以設定規則來控制該類型的異常行為。|  
|可疑的雲端使用|此警示可讓您知道已偵測到異常活動，它不符合預期的活動或貴組織的使用者。|調查行為並向使用者確認。<br /><br /> 這類警示是開始深入了解環境及使用這些警示來建立新原則的最佳位置。 例如，如果有人突然上傳大量的資料到您某個連接的應用程式，您可以設定規則來控制該類型的異常行為。|  
|使用個人帳戶|此警示可讓您知道新的個人帳戶可以存取已連線應用程式的資源。|請在外部帳戶中，移除使用者的共同作業。|  

## <a name="use-policies-to-assess-risk"></a>使用原則評估風險  
查看未解決的警示後，請移至原則中心檢閱未觸發警示的原則違規。  

-   在 Cloud App Security 儀表板中，依序按一下 **[控制]** 及 **[原則]**。  

-   選取特定的原則，查看符合原則但未觸發警示的 **[立即違規]** 清單。  

-   按一下違規，一次一個，判斷該如何處理每個違規。 如需管理動作的詳細資訊，請參閱以下圖表。  

     如果原則設定為尋找相容性缺口，而有人將信用卡號碼儲存在 OneDrive 的檔案中，原則中就會有相符項目。  

     ![PCI 相符項目](./media/pci-matches.png "pci matches")  

-   選取相符項目，查看違反原則的實際檔案。  

     ![PCI 內容相符項](./media/pci-content-matches.png "pci content matches")  

     您可以選取檔案本身以取得檔案的相關資訊。  

     您可以按一下 **[共同作業者]**，查看可以存取這個檔案的人員。  

     您可以按一下 **[相符項目]**，查看實際的信用卡號碼。  

     ![內容相符項 ccn](./media/content-matches-ccn.png "content matches ccn")  

## <a name="next-steps"></a>接下來的步驟  
如需如何調查警示的詳細資訊，請參閱[調查](investigate.md)。  
如需技術支援，請前往 [Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。  



<!--HONumber=Nov16_HO5-->


