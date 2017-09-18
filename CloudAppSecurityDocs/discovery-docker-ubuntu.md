---
title: "設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題說明在 Ubuntu 上使用 Docker，在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cc29a6cb-1c03-4148-8afd-3ad47003a1e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dba7c5cf9a5160e4bd6be4a236f8e64ac4a412e2
ms.sourcegitcommit: d012fc1a099773bd9e9dc61906faab68dae0e996
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2017
---
# <a name="set-up-and-configuration-on-ubuntu"></a>在 Ubuntu 上安裝與設定

> [!NOTE]
> 此功能正逐步在租用戶間推出。 如果您希望加入預覽，請連絡支援服務。

## <a name="technical-requirements"></a>技術需求

-   作業系統：Ubuntu 14.04 或更高版本

-   磁碟空間：250 GB

-   CPU：2

-   RAM：4 GB

-   防火牆設定：

    -   允許記錄收集器接收輸入的 FTP 和 Syslog 流量。

    -   允許記錄收集器起始輸出流量至連接埠 443 上的入口網站 (例如 contoso.cloudappsecurity.com)。

## <a name="log-collector-performance"></a>記錄收集器效能

記錄收集器可以處理的記錄檔容量，每小時最多 50 GB。 記錄收集程序的主要瓶頸是︰

-   網路頻寬：您的網路頻寬決定記錄檔的上傳速度。

-   IT 配置的虛擬機器 I/O 效能：決定記錄檔寫入記錄收集器磁碟的速度。 記錄收集器有內建的安全機制，會監視記錄檔到達的速率，並與上傳速率相比較。 如果網路擁塞，記錄收集器就會開始卸除記錄檔。 如果您的安裝程式每小時通常超過 50 GB，建議將流量分割至多個記錄收集器。

## <a name="set-up-and-configuration"></a>安裝與設定  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>步驟 1 – Web 入口網站設定：定義資料來源並將它們連結到記錄收集器

1.  請移至自動上傳設定頁面上︰  <br></br>在 Cloud App Security 入口網站中，依序按一下設定圖示 ![設定圖示](./media/settings-icon.png) 以及 [記錄收集器]。

2.  為每個要上傳記錄檔的防火牆或 Proxy，建立相符的資料來源︰

    ![ubuntu1](./media/ubuntu1.png)

    a. 按一下 [加入資料來源]。

    b. **命名** Proxy 或防火牆。

    c. 從 [來源] 清單中選取設備。 如果您選取 [自訂記錄檔格式] 來處理未特別列出的網路設備，請參閱[使用自訂記錄檔剖析器](custom-log-parser.md)以了解組態指示。

    d. 比較您的記錄檔和預期的記錄檔格式範例。 如果您的記錄檔格式不符合此範例，您應該將資料來源加入為 [其他]。

    e. 將 [接收器類型] 設定為 [FTP]、[FTPS]、[Syslog – UDP]、[Syslog – TCP] 或 [Syslog – TLS]。
    >[!NOTE]
    >與安全傳輸通訊協定 (FTPS 及 Syslog – TLS) 整合通常需要額外的設定或防火牆/Proxy。

    f. 為記錄檔可用來偵測網路流量的每個防火牆和 Proxy 重複這個程序。

3.  移至上方的 [記錄收集器] 索引標籤。

    a. 按一下 [加入記錄收集器]。

    b. 為記錄收集器**命名**。

    c. 輸入您要用來部署 Docker 之電腦的 [主機 IP 位址]。

    d. 選取您想要連線到收集器的所有 [資料來源]，然後按一下 [更新] 以儲存設定 (參閱接下來的部署步驟)。

    ![ubuntu2](./media/ubuntu2.png)

    >  [!NOTE]
    > - 單一記錄收集器可以處理多個資料來源。
    >- 請複製螢幕的內容，因為當您進行記錄收集器與 Cloud App Security 的通訊設定時會需要這些資訊。 如果您已選取 Syslog，則這些資訊會包含 Syslog 接聽程式會在哪個連接埠接聽的資訊。

4.  進一步的部署資訊會出現。

 ![ubuntu3](./media/ubuntu3.png)

5.  從對話方塊**複製**執行命令。 您可以使用複製至剪貼簿圖示 ![複製至剪貼簿圖示](./media/copy-icon.png)。

6.  **匯出**預期的資料來源設定。 此設定會告訴您如何在設備中設定記錄檔匯出。

  ![ubuntu4](./media/ubuntu4.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>步驟 2 – 電腦的內部部署

> [!Note]
> 下列步驟描述 Ubuntu 中的部署。 其他平台的部署步驟有些不同。

1.  在 Ubuntu 電腦上開啟終端機。

2.  使用下列命令變更為 root 權限：`sudo -i`

3.  執行下列命令解除安裝舊版並安裝 Docker CE：

    `curl -o /tmp/MCASInstallDocker.sh
    https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh
    && chmod +x /tmp/MCASInstallDocker.sh; sudo /tmp/MCASInstallDocker.sh`

    ![ubuntu5](./media/ubuntu5.png)

4.  使用在入口網站中產生的執行命令部署收集器映像。

    ![ubuntu6](./media/ubuntu6.png)

    >[!NOTE]
    >如果您需要設定 Proxy，請在之下新增 Proxy IP 位址和通訊埠。 例如，如果您的 Proxy 詳細資料是 192.168.10.1:8080，更新的執行命令是：<br></br>
     `sudo docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e
    "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e
    "TOKEN=41f8f442c9a30519a058dd3bb9a19c79eb67f34a8816270dc4a384493988863a" -e
    "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt
    apparmor:unconfined --cap-add=SYS_ADMIN -dt microsoft/caslogcollector starter`

    ![ubuntu7](./media/ubuntu7.png)

5.  執行下列命令，確認收集器正常執行：`docker logs \<collector_name\>`

您應該會看到訊息：**Finished successfully!**

  ![ubuntu8](./media/ubuntu8.png)

### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>步驟 3 - 網路設備的內部部署設定

設定網路防火牆和 Proxy 定期將記錄匯出到對話方塊指示的專用 FTP 目錄 Syslog 連接埠，例如︰

    BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>步驟 4 - 確認已在 Cloud App Security 入口網站中部署成功

在 [記錄收集器] 資料表中檢查收集器狀態，並確定狀態為 [已連線]。 如果是 [已建立]，記錄收集器連線和剖析可能尚未完成。

 ![ubuntu9](./media/ubuntu9.png)

您也可以移至 [治理記錄] 並確認記錄檔會定期被上傳到入口網站。

如果您在部署期間遇到問題，請參閱[為雲端探索進行疑難排解](troubleshooting-cloud-discovery.md)。

### <a name="optional---create-custom-continuous-reports"></a>選擇性 - 建立自訂連續報告

在您確認要將記錄檔上傳到 Cloud App Security 並產生報告之後，您可以建立自訂報告。 您現在可以根據 Azure Active Directory 使用者群組建立自訂探索報告。 例如，如果您想要查看行銷部門的雲端使用情況，您可以使用 [匯入使用者群組] 功能匯入行銷群組，然後為此群組建立自訂報告。 您也可以自訂以 IP 位址標籤或 IP 位址範圍為基礎的報告。

1. 在 Cloud App Security 入口網站中，選取設定齒輪下的 [Cloud Discovery 設定]，然後選取 [管理連續報告]。 
2. 按一下 [建立報告] 按鈕並填入欄位。
3. 在 [篩選] 下，您可以依資料來源、依[匯入的使用者群組](user-groups.md)或依 [IP 位址標籤和範圍](ip-tags.md)來篩選資料。 

![自訂連續報告](./media/custom-continuous-report.png)

## <a name="see-also"></a>另請參閱
[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)  
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

