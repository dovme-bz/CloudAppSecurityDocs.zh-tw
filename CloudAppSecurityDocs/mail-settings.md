---
title: 設定電子郵件通知喜好設定 | Microsoft Docs
description: 本文說明如何個人化 Cloud App Security 所傳送的電子郵件通知。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/29/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 682d3e7a988e7662f393b20296322ee590d85315
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44143202"
---
*適用於：Microsoft Cloud App Security*


##  <a name="mailsettings"></a> 設定電子郵件通知喜好設定  

針對從 Microsoft Cloud App Security 傳送給管理員要求警示的電子郵件通知，以及傳送給使用者與他們相關的缺口通知，若要設定這些通知的參數，請遵循此步驟。 如需應加入反垃圾郵件服務允許清單的 Microsoft Cloud App Security 電子郵件伺服器 IP 位址的詳細資訊，請參閱[網路需求](network-requirements.md)。 


1. 在功能表列中，按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 並選取 [設定]，然後選取 [郵件設定] 索引標籤。  

   ![郵件設定](./media/mail-settings-config.png)

2. 在 [電子郵件寄件者身分識別] 下：如果您打算使用預設的電子郵件設定，則無需在此區段變更任何內容。 如果您想要自訂電子郵件寄件者身分識別，您可以進行這裡任一項設定，以自訂您要變更的欄位。 您可以變更下列任一項或所有設定：[寄件者顯示名稱]、[寄件者電子郵件地址]、[收件者電子郵件地址]。 Microsoft Cloud App Security 會透過使用名稱為 MailChimp®的協力廠商郵件服務為您完成。 請確定您檢閱並接受 MailChimp 的服務條款及隱私權聲明以啟用此功能，否則 Microsoft Cloud App Security 會使用預設設定傳送通知。
   
   > [!NOTE]
   > 根據 [rfc822 標準](http://www.rfc-editor.org/rfc/rfc822.txt)，顯示名稱與電子郵件地址只能使用 Unicode 字元。

  
3. 針對 [電子郵件設計]，您可以使用 HTML 檔案，以自訂和設計從系統傳送的電子郵件訊息。 用於範本的 HTML 檔案應該包含下列項目︰  
  
   -   所有範本 CSS 檔案都應內嵌在範本中。  
  
   -   範本中應該有三個無法編輯的預留位置︰  
  
        %%logo%% - 在 [一般設定] 頁面中已上傳之公司標誌的 URL。  
  
        %%title%% - 電子郵件標題的預留位置，由原則所設定。  

        %%content%% - 針對一般使用者所包含內容的預留位置，其由原則所設定。  
     
4. 按一下 [上傳範本...] ，然後選取您建立的檔案。 

5. 然後按一下 [傳送測試電子郵件]，傳送測試電子郵件給自己，以查看您所建立範本的範例。 電子郵件將傳送至您用來登入入口網站的帳戶。 在測試電子郵件中，您將能夠看到中繼資料欄位、範本、電子郵件主旨、電子郵件內文中的標題，以及內容。  範例電子郵件範本如下︰ 



```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
  <html>  
       <head>  
            <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>  
            <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
          </head>  
          <body class="end-user">  
          <table border="0" cellpadding="20%" cellspacing="0" width="100%" id="background-table">  
            <tr>  
              <td align="center">  
                <!--[if (gte mso 9)|(IE)]>  
                <table width="600" align="center" cellpadding="0" cellspacing="0" border="0">  
                  <tr>  
                    <td>  
                <![endif]-->  
                <table bgcolor="#ffffff" align="center" border="0" cellpadding="0" cellspacing="0" style="padding-bottom: 40px;" id="container-table">  
                  <tr>  
                    <td align="right" id="header-table-cell">  
                      <img src="%%logo%%" alt="Microsoft Cloud App Security" id="org-logo" />  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding-top: 58px;" align="center" valign="top">  
                      <table width="100%" cellpadding="12">  
                        <tr>  
                          <td align="center" class="round-title">  
                            %%title%%  
                          </td>  
                        </tr>  
                      </table>  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding: 0 40px 79px 40px;" class="content-table-cell" align="left" valign="top">  
                        %%content%%  
                    </td>  
                  </tr>  
                  <tr>  
                    <td class="last-row"></td>  
                  </tr>  
                </table>  
                <!--[if (gte mso 9)|(IE)]>  
                </td>  
                </tr>  
                </table>  
                  <![endif]-->  
              </td>  
              </tr>  
          </table>  
            </body>  
          </html>  
   ```
  

  
  

  
    
## <a name="see-also"></a>另請參閱  
[設定 Cloud Discovery](set-up-cloud-discovery.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  