---
title: "設定 IP 範圍和標籤 | Microsoft Docs"
description: "本主題提供使用 IP 標籤和 IP 分類的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b3c8c8917606f3c34055eef0334f010d8aab7998
ms.sourcegitcommit: 661f4ce41262e8462c90fd2a4f1232e2154d5113
translationtype: HT
---
#  <a name="IPtagsandRanges"></a> 使用 IP 範圍和標籤

若要輕鬆找出已知的 IP 位址，例如您的實體辦公室 IP 位址，您需要設定 IP 位址範圍，讓您能標記並適當地分類，以及自訂記錄檔和警示顯示與調查的方式。   
每個 IP 範圍群組可根據預先設定的 IP 類別清單來分類，或是以您自己建立的 IP 標記加以標記。 此外，此設定可讓您根據您的內部網路知識，覆寫公用地理位置資訊。  
  
可支援 IPv4 和 IPv6。  
  
Cloud App Security 對下列 IP 位址有預先設定的內建標籤︰ 
- 原生用戶端
- 過期的作業系統
- 受管理的裝置
- 匿名 Proxy
- 殭屍網路
- Tor
- 相容的裝置
- 已驗證的裝置
- Impersonate

若要在搜尋中使用這些內建的標籤，請參閱其在 Cloud App Security API 文件中的識別碼。 



在功能表列中，按一下設定圖示 ![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [IP 位址範圍]。 按一下 [+新增 IP 位址範圍] 並進行下列設定︰  
  
> [!NOTE]  
>  位置和已註冊的 ISP 會覆寫預設值。   
> 不過，IP 標記會新增至活動而不會覆寫資料。  
  
1.  **命名**您的 IP 範圍。 名稱不會出現在活動記錄檔，它只用於管理您的 IP 範圍。  
  
     若要將 IP 範圍包含在 IP 類別中，請從下拉式功能表選取類別。  
  
2.  輸入您想要設定的 [IP 位址範圍]，然後按一下 "+" 按鈕。 您可以使用網路首碼表示法 (也稱為 CIDR 表示法) 新增任意數目的 IP 位址和子網路，例如 192.168.1.0/32。  
  
3.  若要覆寫這些位址的 [位置] 或 [組織 (ISP)] 欄位，請輸入新值。 例如，如果您的 IP 位址被公開認為在愛爾蘭，但您知道它是在美國，您可以覆寫此設定。  
  
4.  輸入 [已註冊的 ISP]。 這會覆寫您活動中的資料  
  
5.  若要**標記**來自這些 IP 位址的活動，請輸入標記。 在方塊中輸入文字即可建立標記。 您已經設定標記之後，就可以從清單中選擇它，輕鬆地將它新增到其他 IP 範圍。 您可以為每個範圍新增任意數量的 IP 標記。 建立原則時，可以使用 IP 標記。  除了您設定的 IP 標記之外，Cloud App Security 具有不可設定的內建標記。 您可以在 [IP 標記篩選](activity-filters.md)下看到標記清單。  
  
6.  **IP 類別**可用來輕鬆地辨識來自有趣 IP 位址的活動。 類別可在入口網站取得，但需要使用者設定才能決定哪些 IP 位址會包含在每個類別中，「風險」類別除外，它包含兩個 IP 標記 - 匿名 Proxy 和 Tor。  
  
     可以使用下列 IP 類別︰  
  
    -   **系統管理**︰這些應為您管理員的所有 IP 位址。  
  
    -   **內部**︰這些應為您的內部網路、分公司和 Wi-Fi 漫遊位址的所有 IP 位址。  
  
    -   **風險**︰這些應為任何您視為危險的 IP 位址。 它們可以包含您在過去已看到的可疑 IP 位址、競爭對手網路中的 IP 位址等等。  
  
    -   **VPN**︰這些應為您用於遠端工作者的任何 IP 位址。  
  
    -   **雲端 Proxy**︰這應該是您雲端 Proxy 的 IP 位址。  
  
7.  完成時按一下 [建立]。  
  
     ![newipaddress 範圍](./media/newipaddress-range.png "newipaddress 範圍")  
  
  
    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  