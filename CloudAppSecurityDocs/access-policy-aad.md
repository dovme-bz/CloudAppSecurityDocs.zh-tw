---
title: 建立允許及封鎖存取的 Cloud App Security 存取原則 | Microsoft Docs
description: 本主題描述設定 Cloud App Security 條件式存取應用程式控制原則的程序，以使用反向 Proxy 功能允許和封鎖透過 Azure AD 連線的應用程式存取。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 9095cff1-f8b0-44a7-b1df-a83e674abbc6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7188174777e87293576f20cbd6ee512b82e51b8e
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143119"
---
*適用於：Microsoft Cloud App Security*

# <a name="access-policies"></a>存取原則 



>[!div class="step-by-step"]
[« 上一篇：如何建立工作階段原則](session-policy-aad.md)<br>
[下一篇：探索熱門使用案例 »](use-case-proxy-block-session-aad.md)


Microsoft Cloud App Security 的存取原則可以根據使用者、位置、裝置和應用程式，即時監視和控制對雲端應用程式的存取。 您可以推出受控裝置的用戶端憑證，或利用現有的憑證，例如協力廠商 MDM 憑證，建立任何裝置的存取原則，包括未加入網域的裝置，以及不受 Windows Intune 管理的裝置。 例如，您可以將用戶端憑證部署到受控裝置，然後封鎖無憑證裝置的存取。 

> [!NOTE]
> 使用[工作階段原則](session-policy-aad.md)可以在允許存取的同時，監視工作階段及/或限制特定的工作階段活動，而不是完全允許或完全封鎖存取。 

## <a name="prerequisites-to-using-access-policies"></a>使用存取原則的必要條件

- Azure AD Premium P1 授權
- 相關的應用程式應該要[部署條件式存取應用程式控制](proxy-deployment-aad.md)
- [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)應已就位，可將使用者重新導向至 Microsoft Cloud App Security，如下所述。

> [!NOTE]
> - 存取原則也支援設定使用 Azure AD 以外之識別提供者的應用程式。 如需詳細資訊，傳送電子郵件至 mcaspreview@microsoft.com。

## <a name="create-an-azure-ad-conditional-access-policy"></a>建立 Azure AD 條件式存取原則

Azure Active Directory 條件式存取原則和 Cloud App Security 工作階段原則合作，檢查每個使用者工作階段，並決定每個應用程式的原則。 若要在 Azure AD 中設定條件式存取原則，請遵循此程序：

1. 設定已指派使用者或使用者群組的 [Azure AD 條件式存取原則](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)，以及您想要利用條件式存取應用程式控制進行控制的 SAML 應用程式。 

   > [!NOTE]
   > 這個原則只會影響已[部署條件式存取應用程式控制](proxy-deployment-aad.md)的應用程式。

2. 選取 [工作階段] 刀鋒視窗的 [Use Conditional Access App Control enforced restrictions] \(使用條件式存取應用程式控制強制的限制\)，將使用者路由至 Microsoft Cloud App Security。
 
## <a name="create-a-cloud-app-security-access-policy"></a>建立 Cloud App Security 存取原則 

若要建立新的存取原則，請遵循此程序︰

1. 在入口網站中，選取後面跟著 [原則] 的 [控制]。
2. 在 [原則] 頁面中，按一下 [建立原則]，然後選取 [存取原則]。  

3. 在 [存取原則] 視窗中指派原則名稱，例如「封鎖不受控裝置的存取」。

4. 在 [Activities matching all of the following] \(符合下列所有條件的活動) 區段的 [活動來源] 下，選取要套用至原則的其他活動篩選。 這些會包含下列選項︰ 
     
   - **裝置標記**：用以篩選識別受管理的裝置。

   - **位置**：用以篩選識別不明 (所以有風險) 的位置。 

   - **IP 位址**：用這個篩選依 IP 位址篩選，或使用之前指派的 IP 位址標記篩選。 

   - **使用者代理程式標記**：用以篩選啟用啟發學習法，以識別行動裝置及桌面應用程式。 此篩選可設定為等於或不等於**原生用戶端**，應該分別對每個雲端應用程式的行動裝置版和桌面應用程式版進行測試。
  
5. 在 [動作] 下選取下列其中一個選項： 

    - **允許**：設定此動作，根據您設定的原則篩選明確允許存取。

    - **封鎖**：設定此動作，根據您設定的原則篩選明確封鎖存取。 

6. 您可以 [Create an alert for each matching event with the policy's severity] \(使用原則嚴重性為每個相符的事件建立警示)，然後設定警示限制，選取要以電子郵件和/或來發送警示。



>[!div class="step-by-step"]
[« 上一篇：如何建立工作階段原則](session-policy-aad.md)<br>
[下一篇：探索熱門使用案例 »](use-case-proxy-block-session-aad.md)

 
## <a name="see-also"></a>另請參閱  
[使用 Azure AD 條件式存取應用程式控制功能封鎖非受控裝置的下載作業](use-case-proxy-block-session-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  