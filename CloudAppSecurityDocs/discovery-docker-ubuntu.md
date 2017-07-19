---
title: "設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題說明使用 Ubuntu 上的 Docker，在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cc29a6cb-1c03-4148-8afd-3ad47003a1e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e32eebc75355e8016fcdb62a1b113431db346c31
ms.sourcegitcommit: ae4c8226f6037c5eb286eb27142d6bbb397609e9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2017
---
# <a name="set-up-and-configuration-on-ubuntu"></a>Ubuntu 上的安裝與設定

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

-   IT 配置的虛擬機器 I/O 效能：決定記錄檔寫入記錄收集器磁碟的速度。 記錄收集器有內建的安全機制，會監視記錄檔到達的速率，並與上傳速率相比較。 如果網路擁塞，記錄收集器就會開始卸除記錄檔。 如果您的安裝程式通常每小時超過 50 GB，建議您將流量分割至多個記錄收集器。

## <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>步驟 1 – Web 入口網站設定：定義資料來源並將它們連結到記錄收集器

1.  請移至自動上傳設定頁面上︰  <br></br>在 Cloud App Security 入口網站中，依序按一下設定圖示 ![設定圖示](./media/settings-icon.png) 和 [記錄收集器]。

2.  為每個要上傳記錄檔的防火牆或 Proxy，建立相符的資料來源︰

    ![ubuntu1](./media/ubuntu1.png)

    a. 按一下 [加入資料來源]。

    b. **命名** Proxy 或防火牆。

    c. 從 [來源] 清單中選取設備。

    d. 比較您的記錄檔和預期的記錄檔格式範例。 如果您的記錄檔格式不符合此範例，您應該將資料來源加入為 [其他]。

    e. 將 [接收器類型] 設定為 [FTP]、[FTPS]、[Syslog – UDP]、[Syslog – TCP] 或 [Syslog – TLS]。
    >[!NOTE]
    >與安全傳輸通訊協定 (FTPS 和 Syslog – TLS) 整合通常需要額外的設定或您的防火牆/Proxy。

    f. 為記錄檔可用來偵測網路流量的每個防火牆和 Proxy 重複這個程序。

3.  移至上方的 [記錄收集器] 索引標籤。

    a. 按一下 [加入記錄收集器]。

    b. 為記錄收集器**命名**。

    c. 輸入您用來部署 Docker 之機器的 [主機 IP 位址]。

    d. 選取所有您想要連接到收集器的 [資料來源]，然後按一下 [更新] 以儲存設定，請參閱接下來的部署設定。

    ![ubuntu2](./media/ubuntu2.png)

    >  [!NOTE]
    > - 單一記錄收集器可以處理多個資料來源。
    >- 請複製螢幕的內容，因為當您進行記錄收集器與 Cloud App Security 的通訊設定時會需要這些資訊。 如果您已選取 Syslog，則這些資訊會包含 Syslog 接聽程式會在哪個連接埠接聽的資訊。

4.  隨即會出現進一步的部署資訊。

 ![ubuntu3](./media/ubuntu3.png)

5.  **複製**對話方塊中的執行命令。 您可以使用複製到剪貼簿圖示 ![複製到剪貼簿圖示](./media/copy-icon.png)。

6.  **匯出**預期的資料來源設定。 此設定會說明您應如何在應用裝置中設定記錄檔匯出。

  ![ubuntu4](./media/ubuntu4.png)

## <a name="step-2--on-premises-deployment-of-your-machine"></a>步驟 2 – 進行機器的內部部署

> [!Note]
> 下列步驟說明 Ubuntu 中的部署。 其他平台的部署步驟有些不同。

1.  開啟 Ubuntu 機器上的終端機。

2.  使用命令變更為根權限：`Sudo - i`

3.  執行下列命令，解除安裝舊版本並安裝 Docker CE：

    `curl -o /tmp/MCASInstallDocker.sh
    https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh
    && chmod +x /tmp/MCASInstallDocker.sh; sudo /tmp/MCASInstallDocker.sh`

    ![ubuntu5](./media/ubuntu5.png)

4.  使用入口網站中產生的執行命令，部署收集器映像。

    ![ubuntu6](./media/ubuntu6.png)

    >[!NOTE]
    >如果您需要設定 Proxy，請在其下新增 Proxy IP 位址和連接埠。 比方說，如果您的 Proxy 詳細資料是 192.168.10.1:8080，則更新的執行命令如下：<br></br>
     `Sudo docker run --name casCollector -p 21:21 -p 20000-20099:20000-20099 -e
    "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e
    "TOKEN=41f8f442c9a30519a058dd3bb9a19c79eb67f34a8816270dc4a384493988863a" -e
    "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=casCollector" --security-opt
    apparmor:unconfined --cap-add=SYS_ADMIN -dt microsoft/caslogcollector starter`

    ![ubuntu7](./media/ubuntu7.png)

5.  執行下列命令，確認收集器正常執行：`Docker logs \<collector_name\>`

您應該會看到下列訊息：**已順利完成！**

  ![ubuntu8](./media/ubuntu8.png)

## <a name="step-4---on-premises-configuration-of-your-network-appliances"></a>步驟 4 - 網路設備的內部部署設定

設定網路防火牆和 Proxy 定期將記錄匯出到對話方塊指示的專用 FTP 目錄 Syslog 連接埠，例如︰

    BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

## <a name="step-5---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>步驟 5 - 確認已在 Cloud App Security 入口網站中部署成功

在 [記錄收集器] 資料表中檢查收集器狀態，並確定狀態為 [已連線]。 如果是 [已建立]，記錄收集器連線和剖析可能尚未完成。

 ![ubuntu9](./media/ubuntu9.png)

您也可以移至 [治理記錄] 並確認記錄檔會定期上傳到入口網站。

如果您在部署期間遇到問題，請參閱[為雲端探索進行疑難排解](troubleshooting-cloud-discovery.md)。

## <a name="see-also"></a>另請參閱
[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)  
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security](https://premier.microsoft.com/)

