---
title: "設定電子郵件通知喜好設定 | Microsoft Docs"
description: "本文說明如何個人化 Cloud App Security 所傳送的電子郵件通知。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 49c2c444b0ae378584f3ddbccccf7c8b34bb50d3
ms.sourcegitcommit: 26ae7b0e1ee0ec3b2c7464a6424d4ebd1cd436ac
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2017
---
##  <a name="mailsettings"></a> 設定電子郵件通知喜好設定  
在功能表列中，按一下設定圖示 ![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [郵件設定]，以針對從 Cloud App Security 傳送給管理員要求警示的電子郵件通知，還有傳送給使用者與他們相關的缺口通知中來設定參數。  
  
![郵件設定功能表](./media/mail-setting-menu.png "郵件設定功能表")  
  
設定下列各項：  
  
1.  **寄件者電子郵件地址**︰您想要用來傳送通知的電子郵件帳戶。  
  
     **寄件者顯示名稱**︰您想要顯示在電子郵件 [寄件者] 欄位中的名稱。  
  
     **回覆電子郵件地址**︰要用於訊息回覆的電子郵件帳戶。  
  
     ![郵件設定組態](./media/mail-settings-config.png "郵件設定組態")  
  
2.  針對 [電子郵件設計]，您可以使用 HTML 檔案，以自訂和設計從系統傳送的電子郵件訊息。 用於範本的 HTML 檔案應該包含下列項目︰  
  
    -   所有範本 CSS 都應內嵌在範本中。  
  
    -   範本中應該有三個無法編輯的預留位置︰  
  
         %%logo%% - 在 [一般設定] 頁面中已上傳之公司標誌的 URL。  
  
         %%title%% - 電子郵件標題的預留位置，由原則所設定。  

         %%content%% - 針對一般使用者所包含內容的預留位置，其由原則所設定。  
     
3.  按一下 [上傳範本...] ，然後選取您建立的檔案。 

4. 然後按一下 [傳送測試電子郵件]，傳送測試電子郵件給自己，以查看您所建立範本的範例。 電子郵件將傳送至您用來登入入口網站的帳戶。 在測試電子郵件中，您將能夠看到中繼資料欄位、範本、電子郵件主旨、電子郵件內文中的標題，以及內容。  範例電子郵件範本如下︰ 



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
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)。   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  