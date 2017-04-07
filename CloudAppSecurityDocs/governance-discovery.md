---
title: "封鎖探索到的應用程式 | Microsoft Docs"
description: "本主題說明匯出用於封鎖探索到之應用程式的指令碼程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/21/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ca4a10f64429c481f49c75740f651302b1c7d1ef
ms.sourcegitcommit: 7493d88e4fe7c827f870b81e2090ffcc77f1408a
translationtype: HT
---
# <a name="governing-discovered-apps"></a>治理探索到的應用程式
Cloud App Security 可讓您使用現有的內部安全性設備來禁止存取待批准的應用程式。 產生專用的封鎖指令碼，並將其匯入您的設備。
此解決方案不需要將組織的所有網路流量全部重新導向到 Proxy。


## <a name="export-a-block-script-to-govern-discovered-apps"></a>匯出封鎖指令碼來治理探索到的應用程式

1. 在 Cloud Discovery 儀表板中，將您要封鎖的應用程式標記為**待批准**。

   ![標記為待批准](./media/tag-as-unsanctioned.png)  

2. 在標題列上，按一下三個點，然後選取 [Generate block script] (產生封鎖指令碼)。 

   ![產生封鎖指令碼](./media/generate-block-script.png)  

3. 在 [Generate block script] (產生封鎖指令碼) 中，選取所產生之封鎖指令碼的適用裝置。 

   ![[Generate block script] (產生封鎖指令碼) 快顯](./media/generate-block-script-popup.png)  

4. 然後按一下 [產生指令碼] 按鈕。 這會為所有待批准的應用程式建立封鎖指令碼。 根據預設，檔案會依其匯出日期及您選取的設備類型命名，例如 *2017年-02-19_CAS_Fortigate_block_script.txt* 

   ![[Generate block script] (產生封鎖指令碼) 按鈕](./media/generate-block-script-button.png)  

5. 將建立的檔案匯入您的設備。



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  