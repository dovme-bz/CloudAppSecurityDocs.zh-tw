---
title: 在 Cloud App Security 中新增自訂應用程式到 Cloud Discovery | Microsoft Docs
description: 本主題提供如何在 Cloud App Security 中新增自訂應用程式到 Cloud Discovery 以監視影子 IT。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 98b0d841-b33d-4ae9-b48b-d9ee77785eaa
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4eeaca599a51e110773555d1c6862d34f8fd99a2
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*

# <a name="add-custom-apps-to-cloud-discovery"></a>新增自訂應用程式到 Cloud Discovery
    
Cloud Discovery 以 Microsoft Cloud App Security 雲端應用程式目錄中超過 15,000 個雲端應用程式來分析您的流量記錄。 該目錄只包含公開可用的雲端應用程式，Cloud App Security 會針對這些應用程式提供可見度和風險資訊。

為了看到雲端應用程式目錄所排除的雲端應用程式，Cloud App Security 可讓您探索專為您的組織開發或指派的自訂雲端應用程式 (LOB 應用程式) 使用情形。

藉由新增自訂雲端應用程式，Cloud App Security 可將上傳的防火牆和 Proxy 記錄訊息與應用程式比對，然後在 Cloud Discovery 頁面中讓您看到此應用程式在整個組織中的使用方式，例如，使用該應用程式的使用者人數、使用該應用程式的唯一來源 IP 位址數量，以及傳輸進出該應用程式的流量多寡。 

新增自訂雲端應用程式：

1. 在 Cloud App Security 入口網站中，按一下 [探索]，然後按一下 [Cloud Discovery 儀表板]。 
  
   ![Cloud Discovery 儀表板功能表](./media/cloud-discovery-dashboard-menu.png)

2. 在右上角，按一下 3 個點然後選取 [新增自訂應用程式]。 

   ![新增自訂應用程式功能表](./media/add-custom-app-menu.png)

3. 填入定義新應用程式記錄的欄位，當防火牆記錄中探索到這些欄位之後，就會在雲端應用程式目錄和 Cloud Discovery 中將之列出。

   ![自訂應用程式](./media/add-custom-app.png)

4. 在 [網域] 下，填入存取自訂應用程式時所使用的唯一網域。 這些網域會用來比對流量記錄訊息與此應用程式。 如果您使用的資料來源不包含應用程式 URL 資訊，請務必填入 [IPv4] 和 [IPv6] 位址欄位。
5. 建議您新增可讓您追蹤此記錄變更的附註。

應用程式建立之後，您就可以在雲端應用程式目錄中取得它。

您隨時都可以按一下列尾端的 3 個點，以編輯或刪除自訂應用程式。

>[!NOTE]
> - 新增自訂應用程式之後，便會自動加上 [自訂應用程式] 標籤。 您無法移除此應用程式標籤。
若要檢視所有您的自訂應用程式，請將 [應用程式標籤] 篩選器設定為等於「自訂應用程式」。 
> - 根據預設，自訂應用程式的風險分數為 10，但您可以隨時使用 [覆寫應用程式分數] 動作來加以變更。

  
## <a name="see-also"></a>另請參閱  
[使用者活動原則](user-activity-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  