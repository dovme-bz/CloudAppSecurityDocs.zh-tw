---
title: 將 Cloud App Security 與 Zscaler 整合，以便獲得無接縫 Cloud Discovery 與自動化封鎖獲批准的應用程式 | Microsoft Docs
description: 將 Cloud App Security 與 Zscaler 整合，以便獲得無接縫 Cloud Discovery 與獲批准的應用程式的自動化封鎖。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8abeab8e-3b7a-46a7-bbec-9aaf26f778a8
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a36a678b455442226e4520df0ff771087b3f93dd
ms.sourcegitcommit: 1744ef45b9c5ac8e08b3489bb9b73fc1347587ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2018
ms.locfileid: "43115704"
---
*適用於：Microsoft Cloud App Security*

# <a name="integrate-cloud-app-security-with-zscaler"></a>整合 Cloud App Security 與 Zscaler

若您同時使用 Cloud App Security 與 Zscaler，您可以整合這兩個產品以加強您的安全性 Cloud Discovery 體驗。 Zscaler 是獨立式雲端 Proxy，它會監視您組織的流量，讓您設定封鎖交易的原則。 Cloud App Security 與 Zscaler 結合可提供下列功能：

- 無接縫的 Cloud Discovery 部署 - 使用 Zscaler 來 Proxy 您的流量並將它傳送到 Cloud App Security 可減少在您的網路端點上安裝記錄收集器以啟用 Cloud Discovery 的需求。
- Zscaler 的封鎖功能會自動套用到您在 Cloud App Security 中設定為待批准的應用程式上。
- 使用 Cloud App Security 200 適用於個領先的雲端應用程式的風險評定 (可直接從 Zscaler 入口網站檢視) 來加強 Zscaler 入口網站。
    

## <a name="prerequisites"></a>必要條件

- 適用於 Microsoft Cloud App Security 的有效授權
- 適用於 Zscaler Cloud 5.6 的有效授權
- 有效的 Zscaler NSS 訂用帳戶 

## <a name="deployment"></a>部署

1. 在 Zscaler 入口網站中，執行必要步驟以完成 [Zscaler 合作夥伴 Microsoft Cloud App Security 整合](https://help.zscaler.com/zia/configuring-mcas-integration) \(英文\)。
2. 在 Cloud App Security 入口網站中，執行下列整合步驟：
    1. 按一下設定齒輪並選取 [Cloud Discovery 設定]。 
    2. 按一下 [自動記錄上傳] 索引標籤，然後按一下 [加入資料來源]。
    3. 在 [加入資料來源] 頁面中，輸入下列設定：
        - 名稱 = NSS
        - 來源 = Zscaler QRadar LEEF
        - 接收器類型 = Syslog - UDP

          ![資料來源 zscaler](./media/data-source-zscaler.png)

    4. 按一下 [檢視所需記錄檔的範例]。 接著，按一下 [下載範例記錄檔] 以檢視範例探索記錄，並確定它符合您的記錄。<br>
    
3. 調查在您的網路上探索到的雲端應用程式，請參閱[使用 Cloud Discovery](working-with-cloud-discovery-data.md) 以取得詳細資訊與調查步驟。
 
4. 您在 Cloud App Security 中設定為待批准的任何應用程式每小時都會被 Zscaler Ping 兩次，然後自動由 Zscaler 封鎖。 如需有關不批准應用程式的詳細資訊，請參閱[批准/不批准應用程式](governance-discovery.md#govern-discovered-apps)。
    
    
    
    
    

 
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  