---
title: "整合 Azure Information Protection 與 Cloud App Security | Microsoft Docs"
description: "本文提供如何在 Cloud App Security 中使用 Azure Information Protection 標籤，提升您對組織之雲端應用程式的控制程度。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 64fd889e309be254d5aa99320e040129a5de8e1d
ms.sourcegitcommit: fbeb299e8c41fc57b50d491b1becbf488fdd3642
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2017
---
# <a name="azure-information-protection-integration"></a>Azure 資訊保護整合

Cloud App Security 可讓您調查檔案，並依據 Azure Information Protection 分類標籤設定原則，提升您監視及控制雲端上敏感性資料的能力。 整合 Azure Information Protection 與 Cloud App Security 就像選取一個單一核取方塊一樣簡單。 

將 Azure Information Protection 整合到 Cloud App Security，即可利用這兩個服務的完整功能，以及保護雲端中的檔案，包括︰
- 在集中位置檢視所有分類檔案的能力
- 根據分類層級執行調查以及量化雲端應用程式上敏感性資料暴露的能力
- 建立原則以確認正確處理分類檔案的能力

> [!NOTE] 
> 若要能夠執行此功能，除了需要 Cloud App Security 授權之外，也需要 Azure Information Protection Premium P1 或 P2 的授權。 當這項兩種授權準備就緒之後，Cloud App Security 便會從 Azure 資訊保護服務同步組織標籤。
> Cloud App Security 不支援 Azure 資訊保護限域原則。


## <a name="how-it-works"></a>運作方式
您可能熟悉 [Azure Information Protection](https://docs.microsoft.com/information-protection/) 中的檔案分類標籤。 您可以在 Cloud App Security 中查看 Azure Information Protection 分類標記。 整合 Cloud App Security 與 Azure Information Protection 之後，Cloud App Security 就會如下所述掃描檔案：
1. Cloud App Security 會擷取您租用戶所使用的所有分類標籤清單。 每隔一小時會執行一次，使清單維持最新狀態。
2. Cloud App Security 接著會掃描檔案是否有分類標籤，如下所示︰a. 如果您已啟用自動掃描 (請參閱後文)，則會將所有新的或修改過的檔案新增至掃描佇列。
    b. 如果您設定檔案原則 (請參閱後文) 以搜尋分類標籤，則會將這些檔案新增至分類標籤的掃描佇列。
3. 如上所述，這些掃描是針對 Cloud App Security 執行初始掃描時所發現的分類標籤，以查看租用戶所使用的分類標籤。 外部標籤 (租用戶外部人員所設定的分類標籤) 會新增至分類標籤清單。 若不想掃描，請選取 [Only scan files for Azure Information Protection classification labels from this tenant] \(只掃描此租用戶的 Azure 資訊保護分類標籤) 核取方塊 (請參閱後文)。
4. 在 Cloud App Security 上啟用 Azure Information Protection 之後，也會掃描所有已新增至 Office 365 的新檔案是否有分類標籤。

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>如何整合 Azure Information Protection 與 Cloud App Security
  
### <a name="enable-azure-information-protection"></a>啟用 Azure Information Protection

整合 Azure Information Protection 與 Cloud App Security 時，您只需要：啟用自動掃描以在 Office 365 檔案搜尋 Azure Information Protection 分類標籤，而不需要建立一個原則。 啟用這項功能之後，如果您有雲端環境中標上 Azure Information Protection 分類標籤的檔案，則會在 Cloud App Security 中看到它們。

讓 Cloud App Security 掃描已啟用分類標籤內容檢查的檔案：

1. 在 Cloud App Security 的 [設定] 齒輪下，選取 [一般設定] 頁面。
2. 在 Azure 資訊保護下，選取 「Automatically scan files for Azure Information Protection classification labels」 (自動掃描檔案尋找 Azure 資訊保護分類標籤)。 

啟用 Azure Information Protection 之後，就可以在 Cloud App Security 中查看具有分類標籤的檔案以及根據標籤進行篩選。

 ![啟用 Azure Information Protection](./media/enable-azip.png)

> [!NOTE] 
> 自動掃描不會掃描現有的檔案，直到這些檔案經過修改為止。 若要掃描現有檔案是否有 Azure 資訊保護分類標籤，您至少要有一項**內容檢查檔案原則**。 如果完全沒有的話，請建立新的**檔案原則**、刪除所有預設篩選，並選取 [內容檢查] 選項。 接著在 [內容檢查] 下，按一下 [Include files that match a preset expression (包含符合預設運算式的檔案)] 並選取任何預先定義的值，然後儲存原則。 如此便可啟用內容檢查，以自動偵測 Azure 資訊保護分類標籤。

### <a name="set-internal-and-external-tags"></a>設定內部和外部標記
Cloud App Security 預設會掃描組織中所定義的分類標籤，以及其他組織所定義的外部分類標籤。 


若要忽略在組織外部設定的分類標籤，請在 Cloud App Security 入口網站，從 [一般設定] 的 [Auzre 安全性設定] 下，選取 [Ignore Azure Information Protection classification labels from other tenants]\(忽略其他租用戶的 Azure Information Protection 分類標籤)。
 
![忽略標籤](./media/azip-ignore.png)

### <a name="control-file-exposure"></a>控制檔案暴露
- 如果這是您使用 Azure 資訊保護分類標籤標來標籤的文件︰

![Azure 資訊保護範例畫面](./media/azip-screen.png)

- 篩選分類標籤之後，即可在 Cloud App Security 的 [檔案] 頁面中看到此檔案︰

![Cloud App Security 與 Azure 資訊保護的比較](./media/cas-compared-azip.png)

- 您可以取得檔案抽屜中這些檔案和其分類標籤的詳細資訊。

- 在 [檔案] 頁面中，按一下相關檔案以查看其中是否有任何分類標籤：

![檔案抽屜](./media/azip-file-drawer.png)

- 您可以按一下分類標籤檢視更多資訊，或查看完整分類標籤清單：
 
![標籤清單](./media/azip-tags-list.png)

- 接著，您可以在 Cloud App Security 建立檔案原則，以控制不當共用的檔案，以及找到已標示標籤但近期曾修改過的檔案。
- 此外，您可對與分類檔案相關的活動觸發警示。

![Cloud App Security 中的 Azure 資訊保護標籤](./media/azip-tags-in-cas.png)

> [!Note]
> 當停用檔案上的 Azure Identity Protection 標籤時，停用的標籤在 Cloud App Security 中會顯示為「已停用」。 已刪除的標籤則不會顯示。


**原則 #1 - 在 Box 上對外共用機密資料：** 

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找在 Box 上對外共用的所有機密資料：

![機密性原則](./media/azip-confidentiality-policy.png) 

**原則 #2 - 受限制的資料最近曾在 SharePoint 的 Finance 資料夾以外之處修改過：**

1.  建立檔案原則。
2.  設定原則的名稱、嚴重性及類別。
3.  新增下列篩選尋找所有最近曾經修改過之受限制的資料，並在資料夾選擇選項中新增排除 Finance 資料夾： 
 
![受限制的資料原則](./media/azip-restricted-data-policy.png) 

您也可以為這些原則選擇設定警示、使用者通知或立即採取行動。
深入了解[管理動作](governance-actions.md)。

深入了解 [Azure 資訊保護](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection)及查看 Azure 資訊保護[快速入門教學課程](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial)。


## <a name="integration-with-azure-rights-management"></a>與 Azure 版權管理整合

您的組織必須具有 Azure 版權管理的授權，並已啟用來在 Cloud App Security 與 Azure RMS 之間進行整合。 這兩個不同的步驟可已在[啟用 Azure 版權管理](https://docs.microsoft.com/information-protection/deploy-use/activate-service)中找到。

Cloud App Security 目前支援 Office 檔案的原生保護 (2016 和更新版本)。 未來版本會提供對 PDF 和影像檔案的原生保護。 

此功能目前適用於儲存於SharePoint Online 和商務用 OneDrive 中的檔案。 未來版本中將支援更多雲端應用程式。

將 Cloud App Security 連線到您的 Office 365 服務之後，您將能夠使用 Cloud App Security RMS 整合功能，可讓您直接在 Cloud App Security 入口網站中使用 RMS 保護文件：

1. 從 [檔案] 頁面上，選取您要保護的檔案，然後按一下檔案資料列結尾的三個點，接著選擇 [保護]。 
![保護應用程式](./media/protect-app.png)
>[!NOTE]
>Azure 資訊保護所保護的檔案，其大小上限為 50 MB。 

2. 系統會要求您選擇組織的其中一個分類標籤，用以保護檔案，然後按一下 [保護]。 
![保護分類標籤](./media/protect-template.png)
3. 當您選擇分類標籤並按一下 [保護]之後，Cloud App Security 會套用分類標籤並保護原始檔案。
> [!NOTE]
>   建議您在檔案上套用全公司適用的 RMS 分類標籤，讓組織中的所有使用者都可存取這些檔案，包括檔案的原始擁有者。 檔案的擁有者、檔案的共用原則，以及已經有權存取它的使用者清單，不會在檔案變成受保護狀態時變更。

4. 如果使用者想要存取受保護的檔案，他們必須已在其裝置上安裝 RMS 共用應用程式。 如需詳細資訊，請參閱 [Microsoft Rights Management 共用應用程式技術概觀與保護詳細資料](https://docs.microsoft.com/information-protection/rms-client/sharing-app-admin-guide-technical)。

5. 您可以隨時都能在 [治理記錄] 中，於先前採取之 [保護] 動作的資料列結尾按一下 [還原] 按鈕來還原此動作。 


如需 Cloud App Security 與 Azure 資訊保護如何搭配使用的詳細資訊，請參閱[保護資料不受使用者錯誤影響](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake)。

 
## <a name="related-videos"></a>相關影片  
[Cloud App Security 與 Azure 資訊保護的整合](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  \(英文\)。  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
