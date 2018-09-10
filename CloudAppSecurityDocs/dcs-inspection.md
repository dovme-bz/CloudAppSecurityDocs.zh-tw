---
title: Cloud App Security 如何使用 Microsoft 資料分類服務執行內容檢查| Microsoft Docs
description: 本文說明在使用 Microsoft 資料分類服務執行 DLP 內容檢查時，Cloud App Security 所遵循的程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/1/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bf25d1e6-e5dc-449f-b50e-1cd4a21b6d3d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9d3abbd87822d97b0c72f20ff42f3aa18b6e57db
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143355"
---
*適用於：Microsoft Cloud App Security*



# <a name="microsoft-data-classification-services-integration"></a>Microsoft 資料分類服務整合

Microsoft Cloud App Security 讓您能夠以原生方式利用 Microsoft 資料分類服務，以便對雲端應用程式中的檔案進行分類。
Microsoft 資料分類服務在 Office 365、Azure 資訊保護和 Microsoft Cloud App Security 中提供統一的資訊保護體驗，並允許您將資料分類工作擴充到受 Microsoft Cloud App Security 保護的協力廠商雲端應用程序，從而充分利用您對多個應用程式所做出的決策，並使其遍及更多的應用程式。

>[!NOTE]
> 此功能目前只適用於美國和歐洲 (法國除外)。

在為 Microsoft Cloud App Security 中的檔案建立資料洩漏防護原則時，您將自動會有設定**檢查方法**以使用 **Microsoft 資料分類服務**的選項，而無需額外設定。

![資料分類服務設定](./media/dcs-enable.png)

若要使用資料分類服務啟用內容檢查：

1. 在 [[檔案原則]](data-protection-policies.md) 頁面的 [檢查方法] 下，選取 [資料分類服務]。
2. 選取滿足 [任何] 或 [全部] 條件時，是否應套用該原則。
3. 透過選取機密資訊類型來選擇您的內容檢查類型。
 ![資料分類服務設定](./media/dcs-sensitive-information-type.png)

5. 您可以使用在 Office 365 中建立的[預設機密資訊類型](https://support.office.com/article/what-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b)以及[自訂機密資訊類型](https://support.office.com/article/create-a-custom-sensitive-information-type-82c382a5-b6db-44fd-995d-b333b3c7fc30) (支援使用 Regex、關鍵字和大型字典的複雜模式)，並重複使用這些類型以定義受 Microsoft Cloud App Security 保護的檔案會發生什麼情況。

6. 或者，您可以將相符項目的最後四個字元取消遮罩。 根據預設，符合項目會加上遮罩，並顯示在其上下文中，且包含符合項目之前與之後的 40 個字元。 如果您選取此核取方塊，它會將相符項目本身的最後四個字元取消遮罩。

7. 您也可以針對原則設定警示和治理動作。 如需詳細資訊，請參閱[檔案原則](data-protection-policies.md)和[治理動作](governance-actions.md)。

在 Microsoft Cloud App Security 中設定這些原則，可讓您輕鬆地將 Office 365 DLP 功能的優勢擴充到所有其他受核可的雲端應用程式，並使用 Microsoft Cloud App Security 所提供的完整工具集來保護儲存在其中的資料，例如[自動套用 Azure 資訊保護分類標籤](azip-integration.md)以及控制共用權限的能力。



## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  