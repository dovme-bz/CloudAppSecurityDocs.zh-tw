---
title: "什麼是 Cloud App Security？ | Microsoft Docs"
description: "本主題說明 Cloud App Security 及其運作方式。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/2/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 041c22aea7ab20682cab199af2a0f17129cade3e
ms.sourcegitcommit: 8c7c25bc727d9c471261da144d5c1d430c26af56
translationtype: HT
---
# <a name="what-is-cloud-app-security"></a>什麼是 Cloud App Security

> [!NOTE]
> 如需進階安全性管理及適用於 Office 365 的 Cloud App Security 相關資訊，請參閱[開始使用進階安全性管理](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a)。

轉移至雲端雖然可增加員工的彈性並降低 IT 成本，但也在維護組織安全方面帶來新的複雜性與挑戰。 若要完整發揮雲端應用程式的優點，IT 團隊必須在支援存取與維持掌控權之間找到適當的平衡，才可保護重要的資料。  

Cloud App Security 是 Microsoft Cloud Security 堆疊的重要元件。 它是全方位的解決方案，可協助組織充分發揮雲端應用程式所保證的優勢，同時透過改良的活動可見度來維持控管能力。 它也能針對跨雲端應用程式的重要資料，協助提供強化的保護。 貴組織可以使用有助找出影子 IT、評估風險、強制執行原則、調查活動並停止威脅的相關工具，更安全地轉移到雲端，同時保有重要資料的控管能力。 

## <a name="the-cloud-app-security-framework"></a>Cloud App Security 的架構  

- **Cloud Discovery**：探索組織中的所有雲端使用，包含 Shadow IT 報告以及控制和風險評估。
    
- **資料保護**︰透過取得可見度、強制執行 DLP 原則、警示和調查，以監視和控制雲端中的資料。 
    
- **威脅保護**︰偵測異常使用和安全性事件。 使用行為分析和進階調查工具來降低風險，以及設定原則和警示，以盡最大可能控制網路雲端流量。

## <a name="architecture"></a>架構  

Cloud App Security 可整合您雲端的可見度，  

-   方法是使用 Cloud Discovery 對應並識別您的雲端環境，以及貴組織正在使用的雲端應用程式。
-   批准及不批准雲端中的應用程式。  
-   使用易於部署且善用提供者 API 的 App 連線程式，以取得您所連接之應用程式的可見度及治理功能。  
-   透過設定並持續精確微調原則，協助您保有掌控度。  

![Cloud App Security 架構圖](./media/architecture.png)  

### <a name="data-retention--compliance"></a>資料保留與相容性

Cloud App Security 通過 Microsoft Compliance 的官方認證，符合 ISO、HIPAA、CSA STAR、歐盟示範條款 (EU Model Clauses) 等等。 若要檢視認證的完整的憑證清單，請前往 [Microsoft Compliance Offerings] (Microsoft Compliance 認證清單) (https://go.microsoft.com/fwlink/?linkid=842039) 選取 [Cloud App Security]。  

當 Cloud App Security 執行內容檢查時，會強制執行資料隱私權。 檔案內容不會儲存在 Cloud App Security 資料庫中；只有檔案記錄的中繼資料或任何已識別的違規會儲存在 Cloud App Security 資料庫中。 如需資料保留的詳細資訊，請參閱[隱私權原則](http://go.microsoft.com/fwlink/?LinkId=512132)及 [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data)。
Cloud App Security 如下保留資料︰ 
 
- 活動記錄：180 天 
- 探索資料：90 天 
- 警示︰180 天 

Cloud App Security 從這些來源收集資料後，即會對資料執行複雜的分析。 它會立即提醒您有異常活動，並讓您深入了解您的雲端環境。 您可以在 Cloud App Security 中設定原則，並使用該原則保護雲端環境中的所有項目。  

### <a name="cloud-discovery"></a>雲端探索  

Cloud Discovery 會使用您的流量記錄，動態探索並分析組織中正在使用的雲端應用程式。 若要建立貴組織雲端使用狀況的快照集報表，您可從防火牆或 Poxy 手動上傳記錄檔進行分析。 若要設定持續報告，請使用 Cloud App Security 記錄收集器定期轉寄您的記錄。  

如需 Cloud Discovery 的詳細資訊，請參閱[設定 Cloud Discovery](set-up-cloud-discovery.md)。

### <a name="sanctioning-and-unsanctioning-an-app"></a>批准及不批准應用程式  

Cloud App Security 可讓您使用 *[雲端應用程式目錄]*，決定批准或不批准組織中的應用程式。 Microsoft 的分析師團隊具有非常龐大且持續增加的目錄，其中包含 13,000 多種根據業界標準排名及評分的雲端應用程式。 您可使用雲端應用程式目錄，依據認證法規、業界標準及最佳做法替您的雲端應用程式風險分級。 接著按照組織需求自訂分數及不同參數的加權。 Cloud App Security 會根據這些分數以及 50 多個可能影響環境的風險因素，讓您了解應用程式的風險性。  

### <a name="app-connectors"></a>App 連線程式  
App 連線程式使用雲端應用程式提供者的 API，將 Cloud App Security 雲端與其他雲端應用程式相整合。 App 連線程式擴充控制及保護。 其同時讓您直接從雲端應用程式存取 Cloud App Security 分析的資訊。  

若要連接應用程式並擴充保護，應用程式管理員可授權 Cloud App Security 存取應用程式。 接著 Cloud App Security 會查詢應用程式的活動記錄，並掃描資料、帳戶及雲端內容。 Cloud App Security 可強制執行原則、偵測威脅，並提供治理動作來解決問題。  

Cloud App Security 使用雲端提供者所提供的 API。 每個應用程式都有自己的架構及 API 限制。 Cloud App Security 利用應用程式提供者使 API 使用情況達到最佳化，並且確保最佳的效能。 Cloud App Security 引擎會將應用程式加諸於 API 的各種限制列入考量 (例如節流、API 限制、動態時間調整 API 範圍)，進而充分利用允許的容量。 某些作業需要大量的 API，例如掃描租用戶中的所有檔案，因此會分散在較長的時間內進行。 請預期某些原則會執行長達幾個小時或幾天。  

### <a name="policy-control"></a>原則控制  

您可以使用原則定義您使用者在雲端中的行為。 使用原則偵測雲端環境中的具風險行為、違規或可疑的資料點與活動。 如有需要，您可使用原則整合補救程序，以完整降低風險。 有多種不同類型的原則，與您想要收集的雲端環境資訊以及您可能要採取的修復動作類型相互關聯。  

## <a name="see-also"></a>另請參閱  

在[開始使用 Cloud App Security](getting-started-with-cloud-app-security.md) 中了解基本概念。    
如需技術支援，請前往 [Cloud App Security 的輔助支援](http://support.microsoft.com/oas/default.aspx?prid=16031)頁面。   
頂級客戶也可以直接從[頂級支援入口網站](https://premier.microsoft.com/)選擇 Cloud App Security。   
