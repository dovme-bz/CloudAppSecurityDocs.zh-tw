---
title: 連接 Office 365 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs
description: 本主題提供如何使用 API 連接器將 Office 365 連接至 Cloud App Security 的資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/30/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f37b1a828ab13bd2b66a9b43bcb2c625fab0cc00
ms.sourcegitcommit: af8fad9709171b200699ca1ed513e2831826ed7e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2018
ms.locfileid: "34568436"
---
*適用於：Microsoft Cloud App Security*



# <a name="connect-office-365-to-microsoft-cloud-app-security"></a>將 Office 365 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連線程式 API，將 Microsoft Cloud App Security 連接至您現有的 Microsoft Office 365 帳戶。  
  
Cloud App Security 支援舊版 Office 365 專用平台，以及 Office 365 服務的最新供應項目 (通常稱為 Office 365 的 vNext 版系列)。  Cloud App Security 不支援舊版 Microsoft Business Productivity Online Standard Suite。 

> [!NOTE]
> 在某些情況下，vNext 服務版本在系統管理和一般管理層級方面，與標準 Office 365 供應項目稍有不同。

Cloud App Security 支援下列 Office 365 應用程式：

- Office 365
- SharePoint
- OneDrive
- Teams (只有在入口網站中偵測到來自 Teams 的活動之後才會出現)
- PowerBI (只有在入口網站中偵測到來自 PowerBI 的活動之後才會出現，而且需要您開啟稽核)
- Exchange (只有在入口網站中偵測到來自 Exchange 的活動之後才會出現，而且需要您開啟稽核)

 
## <a name="how-to-connect-office-365-to-cloud-app-security"></a>如何將 Office 365 連接至 Cloud App Security  
  
> [!NOTE]
>- 您必須至少獲得一個指派的 Office 365 授權，才能連接 Office 365 與 Cloud App Security。
>-  Office 365 預設會啟用 Exchange 系統管理員稽核記錄功能，當系統管理員 (或已獲得系統管理權限指派的使用者) 在您的 Exchange Online 組織中進行變更時，這項功能即會將事件記錄至 Office 365 稽核記錄中。 使用 Exchange 系統管理中心進行的變更，或是在 Windows PowerShell 中執行 Cmdlet 所做的變更，皆會記錄在 Exchange 系統管理稽核記錄檔中。 如需 Exchange 系統管理員稽核記錄功能的詳細資訊，請參閱 [Administrator audit logging](http://go.microsoft.com/fwlink/p/?LinkID=619225) (系統管理員稽核記錄)。
>- 您必須針對每個使用者信箱開啟 Exchange 信箱稽核記錄功能，才能記錄 Exchange Online 中的使用者活動，請參閱 [Exchange 信箱活動](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。
>- 如果已啟用 Office 應用程式，則屬於 Office 365 的群組也會從特定 Office 應用程式匯入 Cloud App Security。例如，如果已啟用 SharePoint，則會匯入 Office 365 群組與 SharePoint 群組。
>- 您必須[在 PowerBI 中啟用稽核](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/)才能從中取得記錄檔。 啟用稽核之後，Cloud App Security 便開始取得記錄檔 (具有 24-72 小時的延遲)。
> 如果您的 Azure Active Directory 已設定為與 Active Directory 內部部署環境中的使用者自動同步，內部部署環境中的設定將會覆寫 Azure AD 設定，且會還原 [暫時停止使用者的權限] 治理動作的使用。 
 
1.  在 [連線應用程式] 頁面中，按一下加號按鈕並選取 [Office 365]。  

      ![連接 0365](./media/connect-0365.png) 

2.  在 Office 365 快顯視窗中，按一下 [連接 Office 365]。

      ![連接 0365](./media/office-connect.png) 
 
3.   顯示已成功連接 Office 365 之後，請按一下 [關閉]。
  
> [!NOTE] 
> 連接 Office 365 之後，您會看到一週前的資料，包括任何連接到 Office 365 以提取 API 的協力廠商應用程式。 針對在連線之前並未提取 API 的協力廠商應用程式，由於 Cloud App Security 會開啟所有預設為關閉的 API，因此您會看到從連線至 Office 365 開始的所有事件。

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  