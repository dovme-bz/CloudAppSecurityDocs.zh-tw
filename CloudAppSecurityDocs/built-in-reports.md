---
title: 如何在 Microsoft Cloud App Security 中產生報告 | Microsoft Docs
description: 本主題提供有關在 Microsoft Cloud App Security 中產生資料管理報告的指示。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/30/2018
ms.topic: article
ms.prod: ''
ms.app: cloud-app-security
ms.technology: ''
ms.assetid: 0dcc3c35-f787-4822-84c6-d4dff897dd6c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4eca209bb4ec71e519439704a7dbb33e48107c9b
ms.sourcegitcommit: af8fad9709171b200699ca1ed513e2831826ed7e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2018
ms.locfileid: "34568695"
---
*適用於：Microsoft Cloud App Security*



# <a name="generate-data-management-reports"></a>產生資料管理報告

Microsoft Cloud App Security 可讓您產生報告，其可提供您雲端應用程式中檔案的概觀。

產生這些報告

1. 移至 [檔案]。 
2. 在右上角處，按一下三個點，然後在 [資料管理報告] 下，選取下列其中一個報告。

   ![報告](./media/reports.png) I
## <a name="data-sharing-overview"></a>資料共用概觀 

這會列出儲存在您雲端應用程式中的檔案數目，並根據存取權限而區分。 雲端應用程式讓共用變得很容易，因為易於存取且無所不在。 未與擁有者以外的任何人共用的檔案，稱為私人檔案。 如果共用檔案，Cloud App Security 會區別四種類型的狀態︰ <br> - 公開共用的 (Web) 檔案是不需要驗證，甚至是透過搜尋引擎結果就能存取的檔案。<br> - 公開共用檔案是不需要驗證就能使用連結來存取的檔案。<br> - 外部共用檔案是組織外部人員在向雲端應用程式驗證自己之後即可存取的檔案。<br> - 內部共用檔案是可以由您組織所有或部分使用者存取的檔案。

## <a name="outbound-sharing-by-domain"></a>域外共用 (依網域)

這會列出您的員工與其共用公司檔案的網域。 報告中的每個網域會詳細指出哪些公司使用者正與該網域共用檔案、共用了哪些檔案，以及檔案共用對象是哪些共同作業者。 建議您透過每個相關應用程式的 [應用程式] 頁面 [檔案] 索引標籤來管理與這些網域的共用。

## <a name="owners-of-shared-files"></a>共用檔案的擁有者

這會列出正與外界共用公司檔案的使用者。 外部共用檔案會與特定的外部共同作業者共用。 公開共用檔案可供網際網路上的任何人透過私人連結存取，且只有明確公開連結的對象可以找到。 公開共用檔案 (網際網路) 可供網際網路上的任何人甚至透過搜尋引擎結果存取。 如果您發現共用過多數量檔案的使用者，建議您使用 [檔案] 索引標籤調查這些過多共用權限的本質，並連絡這些使用者來進一步了解他們的外部共用使用情形。


  
## <a name="see-also"></a>另請參閱 
[控制](control.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  