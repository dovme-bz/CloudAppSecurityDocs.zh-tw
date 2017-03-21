---
title: "在 Cloud App Security 中為 Cloud Discovery 錯誤進行疑難排解 | Microsoft Docs"
description: "本主題提供 Cloud Discovery 常見錯誤和其解決建議的清單。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 76dfaebb-d477-4bdb-b3d7-04cc3fe6431d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1cd697631f776c55fbedcec9a0ed34a3b68d8ac0
ms.sourcegitcommit: 355226ee21981563066d637e7db0bff0d53c2da6
translationtype: HT
---
# <a name="troubleshooting-cloud-discovery"></a>為 Cloud Discovery 進行疑難排解
## <a name="log-parsing-errors"></a>記錄剖析錯誤

您可以使用治理記錄來追蹤 Cloud Discovery 記錄的處理。 本指南提供要針對可在該處顯示的每個錯誤採取的解決動作。

### <a name="governance-log-errors"></a>治理記錄錯誤
|錯誤|描述|解決方法|
|----|----|----|
|不支援的檔案類型|上傳的檔案不是有效的記錄檔 (例如影像檔)。|上傳直接從防火牆或 Proxy 匯出的 **text**、**zip** 或 **gzip** 檔案。|
|內部錯誤|偵測到內部資源失敗|按一下 [重試] 重新執行工作。|
|記錄格式不相符|上傳的記錄格式不符合此資料來源的預期記錄格式。|1.確認記錄未損毀。 <br /> 2.比較並比對記錄檔與上載頁面中所顯示的範例格式。|
|交易超過 90 天|所有交易都超過 90 天，因此將予以忽略。|匯出具有最新事件的新記錄檔，並重新進行上傳。|
|沒有可分類雲端應用程式的交易|在記錄中找不到任何可辨識雲端應用程式的交易。|確認記錄包含輸出流量資訊。|
|不支援的記錄類型|當您選取 [資料來源 = 其他 (不支援)] 時，不會剖析記錄檔。 相反地，它是基於檢閱而傳送至 Cloud App Security 技術團隊。|Cloud App Security 技術團隊會根據每個資料來源建置專用剖析器。 [已經支援](set-up-cloud-discovery.md)最常用資料來源。 不受支援資料來源的每次上傳都會進行檢閱並新增至新資料來源剖析器的管線。 新的剖析器通知會發行為 Cloud App Security 版本資訊的一部分。|
## <a name="log-collector-errors"></a>記錄收集器錯誤

|問題|解決方法|
|----|----|
|無法透過 FTP 連線至記錄收集器|1.確認使用的是 FTP 認證，而非 SSH 認證。 <br />2.確認您使用的 FTP 用戶端未設定為 SFTP。|
|更新收集器組態時失敗|1.確認您輸入的是最新存取權杖。 <br />2.確認防火牆中允許記錄收集器起始連接埠 443 上的輸出流量。|
|傳送至收集程式的記錄未出現在入口網站中|1.確認治理記錄中是否有失敗的剖析工作。  <br />  &nbsp;&nbsp;&nbsp;&nbsp;如果是這樣，請為上述記錄剖析錯誤表的錯誤進行疑難排解。<br /> 2.否則，請檢查入口網站中的資料來源和記錄收集器組態。 <br /> &nbsp;&nbsp;&nbsp;&nbsp;a. 在 [資料來源] 頁面中，確認已正確設定您所使用的資料來源。 <br />&nbsp;&nbsp;&nbsp;&nbsp;b. 在 [記錄收集器] 頁面中，確認資料來源連結到正確的記錄收集器。 <br /> 3.檢查內部部署記錄收集器電腦的本機組態。  <br />&nbsp;&nbsp;&nbsp;&nbsp;a. 透過 SSH 登入記錄收集器，並執行 collector_config 公用程式。<br/>&nbsp;&nbsp;&nbsp;&nbsp;b. 確認防火牆或 Proxy 使用您定義的通訊協定 (Syslog/TCP、Syslog/UDP 或 FTP) 將記錄傳送至記錄收集器，以及將它們傳送至正確的連接埠和目錄。<br /> &nbsp;&nbsp;&nbsp;&nbsp;c. 在電腦上執行 netstat，並確認它接收到來自防火牆或 Proxy 的連入連線 <br /> 4. 確認允許記錄收集器起始連接埠 443 上的輸出流量。|

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  