---
title: 設定 IP 範圍和標籤 | Microsoft Docs
description: 本主題提供使用 IP 標籤和 IP 分類的指示。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/18/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f066e17f8b4f2e54a65abb5c58095c0917e4e985
ms.sourcegitcommit: a074880eed43cf6e5ae95807640e99655b24d9be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2018
---
#  <a name="IPtagsandRanges"></a> 使用 IP 範圍和標籤

若要輕鬆找出已知的 IP 位址，例如您的實體辦公室 IP 位址，您需要設定 IP 位址範圍，讓您能適當標記並分類，以及自訂記錄檔和警示的顯示與調查方式。 <br></br>  
每個 IP 範圍群組可根據預先設定的 IP 類別清單來分類，或是以您自己建立的 IP 標記加以標記。 此外，此設定可讓您根據您的內部網路知識，覆寫公用地理位置資訊。  
  
可支援 IPv4 和 IPv6。  
  
Cloud App Security 推出時即已預先設定，具有 Azure 及 Office 365 等熱門雲端提供者的內建 IP 範圍。 此外還有以 Microsoft 威脅情報為基礎的內建標記，包括匿名 Proxy、殭屍網路及 Tor。 您可以在 [IP 位址範圍] 頁面上的下拉式清單看到完整清單。

若要在搜尋中使用這些內建的標籤，請參閱其在 Cloud App Security API 文件中的識別碼。 

> [!NOTE]
> 您可以藉由使用 **IP 位址範圍 API** 來建立指令碼，以便大量新增 IP 範圍。在 Cloud App Security 入口網站功能表列中，依序按一下問號、[API 文件]，便能找到此 API。


內建 IP 位址標籤和自訂 IP 標籤會依階層考量，其中自訂 IP 標籤優先於內建 IP 標籤。 例如，如果 IP 位址依威脅情報標記為 [具風險]，但有自訂 IP 標記將其識別為 [公司]，則優先使用自訂類別和標記。

在功能表列中，按一下設定圖示![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [IP 位址範圍]。 按一下加號以新增 IP 位址範圍，並設定下列欄位︰  
  
> [!NOTE]  
> - 位置和已註冊的 ISP 會覆寫預設。   
> - 不過，IP 標記會新增至活動而不會覆寫資料。  
  
1.  **命名**您的 IP 範圍。 名稱不會顯示在活動記錄檔，而只用於管理您的 IP 範圍。  
  
     若要將 IP 範圍包含在 IP 類別中，請從下拉式功能表選取類別。  
  
2.  輸入您想要設定的 [IP 位址範圍]，然後按一下 "+" 按鈕。 您可以使用網路首碼表示法 (也稱為 CIDR 表示法) 新增任意數目的 IP 位址和子網路，例如 192.168.1.0/32。  
  
3.  **類別**可用來輕鬆地辨識來自特定 IP 位址的活動。 類別可在入口網站取得，但需要使用者設定才能決定各個類別包含哪些 IP 位址，「具風險」類別除外，其包含兩個 IP 標記：匿名 Proxy 和 Tor。  
  
     可以使用下列 IP 類別︰  
  
    -   **系統管理**︰這些應為您管理員的所有 IP 位址。  
  
    -  **雲端提供者**：這些應該是雲端提供者使用的 IP 位址。
  
    -   **公司**︰這些應為您內部網路、分公司和 Wi-Fi 漫遊位址的所有 IP 位址。  
  
    -   **風險**︰這些應為任何您視為危險的 IP 位址。 它們可以包含您在過去已看到的可疑 IP 位址、競爭對手網路中的 IP 位址等等。  
  
    -   **VPN**︰這些應為您用於遠端工作者的任何 IP 位址。  
4.  若要**標記**來自這些 IP 位址的活動，請輸入標記。 在方塊中輸入文字即可建立標記。 在您設定好標記後，就可以從清單中予以選擇，輕鬆地將其新增至其他 IP 範圍。 您可以為每個範圍新增任意數量的 IP 標記。 建立原則時，可以使用 IP 標記。  除了您設定的 IP 標記之外，Cloud App Security 具有不可設定的內建標記。 您可以在 [IP 標記篩選](activity-filters.md)下看到標記清單。  
  
5.  若要覆寫這些位址的 [位置] 或 [組織 (ISP)] 欄位，請輸入新值。 例如，如果您的 IP 位址被公開認為在愛爾蘭，但您知道它是在美國，您可以覆寫此設定。  
  
6.  輸入 [已註冊的 ISP]。 這會覆寫您活動中的資料  
 
7.   完成時按一下 [建立]。  
  
     ![newipaddress 範圍](./media/newipaddress-range.png "newipaddress 範圍")  
  
  
    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  