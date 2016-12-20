---
title: "連接 Office 365 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 Office 365 連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: e0ca79daddaaa2cdcbc51308653b3ec05da1b5e2


---

# <a name="connect-office-365-to-microsoft-cloud-app-security"></a>將 Office 365 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用 App 連線程式 API，將 Cloud App Security 連接至您現有的 Microsoft Office 365 帳戶。  
  
  

## <a name="how-to-connect-office-365-to-cloud-app-security"></a>如何將 Office 365 連接至 Cloud App Security  
  
> [!NOTE]
>- 您必須至少獲得一個指派的 Office 365 授權，才能連接 Office 365 與 Cloud App Security。
>-  Office 365 預設會啟用 Exchange 系統管理員稽核記錄功能，當系統管理員 (或已獲得系統管理權限指派的使用者) 在您的 Exchange Online 組織中進行變更時，這項功能即會將事件記錄至 Office 365 稽核記錄中。 使用 Exchange 系統管理中心進行的變更，或是在 Windows PowerShell 中執行 Cmdlet 所做的變更，皆會記錄在 Exchange 系統管理稽核記錄檔中。 如需 Exchange 系統管理員稽核記錄功能的詳細資訊，請參閱 [Administrator audit logging](http://go.microsoft.com/fwlink/p/?LinkID=619225) (系統管理員稽核記錄)。
>- 您必須開啟每個使用者信箱的 Exchange 信箱稽核記錄功能，才能記錄 Exchange Online 中的使用者活動，請參閱 [Exchange 信箱活動](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。
>- 如果已啟用 Office 應用程式，則特定 Office 應用程式中也會建立屬於 Office 365 的群組。好比說，如果已啟用 SharePoint，則 SharePoint 中也會建立 Office 365 群組。
 
1.  在 [連線應用程式] 頁面中，按一下加號按鈕並選取 [Office 365]。  

2.  在 Office 365 快顯視窗中，按一下 [連線至 Office 365]。

      ![連接 0365](./media/connect-0365.png) 
 
3.  按一下 [立即測試] 以測試 Office 365 的連線。 測試可能需要幾分鐘的時間。
  
    ![O365 測試連線](./media/o365-test-connection.png) 
 
4.   顯示已成功連接 Office 365 之後，請按一下 [關閉]。
  
     ![O365 已連接](./media/o365-connected.png) 

> [!NOTE] 
> 連接 Office 365 之後，您會看到一週前的資料，包括任何連接到 Office 365 以提取 API 的協力廠商應用程式。 若是在連線之前並未提取 API 的協力廠商應用程式，由於 Cloud App Security 會開啟任何預設為關閉的 API，因此您會看到自連接 Office 365 起的事件。

## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


