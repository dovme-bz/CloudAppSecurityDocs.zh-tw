---
title: 封鎖探索到的應用程式 | Microsoft Docs
description: 本主題說明匯出用於封鎖探索到之應用程式的指令碼程序。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3fbbf979dddb96db69e57c86758c6c1a699c8a51
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*


## <a name="govern-discovered-apps"></a>治理探索到的應用程式

在您檢閱環境中探索到的應用程式清單之後，您可以透過下列方式來保護環境免受垃圾應用程式使用威脅。

### <a name="sanctioningunsanctioning-an-app"></a>批准/不批准應用程式 

您可以按一下資料列結尾的三個點，然後選取 [不批准]，不批准具風險的特定應用程式。
不批准應用程式不會封鎖使用，而是讓您透過 Cloud Discovery 篩選更輕鬆地監視其使用情況。 您可以接著通知應用程式的使用者該應用程式已成為待批准，並建議他們使用其他安全的應用程式。

![標記為待批准](./media/tag-as-unsanctioned.png)  


如果您有一份想要批准或不批准的應用程式清單，您可以使用此核取方塊來選取所有想要管理的應用程式，然後選取此動作。

若要查詢待批准應用程式的清單，您可以[使用 Cloud App Security API 產生區塊指令碼](https://mod636914.us.portal.cloudappsecurity.com/api-docs/#generate-block-script)。

## <a name="export-a-block-script-to-govern-discovered-apps"></a>匯出封鎖指令碼來治理探索到的應用程式

Cloud App Security 可讓您使用現有的內部安全性設備來禁止存取待批准的應用程式。 產生專用的封鎖指令碼，並將其匯入您的設備。
此解決方案不需要將組織的所有網路流量全部重新導向到 Proxy。

1. 在 Cloud Discovery 儀表板中，將您要封鎖的應用程式標記為**待批准**。

   ![標記為待批准](./media/tag-as-unsanctioned.png)  

2. 在標題列上，按一下三個點，然後選取 [Generate block script]\(產生封鎖指令碼)。 

   ![產生封鎖指令碼](./media/generate-block-script.png)  

3. 在 [Generate block script]\(產生封鎖指令碼) 中，選取所產生之封鎖指令碼的適用裝置。 

   ![[Generate block script] (產生封鎖指令碼) 快顯](./media/generate-block-script-popup.png)  

4. 然後按一下 [產生指令碼] 按鈕。 這會為所有待批准的應用程式建立封鎖指令碼。 根據預設，檔案會依其匯出日期及您選取的設備類型命名，例如 *2017年-02-19_CAS_Fortigate_block_script.txt* 

   ![[Generate block script] (產生封鎖指令碼) 按鈕](./media/generate-block-script-button.png)  

5. 將建立的檔案匯入您的設備。



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  