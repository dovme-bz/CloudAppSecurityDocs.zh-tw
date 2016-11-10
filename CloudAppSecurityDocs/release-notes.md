---
title: "版本資訊 | Microsoft Docs"
description: "本主題會經常更新，讓您知道最新版 Cloud App Security 的新功能。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/30/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4949ab4f-22c3-4371-b2dc-c8422a097dfe
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 400741713d40422a3b1c7680663a572d18e9c692
ms.openlocfilehash: d95ddaef15cbb11f005156f272578f49f012e16d


---

# <a name="release-notes"></a>版本資訊

## <a name="cloud-app-security-release-83"></a>Cloud App Security 版本 83
發行日期：2016 年 10 月 30 日

**新功能**
-   為了簡化[活動記錄](activity-filters.md)和[檔案記錄](file-filters.md)中的篩選功能，而合併了相似的篩選條件。 使用活動篩選條件：[活動物件]、[IP 位址] 和 [使用者]。 使用檔案篩選條件 [共同作業者] 準確尋找您需要的內容。
-   從活動記錄下拉式清單中，在 [來源] 下按一下 [檢視未經處理資料] 的連結，下載用來產生活動記錄的未經處理資料，以更進一步向下切入應用程式事件。 
-   新增 Okta 中額外登入活動的支援。 [私人預覽]
-   新增 Salesforce 中額外登入活動的支援。 

**改善**
-   改進 Cloud Discovery 快照集報告的可用性及疑難排解。
-   改進警示清單中，對多個應用程式發出的警示可見度。
-   改進建立新 Cloud Discovery 連續報告時的可用性。
-   改進治理記錄的可用性。



## <a name="cloud-app-security-release-82"></a>Cloud App Security 版本 82
發行日期：2016 年 10 月 9 日

**改善**

- **變更電子郵件**和**變更密碼**活動現在與 Salesforce 中的泛型**管理使用者**活動無關。
- 已新增 SMS 每日警示限制的釐清。 每個電話號碼每天 (UTC) 最多傳送 10 則訊息。
- 已將新的憑證新增至已取代 Safe Harbor 之「隱私盾」的 Cloud Discovery 屬性 (僅與美國廠商有關)。
- 已新增 API 連接器失敗訊息的疑難排解，讓您更輕鬆地修復問題。
- 已改善 Office 365 協力廠商應用程式掃描的更新頻率。
- 已改善 Cloud Discovery 儀表板。
- 已改善 Checkpoint Syslog 剖析器。
- 改善治理記錄中的禁止和取消禁止協力廠商應用程式。
 
**錯誤修正**
 
- 改善標誌上傳程序。
 
## <a name="cloud-app-security-release-81"></a>Cloud App Security 版本 81
發行日期：2016 年 9 月 18 日

**改善**
- Cloud App Security 現在是 Office 365 中的第一方應用程式！ 從現在起，只要按一下，就可以將 Office 365 連線至 Cloud App Security。

- 治理記錄的新外觀 - 現在已升級成與活動記錄和檔案資料表相同的實用外觀。 使用新的篩選，輕鬆找出您的需求以及監視您的治理動作。 
- 已改善異常偵測引擎的多次失敗登入和其他風險因子。
- 已改善 Cloud Discovery 快照集報告。
- 已改善活動記錄中的管理活動；變更密碼、更新使用者、重設密碼現在指出活動是否執行為管理活動。
- 已改善系統警示的警示篩選。 
- 警示內原則的標籤現在連結回原則報告。
- 如果未指定 Dropbox 檔案的擁有者，則會將通知電子郵件訊息傳送給您設定的收件者。 
- Cloud App Security 支援額外的 24 種語言，以將我們的支援擴充到共 41 種語言。  


## <a name="cloud-app-security-release-80"></a>Cloud App Security 版本 80
發行日期：2016 年 9 月 4 日 

**改善**
- DLP 掃描失敗時，會提供 Cloud App Security 為何無法掃描檔案的解釋。 如需詳細資訊，請參閱[內容檢查](https://aka.ms/aka.ms/cas-contentinspection)。
- 已改善異常偵測引擎，包括改善不可能的旅遊警示。
- 改善關閉警示經驗，您也可以新增意見反應，讓 Cloud App Security 團隊知道警示是否有趣，以及為什麼您的意見反應可以用來改善 Cloud App Security 偵測。
- 已增強 Cisco ASA Cloud Discovery 剖析器。
- 現在，Cloud Discovery 記錄手動上傳完成時，即可收到電子郵件通知。
   



## <a name="cloud-app-security-release-79"></a>Cloud App Security 版本 79
發行日期：2016 年 8 月 21 日 

**新功能**

- **新的 Cloud Discovery 儀表板**  
提供全新 Cloud Discovery 儀表板，設計目的是讓您深入了解如何在組織中使用雲端應用程式。 它概述正在使用的應用程式種類、未解決的警示以及組織中應用程式的風險層級。 它也可讓您知道誰是組織中的最上層應用程式使用者，並提供 App Headquarter 位置圖。
新的「儀表板」具有多個用於篩選資料的選項，可讓您根據最感興趣的項目來產生特定檢視，並且提供容易了解的圖形，讓您一目瞭然。

- **新的 Cloud Discovery 報告** 若要檢視 Cloud Discovery 結果，您現在可以產生兩種類型的報告：快照集報告和連續報告。
快照集報告提供一組手動從防火牆和 Proxy 上傳之流量記錄的臨機操作可見度。 連續報告顯示使用 Cloud App Security 的記錄收集器從您的網路轉寄的所有記錄結果。 這些新的報告提供所有資料的改良可見度、自動識別 Cloud App Security 機器學習異常偵測引擎所識別的異常使用，以及識別您使用強固且更細微原則引擎所定義的異常使用。 如需詳細資訊，請參閱[設定 Cloud Discovery](set-up-cloud-discovery.md)。
 
**改善**
- 改善下列頁面中的一般使用性︰原則頁面、一般設定、郵件設定。
- 在 [警示] 表格中，現在較容易區分讀取與未讀取警示。 讀取警示的左邊會有藍色線並呈現灰色，表示您已讀取過它們。
- 已更新活動原則**重複活動**參數。 
- 在 [帳戶] 頁面中，已新增使用者**類型**資料行，因此，您現在可以看到每個使用者所具有的使用者帳戶類型。 使用者類型是應用程式特有的。 
- 在 OneDrive 和 SharePoint 中，已新增檔案相關活動的近乎即時支援。 檔案變更時，Cloud App Security 幾乎會立即觸發掃描。


## <a name="cloud-app-security-release-78"></a>Cloud App Security 版本 78
發行日期：2016 年 8 月 7 日

**改善**
- 從特定檔案中，您現在可以按一下滑鼠右鍵，並 [尋找相關內容]。 從活動記錄中，您可以使用目標物件篩選，然後選取特定檔案。

- 改善 Cloud Discovery 記錄檔剖析器 (包括新增 Juniper 和 Cisco ASA)。
- 現在，當您關閉警示時，Cloud App Security 可讓您提供改善警示的意見。 讓我們知道為什麼關閉警示 (例如，不有趣、收到許多類似警示、實際嚴重性應該更低、警示不精確)，就可以協助改善 Cloud App Security 警示品質。
- 在 [檔案原則] 檢視中，或檢視檔案時，如果您開啟檔案抽屜，則已新增 [相符的原則] 的新連結。 當您按一下它時，即可檢視所有相符項目，您現在已可以關閉全部。 
- 使用者所屬的組織單位現在新增至所有相關警示。
- 現在，要讓您知道手動上傳記錄檔的處理完成時會傳送電子郵件通知。


## <a name="cloud-app-security-release-77"></a>Cloud App Security 版本 77
發行日期：2016 年 7 月 24 日

**改善：**
- 已改善 Cloud Discovery [匯出] 按鈕圖示的使用性。
- 調查活動時，如果尚未剖析使用者代理程式，則您現在可以看到原始資料。
- 異常偵測引擎中已新增兩個新的風險因素︰ 
    - Cloud App Security 現在將殭屍網路相關 IP 位址標記和匿名 IP 位址當成風險計算的一部分。 
    - 現在會監視 Office 365 活動是否具有高下載率。 如果 Office 365 下載率遠大於您組織 (或特定使用者) 的一般下載率，則會觸發「異常偵測」警示。 
- Cloud App Security 現在已與新的 Dropbox [安全共用功能](https://blogs.dropbox.com/dropbox/2016/06/new-dropbox-productivity-tools/) API 相容。 
- 已改善將詳細資料新增至 Discovery 記錄剖析錯誤，包括：沒有雲端相關交易、所有事件都已過時、檔案損毀、記錄格式不相符。
- 已改善活動記錄日期篩選；它現在包含依時間進行篩選的能力。
- 已改善 IP 位址範圍頁面的使用性。
- Cloud App Security 現在支援 Microsoft Azure 資訊保護 (預覽版本)。 您可以使用標記安全分類來篩選檔案以及設定檔案原則，然後設定您想要檢視的分類標籤層級。 標籤也會指出您的組織或另一個租用戶 (外部) 中是否有人已設定分類。 



## <a name="cloud-app-security-release-76"></a>Cloud App Security 版本 76
發行日期：2016 年 7 月 10 日

**改善：**

- 現在可以匯出內建報告中的使用者清單。
- 改善彙總活動原則的使用性。
- 改善 TMG W3C 防火牆記錄訊息剖析器的支援。
- 檔案治理動作的改良使用性下降，現在已分成共同作業、安全性和調查動作。
- 改善 Exchange Online 活動的不可能旅遊偵測︰傳送郵件。
- 新的標題 (軌跡) 清單已新增至 [警示] 和 [原則] 頁面頂端，方便進行瀏覽。

**錯誤修正：**
- 檔案原則 DLP 設定中之信用卡的預設運算式已變更為「全部︰財務︰信用卡」。


## <a name="cloud-app-security-release-75"></a>Cloud App Security 版本 75
發行日期：2016 年 6 月 27 日


**新功能：**
* 新的新增項目已新增至不斷成長的支援 Salesforce 事件清單，包含了解報告、共用連結、內容發佈、模擬登入等事件。
* Cloud App Security 儀表板上的已連線應用程式圖示狀態，會與儀表板上所顯示以反映最近 30 天的應用程式狀態一致。
* 全螢幕支援。


**錯誤修正：**
* SMS 警示電話號碼現在會在插入時進行驗證。

## <a name="cloud-app-security-release-74"></a>Cloud App Security 版本 74
發行日期：2016 年 6 月 13 日
* [警示] 畫面已更新，為您提供更多資訊的概觀，包括能夠快速查看所有使用者活動、活動對應、相關的使用者治理記錄檔、觸發警示的原因描述，以及使用者頁面中的其他圖形和對應。 
* Cloud App Security 產生的事件現在包括事件類型、格式、群組原則、相關的物件和描述。
* 針對 Office 365 ProPlus、OneNote、Office Online 和 Exchange Online Protection 新增了新的 IP 位址標記。
* 您現在可以選擇從主要探索功能表上傳記錄檔。
* IP 位址類別篩選已獲得改善。 Null 的 IP 位址類別現在稱為未分類，並且新增了稱為「沒有值」的新類別，以包含沒有 IP 位址資料的所有活動。
* Cloud App Security 中的安全性群組現在稱為使用者群組，以避免和 Active Directory 安全性群組混淆。
* 現在可以針對每個 IP 位址篩選，和篩選掉不含 IP 位址的事件。 
* 在活動原則與檔案原則中偵測到相符項目時，傳送通知電子郵件的設定已變更。 您現在可以為您想要寄送通知副本的收件者新增電子郵件地址。


## <a name="cloud-app-security-release-73"></a>Cloud App Security 版本 73
發行日期：2016 年 5 月 29 日

* 更新警示功能︰現已可為每項原則設定警示，透過電子郵件傳送或傳送簡訊。
* 警示頁面︰已改善了設計，更可運用進階的解決方法選項及事件管理。
* 調整原則︰您現已可利用警示，直接從警示解決方法選項移到 [原則設定] 頁面，以便更容易依警示加以調整。
* 根據客戶的意見，改善了異常偵測風險分數的計算，且降低了誤判率。
* 活動記錄匯出現已包含事件識別碼、事件分類與事件類型名稱。
* 已改善建立原則治理動作的外觀與可用性。
* 已簡化 Office 365 的調查與控制 - 選擇使用 Office 365 會自動選取隸屬於 Office 365 套件的所有應用程式。
* 通知現已會傳送到連線的應用程式中所設定之電子郵件地址。 
* 發生連線錯誤時，雲端應用程式現已可提供有關錯誤的詳細說明。
* 當檔案符合原則時，現已於檔案抽屜中提供用於存取檔案的 URL。
* 活動原則或異常偵測原則觸發警示時，會傳送新的詳細通知，提供符合項目的相關資訊。 
* 中斷應用程式連接器的連線時，就會觸發自動化系統警示。
* 您現已可關閉及解決單一警示，或從 [警示] 頁面選取大範圍的警示。

## <a name="cloud-app-security-release-72"></a>Cloud App Security 版本 72
發行日期：2016 年 5 月 15 日

*  已改善一般外觀與基礎結構，包括：
    * 有新的圖表可提供 Cloud Discovery 手動記錄上傳程序的更多協助。
    * 已改善更新無法辨識 (「其他」) 的記錄檔之程序，包括讓您知道檔案需要其他檢閱的快顯視窗，而且會在資料可使用時通知您。
    * 調查活動與過時瀏覽器和作業系統的檔案記錄時，可反白顯示更多活動及檔案違規。
* 已改善 Cloud Discovery 記錄檔剖析器，包括加入 Cisco ASA、Cisco FWSM、Cisco Meraki 與 W3C。
* 改善 Cloud Discovery 已知問題。
* 已為擁有者的網域與內部/外部聯盟加入了新的活動篩選器。
* 已加入新的篩選器，您可用以搜尋任何 Office 365 物件 (檔案、資料夾、URL)。
* 已加入一項功能，可設定異常偵測原則的最低風險分數。
* 當您設定在違反原則時要傳送警示，現已可設定您要接到警示的最低嚴重性等級。 您可以選擇為此使用貴組織的預設值，您可以設定特定的警示設定作為您組織的預設值。

## <a name="see-also"></a>另請參閱  
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


