---
title: "建立 Cloud Discovery 快照集報告 | Microsoft Docs"
description: "本文提供的資訊說明如何手動上傳記錄檔，以建立 Cloud Discovery 應用程式的快照集報告。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 851617bc68618b177600523a4d4432b3e557f394
ms.openlocfilehash: abd134c9ff3b000170bce474e8ecebb71b762b98


---

# <a name="create-snapshot-cloud-discovery-reports"></a>建立 Cloud Discovery 快照集報告
請務必手動上傳記錄檔，讓 Cloud App Security 剖析過後再嘗試使用自動記錄收集器。

若要建立快照集報告：
  
1.  收集來自防火牆和 Proxy 的記錄檔，貴組織的使用者是透過它們存取網際網路。 請務必收集尖峰流量時段的記錄檔，這代表貴組織中所有的使用者活動。  
  
2.  在 Cloud App Security 入口網站中，依序按一下 [探索] 和 [建立新的快照集報告]。  
  
     ![建立新的快照集報告](./media/create-new-snapshot-report.png)
     
      
3.  輸入**報告名稱**和**描述**。
  
4.  選取您要上傳記錄檔的 [資料來源]。  
  
5.  選擇您想要上傳的**流量記錄檔**。 一次最多可以上傳 20 個檔案。 亦支援壓縮檔及 ZIP 壓縮檔案。  
  
6.  按一下 [建立]。  
  
     ![新的快照集報告](./media/new-snapshot-report.png) 
  
7.  上傳完成之後，狀態訊息會出現在畫面的右上角，告訴您已成功上傳記錄檔。  
  
8.  上傳記錄檔之後，需要一些時間進行剖析和分析。  
記錄檔處理完成之後，您會收到一封已完成處理的通知電子郵件。 
  
9. 入口網站上方的狀態列會顯示通知橫幅，以更新記錄檔的處理狀態。  
![處理記錄檔的功能表列](./media/processing-log-file-menu-bar.png) 
   
10. 在記錄上傳成功之後，您應該會看到通知，告訴您已成功完成記錄檔的處理。 此時，若要檢視報告，您可以按一下狀態列中的連結，或移至 [設定] 齒輪，然後選取 **「Cloud Discovery settings」** (Cloud Discovery 設定)。   
  
     ![探索設定索引標籤](./media/discovery-settings-tab.png)
11. 接下來，依序選取 [管理快照集報告] 和您的快照集報告。
 
![快照集報告的管理](./media/snapshot-report-managment.png)

  
      
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
    
      
  


<!--HONumber=Nov16_HO5-->


