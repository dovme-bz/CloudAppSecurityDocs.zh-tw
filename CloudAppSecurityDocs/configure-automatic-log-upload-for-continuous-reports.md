---
title: "設定自動記錄檔上傳以進行連續報告 | Microsoft Docs"
description: "本主題提供如何上傳記錄檔以建立自動 Cloud Discovery 報告的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9672336d69f19875d160eb414bf3ca2c525692e1


---

# <a name="configure-automatic-log-upload-for-continuous-reports"></a>設定自動記錄檔上傳以進行連續報告
在設定自動收集記錄檔之前，請確認您的記錄檔與預期記錄檔類型相符，以確保 Cloud App Security 可以剖析特定檔案。 

## <a name="technical-requirements"></a>技術需求
- Hypervisor：HyperV 或 VMware
- 磁碟空間：250 GB
- CPU：2
- RAM：4 GB 
- 防火牆設定： 
- 允許記錄收集器接收輸入的 FTP 和 Syslog 流量
- 允許記錄收集器起始輸出流量至連接埠 443 上的入口網站 (例如 contoso.cloudappsecurity.com)

  
## <a name="set-up-automatic-log-file-collection"></a>設定自動收集記錄檔  
  
記錄收集器可讓您輕鬆地從網路自動上傳記錄檔。 記錄收集器會在您的網路上執行，透過 Syslog 或 FTP 接收記錄檔。 每個記錄檔都會自動處理、壓縮和傳送至入口網站。 在檔案完成 FTP 至記錄收集器以及針對 Syslog 的傳輸之後，即會將 FTP 記錄檔上傳到 Cloud App Security，記錄收集器會寫入記錄檔，由磁碟每隔 20 分鐘接收一次，然後將檔案上傳到 Cloud App Security。  記錄收集器的虛擬機器適用於 Hyper-V (VHD 格式) 和 VMware Hypervisor (OVF 格式)，且需要 250 GB 磁碟空間、2 個 CPU 和 4 GB RAM。 
     
  
     The log collector VHD image can be downloaded and run on Azure servers.  
  
2.  請移至自動上傳設定頁面上︰  
    在 Cloud App Security 入口網站中，依序按一下設定圖示 ![設定圖示](./media/settings-icon.png "settings icon") 和 [Cloud Discovery 設定]，然後選取 [自動上傳記錄] 索引標籤。  
  
3.  為每個要上傳記錄檔的防火牆或 Proxy，建立相符的資料來源︰  
  
    1.  按一下 [加入資料來源]。  
  
    2.  **命名** Proxy 或防火牆。  
  
    3.  從 [來源] 清單中選取設備。  
  
    4.  比較您的記錄檔和預期的記錄檔格式範例。 如果您的記錄檔格式不符合此範例，您應該將資料來源加入為 [其他]。  
  
    5.  將 [接收器類型] 設為 [FTP] 或 [Syslog]。  
  
         若為 **Syslog** 請選擇 [UDP] 或 [TCP]。  
  
    6.  為記錄檔可用來偵測網路流量的每個防火牆和 Proxy 重複這個程序。  
  
4.  移至上方的 [記錄收集器] 索引標籤。  
  
    1.  按一下 [加入記錄收集器]。  
  
    2.  為記錄收集器**命名**。  
  
    3.  選取所有想要連接到收集器的**資料來源**，然後按一下 [更新]。  
  
         > [!NOTE] 
       > 請複製螢幕的內容，因為當您進行記錄收集器與 Cloud App Security 的通訊設定時會需要這些資訊。 如果您已選取 Syslog，則這些資訊會包含 Syslog 接聽程式會在哪個連接埠接聽的資訊。
         
![探索資料來源](./media/discovery-data-sources.png)
> [!NOTE] 
         > 單一記錄收集器可以處理多個資料來源。
  
4.  按一下 Hyper-V 或 VMWare，以**下載**新的記錄收集器虛擬機器，並使用您在入口網站接收到的密碼解壓縮檔案。  
  
## <a name="set-up-your-virtual-machine-in-hyperv"></a>在 Hyper-V 中設定虛擬機器︰  
  
1.  開啟 Hyper-V 管理員。  
  
2.  依序選取 [新增] 和 [虛擬機器]，然後按一下 [下一步]。  
  
             ![discovery hyperv virtual machine](./media/discovery-hyperv-virtual-machine.png "discovery hyperv virtual machine")  
  
3.  為新的虛擬機器**命名**，例如 CloudAppSecurityLogCollector01，然後按一下 [下一步]。  
  
4.  選取 [Generation 1 (第 1 代)]，並按一下 [下一步]。  
  
5.  將 [啟動記憶體] 變更至 [4096 MB]。  
        
6. 檢查此虛擬機器的 [Use Dynamic Memory (使用動態記憶體)]，然後按一下 [下一步]。  
  
7.  如果有此選項，請選擇網路 [連線]，並按一下 [下一步]。  
  
8.  選擇 [使用現有的虛擬硬碟]並選取包含在下載之 ZIP 檔案中的 .**vhd** 檔案。  
  
9.  按 [下一步]  ，然後按一下 [完成] 。  
  
             The machine will be added to your Hyper-V environment.  
  
9. 按一下 [虛擬機器] 資料表中的機器，然後按一下 [啟動]。   
  
10. 連接至記錄收集器的虛擬機器，查看其是否已指派 DHCP 位址：按一下虛擬機器，然後選取 [連線]。 您應該會看到登入提示。 如果您有看到 IP 位址，即可使用終端機/SSH 工具連接至虛擬機器。  如果未顯示 IP 位址，請使用 Hyper-V/VMWare 連線工具與您在建立上述記錄收集器時所複製的認證，進行登入。 您可以變更密碼，並執行下列命令來設定虛擬機器。
```
sudo network_config
```
> [!NOTE]
> 虛擬機器已預先設定為從 DHCP 伺服器取得 IP 位址。 如果您需要設定靜態 IP 位址、預設閘道、主機名稱、DNS 伺服器和 NTPS，您可以使用 **network_config** 公用程式，或以手動方式執行變更。


此時，您的記錄收集器應已連接網路，並能夠連線至 Cloud App Security 入口網站。  

## <a name="log-in-and-import"></a>登入與匯入 
當第一次登入記錄收集器並從入口網站匯入記錄收集器的設定時，步驟如下： 

1.  使用入口網站提供給您的互動式管理認證，透過 SSH 登入記錄收集器。 (如果這是您第一次登入主控台，您必須變更密碼，並在變更密碼之後，再次登入。 如果您使用終端機工作階段，可能需要重新啟動終端機工作階段。 )
2.  使用您在建立記錄收集器時系統提供的存取權杖，執行收集器設定公用程式。 

```
sudo collector_config <access token>
```

3. 輸入您的主控台網域，例如︰

```
contoso.portal.cloudappsecurity.com
```

在您登入 Cloud App Security 入口網站之後，這項資訊會顯示在 URL 中。 
 

4. 輸入您要設定的記錄收集器名稱，例如︰

**CloudAppSecurityLogCollector01** 或上圖的 **NewYork**。
 
8.  從入口網站匯入記錄收集器的組態，如下所示︰  
  
      1.  使用入口網站提供給您的互動式管理認證，透過 SSH 登入記錄收集器。  
  
       2.  使用 **sudo collector_config \<access token>** 命令中提供給您的存取權杖，執行收集器設定公用程式。  
  
             輸入您的主控台網域，例如︰  
  
             **contoso.portal.cloudappsecurity.com ** 
  
             輸入您要設定的記錄收集器名稱，例如︰  
  
             **CloudAppSecurityLogCollector01**  
  
5.  設定網路防火牆和 Proxy 定期將記錄匯出到對話方塊指示的專用 FTP 目錄 Syslog 連接埠，例如︰  
  
     `London Zscaler - Destination path: 614`  
  
     `SF Blue Coat - Destination path: \\CloudAppSecurityCollector01\BlueCoat\`  
  
6.  使用治理記錄來確認記錄檔是否定期上傳至入口網站。  
  
## <a name="log-collector-performance"></a>記錄收集器效能
記錄收集器可以處理的記錄檔容量，每小時最多 50 GB。

記錄收集程序的主要瓶頸是︰
* 網路頻寬：您的網路頻寬決定記錄檔的上傳速度。
* IT 配置的虛擬機器 I/O 效能：決定記錄檔寫入記錄收集器磁碟的速度。

記錄收集器有內建的安全機制，會監視記錄檔到達的速率，並與上傳速率相比較。 如果網路擁塞，記錄收集器就會開始卸除記錄檔。 如果您的安裝程式通常每小時超過 50 GB，建議您將流量分割至多個記錄收集器。


<!--HONumber=Oct16_HO4-->

