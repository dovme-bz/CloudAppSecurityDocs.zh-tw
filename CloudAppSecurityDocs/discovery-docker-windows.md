---
title: "在 Windows 上使用 Docker 設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題說明在 Windows 中使用 Docker，在 Cloud App Security 中設定自動記錄檔上傳以進行連續報告的程序。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 308c06b3-f58b-4a21-86f6-8f87823a893a
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 062ada4cc621eff89bf2968dd230f33fc84000d6
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2017
---
# <a name="set-up-and-configure-the-automatic-log-collector-docker-on-windows-server-2016"></a>在 Windows Server 2016 上安裝和設定自動記錄檔收集器 Docker

> [!NOTE]
> 此功能正逐步在租用戶間推出。 如果您希望加入預覽，請連絡支援服務。

## <a name="technical-requirements"></a>技術需求

-   作業系統：Windows Sever 2016 或 Windows 10

-   磁碟空間：250 GB

-   CPU：2

-   RAM：4 GB

-   防火牆設定：

    -   允許記錄收集器接收輸入的 FTP 和 Syslog 流量。

    -   允許記錄收集器起始輸出流量至連接埠 443 上的入口網站 (例如 contoso.cloudappsecurity.com)。

> [!NOTE]
> 如果您的防火牆要求靜態 IP 位址存取清單，且不支援以 URL 為基礎的白名單，請允許記錄收集器在[連接埠 443 上初始化針對 Microsoft Azure 資料中心 IP 範圍的輸出流量](https://www.microsoft.com/download/details.aspx?id=41653&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)。

## <a name="log-collector-performance"></a>記錄收集器效能

記錄收集器可以處理的記錄檔容量，每小時最多 50 GB。 記錄收集程序的主要瓶頸是︰

-   網路頻寬：您的網路頻寬決定記錄檔的上傳速度。

-   IT 配置的虛擬機器 I/O 效能：決定記錄檔寫入記錄收集器磁碟的速度。 記錄收集器有內建的安全機制，會監視記錄檔到達的速率，並與上傳速率相比較。 如果網路擁塞，記錄收集器就會開始卸除記錄檔。 如果您的安裝程式通常每小時超過 50 GB，建議您將流量分割至多個記錄收集器。

## <a name="set-up-and-configuration"></a>安裝與設定  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>步驟 1 – Web 入口網站設定：定義資料來源並將它們連結到記錄收集器

1.  請移至自動上傳設定頁面上︰<br></br> 在 Cloud App Security 入口網站中，依序按一下設定圖示 [設定圖示](./media/settings-icon.png) 以及 [記錄收集器]。

2.  為每個要上傳記錄檔的防火牆或 Proxy，建立相符的資料來源︰

    ![Windows 1](./media/windows1.png)

    a. 按一下 [加入資料來源]。

    b. **命名** Proxy 或防火牆。

    c. 從 [來源] 清單中選取設備。 如果您選取 [自訂記錄檔格式] 來處理未特別列出的網路設備，請參閱[使用自訂記錄檔剖析器](custom-log-parser.md)以了解組態指示。

    d. 比較您的記錄檔和預期的記錄檔格式範例。 如果您的記錄檔格式不符合此範例，您應該將資料來源加入為 [其他]。

    e. 將 [接收器類型] 設定為 [FTP]、[FTPS]、[Syslog – UDP]、[Syslog – TCP] 或 [Syslog – TLS]。

    > [!NOTE]
    > 與安全傳輸通訊協定 (FTPS 及 Syslog – TLS) 整合通常需要額外的設定或防火牆/Proxy。

    f. 為記錄檔可用來偵測網路流量的每個防火牆和 Proxy 重複這個程序。

3.  移至上方的 [記錄收集器] 索引標籤。

    a. 按一下 [加入記錄收集器]。

    b. 為記錄收集器**命名**。

    c. 輸入您要用來部署 Docker 之電腦的 [主機 IP 位址]。

    d. 選取您想要連線到收集器的所有 [資料來源]，然後按一下 [更新] 以儲存設定 (參閱接下來的部署步驟)。

    ![Windows2](./media/windows2.png)

    > [!NOTE]
    > - 單一記錄收集器可以處理多個資料來源。

    > -   請複製螢幕的內容，因為當您進行記錄收集器與 Cloud App Security 的通訊設定時會需要這些資訊。 如果您已選取 Syslog，則這些資訊會包含 Syslog 接聽程式會在哪個連接埠接聽的資訊。

4.  進一步的部署資訊會出現。

    ![Windows3](./media/windows3.png)

5.  從對話方塊**複製**執行命令。 您可以使用複製至剪貼簿圖示 [複製至剪貼簿圖示](./media/copy-icon.png)。

6.  **匯出**預期的資料來源設定。 此設定會告訴您如何在設備中設定記錄檔匯出。

    ![Windows4](./media/windows4.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>步驟 2 – 電腦的內部部署

>[!NOTE]
>下列步驟描述 Windows Server 中的部署。 其他平台的部署步驟有些不同。

1.  **下載**[適用於 Windows 的最新穩定 Docker](https://docs.docker.com/docker-for-windows/install/\#download-docker-for-windows) \(英文\)。
    
2.  **執行** InstallDocker.msi 安裝程式。

3.  在 Windows 電腦上開啟 PowerShell 終端機。

4.  使用下列命令，**連線**至 docker 中樞：`docker login -u caslogcollector`

5.  使用下列密碼 `C0llector3nthusiast`

    ![windows5](./media/windows5.png)

6.  使用下列命令，從 docker 中樞**提取**至收集器映像：`docker pull microsoft/caslogcollector`

    ![windows6](./media/windows6.png)

7.  使用在入口網站中產生的執行命令部署收集器映像。

    ![windows8](./media/windows8.png)

    >[!NOTE]
    >如果您需要設定 Proxy，請在之下新增 Proxy IP 位址和通訊埠。 例如，如果您的 Proxy 詳細資料是 192.168.10.1:8080，更新的執行命令是：  
 `   docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e
    "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e
    "TOKEN=41f8f442c9a30519a058dd3bb9a19c79eb67f34a8816270dc4a384493988863a" -e
    "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt
    apparmor:unconfined --cap-add=SYS_ADMIN -dt microsoft/caslogcollector starter`

    ![windows9](./media/windows9.png)

9.  執行下列命令，確認收集器正常執行：`docker logs <collector_name>`

您應該會看到 **Finished successfully!** 的訊息。
  ![windows10](./media/windows10.png)

### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>步驟 3 - 網路設備的內部部署設定

設定網路防火牆和 Proxy 定期將記錄匯出到對話方塊指示的專用 FTP 目錄 Syslog 連接埠，例如︰

        BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>步驟 4 - 確認已在 Cloud App Security 入口網站中部署成功

在 [記錄收集器] 資料表中檢查收集器狀態，並確定狀態為 [已連線]。 如果是 [已建立]，記錄收集器連線和剖析可能尚未完成。

![windows11](./media/windows11.png)

您也可以移至 [治理記錄] 並確認記錄檔會定期被上傳到入口網站。

如果您在部署期間遇到問題，請參閱[為雲端探索進行疑難排解](troubleshooting-cloud-discovery.md)。

## <a name="optional---create-custom-continuous-reports"></a>選擇性 - 建立自訂連續報告

在您確認要將記錄檔上傳到 Cloud App Security 並產生報告之後，您可以建立自訂報告。 您現在可以根據 Azure Active Directory 使用者群組建立自訂探索報告。 例如，如果您想要查看行銷部門的雲端使用情況，您可以使用 [匯入使用者群組] 功能匯入行銷群組，然後為此群組建立自訂報告。 您也可以自訂以 IP 位址標籤或 IP 位址範圍為基礎的報告。

1. 在 Cloud App Security 入口網站中，選取設定齒輪下的 [Cloud Discovery 設定]，然後選取 [管理連續報告]。 
2. 按一下 [建立報告] 按鈕並填入欄位。
3. 在 [篩選] 下，您可以依資料來源、依[匯入的使用者群組](user-groups.md)或依 [IP 位址標籤和範圍](ip-tags.md)來篩選資料。 

![自訂連續報告](./media/custom-continuous-report.png)

## <a name="see-also"></a>另請參閱
 
[建立 Cloud Discovery 快照集報告](create-snapshot-cloud-discovery-reports.md)

[設定自動記錄上傳以進行連續報告](configure-automatic-log-upload-for-continuous-reports.md)

[使用 Cloud Discovery 資料](working-with-cloud-discovery-data.md)

