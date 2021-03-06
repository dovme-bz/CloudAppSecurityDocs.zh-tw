---
title: 使用 RegEx 引擎進行內容檢查原則 | Microsoft Docs
description: 本主題提供在 Cloud App Security 原則中使用 RegEx 進行模式比對的指示。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 52a18f28382ffefca7785419fb67e8b0f2de66df
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143238"
---
*適用於：Microsoft Cloud App Security*


# <a name="working-with-the-regex-engine"></a>使用 RegEx 引擎
 
Microsoft Cloud App Security 的內容檢查原則會利用 RegEx 進行模式比對。 您可以將內容檢查與檔案原則一起套用。 若要測試規則運算式，您可以使用下列網站：  
  
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
  
     從 * 改為使用 {0,9}  
  
     從 + 改為使用 {1,9}  
  
-   不允許反向參考：\\<數字\> 或 \k\<名稱>  
  
運算式範例  
  

|                                                               |                                                               |                                    |
|---------------------------------------------------------------|---------------------------------------------------------------|------------------------------------|
|              <strong>規則運算式</strong>              |                     <strong>資料</strong>                     |      <strong>相符項目</strong>      |
|            Colou?r (?:black&#124;blue&#124;white)             |   Color black<br /><br /> Color white<br /><br /> Color red   | 是<br /><br /> 是<br /><br /> 否 |
|           [a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}            | Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com  | 是<br /><br /> 是<br /><br /> 否 |
| 20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31) |   2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31    | 是<br /><br /> 是<br /><br /> 否 |
|                       d.n't\s{0,10}c.r.                       | Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care | 是<br /><br /> 是<br /><br /> 否 |

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  

## <a name="check-out-this-video"></a>請觀賞這部影片！
[Working with the Regex Engine](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security-Working-with-the-Regex-Engine) (使用 RegEx 引擎)    