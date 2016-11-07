---
title: "什麼是 Cloud App Security | Microsoft Docs"
description: "本主題提供什麼是 Cloud App Security 和其運作方式的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2cb87afa3c5342e01cfd4049669ac4b3b7efa4fe
ms.openlocfilehash: c6df59d7c5ced9dc378463bc5bef411259294c47


---
# <a name="what-is-cloud-app-security"></a>什麼是 Cloud App Security
 
> [!NOTE] 
> 如需進階安全性管理 (Office 365 中的 Cloud App Security 功能) 的相關資訊，請參閱[開始使用進階安全性管理](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a)。 
 
轉移至雲端雖然可增加員工的彈性並降低 IT 成本，但也在維護組織安全方面帶來新的複雜性與挑戰。 若要實現雲端應用程式的完整優點，IT 團隊必須在保障存取與擁有可保護重要資料的掌控權之間找到適當的平衡。  
  
Cloud App Security 是 Microsoft Cloud Security 堆疊的重要元件。 它是全方位的解決方案，可協助組織充分發揮雲端應用程式所保證的優勢，同時透過改良的活動可見度來維持控管能力。 它也能針對跨雲端應用程式的重要資料，提供強化的保護。 組織可以使用有助找出陰影 IT、評估風險、強制執行原則、調查活動並停止威脅的相關工具，安全地轉移到雲端，同時保有重要資料的控管能力。  
  
## <a name="the-cloud-app-security-framework"></a>Cloud App Security 的架構  

|       |   |   |
|-------|---|:---|
|![探索](./media/discovery-icon.png)|探索|揭露 Shadow IT 與 Cloud App Security。 探索雲端環境中的應用程式、活動、使用者、資料和檔案，以及連線至您雲端的協力廠商應用程式，以取得可見度。|
|![調查](./media/investigate-icon.png)|調查|您可使用雲端鑑識調查工具，深入了解具風險的應用程式、特定使用者以及網路中的檔案，並從雲端收集的資料中尋找模式，產生報告以監視雲端，藉此調查雲端應用程式。|
|![控制](./media/protect-icon.png)|控制|設定原則和警示，以盡最大可能控制網路雲端流量並降低風險。 使用 Cloud App Security，將使用者移轉至獲批准的安全雲端應用程式替代方案。|
|![保護](./media/protect-icon.png)|保護|您可使用 Cloud App Security 以批准/不批准應用程式、強制執行資料外洩防護 (DLP)、控制權限和共用，以及產生自訂報告和警示。|


## <a name="architecture"></a>架構  

Cloud App Security 可透過下列方式啟用雲端的可見度整合︰  
  
-   可見度功能，其使用 Cloud Discovery 對應並識別您的雲端環境，以及您已使用的雲端應用程式。  
-   批准/不批准雲端中應用程式的功能。  
-   您所連線之應用程式的可見度和治理功能，其使用易於部署的 App 連線程式 (運用提供者 API )。  
-   連續控制功能，可讓您設定並持續精確微調原則。  
  
![](./media/architecture.png)  
  
> [!NOTE]  
>  當 Cloud App Security 執行內容檢查時，會強制執行資料隱私權。 您的資料不會儲存在 Cloud App Security 資料庫中，而僅會儲存已識別出的檔案記錄與違規中繼資料。 如需資料保留的詳細資訊，請參閱[隱私權原則](http://go.microsoft.com/fwlink/?LinkId=512132)和 [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data)。
Cloud App Security 如下保留資料︰
>- 活動記錄：180 天
>- 探索資料：90 天
>- 警示：無限制 

從這些來源收集資料之後，Cloud App Security 會針對這些資料執行複雜的分析，並提出異常活動的立即警示與深入的可見度。 接著，您可以在 Cloud App Security 中設定原則，然後用它來保護雲端環境中的所有項目。  
  
###  <a name="how-cloud-discovery-works"></a>Cloud Discovery 如何運作  

Cloud Discovery 會使用您的流量記錄，動態探索並分析組織中正在使用的雲端應用程式。  
  
您可以手動從防火牆或 Proxy 上傳用於進行分析的記錄檔來建立組織雲端使用的快照集報告，或使用 Cloud App Security 記錄收集器定期轉送記錄檔來設定連續報告。  

如需 Cloud Discovery 的詳細資訊，請參閱[設定 Cloud Discovery](set-up-cloud-discovery.md)。
  
### <a name="how-sanctioning-and-unsanctioning-an-app-works"></a>批准和不批准應用程式的運作方式  

Cloud App Security 可讓您使用 [雲端應用程式目錄]，決定批准/不批准組織中的應用程式。  
  
Microsoft 的分析師團隊具有非常龐大且持續增加的目錄，其中包含 13000 多種根據業界標準排名和評分的雲端應用程式。 [雲端應用程式目錄] 會依據認證法規、業界標準和最佳做法來進行雲端應用程式的風險分級。 您可以按照組織需求自訂分數和不同參數的加權。 Cloud App Security 會根據這些分數以及 50 多個可能影響環境的風險因素，讓您了解應用程式的風險性。  
  
### <a name="how-app-connectors-work"></a>App 連線程式的運作方式  
App 連線程式可利用各種雲端應用程式提供者所提供的 API，讓 Cloud App Security 雲端與其他雲端應用程式整合，並擴充控制和保護能力。 這可讓 Cloud App Security 直接從雲端應用程式提取資訊，以進行分析。  
為了連線應用程式和擴充保護，應用程式管理員需授與 Cloud App Security 存取應用程式的權限，Cloud App Security 即可查詢應用程式的活動記錄、掃描資料、帳戶和雲端內容。 Cloud App Security 就能強制執行原則、偵測威脅，並提供治理動作來解決問題。  
  
Cloud App Security 利用雲端提供者提供的 API，每個應用程式都有自己的架構和 API 限制。 Cloud App Security 使用應用程式提供者來使 API 的使用達到最佳化，並且確保最佳的效能。 Cloud App Security 引擎會考慮應用程式加諸於 API 的不同限制 (例如節流、API 限制、動態時間調整 API 範圍等)，而利用允許的容量。 某些作業，例如掃描租用戶中的所有檔案，需要大量的 API，因此會分散在較長的時間。 某些原則可能會執行長達幾個小時或幾天。  
  
### <a name="how-policy-control-works"></a>原則控制的運作方式  

您可使用原則來定義您預期使用者在雲端中的行為模式。 原則可讓您偵測雲端環境中具風險的行為、違規或可疑的資料點和活動，必要時，也可整合補救流程，以完全降低風險。 您可使用多種不同類型的原則，將其與想要收集的雲端環境資訊以及想採取的修復動作類型相互關聯。  
  
## <a name="see-also"></a>另請參閱  

[開始使用 Cloud App Security](getting-started-with-cloud-app-security.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


