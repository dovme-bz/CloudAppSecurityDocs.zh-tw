---
title: "使用 RegEx 引擎 | Microsoft Docs"
description: "本主題提供在 Cloud App Security 原則中使用 RegEx 進行模式比對的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 77468efb5d4cb62f560c11e624545fc8abe8c99e


---

# <a name="working-with-the-regex-engine"></a>使用 RegEx 引擎
 
Cloud App Security 的內容檢查原則會利用 RegEx 進行模式比對。 您可以將內容檢查與檔案原則一起套用。 若要測試規則運算式，您可以使用下列網站：  
  
-   [http://regexpal.com/](http://regexpal.com/)  
  
     請務必選取 [不區分大小寫]。  
  
-   [https://regex101.com/](https://regex101.com/)  
  
     提供 RegEx 的詳細分析。  
  
自訂的規則運算式有加諸下列限制：  
  
-   搜尋一律不區分大小寫  
   
-   允許的數量詞：{n,m}，其中 n、m < 10  
  
-   所有群組都必須為非擷取群組，例如 (?:xxx)  
  
     而不是 (group) 與 (?:group)  
  
-   不允許的數量詞：*、+、{n,}  
  
     而不是 * 與 {0,9}  
  
     而不是 + 與 {1,9}  
  
-   不允許反向參考：\\<數字\> 或 \k\<名稱>  
  
運算式範例  
  
||||  
|-|-|-|  
|**規則運算式**|**資料**|**相符項目**|  
|Colou?r (?:black&#124;blue&#124;white)|Color black<br /><br /> Color white<br /><br /> Color red|是<br /><br /> 是<br /><br /> 否|  
|[a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}|Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com|是<br /><br /> 是<br /><br /> 否|  
|20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31)|2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31|是<br /><br /> 是<br /><br /> 否|  
|d.n't\s{0,10}c.r.|Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care|是<br /><br /> 是<br /><br /> 否|  
 

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


