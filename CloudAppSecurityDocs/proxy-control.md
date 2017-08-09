---
title: "建立原則來控制搭配 Cloud App Security Proxy 使用的雲端應用程式 | Microsoft Docs"
description: "本主題提供如何建立原則來控制搭配 Cloud App Security Proxy 使用之雲端應用程式的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/16/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b419aff0-3f50-4917-9ee2-9ecf7539a5d7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4544f5b48484f9341bb85d09d8fdc8d11fd4ba00
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/03/2017
---
# <a name="controlling-app-use-with-proxy-control"></a>控制搭配 Proxy 控制使用的應用程式

部署 Proxy 之後，您可以在貴組織的雲端中建立原則來封鎖未經授權的存取和行為，來控制存取和工作階段。

## <a name="create-access-control-policies-in-cloud-app-security"></a>在 Cloud App Security 中建立存取控制原則

建立存取控制原則：

1.  在 [控制] 下，選取 [原則]。

2.  在 [建立原則] 下，選擇 [Proxy 原則]，然後在 [活動類型] 選取 [單一登入式登入]。

3.  然後，選擇相關的應用程式和篩選，並選擇您偏好的緩和選項。

>[!NOTE]
> 在篩選中，您可以選擇 [裝置標籤] 並將它設為等於或不等於 [受管理的裝置]。 如需[受管理的裝置](#_Managed_devices)的詳細資訊，請參閱下面。

也請注意，在 [緩和的動作] 中，您可以選擇 [記錄] 或 [封鎖存取]，或選擇 [路由至 Cloud App Security]，這能讓您在工作階段上監視及建立原則。 這在[在 Cloud App Security 中建立工作階段控制原則](#_Creating_session_control)中有進一步的說明。

## <a name="create-session-control-policies-in-cloud-app-security"></a>在 Cloud App Security 中建立工作階段控制原則 

部署 Proxy 之後，您可以在 Cloud App Security 入口網站中定義工作階段原則，來新增工作階段控制功能。

我們建議您先為一小群使用者啟用工作階段控制，再部署到整個組織。 此外，我們不建議為所有工作階段或大部分工作階段啟用工作階段控制。 因為工作階段控制所根據的無代理程式部署有其限制，所以它是特別設計來涵蓋對裝置和應用程式只有有限控制或無法控制的案例。

建立工作階段控制原則：

1.  建立[存取原則](#working-with-proxy-control-features)，然後對於 [緩和的動作] 選擇 [路由至 Cloud App Security]。

2.  在 [控制] 下，移至 [原則]，然後在 [建立原則] 下選擇 [Proxy 原則]。

3.  然後對於 [活動類型] 選擇 [下載檔案] 或 [匯出報告]。 選擇相關的應用程式和篩選，並視需要選擇緩和選項。

## <a name="enabling-managedunmanaged-device-control"></a>啟用受管理/未受管理的裝置控制

### <a name="step-1-deploy-certificates"></a>步驟 1：部署憑證

為了讓 Cloud App Security 識別連線到您雲端的裝置是受管理的裝置或未受管理的裝置，您必須部署用戶端憑證。 執行的方式很多，通常是利用現有的行動裝置管理解決方案的憑證，或使用 Active Directory 群組原則。

### <a name="step-2-upload-the-root-certificate-to-cloud-app-security"></a>步驟 2：上傳根憑證至 Cloud App Security

若要在 Cloud App Security 入口網站中識別受管理的裝置，您必須先上傳憑證授權單位的根憑證：

1.  按一下 [設定] 齒輪，然後選擇 [受管理的裝置]。

2.  啟用 [裝置識別]。

3. 上傳根憑證。

![cloud app security proxy 受管理的裝置憑證](./media/managed-device-cert.png)

### <a name="step-3-create-managed-device-policies"></a>步驟 3：建立受管理的裝置原則

上傳根憑證之後，使用篩選 [裝置標籤] 等於或不等於 [受管理的裝置] 來建立 Proxy 原則，或搜尋 [活動] 記錄中的事件。

使用用戶端憑證來識別受管理的裝置時，我們建議先以監視模式開始，然後再嘗試封鎖或監視工作階段。 這表示您使用緩和的動作是 [僅限記錄] 的 [受管理的裝置] 篩選來定義存取原則。 您在使用者部分獲得經驗之後，就可以新增其他緩和動作，例如封鎖存取或監視工作階段。


## <a name="see-also"></a>另請參閱  
[使用 Cloud App Security Proxy](proxy-intro.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  