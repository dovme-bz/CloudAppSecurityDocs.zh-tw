---
title: "將 Azure 連線到 Cloud App Security 以取得可見度及使用方式控制權 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Azure 連線到 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d2c5dff92c790a9ad27c872ebbd09769eef9898d
ms.sourcegitcommit: 27170447acfaeded585c264e425a46a485e7fb19
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2017
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>將 Azure 連線到 Microsoft Cloud App Security

本節提供使用應用程式連接器 API 將 Cloud App Security 連線到現有 Azure 帳戶的指示。  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>設定 Azure 以與 Cloud App Security 連線

Cloud App Security 會透過事件中樞連線到 Azure。 本節提供在訂用帳戶中將所有活動記錄串流至單一事件中樞的指示。 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>步驟 1：將您的 Azure 活動記錄串流至事件中樞

1.  將 Azure 訂用帳戶的 Azure 活動記錄串流至事件中樞。 請遵循 Azure 文件中的官方指南：https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > 如果您有多個 Azure 訂用帳戶，請對每一個訂用帳戶重複此步驟，但訂用帳戶間則共用單一事件中樞。

 完成指示後，新的事件中樞會建立於您選擇的命名空間。
 
 > [!NOTE]
 > 如果您在嘗試匯出活動記錄後發生錯誤，請在 Azure 中前往 [資源提供者] 刀鋒視窗，並確認已註冊 ‘microsoft.insights’。

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>步驟 2：取得事件中樞的連接字串

1.  前往 [事件中樞 - 預覽] 刀鋒視窗。
  
   ![事件中樞刀鋒視窗](media/azure-event-hubs.png "Azure 事件中樞")

2.  選取事件中樞命名空間。
  
    ![事件中樞命名空間](media/azure-namespace.png "Azure 命名空間")

3.  在功能表的 [實體] 按一下 [事件中樞]。 
  
    ![事件中樞實體](media/azure-event-hubs-entities.png "Azure 事件中樞實體")

4.  選取 Azure 監視器新建立的事件中樞。 其名為 **insights-operational-logs**。
  > [!NOTE]
  > 建立事件中樞可能需要幾分鐘的時間。

   ![Insights operational logs](media/azure-insight-operational-logs.png "Azure Insights operational logs")
  
  
5. 按一下 [共用存取原則]，再按一下 [新增]，就可建立新的存取原則，提供 Cloud App Security 權限讀取事件中樞。
  
    ![共用存取原則](media/azure-shared-access-policies.png "Azure 共用存取原則")

6.  輸入新原則的名稱，至少務必包含**接聽宣告**。 完成之後，按一下 [建立]。
  
    ![Azure 新的原則](media/azure-new-policy.png "Azure 建立新的原則")

7.  在 [設定] 下的 [共用的存取原則]，按一下剛建立好的存取原則。   
  
    ![Azure 選取原則](media/azure-select-policy.png "Azure 選取原則")

8. 在 [原則] 視窗中，按一下 [連接字串 - 主索引鍵] 或 [連接字串 - 次索引鍵] 旁的按鈕來複製其中一個連接字串。

### <a name="step-3-add-azure-to-cloud-app-security"></a>步驟 3：將 Azure 新增至 Cloud App Security
 
1.  在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
3.  在 [App 連線程式] 頁面中，按一下加號按鈕並選取 [Microsoft Azure]。  
  
     ![將 Azure 連線到 Cloud App Security](media/azure-connect-app.png "與 Azure 連線")  
  
4.  在 [連接字串]欄位中，貼上您在上一個步驟中複製的連接字串。  
  
5.  在 [取用者群組] 欄位中鍵入：`$Default`
    
   >[!NOTE] 
   > 如果您建立了其他取用者群組來使用，請使用該**取用者群組**名稱。
  
6.  按一下 [連線] 。
     如此會以簡訊傳送連線，因此可能需要幾分鐘的時間。 收到成功通知之後，按一下 [關閉]。  
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  