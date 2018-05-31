---
title: 將 Azure 連線到 Cloud App Security 以取得可見度及使用方式控制權 | Microsoft Docs
description: 本主題提供如何使用 API 連接器將 Azure 連線到 Cloud App Security 的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/27/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f93a78e35c76e9dd76e1264fb11d6046ed2b6d18
ms.sourcegitcommit: 0d73d21f961dc883f01a329bcf16dcaf070dca2a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2018
ms.locfileid: "34558935"
---
*適用於：Microsoft Cloud App Security*


# <a name="connect-azure-to-microsoft-cloud-app-security"></a>將 Azure 連線到 Microsoft Cloud App Security

本節提供使用應用程式連接器 API 將 Microsoft Cloud App Security 連線到現有 Azure 帳戶的指示。  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>設定 Azure 以與 Cloud App Security 連線

Cloud App Security 會透過事件中樞連線到 Azure。 本節提供在訂用帳戶中將所有活動記錄串流至單一事件中樞的指示。 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>步驟 1：將您的 Azure 活動記錄串流至事件中樞

1. 將 Azure 訂用帳戶的 Azure 活動記錄串流至事件中樞。 請依照 Azure 文件中的正式指南進行： https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

   > [!NOTE]
   > 如果您有多個 Azure 訂用帳戶，請對每一個訂用帳戶重複此步驟，並於所有訂用帳戶之間共用單一事件中樞。

   完成指示後，新的事件中樞會建立於您選擇的命名空間。
 
   > [!NOTE]
   > 如果您在嘗試匯出活動記錄後發生錯誤，請移至 Azure 中位於左側功能表上的 [資源提供者]，並確認已註冊 'microsoft.insights'。

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>步驟 2：取得事件中樞的連接字串

1. 移至左側功能表上的 [事件中樞 - 預覽]。
  
   ![事件中樞功能表](media/azure-event-hubs.png "Azure 事件中樞")

2.  在 Azure 快顯視窗中，按一下 [連線 Microsoft Azure]。

3. 在功能表的 [實體] 按一下 [事件中樞]。 
  
   ![事件中樞實體](media/azure-event-hubs-entities.png "Azure 事件中樞實體")

4. 選取 Azure 監視器新建立的事件中樞。 其名為 **insights-operational-logs**。
   > [!NOTE]
   > 建立事件中樞可能需要幾分鐘的時間。

   ![Insights operational logs](media/azure-insight-operational-logs.png "Azure Insights operational logs")
  
  
5. 按一下 [共用存取原則]，再按一下 [新增]，就可建立新的存取原則，提供 Cloud App Security 權限讀取事件中樞。
  
    ![共用存取原則](media/azure-shared-access-policies.png "Azure 共用存取原則")

6. 輸入新原則的名稱，至少務必包含**接聽宣告**。 完成之後，按一下 [建立]。
  
   ![Azure 新的原則](media/azure-new-policy.png "Azure 新的原則")

7. 在 [設定] 的 [共用的存取原則] 底下，按一下您所建立的存取原則。   
  
   ![Azure 原則](media/azure-select-policy.png "Azure 原則")

8. 在 [原則] 視窗中，透過按一下 [連接字串 - 主索引鍵] 或 [連接字串 - 次索引鍵] 旁的按鈕，來複製其中一個連接字串。

### <a name="step-3-add-azure-to-cloud-app-security"></a>步驟 3：將 Azure 新增至 Cloud App Security
 
1. 在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
2. 在 [App 連線程式] 頁面中，按一下加號按鈕並選取 [Microsoft Azure]。  
  
    ![將 Azure 連線到 Cloud App Security](media/azure-connect-app.png "與 Azure 連線")  
  
3. 在 [連接字串]欄位中，貼上您在上一個步驟中複製的連接字串。  
  
4. 在 [取用者群組] 欄位中鍵入：`$Default`
    
   >[!NOTE] 
   > 如果您建立了其他取用者群組來使用，請使用該**取用者群組**名稱。
  
5. 按一下 [連線] 以連線並測試連線。 這可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  


> [!NOTE]
> 這項功能是在私人預覽。


## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  