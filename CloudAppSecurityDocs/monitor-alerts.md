---
title: 在 Cloud App Security 中使用警示 | Microsoft Docs
description: 本主題提供所有警示的清單和描述。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: f118a3bf-1663-46ba-884f-b1b03a84ab66
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c542968b0946dad903d0e77e9f44c92d957cc8e1
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143508"
---
*適用於：Microsoft Cloud App Security*

# <a name="alerts"></a>警示
檢視警示：

在 Microsoft Cloud App Security 入口網站中，按一下 [警示]。


![警示功能表](./media/alert-menu.png)

當您查看警示後發現不相關，您可以將其 [關閉]。 您可以輸入註解來說明關閉警示的原因，也可以**傳送意見反應給 Cloud App Security 小組**。 我們的安全性研究小組會檢閱意見反應，以持續改進警示機制。 

若您調查警示並降低風險，隨後即可 [解決] 警示。 警示表格中就不會再顯示該警示。 若您已開始調查問題，但想要確保您會記得繼續，可以將問題 [標記為未讀取]。 您也可以**調整符合警示的原則**，以利改善往後的警示比對。 解決警示也會提供選項，讓您能夠輸入註解及**傳送意見反應給 Cloud App Security 小組**。



將會顯示下列警示類型。 

## <a name="built-in-alerts"></a>內建警示

|警示名稱|AlertID|說明|
|----|----|----|
|新增位置|ALERT_GEOLOCATION_NEW_COUNTRY|在掃描開始 (最多 6 個月) 後偵測到新位置。 這只會對整個組織的每個國家 (地區) 顯示一次。 |
|新增管理使用者|ALERT_ADMIN_USER|偵測到特定應用程式的新管理員 – 這可以是某個應用程式中之管理員但現在是另一個應用程式中之管理員的人員。 此警示與特定管理員類型相關，因此會在每次變更管理員類型時顯示。 如果使用者遺失後再次取得管理員權限，則會顯示此警示。|
|非使用中帳戶|ALERT_ZOMBIE_USER|如果單一個應用程式的使用者未使用 60 天；例如，如果有人使用 Box 但未接觸 G Suite 60 天，則使用者在 G Suite 中視為非使用中。 標記已新增至這些使用者，因此您可以搜尋非作用中帳戶。|
|未預期的管理員位置|ALERT_NEW_ADMIN_LOCATION|在掃描開始 (最多 6 個月) 後偵測到系統管理員的新位置。 這只會對您組織之任何管理員的每個國家 (地區) 顯示一次。 |
|遭盜用的帳戶|ALERT_COMPROMISED_ACCOUNT|如果應用程式中發生中斷，並且發行中斷帳戶清單，則 Cloud App Security 會下載清單，並將它與您的使用者清單進行比較 (包括內部使用者、外部使用者和個人帳戶)。 |

## <a name="custom-alerts"></a>自訂警示

|警示名稱|AlertID|說明|
|----|----|----|
|可疑活動警示|ALERT_SUSPICIOUS_ACTIVITY|可疑活動會根據異常活動的可疑程度進行評分 (是否包含非使用中帳戶？ 它是否來自新的位置？)這些準則都會一起計算，以根據下列風險因素來提供風險分數︰ <br>使用者是系統管理員 <br>純遠端使用者<br>匿名 Proxy<br> 整個工作階段讓登入失敗<br>許多失敗登入<br>新增 (管理員)<br>IP/ISP/國家 (地區)/使用者的使用者代理程式/租用戶<br> IP/ISP/國家 (地區)/僅供 (管理員) 使用者使用的使用者代理程式<br>第一個 (管理員) 使用者活動執行一段時間<br>第一次執行這個特定管理活動一段時間<br>這個特定管理活動不常見/之前未曾執行過<br>過去，此 IP 只會讓登入失敗<br>不可能的旅遊|
|可疑的雲端使用警示|ALERT_DISCOVERY_ANOMALY_DETECTION|Cloud Discovery 異常偵測會檢查一般行為模式，並尋找以異常方式使用的使用者或應用程式。 |
|活動原則違規|ALERT_CABINET_EVENT_MATCH_AUDIT|此警示可讓您知道何時偵測到原則相符項目。|
|檔案原則違規|ALERT_CABINET_EVENT_MATCH_FILE|此警示可讓您知道何時偵測到原則相符項目。|
|Proxy 原則違規|ALERT_CABINET_INLINE_EVENT_MATCH|此警示可讓您知道何時偵測到原則相符項目。|
|欄位原則違規|ALERT_CABINET_EVENT_MATCH_OBJECT|此警示可讓您知道何時偵測到原則相符項目。|
|探索到新的服務|ALERT_CABINET_DISCOVERY_NEW_SERVICE|發現新的應用程式。|
|使用個人帳戶|ALERT_PERSONAL_USER_SAGE|根據檔案共用和使用者名稱，偵測引擎會搜尋個人帳戶。 |

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  