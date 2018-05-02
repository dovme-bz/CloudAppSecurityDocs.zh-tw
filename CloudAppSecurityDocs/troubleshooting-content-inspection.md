---
title: 在 Cloud App Security 中為內容檢查錯誤進行疑難排解 | Microsoft Docs
description: 本主題提供內容檢查狀態及其意義的清單。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 359eb77f-e719-4c50-9b62-6ef64149a5a5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 58a3a202c7c31ec3fa063a5067821a657d47d836
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


# <a name="troubleshooting-content-inspection"></a>為內容檢查進行疑難排解

|內容檢查狀態|說明|
|----|----|
|Completed|已順利完成內容檢查。|
|不適用|內容檢查不適用此檔案。 這可能是因為沒有原則要求此檔案必須進行內容檢查，或是因為檔案類型不受支援。|
|Pending|檔案目前正在內容檢查佇列中。|
|失敗：下載錯誤|Microsoft Cloud App Security 無法下載要進行檢查的檔案。|
|失敗：檔案已加密|無法解密檔案。|
|失敗：檔案已損毀|檔案因故損毀且無法檢查。|
|失敗：內部錯誤|嘗試檢查檔案時發生無法判定的錯誤。|
|失敗：外部 DLP 錯誤|您的外部 DLP 發生錯誤，導致 Cloud App Security 無法檢查內容。|
|失敗：檔案過大|檔案限制會依據檔案大小和字元數目而異。|
|失敗：拒絕存取檔案|檔案位於您的雲端外部，因此 Cloud App Security 無法存取。|
|失敗：檔案已刪除|檔案不再存在於您的雲端，因此無法檢查。|
|失敗：不支援的檔案類型|Cloud App Security 無法針對此檔案類型執行內容檢查。 這可能是因為檔案類型不受支援，或檔案格式實際上並不是預期的檔案類型。|

> [!NOTE]
> 如果您在掃描狀態中看到虛線，表示該檔案未排入佇列掃描。 如需設定內容檢查原則的資訊，請參閱[檔案原則](data-protection-policies.md)。

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  

