---
title: 在 Cloud App Security 中使用探索到的應用程式 | Microsoft Docs
description: 本主題描述用來識別及修復 Cloud App Security 中具風險之 Cloud Discovery 應用程式的程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 645fd8c7-06d0-4f93-a85c-2976e7b3766d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 18601bab78ac48637e4060c189846594ba340c65
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143542"
---
*適用於：Microsoft Cloud App Security*


# <a name="working-with-discovered-apps"></a>使用探索到的應用程式

## <a name="review-the-cloud-discovery-dashboard"></a>檢閱 Cloud Discovery 儀表板

Cloud Discovery 儀表板的設計目的是讓您深入了解如何在組織中使用雲端應用程式。 它概述正在使用的應用程式種類、未解決的警示以及組織中應用程式的風險層級。 它也會示範誰是最上層應用程式使用者，並提供 App Headquarter 位置圖。 「Cloud Discovery 儀表板」具有許多用於篩選資料的選項，可讓您根據最感興趣的項目來產生特定檢視，並且提供容易了解的圖形，讓您一目瞭然。

![Cloud Discovery 儀表板](./media/cloud-discovery-dashboard.png)

了解 Cloud Discovery 應用程式時應該執行的第一件事是查看 Cloud Discovery 儀表板，以及檢閱下列項目︰
 
1. 第一次查看**高階使用概觀**中組織的整體雲端應用程式使用。

2. 接著，深入探討以查看組織中每個不同使用參數正在使用的**前幾個類別**，以及批准應用程式的這項使用情況。

3. 進一步探討並查看 [探索到的應用程式] 小工具中特定類別的所有應用程式。

4. 您可以查看**前幾個使用者和來源 IP 位址**，以識別哪些使用者是組織中雲端應用程式的最主要使用者。
5. 根據 **App Headquarters 地圖**中的地理位置 (根據應用程式總部)，查看探索到的應用程式如何分佈。

6. 最後，請不要忘記檢閱**應用程式風險概觀**中探索到應用程式的風險分數，以及檢查**探索警示狀態**來查看您應該調查未解決警示的數目。

## <a name="deep-dive-into-discovered-apps"></a>深入探討探索到的應用程式
如果您想要深入探討 Cloud Discovery 所提供的資料，請使用篩選來檢閱具風險且常用的應用程式。


例如，如果您想要識別常用且具風險的雲端儲存體和共同作業應用程式，您可以使用 [探索到的應用程式] 頁面來篩選所需的應用程式。 之後，您可以[不批准或封鎖](governance-discovery.md)這些應用程式，如下所示：

在 [探索到的應用程式] 頁面的 [依類別瀏覽] 下，同時選取 [雲端儲存體] 和 [共同作業]。 然後使用進階篩選，並將 [合規性風險因素] 設定為 [SOC 2] 等於 [False]、[使用量] > [使用者] 大於 50 位使用者、[使用量]  >  [交易] 大於 100、[安全性風險因素]  >  [待用資料加密] 等於 [False]，然後將 [風險分數] 設定為小於等於 6。

![探索到的應用程式篩選](./media/discovered-app-filters.png)

篩選結果之後，您可以[不批准並封鎖](governance-discovery.md)這些應用程式，方法是使用 [大量動作] 核取方塊以一個動作不批准所有應用程式。 當應用程式處於待批准狀態之後，您可以使用封鎖指令碼以防止在環境中使用這些應用程式。


## <a name="exclude-entities"></a>排除實體  
如有雜訊特別多且無關的系統使用者或 IP 位址或不相干的應用程式，您可能想要從已經分析的 Cloud Discovery 資料中排除它們的資料。 例如，您可能想要排除源自 127.0.0.1 或本機主機的所有資訊。  
  
建立一個排除項目︰  
  
1.  在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2.  按一下 [排除實體] 索引標籤。  
  
3.  選擇 [已排除的使用者] 或 [已排除的 IP 位址] 索引標籤，然後按一下按鈕以 [新增使用者] 或 [新增 IP 位址]。  
  
4.  新增使用者別名或 IP 位址。 我們建議您加入為何排除使用者或 IP 位址的相關資訊。  
  
     ![排除使用者](./media/exclude-user.png "排除使用者")  
  
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
  
6.  設定要對資料執行的篩選，可以是 [組織單位]、[IP 位址標記] 或 [IP 位址範圍]。 如需使用 IP 位址標記和 IP 位址範圍的詳細資訊，請參閱[根據需求組織資料](ip-tags.md)。  
  
    ![建立自訂連續報告](./media/create-custom-continuous-report.png) 

> [!NOTE]
> 所有的自訂報告都有 1 GB 未壓縮資料的上限。 如果資料量超過 1 GB，則前 1 GB 的資料將會輸出至報告。


## <a name="deleting-cloud-discovery-data"></a>刪除 Cloud Discovery 資料  
有數個原因讓您想要刪除 Cloud Discovery 資料。 我們建議您有下列情況時刪除︰  
  
-   如果您手動上傳記錄檔，而且長時間才以新記錄檔更新系統，卻不希望舊資料影響結果。  
  
-   當您設定新的自訂資料檢視時，它只會從該時點開始套用新的資料，因此您可能想要清除舊資料，然後再上傳一次記錄檔，以便自訂資料檢視來取得記錄檔資料中的事件。  
  
-   如果多個使用者或 IP 位址在離線一段時間後，最近又開始活動，他們的活動會被識別為異常，而您可能會收到許多誤判違規。  
  
刪除 Cloud Discovery 資料︰  
  
1. 在入口網站的設定圖示下，選取 [Cloud Discovery 設定]。  
  
2. 按一下 [刪除資料] 索引標籤。  
  
    請務必確認您要刪除資料再繼續 - 此動作無法復原，且會刪除系統中的**所有** Cloud Discovery 資料。  
  
3. 按一下 [刪除] 按鈕。  
  
    ![刪除資料](./media/delete-data.png "刪除資料")  
  
   > [!NOTE]  
   >  刪除程序需要幾分鐘，不會立即完成。  




## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

