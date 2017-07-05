---
title: "使用自訂記錄檔剖析器處理不支援的記錄檔 | Microsoft Docs"
description: "本文提供如何使用自訂的記錄檔剖析器，將不支援的裝置記錄檔上傳至 Cloud App Security 的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a612d87e-5471-4add-b4b1-dbbb530f2b61
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 73da4104de24a7b2e6814f04b227140b0b57235f
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2017
---
# <a name="use-a-custom-log-parser"></a>使用自訂記錄檔剖析器
Cloud App Security 可讓您設定自訂剖析器以符合記錄檔的格式並進行處理，如此一來即使記錄檔來自 Cloud App Security 並未明確支援的防火牆或裝置，Cloud Discovery 也可以使用記錄檔。 

自訂剖析器可讓您使用來自不支援之防火牆的記錄檔，方法是依照此程序。 


 
設定自訂 CSV 剖析器：
1.  在 Cloud App Security 入口網站中，依序按一下 [探索] 和 [建立新的快照集報告]。  
  
    ![建立新的快照集報告](./media/create-new-snapshot-report.png)
     
3.  輸入**報告名稱**和**描述**。
  
4.  在 [資料來源] 底下，選取 [自訂記錄格式]。  

     ![新的快照集報告](./media/custom-log-upload.png)   

5. 收集來自防火牆和 Proxy 的記錄檔，組織的使用者是透過它們來存取網際網路。 請務必收集尖峰流量時段的記錄檔，這代表組織中所有的使用者活動。 

6. 在文字編輯器中開啟您要處理的記錄檔，然後檢閱其格式，確定記錄檔中的資料行名稱對應至 [自訂記錄格式] 畫面中的欄位。

  ![自訂記錄檔剖析器](./media/log-data.png) 

7. 然後，根據您的資料填入欄位，以描述資料中哪些資料行與 Cloud App Security 中的特定欄位相關聯。 您可能要修改記錄檔中的資料行名稱才能正確地相互關聯。
  
   > [!NOTE]
    > 欄位會區分大小寫。 請確定您在 Cloud App Security 與記錄檔中的資料行名稱拼字和輸入相同。 此外，請確定您選擇的日期格式相同。

   ![自訂記錄檔剖析器](./media/custom-log-parser.png) 


7. 按一下 **[儲存]**。 您設定的自訂記錄格式將會儲存為預設的自訂剖析器。 您隨時可以在 [編輯] 上按一下來編輯它。

5. 在 [選擇流量記錄檔] 底下，選取您已修改的記錄檔並上傳。 一次最多可以上傳 20 個檔案。 亦支援壓縮檔及 ZIP 壓縮檔案。  
  

6.  按一下 [建立]。  

7.  上傳完成之後，狀態訊息會出現在畫面的右上角，告訴您已成功上傳記錄檔。  
  
8.  上傳記錄檔之後，需要一些時間進行剖析和分析。  
記錄檔處理完成之後，您會收到一封已完成處理的通知電子郵件。 
  
9. 入口網站上方的狀態列會顯示通知橫幅，以更新記錄檔的處理狀態。  
![處理記錄檔的功能表列](./media/processing-log-file-menu-bar.png) 
   
10. 在記錄上傳成功之後，您應該會看到通知，告訴您已成功完成記錄檔的處理。 此時，若要檢視報告，您可以按一下狀態列中的連結，或移至 [設定] 齒輪，然後選取 **「Cloud Discovery settings」** (Cloud Discovery 設定)。   
  
     ![探索設定索引標籤](./media/discovery-settings-tab.png)
11. 接下來，依序選取 [管理快照集報告] 和您的快照集報告。
 
    ![快照報告管理](./media/snapshot-report-managment.png)

  
      




## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

