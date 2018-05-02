---
title: 為 Azure AD 應用程式部署 Cloud App Security Proxy | Microsoft Docs
description: 本主題提供如何為 Azure AD 應用程式部署 Microsoft Cloud App Security Proxy 的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 64742336717e202f7080a37f447672b953cf124a
ms.sourcegitcommit: 45311f2cafef79483e40d971a4c61c7673834d96
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2018
---
*適用於：Microsoft Cloud App Security*

# <a name="deploy-proxy-for-azure-ad-apps"></a>為 Azure AD 應用程式部署 Proxy

> [!NOTE]
> 這是預覽功能。

請遵循下列步驟，將 Azure AD 應用程式設定為由 Microsoft Cloud App Security Proxy 進行控制。

> [!NOTE]
> 若要為 Azure AD 應用程式部署 Cloud App Security Proxy，您必須具備有效 [Azure AD Premium P2 的授權](https://docs.microsoft.com/azure/active-directory/license-users-groups)。

## <a name="step-1-add-azure-ad-apps-in-cloud-app-security"></a>步驟 1：在 Cloud App Security 中新增 Azure AD 應用程式  

1. 建立 Azure AD 條件式存取 TEST 原則。

   1. 在 Azure Active Directory 的 [安全性] 下，按一下 [條件式存取]。

      ![Azure AD 條件式存取](./media/aad-conditional-access.png)

   2. 按一下 [新增原則] 並建立新的原則，確定選取 [工作階段] 下的 [使用 Proxy 強制的限制]。

      ![Azure AD 條件式存取](./media/proxy-deploy-restrictions-aad.png)

   3. 在 TEST 原則的 [使用者] 下，指派測試使用者或可用於初始登入的使用者。
    
   4. 在 TEST 原則的 [雲端應用程式] 下，指派您要使用 Proxy 控制的應用程式。 

      > [!NOTE]
      >請確定 Proxy 支援您選擇的應用程式。 Proxy 支援在 Azure AD 中設定使用 SAML 單一登入的應用程式。 例如，Office 365 應用程式不設定使用 SAML，所以目前不受支援。


2. 在您建立原則之後，使用原則中設定的使用者，登入原則中設定的每個應用程式。 請務必先登出現有的工作階段。

3. 在 Cloud App Security 入口網站中，移至 [設定] 齒輪，然後選擇 [Proxy]。 
    
     ![Proxy 功能表](./media/proxy-menu.png)

4. 您應該會看到一則訊息，告知您 Proxy 探索到新的 Azure AD 應用程式。 按一下 [檢視新的應用程式] 連結。

   ![Proxy 檢視新的應用程式](./media/proxy-view-new-apps.png)

5. 在開啟的對話方塊中，您可以看到在上一個步驟中登入的所有應用程式。 對於每個應用程式，請按一下 + 符號，然後按一下 [新增]。

   ![Proxy 新的應用程式](./media/proxy-new-app.png)

   > [!NOTE]
   > 如果應用程式未出現在 Cloud App Security 應用程式目錄中，則會連同登入 URL 顯示在此對話方塊中無法辨識的應用程式下。 針對這些應用程式按一下 + 符號時，便能夠建議將應用程式新增至目錄。 在應用程式位於目錄中之後，請再次執行這些步驟來部署應用程式。 

6. 在 Proxy 應用程式資料表中，查看 [可用的控制項] 資料行，並確認 Azure AD 條件式存取和工作階段控制項都會出現。 <br></br>如果應用程式中未出現工作階段控制項，這表示工作階段控制項還無法用於該特定應用程式，您將改為看到 [要求工作階段控制項] 連結。 請按一下該連結以開啟對話方塊，並要求將應用程式上架到工作階段控制項。 在 Proxy 公開預覽期間，上架程序將由 Cloud App Security 小組與您一起執行。
  
   ![要求工作階段控制項](./media/request-session-control.png)

7. 選用 - 使用用戶端憑證識別裝置：

   1. 移至 [設定] 齒輪，然後選擇 [裝置識別]。

   2. 上傳根憑證。

      ![裝置識別](./media/device-identification.png)
 
      上傳憑證之後，您可以根據 [裝置標籤] 等於或不等於 [有效的用戶端憑證] 來建立存取原則和工作階段原則。
 
      > [!NOTE]
      >如果工作階段符合使用有效用戶端憑證篩選條件的原則，則只會向使用者要求憑證。 

## <a name="step-2-test-the-deployment"></a>步驟 2：測試部署

1. 首先，登出任何現有的工作階段。 接著，使用符合 Azure AD 所設定之原則的使用者，嘗試登入已順利部署的每個應用程式。 

2. 在 Cloud App Security 入口網站的 [調查] 下，選取 [活動記錄]，並確定已為每個應用程式擷取登入活動。

3. 您可以按一下 [進階]，然後使用 [來源等於 Azure Active Directory 條件式存取] 來進行篩選。

    ![使用 Azure AD 條件式存取進行篩選](./media/sso-logon.png)

4. 建議您從受管理和未受管理的裝置登入行動及桌面應用程式，以確定活動已正確擷取在活動記錄中。<br></br>
   若要確認已正確擷取活動，請按一下單一登入的登入活動，讓它開啟活動隱藏式選單，並確定 [使用者代理程式標籤] 正確反映出裝置是原生用戶端 (表示是行動或桌面應用程式) 或裝置是受管理裝置 (相容、已加入網域或有效的用戶端憑證)。
 
   ![測試使用者代理程式標籤](./media/domain-joined.png)


您現在已準備好建立[存取原則](access-policy-aad.md)和[工作階段原則](session-policy-aad.md)來控制 Proxy 應用程式。



## <a name="see-also"></a>另請參閱  
[使用 Cloud App Security Proxy](proxy-intro-aad.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  