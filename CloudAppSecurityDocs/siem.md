---
title: "SIEM 與 Cloud App Security 的整合 | Microsoft Docs"
description: "本主題提供整合 SIEM 與 Cloud App Security 的相關資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5880ea404d6830c5d8f12534c04f123d8c517946
ms.sourcegitcommit: ea8207f412f31127beafd18a0bd028052fbadf90
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2017
---
# <a name="siem-integration"></a>SIEM 整合
    
您現在可以整合 Cloud App Security 與 SIEM 伺服器，來啟用警示和活動的集中式監視。 與 SIEM 服務整合可讓您進一步保護雲端應用程式，同時維護一般安全性工作流程、自動化安全性程序，以及關聯雲端型事件與內部部署事件。 Cloud App Security SIEM 代理程式會在您的伺服器上執行，以及從 Cloud App Security 提取警示和活動，並將它們串流至 SIEM 伺服器。

當您初次整合您的 SIEM 與 Cloud App Security 時，過去兩天內的活動和警示會轉寄到 SIEM，並從那時候開始轉寄所有活動和警示 (依據您選取的篩選)。 此外，如果您延長此功能的停用期間，當您再次加以啟用時，其會轉寄過去兩天內的警示和活動，接著轉寄那時候開始的所有警示和活動。

與 SIEM 整合是透過三個步驟完成︰
1. 在 Cloud App Security 入口網站中進行設定。 
2. 下載 JAR 檔案，並在您的伺服器上執行該檔案。
3. 驗證 SIEM 代理程式正在運作。

## <a name="prerequisites"></a>必要條件

- 標準 Windows 或 Linux 伺服器 (可以是虛擬機器)。
- 伺服器必須執行 Java 8；不支援舊版本。

## <a name="integrating-with-your-siem"></a>與 SIEM 整合

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>步驟 1：在 Cloud App Security 入口網站中進行設定

1. 在 Cloud App Security 入口網站的 [設定] 齒輪下，按一下 [SIEM agents]\(SIEM 代理程式)。

2. 按一下 [Add SIEM agent]\(新增 SIEM 代理程式)，啟動精靈。
3. 在精靈中，按一下 [Add SIEM agent]\(新增 SIEM 代理程式)。    
4. 在精靈中，填入名稱，並**選取 SIEM 格式**，然後設定與該格式相關的任何 [進階設定]。 按 [下一步] 。

   ![一般 SIEM 設定](./media/siem1.png)

5. 輸入 [Remote syslog host] (遠端 Syslog 主機) 的 IP 位址和 [Syslog port number] (Syslog 連接埠號碼)。 選取 TCP 或 UDP 作為遠端 Syslog 通訊協定。
如果您沒有這些詳細資料，則可以與安全性系統管理員合作，來取得這些詳細資料。
按 [下一步] 。
  ![遠端 Syslog 設定](./media/siem2.png)

6. 選取您想要匯出至 SIEM 伺服器的資料類型：[警示] 和 [活動]。 使用滑桿來啟用和停用它們，預設會選取所有項目。 您可以使用 [套用至] 下拉式清單來設定篩選條件，以便只將特定警示和活動傳送至 SIEM 伺服器。
您可以按一下 [Edit and preview results] (編輯和預覽結果)，檢查篩選是否如預期運作。 按 [下一步] 。 

  ![資料類型設定](./media/siem3.png)

7. 複製並儲存權杖，以供稍後使用。 按一下 [完成] 並離開精靈之後，回到 SIEM 頁面就可以在表格中看到您新增的 SIEM 代理程式。 在稍後連接之前，它會顯示為 [已建立]。

### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>步驟 2：下載 JAR 檔案，並在您的伺服器上執行該檔案

1. [從 Microsoft 下載中心下載 .zip 檔案](https://go.microsoft.com/fwlink/?linkid=838596)，並將它解壓縮。

2. 從 ZIP 檔案中解壓縮 .jar 檔案，並在您的伺服器上執行該檔案。
 在執行這個檔案之後，請執行下列命令︰
    
      java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
> [!NOTE]
> - 根據 SIEM 代理程式的版本，檔名可能會不同。
> - 方括弧 [] 中的參數是選擇性的，應只在相關情況下使用。

使用下列變數的位置：
- DIRNAME 是您想要用於本機代理程式偵錯記錄的目錄路徑。
- ADDRESS[:PORT] 是 Proxy 伺服器位址以及伺服器用來連接至網際網路的連接埠。
- TOKEN 是您在前一個步驟中所複製的 SIEM 代理程式權杖。

您可以隨時輸入-h 來取得說明。



### <a name="step-3-validate-that-the-siem-agent-is-working"></a>步驟 3：驗證 SIEM 代理程式正在運作

1. 請確認 Cloud App Security 入口網站中的 SIEM 代理程式狀態不是 [連線錯誤] 或 [已中斷連線]，而且沒有代理程式通知。 如果連線關閉超過兩小時，就會顯示 [連線錯誤]，如果連線關閉過 12 小時，則會顯示 [已中斷連線]。
 ![SIEM 已中斷連線](./media/siem-not-connected.png)
 
   相反地，狀態應該是 [已連接]，如下所示︰ ![SIEM 已連接](./media/siem-connected.png)

2. 在 Syslog/SIEM 伺服器中，確定您看到從 Cloud App Security 抵達的活動和警示。


## <a name="regenerating-your-token"></a>重新產生權杖
如果您遺失權杖，則一律可以重新產生權杖，方法是按一下表格中 SIEM 代理程式之資料列結尾的三個點，然後選取 [Regenerate token] (重新產生權杖)。

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
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  