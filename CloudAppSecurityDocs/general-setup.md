---
title: "提供 Cloud App Security 入口網站中的組織設定以獲得最佳結果 | Microsoft Docs"
description: "本文說明如何提供 Cloud App Security 中組織的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 39c2bc972ea09eb9297711aee7bafdd7dc9d1242
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2017
---
# <a name="basic-set-up"></a>基本設定
下列程序會指示您自訂 Cloud App Security 入口網站。

## <a name="prerequisites"></a>必要條件 
若要存取入口網站，請務必將下列 IP 位址新增至防火牆白名單，以提供 Cloud App Security 入口網站的存取權：  
  
- 104.42.231.28  
  
> [!NOTE]  
>  若要在 URL 和 IP 位址變更時取得更新，請訂閱 RSS，如 [Office 365 URL 與 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)中所述。  
  
## <a name="set-up-the-portal"></a>設定入口網站  
  
1.  在 Cloud App Security 入口網站的功能表列中，按一下設定圖示 ![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [一般設定] 設定下列項目︰  
     
     ![一般設定](./media/general-settings.png "一般設定")  
  
3.  請務必在 [組織詳細資料] 下，提供您組織的 [組織顯示名稱]。 它將會顯示在系統傳送的電子郵件和網頁上。  
  
4. 提供**環境名稱** (租用戶)。 如果您管理多個租用戶，這點尤其重要。  
  
4. 您也可以提供**標誌**，它將會顯示在從系統傳送的電子郵件通知和網頁上。 標誌應該是大小上限為 150 x 50 像素且為透明背景的 png 檔案。  

4.  請務必新增 [受管理的網域] 清單。 這是很重要的步驟，因為 Cloud App Security 使用受管理的網域來判斷哪些使用者是內部使用者、哪些是外部使用者，以及檔案應該和不應共用的位置。 這用於報告及警示。  
> [!NOTE] 
> - 網域中未設定為內部的使用者將會標示為外部，而且不會掃描活動或檔案。

5. 如果要與 Azure Information Protection 整合相整合，請參閱[Azure Information Protection 整合](azip-integration.md)以取得相關資訊。 
  
  
6.  如果您在任何時間點想要備份入口網站設定，此畫面可讓您執行此作業。 按一下 [匯出入口網站設定] 來建立所有入口網站設定的 JSON 檔案，包括原則規則、使用者群組和 IP 位址範圍。  
  
       



> [!NOTE] 
> 若您使用 ExpressRoute，Cloud App Security 會在 Azure 中部署並與 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) 完全整合。 與 Cloud App Security 應用程式的所有互動和傳送至 Cloud App Security 的流量，包括上傳探索記錄檔，都會透過 ExpressRoute **公用對等互連**路由傳送以改善延遲、效能和安全性。 客戶端不需要任何組態步驟。  
    如需公用對等互連的詳細資訊，請參閱 [ExpressRoute 線路和路由網域](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)。  
    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  