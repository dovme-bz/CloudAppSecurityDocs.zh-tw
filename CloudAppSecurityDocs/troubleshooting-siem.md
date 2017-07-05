---
title: "針對 SIEM 與 Cloud App Security 的整合進行疑難排解 | Microsoft Docs"
description: "本主題提供將您的 SIEM 連線到 Cloud App Security 時可能發生的問題清單，並提供每個問題的解決方法。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: de64d9ca-eaed-4243-bcf7-adca5aff18c8
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d7b71a3db122db3b7ed6ae28348bb74946b57427
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2017
---
# <a name="troubleshooting-the-siem-agent"></a>為 SIEM 代理程式進行疑難排解

請確認 Cloud App Security 入口網站中的 SIEM 代理程式狀態不是 [連線錯誤] 或 [已中斷連線]，而且沒有代理程式通知。 如果連線關閉超過兩小時，就會顯示 [連線錯誤]，如果連線關閉過 12 小時，則會顯示 [已中斷連線]。

如果您在執行代理程式時於命令提示字元中看到下列其中一個錯誤，請使用下列步驟來補救此問題︰

|錯誤|描述|解決方法|
|----|----|----|
|啟動程序期間的一般錯誤|代理程式啟動程序期間的意外錯誤。|請連絡支援部門。|
|太多嚴重錯誤|連接主控台時發生太多嚴重錯誤。 正在關閉。|請連絡支援部門。|
|權杖無效|提供的權杖無效。|請確定您複製的權杖正確。 您可以使用上述程序來重新產生權杖。|
|Proxy 位址無效|提供的 Proxy 位址無效。|請確定您輸入的 Proxy 和連接埠正確。|


建立代理程式之後，如果您在 Cloud App Security 入口網站的 [SIEM agent] (SIEM 代理程式) 頁面中看到下列其中一個**代理程式通知**，請使用下列步驟來補救此問題︰

|錯誤|描述|解決方法|
|----|----|----|
|**內部錯誤**|SIEM 代理程式發生未知錯誤。|請連絡支援部門。|
|**資料伺服器傳送錯誤**|如果您透過 TCP 使用 Syslog 伺服器，則會收到此錯誤。 SIEM 代理程式無法連接至 Syslog 伺服器。  如果您收到這個錯誤，則代理程式會在修正錯誤之前停止提取新的活動，因此請務必遵循補救步驟，直到錯誤不再出現為止。|1.確定您正確地定義 Syslog 伺服器︰在 Cloud App Security UI 中，編輯您的 SIEM 代理程式 (如上所述)，並確定您所撰寫的伺服器名稱正確，且設定正確的連接埠。 </br>2.檢查 Syslog 伺服器連線︰確定防火牆未封鎖通訊。| 
|**資料伺服器連線錯誤**| 如果您透過 TCP 使用 Syslog 伺服器，則會收到此錯誤。 SIEM 代理程式無法連接至 Syslog 伺服器。  如果您收到這個錯誤，則代理程式會在修正錯誤之前停止提取新的活動，因此請務必遵循補救步驟，直到錯誤不再出現為止。|1.確定您正確地定義 Syslog 伺服器︰在 Cloud App Security UI 中，編輯您的 SIEM 代理程式 (如上所述)，並確定您所撰寫的伺服器名稱正確，且設定正確的連接埠。 </br>2.檢查 Syslog 伺服器連線︰確定防火牆未封鎖通訊。|
|**SIEM 代理程式錯誤**|SIEM 代理程式已中斷連線超過 X 小時|請確認您未在 Cloud App Security 入口網站中變更 SIEM 設定。 否則，這可能表示 Cloud App Security 與您執行 SIEM 代理程式的電腦之間有連線問題。|
|**SIEM 代理程式通知錯誤**|從 SIEM 代理程式收到 SIEM 代理程式通知轉寄錯誤。|這表示您收到有關 SIEM 代理程式與 SIEM 伺服器之間連線的錯誤。 請確認沒有防火牆封鎖您的 SIEM 伺服器或您執行 SIEM 代理程式的電腦。 另外也請檢查 SIEM 伺服器的 IP 位址未變更。|



## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  