---
title: "建立工作階段原則，以深入查看使用者工作階段的活動並封鎖下載 | Microsoft Docs"
description: "本主題描述 Cloud App Security Proxy 工作階段原則的設定程序，讓您深入查看使用者工作階段的活動並封鎖下載。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 06ae1763918d44512ff52ad25ca0c0f77bcab3e9
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2018
---
# <a name="session-policies"></a>工作階段原則 

> [!NOTE]
> 這是預覽功能。

Cloud App Security 工作階段原則可以監視即時工作階段，讓您更清楚雲端應用程式，根據您針對使用者工作階段設定的原則，採取不同的動作。 使用工作階段控制可以在允許存取的同時，監視工作階段及/或限制特定的工作階段活動，而不是[完全允許或完全封鎖存取](access-policy-aad.md)。 

例如，您可以決定針對來自受管理裝置或來自特定位置的工作階段，允許使用者存取應用程式，但限制下載機密檔案或要求某些文件的下載保護。 工作階段原則能讓您設定這些使用者工作階段控制。 

## <a name="prerequisites-to-using-session-policies"></a>使用工作階段原則的必要條件

- Azure AD Premium P2 授權
- 相關的應用程式應該要[部署 Proxy](proxy-deployment-aad.md)
- [Azure Active Directory 中的條件式存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)應已就位，可將使用者重新導向至 Cloud App Security Proxy，如下所述。

> [!NOTE]
> - 工作階段原則也支援使用識別提供者所設定的應用程式，而不是私人預覽之 Azure AD 所設定的應用程式。 如需私人預覽的詳細資訊，請傳送電子郵件至 mcaspreview@microsoft.com。

## <a name="create-an-azure-ad-conditional-access-policy"></a>建立 Azure AD 條件式存取原則

Azure Active Directory 條件式存取原則和 Cloud App Security 工作階段原則合作，檢查每個使用者工作階段，並決定每個應用程式的原則。 若要在 Azure AD 中設定條件式存取原則，請遵循此程序：

1. 設定已指派使用者或使用者群組的 [Azure Active Directory 中的條件式存取](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)，以及您想要利用 Cloud App Security Proxy 控制的 SAML 應用程式。 

  > [!NOTE]
  > 這個原則只會影響[部署 Proxy](proxy-deployment-aad.md) 的應用程式。

2. 選取 [工作階段] 刀鋒視窗的 [使用 Proxy 強制的限制]，將使用者路由至 Cloud App Security Proxy。

 ![Azure AD 條件式存取的 Proxy 限制](./media/proxy-deploy-restrictions-aad.png)

## <a name="create-a-cloud-app-security-session-policy"></a>建立 Cloud App Security 工作階段原則 

若要建立新的工作階段原則，請遵循此程序︰

1. 在入口網站中，選取後面跟著 [原則] 的 [控制]。
3. 在 [原則] 頁面中，按一下 [建立原則]，然後選取 [工作階段原則]。  

 ![建立工作階段原則](./media/create-session-policy.png)

4. 在 [工作階段原則] 視窗中，指派原則的名稱，例如「封鎖下載 Box 行銷使用者機密文件」。

 ![新的工作階段原則](./media/new-session-policy.png)

5. 在 [工作階段控制項類型] 欄位中： 

    1. 選取 [監視所有活動]，如果您只想要依使用者監視活動。

    2. 選取 [監視所有活動及控制檔案下載]，如果您想要監視使用者活動並採取其他動作，例如封鎖或保護使用者下載項目。

    ![工作階段原則控制類型](./media/session-policy-control-type.png)

6. 在 [Activities matching all of the following] \(符合下列所有條件的活動) 區段的 [活動來源] 下，選取要套用至原則的其他活動篩選。 這些會包含下列選項︰ 

     - **裝置標記**：用以篩選識別受管理的裝置。

     - **位置**：用以篩選識別不明 (所以有風險) 的位置。 

     - **IP 位址**：用這個篩選依 IP 位址篩選，或使用之前指派的 IP 位址標記篩選。 

     - **使用者代理程式標記**：用以篩選啟用啟發學習法，以識別行動裝置及桌面應用程式。 此篩選可設定為等於或不等於**原生用戶端**，應該分別對每個雲端應用程式的行動裝置版和桌面應用程式版進行測試。
         
         ![原生用戶端支援](./media/user-agent-tag.png)

       >[!NOTE]
       >工作階段原則不支援行動裝置及桌面應用程式。 請務必測試工作階段原則，確定它們不會干擾行動裝置及桌面應用程式的功能。 如有必要，在工作階段原則中排除行動裝置及桌面應用程式。

     ![工作階段原則活動來源](./media/session-policy-activity-filters.png)

7. 如已選取選項 [監視所有活動及控制檔案下載]：

    1. 在 [Files matching all of the following] \(符合下列所有條件的檔案) 區段的 [活動來源] 下，選取要套用至原則的其他檔案篩選。 這些會包含下列選項︰

        - **分類標籤** - 如果您的組織使用 Azure 資訊保護，而且使用它的分類標籤來保護資料，請使用此篩選。 即可在此根據檔案套用的分類標籤篩選檔案。 如需 Cloud App Security 與 Azure 資訊保護整合的詳細資訊，請參閱 [Azure 資訊保護整合](azip-integration.md)。

        - **檔案名稱** - 使用此篩選將原則套用至特定的檔案。

        - **檔案類型** - 使用此篩選將原則套用至特定的檔案類型，例如，封鎖下載所有的 .xls 檔案。

         ![工作階段原則檔案篩選](./media/session-policy-file-filters.png)

        
    2. 在 [內容檢查] 區段中，設定是否啟用 DLP 引擎掃描文件及檔案內容。
 
     ![工作階段原則內容檢查](./media/session-policy-content-inspection.png)

    3. 在 [動作] 下選取下列其中一個選項： 

        - **允許**：設定此動作，根據您設定的原則篩選明確允許下載。

        - **封鎖**：設定此動作，根據您設定的原則篩選明確封鎖下載。 如需詳細資訊，請參閱[封鎖下載的運作方式](#block-download)。

        - **保護**：如果您的組織使用 Azure 資訊保護，您可以設定 [動作]，將您在 Azure 資訊保護中設定的分類標籤套用到檔案。 如需詳細資訊，請參閱[保護下載的運作方式](#protect-download)。

         ![工作階段原則動作](./media/session-policy-actions.png)

10. 您可以 [Create an alert for each matching event with the policy's severity] \(使用原則嚴重性為每個相符的事件建立警示)，然後設定警示限制，選取要以電子郵件和/或來發送警示。

    ![工作階段原則警示](./media/session-policy-alert.png)


## <a name="how-session-monitoring-works"></a>工作階段監視的運作方式

當您建立工作階段原則時，每個符合原則的使用者工作階段都會重新導向至 Proxy 工作階段控制，而不是直接導向至應用程式。 使用者會看到監視通知，知道他們的工作階段受到監視。

   ![工作階段監視通知](./media/session-monitoring-notice.png)

如果您不想通知使用者受到監視，您可以停用通知訊息。

1. 在設定齒輪下，選取 [一般設定]。 

2. 然後，在 Cloud App Security Proxy 設定下，取消選取 [通知使用者] 核取方塊。

    ![停用工作階段監視通知](./media/disable-session-monitoring-notice.png)

為了讓使用者留在工作階段中，Proxy 會使用 Proxy URL 取代應用程式工作階段內所有相關的 URL、Java 指令碼和 Cookie。 例如：如果應用程式傳回的頁面包含以 myapp.com 結尾的網域連結，Proxy 就會使用以類似 myapp.com.cas.ms 結尾的網域來取代這些連結。 這樣 Proxy 就可以監視整個工作階段。

Proxy 會記錄每個經它路由的使用者工作階段流量記錄。 流量記錄包含時間、IP、使用者代理程式、前往過的 URL，以及上傳和下載的位元組數。 這些記錄會予以分析，一份稱為 **Cloud App Security Proxy** 的持續報告會新增至 Cloud Discovery 儀表板中的 Cloud Discovery 報告清單。

![Proxy 報表](./media/proxy-report.png)


匯出這些記錄：

1. 請移至設定齒輪，然後按一下 [Proxy]。
2. 按一下表格右側的 [匯出] 按鈕 ![[匯出] 按鈕](./media/export-button.png). 
3. 選取報表的範圍，然後按一下 [匯出]。 此程序可能需要一些時間。

下載匯出的記錄：

1. 準備好報表後，請依序移至 [調查] 和 [自訂報告]。
2. 在表格中，從 [Proxy traffic logs] \(Proxy 流量記錄) 清單中選取相關的報表，並按一下 [下載] ![下載按鈕](./media/download-button.png)。 


## 封鎖下載的運作方式<a name="block-download"></a>

當 [封鎖] 設為您想要在 Cloud App Security Proxy 工作階段原則中採取的 [動作] 時，Proxy 會根據原則的檔案篩選阻止使用者下載檔案。 下載事件是由每個 SAML 應用程式的 Proxy 所辨識，而當使用者起始此事件時，Proxy 會即時介入，防止事件執行。 收到使用者已起始下載的信號時，Proxy 會將**下載限制**訊息傳回給使用者，以包含可自訂給使用者訊息的文字檔案取代下載的檔案，這可在 Proxy 工作階段原則中設定。  

## 保護下載的運作方式<a name="protect-download"></a>

當 [保護] 設為要在 Cloud App Security Proxy 工作階段原則中採取的 [動作] 時，Proxy 會根據原則的檔案篩選，強制執行檔案標記及後續保護。 [標籤] 是在 Azure 的 Azure 資訊保護主控台中設定，必須在標籤內選取 [保護]，Cloud App Security 原則才會將標籤顯示為選項。 在符合 Cloud App Security 原則的準則下，選取標籤並下載檔案時，檔案會在下載時套用標籤及對應的保護 (具有權限)。 原始檔案仍保持在雲端應用程式中的狀況，而下載的檔案受到保護。 嘗試存取該檔案的使用者必須符合套用保護決定的權限需求。  
 
 
## <a name="see-also"></a>另請參閱  
[使用 Azure AD Proxy 功能封鎖非受控裝置的下載作業](use-case-proxy-block-session-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  