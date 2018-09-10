---
title: 建立 Cloud Discovery 雲端應用程式使用情況的快照集報告 | Microsoft Docs
description: 本文提供的資訊說明如何手動上傳記錄檔，以建立 Cloud Discovery 應用程式的快照集報告。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 734975276a148ce541b84c4a68751b2bdb5666fb
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143644"
---
*適用於：Microsoft Cloud App Security*


# <a name="create-snapshot-cloud-discovery-reports"></a>建立 Cloud Discovery 快照集報告
請務必手動上傳記錄檔，讓 Microsoft Cloud App Security 剖析過後再嘗試使用自動記錄收集器。
如果還沒有記錄檔，而您想要查看記錄檔應有的外觀範例，請依照下列程序，下載範例記錄檔查看記錄檔應有的外觀。


若要建立快照集報告：
  
1. 收集來自防火牆和 Proxy 的記錄檔，貴組織的使用者是透過它們存取網際網路。 請務必收集尖峰流量時段的記錄檔，這代表貴組織中所有的使用者活動。  
  
2. 在 Cloud App Security 入口網站中，依序按一下 [探索] 和 [建立新的快照集報告]。  
  
   ![建立新的快照集報告](./media/create-new-snapshot-report.png)
     
3. 輸入**報告名稱**和**描述**。
  
    ![新的快照集報告](./media/new-snapshot-report.png) 

4. 選取您要上傳記錄檔的 [資料來源]。  
  
5. 請驗證記錄檔格式，確定它已根據您可以下載的範例正確格式化。 按一下 [檢視並驗證]，再按一下 「Download sample log」 (下載範例記錄檔)。 然後比較您的記錄檔與範例提供的內容，確認二者相容。 

   ![驗證記錄檔格式](./media/cloud-discovery-snapshot-verify.png)  

   > [!NOTE]
   > 快照集和自動上傳支援 FTP 範例格式，但只有自動上傳支援 Syslog。<br></br>
   下載範例記錄檔將會下載範例 FTP 記錄檔。


6. 選擇您想要上傳的**流量記錄檔**。 一次最多可以上傳 20 個檔案。 亦支援壓縮檔及 ZIP 壓縮檔案。  
  
7. 按一下 [建立]。  

8. 上傳完成之後，狀態訊息會出現在畫面的右上角，告訴您已成功上傳記錄檔。  
  
9. 上傳記錄檔之後，需要一些時間進行剖析和分析。  
   記錄檔處理完成之後，您會收到一封已完成處理的通知電子郵件。 
  
10. 入口網站上方的狀態列會顯示通知橫幅，以更新記錄檔的處理狀態。  
    ![處理記錄檔的功能表列](./media/processing-log-file-menu-bar.png) 
   
11. 在記錄上傳成功之後，您應該會看到通知，告訴您已成功完成記錄檔的處理。 此時，若要檢視報告，您可以按一下狀態列中的連結，或移至 [設定] 齒輪，然後選取 **「Cloud Discovery settings」** (Cloud Discovery 設定)。   
  
     ![探索設定索引標籤](./media/discovery-settings-tab.png)
12. 接下來，選取 [快照集報告]，並選取您的快照集報告。
 
![快照報告管理](./media/snapshot-report-managment.png)

  
      
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
    
      
  