---
title: "使用風險分數 | Microsoft Docs"
description: "本主題提供如何使用和自訂 Cloud App Security 應用程式風險分數的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/26/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9cb3594e-5007-48be-9b4f-e1d23355d86e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d617631819744211df5e6bee1f48df36dcedb7ce
ms.sourcegitcommit: cda4a69f9ad9c6eb66fbdb98610f54d79585b84b
translationtype: HT
---
# <a name="working-with-the-risk-score"></a>使用風險分數  
Cloud Discovery 提供供整個環境使用之雲端應用程式可信度及可靠性的重要資料。 在入口網站中，每個探索到的應用程式都會顯示總分數，代表此特定應用程式的企業運用成熟度的 Cloud App Security 評估。 任何指定應用程式的總分數，都是評估可靠性時，Cloud App Security 考慮的三個子類別之三項子分數的加權平均︰  
  
-   **一般** - 此類別是指有關公司生產應用程式的基本事項，包括其網域、創建年份和熱門程度。 這些欄位意在展現公司最基本層面的穩定性。  
  
-   **安全性** - 安全性類別會考量探索到的應用程式所用之資料實體安全性的所有處理標準。 這包括多重要素驗證、加密、資料分類和資料所有權等欄位。  
  
-   **相容性** - 此類別可顯示生產應用程式的公司支持哪些常見的法規標準最佳做法。 規格清單包含 HIPAA、CSA 和 PCI-DSS 等標準。  
  
每個類別都包含許多特定的屬性。 根據我們的評分法，每個屬性會獲得 0 到 10 的初始分數，視值而定。 True/False 值分別會得到 10 或 0，而連續的屬性，例如網域使用期限，會得到範圍內的特定值。 每個屬性的分數會根據類別中所有其他現有欄位加權，以建立類別的子分數。 如果您遇到未計分的應用程式，通常表示應用程式的內容為未知，因此不予計分。  
  
請務必花點時間檢閱並修改 Cloud Discovery 分數設定的預設權重。 評估的各種參數預設都有相同的權重。 如有特定參數對貴組織而言需增加或減少其重要性，請務必如下所示變更其權重︰  
  
1.  在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2.  滑動 [設定分數計量] 下的 [重要性]，將欄位權重變更為 [已略過]、[低]、[中]、[高] 或 [非常高]。  
  
3.  此外，您可以在分數計算中設定特定值為無法使用或不適用。 包含時，N/A 值對計算的分數有負比重。  
  
     ![分數](./media/score.png "分數")  
  
## <a name="manage-continuous-reports"></a>管理連續報告  
監視組織的 Cloud Discovery 記錄資料時，自訂連續報告提供更細微的資訊。 透過建立自訂報告，即可能篩選特定地理位置、網路和網站或組織單位。 Cloud Discovery 報告選擇器預設只會顯示下列報告︰  
  
-  **全域報告**將記錄檔所含全部資料來源的所有資訊合併在入口網站中。  
  
- **資料來源特定報告**只顯示特定資料來源的資訊。  
  
建立新的連續報告：  
  
1.  在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2.  按一下 **「Manage continuous report」** (管理連續報告) 索引標籤。  
  
3.  按一下 [建立報告] 按鈕。  
  
4.  輸入報告名稱。  
  
5.  選取您要包含的資料來源 (全部或特定)。  
  
6.  設定要對資料執行的篩選，可以是 [組織單位]、[IP 位址標記] 或 [IP 位址範圍]。 如需使用 IP 位址標記和 IP 位址範圍的詳細資訊，請參閱[根據需求組織資料](general-setup.md#IPtagsandRanges)。  
  
    ![建立自訂連續報告](./media/create-custom-continuous-report.png) 
  
## <a name="exclude-entities"></a>排除實體  
如有雜訊特別多且無關的系統使用者或 IP 位址或不相干的應用程式，您可能想要從已經分析的 Cloud Discovery 資料中排除它們的資料。 例如，您可能想要排除源自 127.0.0.1 或本機主機的所有資訊。  
  
建立一個排除項目︰  
  
1.  在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2.  按一下 [排除實體] 索引標籤。  
  
3.  選擇 [已排除的使用者] 或 [已排除的 IP 位址] 索引標籤，然後按一下按鈕以 [新增使用者] 或 [新增 IP 位址]。  
  
4.  新增使用者別名或 IP 位址。 我們建議您加入為何排除使用者或 IP 位址的相關資訊。  
  
     ![排除使用者](./media/exclude-user.png "排除使用者")  
  
## <a name="deleting-cloud-discovery-data"></a>刪除 Cloud Discovery 資料  
有數個原因讓您想要刪除 Cloud Discovery 資料。 我們建議您有下列情況時刪除︰  
  
-   如果您手動上傳記錄檔，而且長時間才以新記錄檔更新系統，卻不希望舊資料影響結果。  
  
-   當您設定新的自訂資料檢視時，它只會從該時點開始套用新的資料，因此您可能想要清除舊資料，然後再上傳一次記錄檔，以便自訂資料檢視來取得記錄檔資料中的事件。  
  
-   如果多個使用者或 IP 位址在離線一段時間後，最近又開始活動，他們的活動會被識別為異常，而您可能會收到許多誤判違規。  
  
刪除 Cloud Discovery 資料︰  
  
1.  在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2.  按一下 [刪除資料] 索引標籤。  
  
     請務必確認您要刪除資料再繼續 - 此動作無法復原，且會刪除系統中的**所有** Cloud Discovery 資料。  
  
3.  按一下 [刪除] 按鈕。  
  
     ![刪除資料](./media/delete-data.png "刪除資料")  
  
    > [!NOTE]  
    >  刪除程序需要幾分鐘，不會立即完成。  



 
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  