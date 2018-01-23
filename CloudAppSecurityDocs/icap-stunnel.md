---
title: "透過安全 ICAP 的 Cloud App Security 外部 DLP 整合 | Microsoft Docs"
description: "本主題提供在 Cloud App Security 中設定 ICAP 連線以及 Stunnel 設定所需的步驟。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/21/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9656f6c6-7dd4-4c4c-a0eb-f22afce78071
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: eeda929ecc4bc029f0fd292f4276ba55f202d314
ms.sourcegitcommit: 9cfb4b4e91e37fa3acf238b729cb68be0adc7086
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2018
---
# <a name="external-dlp-integration"></a>外部 DLP 整合

Cloud App Security 可以與現有 DLP 解決方案整合，以將這些控制項擴充至雲端，同時保留內部部署和雲端活動之間的一致且統一原則。 此平台會匯出易用介面 (包括 REST API 和 ICAP)，以啟用與內容分類系統 (例如 Symantec Data Loss Prevention (先前稱為 Vontu Data Loss Prevention) 或 Forcepoint DLP) 的整合。 

整合是利用標準 ICAP 通訊協定 (即 [RFC 3507](https://tools.ietf.org/html/rfc3507) 中所述的 http 類似通訊協定) 所完成。 為了保護 ICAP 安全以進行資料傳輸，需要設定 DLP 解決方案與 Cloud App Security 之間的安全 SSL 通道 (Stunnel)。 Stunnel 設定提供資料的 TLS 加密功能，因為資料是在 DLP 伺服器與 Cloud App Security 之間移動。 

本指南提供在 Cloud App Security 中設定 ICAP 連線以及 Stunnel 設定所需的步驟，來保護透過它的通訊安全。

> [!NOTE]
>此功能處於公開預覽狀態。

## <a name="architecture"></a>架構
Cloud App Security 會掃描您的雲端環境，並根據您的檔案原則設定決定是否要使用內部 DLP 引擎或外部 DLP 來掃描檔案。 如果套用外部 DLP 掃描，則會透過安全通道將檔案傳送至客戶環境，其中，會將檔案轉送至 DLP 結果的 ICAP 設備：允許/封鎖。 回應會透過 Stunnel 傳送回 Cloud App Security，而原則使用 Stunnel 來決定後續動作，例如通知、隔離和共用控制項。

![Stunnel 架構](./media/icap-architecture-stunnel.png)

因為 Cloud App Security 是在 Azure 中執行，所以 Azure 中的部署會產生更佳的效能。 不過，支援包括其他雲端和內部部署的其他選項。 在其他環境中部署可能會因較高延遲和較低輸送量而導致效能降低。 ICAP 伺服器和 Stunnel 必須一起部署到相同的網路，確定已加密流量。

## <a name="prerequisites"></a>必要條件
為了讓 Cloud App Security 透過 Stunnel 將資料傳送至 ICAP 伺服器，請使用動態來源連接埠號碼將 DMZ 防火牆開啟到 Cloud App Security 所使用的外部 IP 位址。 

1.  來源地址：請參閱[必要條件下的連線應用程式](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#prerequisites)
2.  來源 TCP 連接埠：動態
3.  目的地位址：連線到外部 ICAP 伺服器之 Stunnel 的一或兩個 IP 位址，而您將在後續步驟中設定外部 ICAP 伺服器
4.  目的地 TCP 連接埠：如您網路中所定義

> [!NOTE] 
> Stunnel 連接埠號碼預設為 11344。 如有必要，您可以將它變更為另一個連接埠，但請務必記下新的連接埠號碼，在下一個步驟中，您將需要輸入該連接埠號碼。

## <a name="step-1--set-up-icap-server"></a>步驟 1：設定 ICAP 伺服器

設定 ICAP 伺服器，並記下連接埠號碼，然後確定您已將 [模式] 設定為 [封鎖]。 封鎖模式設定 ICAP 伺服器將分類結果轉送回 Cloud App Security。

如需如何完成這項作業的指示，請參閱外部 DLP 產品文件。 如需範例，請參閱[附錄 A：Forcepoint ICAP 伺服器安裝程式](#forcepoint)和[附錄 B：Symantec 部署指南](#symantec)。

## <a name="step-2--set-up-your-stunnel-server"></a>步驟 2：設定 Stunnel 伺服器 

在此步驟中，您將會設定連線到 ICAP 伺服器的 Stunnel。 

>[!NOTE]
> 雖然高度建議，但是這個步驟是選擇性的，並且可以針對測試工作負載略過。 

### <a name="install-stunnel-on-a-server"></a>在伺服器上安裝 Stunnel

**必要條件**

- **伺服器** - 根據主要發佈的 Windows Server 或 Linux 伺服器。

如需支援 Stunnel 安裝之伺服器類型的詳細資訊，請參閱 [Stunnel 網站](https://www.stunnel.org/index.html)。 如果您要使用 Linux，則可以使用 Linux 發佈管理員進行安裝。

#### <a name="install-stunnel-on-windows"></a>在 Windows 上安裝 Stunnel

1. [Download the latest Windows Server installation](https://www.stunnel.org/downloads.html) (下載最新 Windows Server 安裝) (這應該作用於任何最新 Windows Server 版本)。
(預設安裝)

2. 在安裝期間，不會建立新的自我簽署憑證，您將在稍後的步驟中建立憑證。

3. 按一下 [Start server after installation (安裝後啟動伺服器)]。

4. 使用下列其中一種方式建立憑證：

   -    使用您的憑證管理伺服器以在 ICAP 伺服器上建立 SSL 憑證，然後將金鑰複製至您準備安裝 Stunnel 的伺服器。
   -    或者，在 Stunnel 伺服器上，使用下列 OpenSSL 命令產生私密金鑰和自我簽署憑證。 請取代這些變數：
       -    含私密金鑰名稱的 **key.pem**
       -    含憑證名稱的 **cert.pem**
       -    含新建立金鑰名稱的 **stunnel-key**

5. 在 Stunnel 安裝路徑下，開啟 config 目錄。 它預設為：c:\Program Files (x86)\stunnel\config\
6. 以系統管理員權限，執行命令列：`..\bin\openssl.exe genrsa -out key.pem 2048 `
      
     ` ..\bin\openssl.exe  req -new -x509 -config ".\openssl.cnf" -key key.pem -out .\cert.pem -days 1095`

8. 串連 cert.pem 與 key.pem，並將它們儲存至檔案：`type cert.pem key.pem >> stunnel-key.pem`

9. [下載公開金鑰](https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem)，並將它儲存至下列位置：**C:\Program Files (x86)\stunnel\config\MCASca.pem**。

10. 新增下列規則，以在 Windows 防火牆中開啟連接埠：

        rem Open TCP Port 11344 inbound and outbound
        netsh advfirewall firewall add rule name="Secure ICAP TCP Port 11344" dir=in action=allow protocol=TCP localport=11344
        netsh advfirewall firewall add rule name="Secure ICAP TCP Port 11344" dir=out action=allow protocol=TCP localport=11344

11. 執行：`c:\Program Files (x86)\stunnel\bin\stunnel.exe` 以開啟 Stunnel 應用程式。 

12. 按一下 [設定]，然後 [編輯設定]。

   ![編輯 Windows Server 設定](./media/stunnel-windows.png)
 
13. 開啟檔案，並貼上下列伺服器設定行，其中 **DLP Server IP** 是 ICAP 伺服器的 IP 位址、**stunnel-key** 是您在上一個步驟中建立的金鑰，而 **MCASCAfile** 是 Cloud App Security Stunnel 用戶端的公用憑證。 此外，刪除任何現有的範例文字 (在範例中，它會顯示 Gmail 文字)，並將下列內容放入檔案中：

        [microsoft-Cloud App Security]
        accept = 0.0.0.0:11344
        connect = **ICAP Server IP**:1344
        cert = C:\Program Files (x86)\stunnel\config\**stunnel-key**.pem
        CAfile = C:\Program Files (x86)\stunnel\config\**MCASCAfile**.pem
        TIMEOUTclose = 0
        client = no
12. 儲存檔案，然後按一下 [重新載入設定]。

13. 若要驗證所有事項都依預期執行，請從命令提示字元執行：`netstat -nao  | findstr 11344`
 

#### <a name="install-stunnel-on-ubuntu"></a>在 Ubuntu 上安裝 Stunnel

以 root 使用者身分登入時，下列範例是根據 Ubuntu 伺服器安裝；針對其他伺服器，請使用平行命令。 

在備妥的伺服器上，於同時安裝 Stunnel 和 OpenSSL 的 Ubuntu 伺服器上執行下列命令，以下載並安裝最新版的 Stunnel：

    apt-get update
    apt-get install openssl -y
    apt-get install stunnel4 -y
從主控台執行下列命令，確認已安裝 Stunnel。 您應該取得版本號碼以及設定選項清單：

    stunnel-version

### <a name="generate-certificates"></a>產生憑證

ICAP 伺服器和 Cloud App Security 會使用私密金鑰和公開憑證進行跨 Stunnel 的伺服器加密和驗證。 請確定您建立沒有複雜密碼的私密金鑰，因此 Stunnel 可以執行為背景服務。 此外，將 Stunnel 擁有者對檔案的權限設定為「可讀取」，而將其他所有人對檔案的權限設定為「無」。

您可以使用下列其中一種方式建立憑證：
-   使用您的憑證管理伺服器以在 ICAP 伺服器上建立 SSL 憑證，然後將金鑰複製至您準備安裝 Stunnel 的伺服器。 
-   或者，在 Stunnel 伺服器上，使用下列 OpenSSL 命令產生私密金鑰和自我簽署憑證。 請取代這些變數：
    - 含私密金鑰名稱的 **“key.pem”**
    - 含憑證名稱的 **“cert.pem”**
    - 含新建立金鑰名稱的 **“stunnel-key”**
       
            openssl genrsa -out key.pem 2048
            openssl req -new -x509 -key key.pem -out cert.pem -days 1095
            cat key.pem cert.pem >> /etc/ssl/private/stunnel-key.pem

### <a name="download-the-cloud-app-security-stunnel-client-public-key"></a>下載 Cloud App Security Stunnel 用戶端公開金鑰

從這個位置下載公開金鑰：https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem ，並將它儲存至這個位置：**/etc/ssl/certs/MCASCAfile.pem**

### <a name="configure-stunnel"></a>設定 Stunnel 

Stunnel 設定會設定於 stunnel.conf 檔案中。

1. 在下列目錄中建立 stunnel.conf 檔案：**vim /etc/stunnel/stunnel.conf**

3.  開啟檔案，並貼上下列伺服器設定行，其中 **DLP Server IP** 是 ICAP 伺服器的 IP 位址、**stunnel-key** 是您在上一個步驟中建立的金鑰，而 **MCASCAfile** 是 Cloud App Security Stunnel 用戶端的公用憑證：

        [microsoft-Cloud App Security]
        accept = 0.0.0.0:11344
        connect = **ICAP Server IP**:1344
        cert = /etc/ssl/private/**stunnel-key**.pem
        CAfile = /etc/ssl/certs/**MCASCAfile**.pem
        TIMEOUTclose = 1
        client = no


### <a name="update-your-ip-table"></a>更新 IP 表格
使用下列路由規則，以更新您的 IP 位址表格：
   
    iptables -I INPUT -p tcp --dport 11344 -j ACCEPT

若要持續更新 IP 表格，請使用下列命令：

     sudo apt-get install iptables-persistent
     sudo /sbin/iptables-save > /etc/iptables/rules.v4
 

### <a name="run-stunnel"></a>執行 Stunnel
1.  在 Stunnel 伺服器上，執行下列命令：

        vim /etc/default/stunnel4

2.  將變數 ENABLED 變更為 1：

        ENABLED=1

3.  重新啟動服務，讓設定生效：

        /etc/init.d/stunnel4 restart

4.  執行下列命令，確認 Stunnel 正常執行：

        ps -A | grep stunnel

    並且正在接聽所列出的連接埠：

        netstat -anp | grep 11344

5. 請確定部署 Stunnel 伺服器的網路符合網路必要條件，如前所述。 若要允許來自 Cloud App Security 的連入連線可成功連線伺服器，這是必要作業。

如果此程序仍未執行，請參閱 [Stunnel 文件](https://www.stunnel.org/docs.html) 來進行疑難排解。


## <a name="step-3--connect-to-cloud-app-security"></a>步驟 3：連線至 Cloud App Security

1. 在 Cloud App Security 的 [設定] 下，選取 [安全性延伸模組]，然後選取 [外部 DLP] 索引標籤。

2. 按一下加號以新增連線。 

3. 在 [Add  new external DLP wizard (新增外部 DLP 精靈)] 中，提供將用來識別連接器的 [連線名稱]\(例如，My Forcepoint 連接器)。

4. 選取 [連線類型]：
    - **Symantec Vontu** – 選取此選項可使用 Vontu DLP 設備的自訂整合
    - **Forcepoint DLP** – 選取此選項可使用 Forcepoint DLP 設備的自訂整合
    - **一般 ICAP – REQMOD** - 適用於使用[要求修改](https://tools.ietf.org/html/rfc3507) (Request Modification) 的其他 DLP 設備
    - **一般 ICAP – RESPMOD** - 適用於使用[回應通知](https://tools.ietf.org/html/rfc3507) (Response Modification)
    ![Cloud App Security ICAP 連線](./media/icap-wizard1.png) 的其他 DLP 設備

5. 瀏覽以選取在先前步驟中產生的公開憑證 "cert.pem" 以連線到您的 Stunnel，然後按 [下一步]。

   > [!NOTE]
   > 高度建議核取 [Use secure ICAP (使用安全 ICAP)] 方塊，以設定加密的 Stunnel 閘道。 如果基於測試目的，或您沒有 Stunnel 伺服器，則可以取消核取這個方塊，直接與您的 DLP 伺服器整合。 

5. 在 [伺服器設定] 畫面上，提供您在步驟 2 中所設定 Stunnel 伺服器的 [IP 位址] 和 [連接埠]。 基於負載平衡，您可以設定其他伺服器的 [IP 位址] 和 [連接埠]。 提供的 IP 位址應該是您伺服器的外部靜態 IP 位址。

   ![Cloud App Security ICAP 連線](./media/icap-wizard2.png)
6. 按 [下一步] 。 Cloud App Security 會測試與您所設定伺服器的連線。 如果您收到錯誤，請檢閱指示和網路設定。 成功連線之後，即可按一下 [結束]。

7. 現在，若要將流量導向此外部 DLP 伺服器，當您在 [內容檢查方法] 下建立 [檔案原則] 時，請選取您剛剛建立的連線。 深入了解[建立檔案原則](data-protection-policies.md)。


## 附錄 A：Forcepoint ICAP 伺服器設定<a name="forcepoint"></a>

在 ForcePoint 中，使用下列步驟設定設備：

1.  在 DLP 設備中，移至 [部署] > [系統模組]。 

    ![ICAP 部署](./media/icap-system-modules.png)

2.  在 [一般] 索引標籤中，確定 [ICAP 伺服器] 為 [已啟用]，而且預設 [連接埠] 設定為 [1344]。 此外，在 [Allow connection to this ICAP Server from the following IP addresses (允許從下列 IP 位址連線至這個 ICAP 伺服器)] 下，選取 [Any IP address (任何 IP 位址)]。
 
    ![ICAP 設定](./media/icap-ip-address.png)

3.  在 [HTTP/HTTPS] 索引標籤中，請務必將 [模式] 設定為 [封鎖]。
 
    ![ICAP 封鎖](./media/icap-blocking.png)
 

## 附錄 B：Symantec 部署指南<a name="symantec"></a>

支援的 Symantec DLP 版本為 11 及更新版本。 

如先前所述，您應該在與 Cloud App Security 租用戶所在相同的 Azure 資料中心，部署您的偵測伺服器。 偵測伺服器會透過專用的 IPSec 通道，同步處理強制伺服器。 
 
### <a name="detection-server-installation"></a>偵測伺服器安裝 
Cloud App Security 所使用的偵測伺服器是一個標準的 Network Prevent for Web 伺服器。 有幾個應該變更的組態選項：
1.  停用 [Trial Mode] \(試用模式\)：
    1. 在 [System] \(系統\)  >  [Servers and Detectors] \(伺服器和偵測器\) 下，按一下 ICAP 目標。 
    
      ![ICAP 目標](./media/icap-target.png)
    
    2. 按一下 [設定] 。 
    
      ![設定 ICAP 目標](./media/configure-icap-target.png)
    
    3. 停用 [Trial Mode] \(試用模式\)。
    
      ![停用試用模式](./media/icap-disable-trial-mode.png)
    
2. 在 [ICAP]  >  [Response Filtering] \(回應篩選\) 下，將 [Ignore Responses Smaller Than] \(忽略回應小於\) 值變更為 1。

3. 然後將 "application/*" 新增至 [Inspect Content Type] \(檢查內容類型\) 的清單。
     ![檢查內容類型](./media/icap-inspect-content-type.png)
4. 按一下 [儲存]


### <a name="policy-configuration"></a>原則組態
Cloud App Security 會順暢地支援 Symantec DLP 隨附的所有偵測規則類型，因此不需要變更現有的規則。 不過，有一項組態變更必須套用到所有現有原則和新原則，才能完整的整合。 這項變更在所有原則以外新增的特定回應規則。 

對您的 Vontu 新增組態變更：

1.  移至 [Manage] \(管理\)  >  [Policies] \(原則\)  >  [Response Rules] \(回應規則\)，按一下 [Add Response Rule] \(新增回應規則\)。
    
    ![新增回應規則](./media/icap-add-response-rule.png)

2.  確定已選取 [Automated Response] **\(自動回應\)**  並按 [Next] \(下一步\)。

    ![自動回應](./media/icap-automated-response.png)

3. 輸入規則名稱，例如 **Block HTTP/HTTPS**。 在 [Actions] \(動作\) 下，選取 [Block HTTP/HTTPS] \(封鎖 HTTP/HTTPS\)，然後按一下 [Save] \(儲存\)。

    ![封鎖 http](./media/icap-block-http.png)

對任何現有的原則新增您建立的規則：

1. 在每個原則中，切換至 [Response] \(回應\) 索引標籤。

2. 從 [Response rule] \(回應規則\) 下拉式清單，選取您在上面所建立的封鎖回應規則。

3. 儲存原則。
   
    ![停用試用模式](./media/icap-add-policy.png)

此規則必須新增至所有現有的原則。

>[!NOTE]
> 如果您使用 Symantec vontu 掃描 Dropbox 的檔案，CAS 會自動顯示檔案來自下列 URL：http://misc/filename。此預留位置 URL 實際上不會連到任何地方，只是用於記錄之用。


## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  