---
title: "Cloud App Security 如何執行內容檢查 | Microsoft Docs"
description: "本文說明在針對雲端中的資料執行 DLP 內容檢查時，Cloud App Security 所遵循的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 755db0fc6e61b974daec549a8ffbdfcf119ceaae
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="content-inspection"></a>內容檢查
本文說明在針對雲端中的資料執行 DLP 內容檢查時，Cloud App Security 所遵循的程序。 


Cloud App Security 內容檢查功能的運作方式如下︰
1. 首先，Cloud App Security 對磁碟機及偵測為新的或已變更的事件執行近即時 (NRT) 掃描。
2. 這項作業完成之後，Cloud App Security 會在所有磁碟機中執行所有相關檔案的連續掃描。  

系統會將連續掃描中的檔案與 NRT 掃描中的檔案新增至檢查佇列。 掃描佇列中的檔案順序會依據檔案和磁碟機掃描上的每個活動來進行設定。 只有當檔案中繼資料顯示它是受支援的 MIME 類型，才會掃描檔案。 這是因為這項掃描適用於資料掃描相關的檔案 (文件、影像、簡報、試算表、文字檔和 zip/封存檔)。  

已掃描檔案之後，會執行下列動作：

1. Cloud App Security 會套用所有與中繼資料相關的自訂原則，而非與內容本身的相關原則。 比方說，某項原則會在發現檔案超過 20 MB 時警示您，而某項原則會在將 docx 檔案儲存至 OneDrive 時發出警示。 

2. 如果某項原則要求進行內容檢查，且檔案符合內容檢查的資格，即會將該內容排入檢查佇列。 佇列長度取決於租用戶的大小和需要掃描的檔案數目而定。 

3. 此時，您可以前往 [調查] > [檔案]，然後按一下檔案，以檢視內容檢查的狀態。 在檔案抽屜中開啟檔案的詳細資料，**內容檢查狀態**會顯示**已完成**、**擱置**、**不適用** \(若為不支援的檔案類型) 或失敗訊息。 如需內容掃描失敗訊息的資訊，請參閱[為內容檢查進行疑難排解](troubleshooting-content-inspection.md)。

> [!NOTE]
> 如果您在掃描狀態中看到虛線，表示該檔案未排入佇列掃描。 如需設定內容檢查原則的資訊，請參閱[檔案原則](data-protection-policies.md)。

內建的內容檢查掃描原則可以搜尋下列項目：

- 電子郵件地址 
- 信用卡號碼 
  - 所有的信用卡公司 (Visa、MasterCard、美國運通、大來卡、發現卡、JCB、Dankort、及中國銀聯) 
  - 分隔符號- 空格、點或虛線
  - 這項掃描也包含 Luhn 驗證
- SWIFT 銀行代碼
- 國際護照號碼
- 駕照號碼
- 日期
- 銀行 ABA 路由轉帳代碼
- 銀行識別代碼
- HIPAA HICN 健康保險理賠號碼
- HIPAA NPI 全國供應商識別碼
- PHI 全名及生日
- 加州居民卡或駕照號碼
- 駕照號碼
- 住家地址
- 護照卡
- 社會安全號碼

## <a name="supported-languages"></a>支援的語言

Cloud App Security 內容檢查引擎：
-   支援所有 Unicode 字元
-   涵蓋超過 1,000 個檔案類型
-   支援多種語言，特別是使用 Unicode 字元集的檔案。 請確定會定義您的原則來處理那些語言，例如如果您正在尋找關鍵字，您必須跨您想要使用的語言放入關鍵字。
-   在使用非 Unicode 編碼 (例如簡體中文 GB2312) 的文字型檔案類型中，針對 Unicode 中文關鍵字進行比較，將不會如預期般運作。
-   針對依賴協力廠商程式庫的檔案類型，比對字串與文字不一定會如預期般運作。 這在檔案中最常見 (例如二進位檔案類型)，其中的內容檢查依賴協力廠商程式庫，傳回適用於語言和字元集的 Java 字串。



## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  