---
title: SIEM 與 Cloud App Security 的整合 | Microsoft Docs
description: 本主題提供整合 SIEM 與 Cloud App Security 的相關資訊。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/19/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c116a2b199638d60aeb793a8562a0852e07031f0
ms.sourcegitcommit: 00e7adf7ebf26bf414df67e42ff6e3bac709b68b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/19/2018
ms.locfileid: "39143337"
---
*適用於：Microsoft Cloud App Security*

# <a name="siem-integration"></a>SIEM 整合

您現在可以整合 Microsoft Cloud App Security 與您的 SIEM 伺服器，以集中監視來自連線應用程式的警示及活動。 隨著連線應用程式支援的新活動與事件，Microsoft Cloud App Security 也會隨之推出對應的支援。 與 SIEM 服務整合可讓您進一步保護雲端應用程式，同時維護一般安全性工作流程、自動化安全性程序，以及關聯雲端型事件與內部部署事件。 Microsoft Cloud App Security SIEM 代理程式會在您的伺服器上執行，以及從 Microsoft Cloud App Security 提取警示和活動，並將它們串流至 SIEM 伺服器。

當您初次整合您的 SIEM 與 Cloud App Security 時，過去兩天內的活動和警示會轉寄到 SIEM，並從那時候開始轉寄所有活動和警示 (依據您選取的篩選)。 此外，如果您延長此功能的停用期間，當您再次加以啟用時，其會轉寄過去兩天內的警示和活動，接著轉寄那時候開始的所有警示和活動。

## <a name="siem-integration-architecture"></a>SIEM 整合架構

SIEM 代理程式會部署在您的組織網路中。 部署並設定好 SIEM 代理程式之後，代理程式便會提取使用 Cloud App Security RESTful API 所設定的資料類型 (警示與活動)。
之後，便會透過連接埠 443 上加密的 HTTPS 通道進行流量傳輸。

SIEM 代理程式從 Cloud App Security 擷取資料後，便會使用您在安裝期間提供的網路設定 (搭配自訂連接埠的 TCP 或 UDP)，傳送 Syslog 訊息至本機 SIEM。 

![SIEM 整合架構](./media/siem-architecture.png)

## <a name="supported-siems"></a>支援的 SIEM

Cloud App Security 目前支援 Micro Focus ArcSight 和一般 CEF。

## <a name="how-to-integrate"></a>如何整合

與 SIEM 整合是透過三個步驟完成︰
1. 在 Cloud App Security 入口網站中進行設定。 
2. 下載 JAR 檔案，並在您的伺服器上執行該檔案。
3. 驗證 SIEM 代理程式正在運作。

### <a name="prerequisites"></a>必要條件

- 標準 Windows 或 Linux 伺服器 (可以是虛擬機器)。
- 伺服器必須執行 Java 8；不支援舊版本。
- OS：Windows 或 Linux
- CPU：2
- 磁碟空間：20 GB
- RAM：2 GB
- 伺服器必須執行 Java 8。 不支援舊版。
- 如[網路需求](network-requirements.md)中所述，設定您的防火牆
 

## <a name="integrating-with-your-siem"></a>與 SIEM 整合

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>步驟 1：在 Cloud App Security 入口網站中進行設定

1. 在 Cloud App Security 入口網站中，按一下設定齒輪下的 [安全性延伸模組]，然後按一下 [SIEM 代理程式] 索引標籤。

2. 按一下加號圖示以啟動 [新增 SIEM 代理程式精靈]。
3. 在精靈中，按一下 [啟動精靈]。   
4. 在精靈中，填入名稱，並**選取 SIEM 格式**，然後設定與該格式相關的任何 [進階設定]。 
   按 [下一步] 。

   ![一般 SIEM 設定](./media/siem1.png)

5. 輸入 [遠端 Syslog 主機] 的 IP 位址或主機名稱，以及 [Syslog 連接埠號碼]。 選取 TCP 或 UDP 作為遠端 Syslog 通訊協定。
   如果您沒有這些詳細資料，則可以與安全性系統管理員合作，來取得這些詳細資料。
   按 [下一步] 。

   ![遠端 Syslog 設定](./media/siem2.png)

6. 選取您想要匯出至 SIEM 伺服器的資料類型：[警示] 和 [活動]。 
   使用滑桿來啟用和停用它們，預設會選取所有項目。 您可以使用 [套用至] 下拉式清單來設定篩選條件，以便只將特定警示和活動傳送至 SIEM 伺服器。
   您可以按一下 [Edit and preview results]\(編輯和預覽結果)，檢查篩選是否如預期運作。 
   按 [下一步] 。 

   ![資料類型設定](./media/siem3.png)

7. 複製並儲存權杖，以供稍後使用。 
   按一下 [完成] 並離開精靈之後，回到 SIEM 頁面就可以在表格中看到您新增的 SIEM 代理程式。 在稍後連接之前，它會顯示為 [已建立]。

> [!NOTE]
> 您建立的任何權杖皆會繫結到建立該權杖的系統管理員。 亦即，若系統管理員使用者從雲端應用程式安全性中移除，該權杖也會隨之失效。


### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>步驟 2：下載 JAR 檔案，並在您的伺服器上執行該檔案

1. 在 [Microsoft 下載中心](https://go.microsoft.com/fwlink/?linkid=838596) \(英文\) 接受[軟體授權條款](https://go.microsoft.com/fwlink/?linkid=862491)之後，請下載 .zip 檔案並將它解壓縮。

2. 執行伺服器上已解壓縮的檔案：

        java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN

> [!NOTE]
> - 根據 SIEM 代理程式的版本，檔名可能會不同。
> - 方括弧 [  ] 中的參數是選擇性的，應只在相關情況下使用。
> - 建議在伺服器啟動期間執行 JAR。
>   - Windows：當成排程工作執行，確定工作設定為 [Run whether the user is logged on or not] (不論使用者登入與否均執行) 並且取消核取 [Stop the task if it runs logner than] (停止工作，如果執行時間超過) 核取方塊。
>   - Linux：將帶有 **&** 的執行命令新增至 rc.local 檔案。 例如：`java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &`

使用下列變數的位置：
- DIRNAME 是您想要用於本機代理程式偵錯記錄的目錄路徑。
- ADDRESS[:PORT] 是 Proxy 伺服器位址以及伺服器用來連接至網際網路的連接埠。
- TOKEN 是您在前一個步驟中所複製的 SIEM 代理程式權杖。

您可以隨時輸入-h 來取得說明。


## 範例活動記錄<a name="siem-samples"></a>


以下是傳送到 SIEM 的活動記錄範例：
```
2017-11-22T17:50:04.000Z CEF:0|MCAS|SIEM_Agent|0.111.85|EVENT_CATEGORY_LOGOUT|Log out|0|externalId=1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0 rt=1511373004000 start=1511373004000 end=1511373004000 msg=Log out suser=admin@contoso.com destinationServiceName=ServiceNow dvc=13.82.149.151 requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:40:15.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_VIEW_REPORT|View report|0|externalId=1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a rt=1511898015000 start=1511898015000 end=1511898015000 msg=View report: ServiceNow Report 23 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=23,sys_report,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:25:34.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798 rt=1511897134000 start=1511897134000 end=1511897134000 msg=Delete object: ServiceNow Object f5122008db360300906ff34ebf96198a suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:40:14.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_CREATE_USER|Create user|0|externalId=1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c rt=1511815214000 start=1511815214000 end=1511815214000 msg=Create user: user 747518c0db360300906ff34ebf96197c suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,747518c0db360300906ff34ebf96197c,sys_user,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:41:20.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_DELETE_USER|Delete user|0|externalId=1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383 rt=1511815280000 start=1511815280000 end=1511815280000 msg=Delete user: user 233490c0db360300906ff34ebf9619ef suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,233490c0db360300906ff34ebf9619ef,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:24:55.000Z LAB-EUW-ARCTEST CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897117617_5be018ee-f676-4473-a9b5-5982527409be rt=1511897095000 start=1511897095000 end=1511897095000 msg=Delete object: ServiceNow Object b1709c40db360300906ff34ebf961923 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897117617_5be018ee-f676-4473-a9b5-5982527409be,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=
```
以及下列警示記錄檔範例：
```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```
#### <a name="sample-cloud-app-security-alerts-in-cef-format"></a>CEF 格式的 Cloud App Security 警示範例


|   適用   |      CEF 欄位名稱      |                                                   說明                                                   |
|-------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------|
| 活動/警示 |          啟動           |                                           活動或警示的時間戳記                                           |
| 活動/警示 |           結束            |                                           活動或警示的時間戳記                                           |
| 活動/警示 |            rt            |                                           活動或警示的時間戳記                                           |
| 活動/警示 |           msg            |                              如入口網站中顯示的活動或警示描述                               |
| 活動/警示 |          suser           |                                         活動或警示主體使用者                                          |
| 活動/警示 |  destinationServiceName  |                  活動或警示源自的應用程式，例如 Office 365、Sharepoint、Box。                   |
| 活動/警示 |        cs<X>標籤        |        每個標籤具有不同的意義，但標籤本身可說明其意義，例如 targetObjects。        |
| 活動/警示 |          cs<X>           | 對應到標籤的資訊 (如標籤範例所示的活動或警示目標使用者)。 |
|    活動     |     EVENT_CATEGORY_*     |                                       活動的高層級類別                                       |
|    活動     |         <ACTION>         |                                  如入口網站中顯示的活動類型                                  |
|    活動     |        externalId        |                                                    事件識別碼                                                     |
|    活動     |           dvc            |                                             用戶端裝置的 IP                                             |
|    活動     | requestClientApplication |                                         用戶端裝置的使用者代理程式                                         |
|      警示       |       <alert type>       |                                  例如 “ALERT_CABINET_EVENT_MATCH_AUDIT”                                  |
|      警示       |          <name>          |                                             符合的原則名稱                                             |
|      警示       |        externalId        |                                                    警示識別碼                                                     |

### <a name="step-3-validate-that-the-siem-agent-is-working"></a>步驟 3：驗證 SIEM 代理程式正在運作

1. 請確認 Cloud App Security 入口網站中的 SIEM 代理程式狀態不是 [連線錯誤] 或 [已中斷連線]，而且沒有代理程式通知。 如果連線關閉超過兩小時，就會顯示 [連線錯誤]，如果連線關閉過 12 小時，則會顯示 [已中斷連線]。
 ![SIEM 已中斷連線](./media/siem-not-connected.png)

   相反地，狀態應該是如下所示的 [已連線]︰![SIEM 已連線](./media/siem-connected.png)

2. 在 Syslog/SIEM 伺服器中，確定您看到從 Cloud App Security 抵達的活動和警示。


## <a name="regenerating-your-token"></a>重新產生權杖
如果您遺失權杖，則一律可以重新產生權杖，方法是按一下表格中 SIEM 代理程式之資料列結尾的三個點，然後選取 [Regenerate token]\(重新產生權杖)。

 ![SIEM - 重新產生權杖](./media/siem-regenerate-token.png)

## <a name="editing-your-siem-agent"></a>編輯 SIEM 代理程式 
如果您未來需要編輯 SIEM 代理程式，請按一下表格中 SIEM 代理程式之資料列結尾的三個點，然後選取 [編輯]。 如果您編輯 SIEM 代理程式，則不需要重新執行 .jar 檔案，它會自動更新。

![SIEM - 編輯](./media/siem-edit.png)

## <a name="deleting-your-siem-agent"></a>刪除 SIEM 代理程式
如果您未來需要刪除 SIEM 代理程式，請按一下表格中 SIEM 代理程式之資料列結尾的三個點，然後選取 [刪除]。

![SIEM - 刪除](./media/siem-delete.png)

> [!NOTE]
> 此功能處於公開預覽狀態。



## <a name="see-also"></a>另請參閱  
[針對 SIEM 整合問題進行疑難排解](troubleshooting-siem.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  

