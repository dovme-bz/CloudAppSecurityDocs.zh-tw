---
title: "連接應用程式以取得對 Cloud App Security 的深入可見度及控制 | Microsoft Docs"
description: "本主題描述使用 API 連接器將應用程式連接到您組織的雲端應用程式之過程。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b1bc4f7455736f57cf4bb43d8c7d7d020e749f7c
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="connect-apps"></a>連線應用程式 
應用程式連接器利用應用程式提供者的 API，讓 Cloud App Security 對您連線至的應用程式有更好的可見度和控制。  
  
Cloud App Security 利用雲端提供者提供的 API，每個服務都有自己的架構和 API 限制。 Cloud App Security 使用服務來使 API 的使用達到最佳化，並且確保最佳的效能。 Cloud App Security 引擎會考慮服務加諸於 API 的不同限制 (例如節流、API 限制、動態時間調整 API 範圍等)，而利用允許的容量。 某些作業，例如掃描租用戶中的所有檔案，需要大量的 API，因此會分散在較長的時間。 請預期某些原則會執行長達幾個小時或幾天。  
  
## <a name="how-it-works"></a>運作方式  
Cloud App Security 部署時具有系統管理員權限，能夠完整存取您環境中的所有物件。  
  
App 連線程式流程如下所示︰
1. Cloud App Security 可掃描並儲存驗證權限。
2.  Cloud App Security 要求使用者清單。 首次執行時，可能需要一些時間等待掃描完成。 使用者掃描完成後，Cloud App Security 會移至活動和檔案。 掃描啟動時，Cloud App Security 中會有幾個可用的活動。 
4. 完成使用者要求後，Cloud App Security 會定期掃描使用者、群組、活動及檔案。 所有的活動在首次完整掃描後皆可供使用。 
 
這可能需要一些時間，視租用戶大小、使用者數目和大小，以及需要掃描的檔案數目而定。 
 
視您要連線至的應用程式而定 (請參閱下表)，API 連線會啟用下列各項︰  
  
-   **帳戶資訊︰**  
  
     能查看使用者、帳戶、設定檔資訊、狀態 (已擱置、使用中、已停用) 群組和權限。  
  
-   **稽核記錄︰**  
  
     能查看使用者活動、管理員活動、登入活動。  
  
-   **掃描資料︰**  
  
     使用兩個處理序定期 (每隔 12 小時) 和即時掃描 (每次偵測到變更時觸發) 掃描非結構化資料。  
  
-   **應用程式權限：**  
  
     能查看已發出的權杖及其權限。  
  
-   **帳戶治理：**  
  
     能夠暫止使用者、撤銷密碼等。  
  
-   **資料治理：**  
  
     能夠隔離檔案，包括在資源回收筒的檔案，以及能夠覆寫檔案。  
  
-   **應用程式權限治理︰**  
  
     能夠移除權杖。  
  
下表列出，針對雲端應用程式，應用程式連接器支援的功能︰  

> [!div class="mx-tableFixed"]
||**Office 365**|**Box**|**Okta**|**G Suite**|**Service Now**|**Salesforce**|**Dropbox**|**AWS**|  
|-|-|-|-|-|-|-|-|-|  
|**列出帳戶**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**群組**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**權限**|✔|✔|提供者不支援|✔|✔|✔|✔||  
|**使用者治理**|✔|✔||✔|敬請期待|敬請期待|敬請期待||  
|**登入活動**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**使用者活動**|✔*|✔|✔|✔ - 需要 Google Unlimited|部分|Salesforce Shield 予以支援|✔|不適用|  
|**管理活動**|✔|✔|✔|✔|部分|✔|✔|✔|  
|**定期掃描檔案**|✔|✔|不適用|✔|✔|✔|✔|不適用|  
|**接近即時的檔案掃描**|✔|✔|不適用|✔ - 需要 Google Unlimited|||敬請期待||  
|**共用控制權**|✔|✔|不適用|✔|不適用||✔||  
|**隔離**|✔|✔|不適用|敬請期待|||敬請期待||  
|**檢視應用程式權限**|✔|提供者不支援|不適用|✔||✔|提供者不支援||  
|**撤銷應用程式權限**|✔||不適用|✔||✔|不適用||  
|**套用 Azure 資訊保護標籤**|✔|✔|||||||  
  
## <a name="prerequisites"></a>必要條件  

- 針對某些應用程式，您可能必須將 IP 位址新增到允許清單，讓 Cloud App Security 可以收集記錄並提供對 Cloud App Security 主控台的存取權。 如需詳細資訊，請參閱[網路需求](network-requirements.md)。

- 對於您要連接到 Cloud App Security API 整合的每個應用程式，建議您建立專用於 Cloud App Security 的管理服務帳戶。  
  
> [!NOTE]  
>  若要在 URL 和 IP 位址變更時取得更新，請訂閱 RSS，如 [Office 365 URL 與 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)中所述。  
  
若要使用應用程式連接器，您需要確定針對每個特定的應用程式，您具有下列各項︰  
  
|應用程式|授權類型|使用者|  
|---------|------------------|----------|  
|方塊|企業|強烈建議您以管理員身分連線至 Box。以共同管理員身分連線，將會導致僅部分資料可見度。 如果您以共同管理員身分連線，請務必選取所有權限。|  
|G Suite|偏好 G Suite Unlimited<br /><br /> G Suite Enterprise (最低)|進階管理員|  
|Office 365||全域管理員|  
|AWS||新建立的使用者|  
|Dropbox|商務/企業版|系統管理員|  
|Okta|企業版 (非試用版)|系統管理員|  
|Exchange||全域管理員|  
|ServiceNow|Eureka 與更新版本|管理員 +RestAPI 角色|  
|Salesforce||系統管理員|  
  

**ExpressRoute**  
  
Cloud App Security 部署在 Azure 中並完全整合到 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)。 與 Cloud App Security 應用程式的所有互動和傳送至 Cloud App Security 的流量，包括上傳探索記錄檔，都會透過 ExpressRoute **公用對等互連**路由傳送以改善延遲、效能和安全性。 客戶端不需要任何組態步驟。  
如需公用對等互連的詳細資訊，請參閱 [ExpressRoute 線路和路由網域](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/)。  
  
## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  

## <a name="check-out-this-video"></a>請觀賞這部影片！
[Microsoft Cloud App Security – REST API’s and Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens) (Microsoft Cloud App Security – REST API 和權杖)  
   