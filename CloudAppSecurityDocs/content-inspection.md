---
title: "內容檢查 | Microsoft Docs"
description: "本文說明在針對雲端中的資料執行 DLP 內容檢查時，Cloud App Security 所遵循的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: ea1854d6bf32e01afe6183409b68ded32ee37dd1


---

# <a name="content-inspection"></a>內容檢查
本文說明在針對雲端中的資料執行 DLP 內容檢查時，Cloud App Security 所遵循的程序。 


Cloud App Security 內容檢查功能的運作方式如下︰
1. Cloud App Security 會在所有磁碟機中執行所有相關檔案的連續掃描。 
2. Cloud App Security 可執行磁碟機以及偵測為新事件或已變更事件的近即時 (NRT) 掃描。 

系統會將連續掃描中的檔案與 NRT 掃描中的檔案新增至檢查佇列。 掃描佇列中的檔案順序會依據檔案和磁碟機掃描上的每個活動來進行設定。 只有當檔案中繼資料顯示它是受支援的 MIME 類型，才會掃描檔案。 這是因為這項掃描適用於資料掃描相關的檔案 (文件、影像、簡報、試算表、文字檔和 zip/封存檔)。  

已掃描檔案之後，會執行下列動作：

1. Cloud App Security 會套用所有與中繼資料相關的自訂原則，而非與內容本身的相關原則。 比方說，某項原則會在發現檔案超過 20 MB 時警示您，而某項原則會在將 docx 檔案儲存至 OneDrive 時發出警示。 

2. 如果某項原則要求進行內容檢查，且檔案符合內容檢查的資格，即會將該內容排入檢查佇列。 佇列長度取決於租用戶的大小和需要掃描的檔案數目而定。 

3. 此時，您可以前往 [調查] > [檔案]，然後按一下檔案，以檢視內容檢查的狀態。 開啟檔案選單即會顯示檔案詳細資料，其中的 [Content Inspection status] (內容檢查狀態) 會顯示下列其中一項資訊︰ 

|內容檢查狀態|描述|
|----|----|
|Completed|已順利完成內容檢查。|
|不適用|內容檢查不適用此檔案。 這可能是因為沒有原則要求此檔案必須進行內容檢查，或是因為檔案類型不受支援。|
|Pending|檔案目前正在內容檢查佇列中。|
|失敗：下載錯誤|Cloud App Security 無法下載要進行檢查的檔案。|
|失敗：檔案已加密|無法解密檔案。|
|失敗：檔案已損毀|檔案因故損毀且無法檢查。|
|失敗：內部錯誤|嘗試檢查檔案時發生無法判定的錯誤。|
|失敗：外部 DLP 錯誤|您的外部 DLP 發生錯誤，導致 Cloud App Security 無法檢查內容。|
|失敗：檔案過大|檔案限制會依據檔案大小和字元數目而異。|
|失敗：拒絕存取檔案|檔案位於您的雲端外部，因此 Cloud App Security 無法存取。|
|失敗：檔案已刪除|檔案不再存在於您的雲端，因此無法檢查。|
|失敗：不支援的檔案類型|Cloud App Security 無法針對此檔案類型執行內容檢查。 這可能是因為檔案類型不受支援，或檔案格式實際上並不是預期的檔案類型。|

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  


<!--HONumber=Oct16_HO4-->


