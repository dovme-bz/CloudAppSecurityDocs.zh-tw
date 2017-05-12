---
title: "管理 Cloud App Security 入口網站的管理員存取權 | Microsoft Docs"
description: "本主題提供為管理員設定 Cloud App Security 入口網站存取權的指示。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ce7a3bb3951e16efeaeafa3e2fc463a3ac5d9dbc
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: zh-TW
---
## <a name="managing-admin-access"></a>管理管理員存取權

Cloud App Security 支援下列管理員角色：

- 全域管理員：全域管理員有「完整存取」：具有完整存取的管理員在 Cloud App Security 中會擁有完整權限，可以新增管理員、新增原則和設定，上傳記錄檔及執行管理動作。
- 安全性系統管理員：安全性系統管理員有「完整存取」：具有完整存取的管理員在 Cloud App Security 中會擁有完整權限，可以新增管理員、新增原則和設定，上傳記錄檔及執行管理動作。
- 安全性讀取者：安全性讀取者具有唯讀權限，而且可以管理警示。 安全性讀取者受到限制而無法執行下列動作：
      - 建立原則或編輯和變更現有原則 
      - 執行任何管理動作 
      - 上傳探索記錄
      - 禁用或核准第三方應用程式
      - 存取和檢視 IP 位址範圍設定頁面
      - 存取和檢視任何設定頁面 
      - 存取和檢視 Discovery 設定 
      - 存取和檢視 App 連線程式頁面
      - 存取和檢視管理記錄檔 
      - 存取和檢視管理快照集報告頁面 

在 Azure Active Directory 或 Office 365 中具有這些角色的管理員，在 Cloud App Security 中也會有相同的角色。 如需系統管理員角色的詳細資訊，請參閱[在 Azure Active Directory 中指派系統管理員角色 (英文)](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles)。

將其他管理員新增至 Cloud App Security：

1. 按一下設定齒輪 ![設定圖示](./media/settings-icon.png "設定圖示") 然後按一下 [管理管理員存取權]。 

2. 新增應該可以存取 Cloud App Security 的管理員。
  
      
3. 接下來，按一下下拉式清單，設定管理員要擁有的存取類型 ([完整存取] 或 [安全性讀取者])。

     >[!NOTE]
      >任何嘗試存取受限制頁面或執行受限制動作的「安全性讀取者」 將會收到錯誤，指出他們沒有存取頁面或執行動作的權限。

4. 按一下 **關閉**。  

   >[!NOTE]
    >任何非受邀使用者 (使用適當角色 - 全域管理員、安全性系統管理員、相容性管理員) 都可以邀請其他使用者加入 Cloud App Security。
  
 ![管理管理員存取權](./media/manage-admin-access.png "管理管理員存取權")  

**覆寫管理員權限：**

如果您想從 Azure Active Directory 或 Office 365 覆寫系統管理員的權限，可以手動將使用者加入到 Cloud App Security 並指派角色給該使用者來這麼做。
例如，如果您想要指派 Stephanie (她在 Azure Active Directory 中是安全性讀取者)，而要使她在 Cloud App Security 有完整存取權，您可以手動將她新增到 Cloud App Security，然後指派完整存取權給她以覆寫其角色，並允許她在 Cloud App Security 中所需的權限。 


##  <a name="Adminsettings"></a> 自訂管理設定  
若要將您的喜好設定設定為 Cloud App Security 的管理員，請在入口網站功能表列中按一下您的名稱，然後選取 [使用者設定] 來進行下列設定︰  
  
1.  按一下 [帳戶設定]。 這裡，您可以自訂入口網站語言以供自己檢視。 您可以將它設定為以預設語言顯示入口網站，或者自行設定不同的語言。  
  
     ![自訂使用者設定](./media/custom-user-settings.png "自訂使用者設定")  
  
2.  按一下 [通知] 然後針對從系統收到的電子郵件，設定電子郵件和文字通知喜好設定。  您可以設定要接收電子郵件的警示和違規的嚴重性 - 嚴重性會針對每個原則設定，因此當觸發違規時，您將視此處的設定以及遭到違反之原則中的嚴重性設定，而收到電子郵件通知。 電子郵件會傳送給與您用來登入 Cloud App Security 之管理員使用者帳戶相關聯的別名。 輸入電話號碼，以讓 Cloud App Security 能在傳送警示和通知時傳送簡訊給您，並設定您要透過簡訊接收通知的嚴重性層級。  
  
   > [!NOTE] 
   > 每個電話號碼每天透過簡訊傳送的警示數目上限是 10。 請注意，會根據 UTC 時區來計算日期。 
  
  ![通知設定](./media/notification-settings.png "通知設定")  
  
3. 完成時按一下 [儲存]。  


## <a name="region-and-language-settings"></a>地區和語言設定  
  
1. 設定要用於入口網站的預設**語言**。 若要修改特定管理員的語言，請移至 [使用者設定]  >  [帳戶設定]。  
  
   ![時區語言](./media/timezone-language.png "時區語言")  
  
2. 設定 [主要時區]。 Cloud App Security 會持續分析和彙總資料。 根據預設，Cloud App Security 入口網站的時區設定為 UTC。 請務必設定主要時區，這可讓 Cloud App Security 準確地記錄系統事件的日期。 例如，在活動圖表中，資料依日期組織 - 這些日期會受到您系統時區的影響，因此如果您未修改預設時區，您的資料將會根據 UTC 時區組織成 24 小時制的日期，這可能會讓您的資料扭曲數個小時。  
  
     ![主要時區](./media/master-time-zone.png "主要時區")  
  
## <a name="back-up-portal-settings"></a>備份入口網站設定

如果您在任何時間點想要備份入口網站設定，此畫面可讓您執行此作業。 按一下 [匯出入口網站設定] 來建立所有入口網站設定的 json 檔案，包括原則規則、使用者群組和 IP 位址範圍。  
  
![備份主控台](./media/backup-console.png "備份主控台")  
  
##  <a name="mailsettings"></a> 將您的體驗個人化  
在功能表列中，按一下設定圖示 ![設定圖示](./media/settings-icon.png "設定圖示")，然後選取 [郵件設定]，以針對從 Cloud App Security 傳送給管理員要求警示的電子郵件通知，還有傳送給使用者與他們相關的缺口通知中來設定參數。  
  
![郵件設定功能表](./media/mail-setting-menu.png "郵件設定功能表")  
  
設定下列各項：  
  
1.  **寄件者電子郵件地址**︰您想要用來傳送通知的電子郵件帳戶。  
  
     **寄件者顯示名稱**︰您想要顯示在電子郵件 [寄件者] 欄位中的名稱。  
  
     **回覆電子郵件地址**︰要用於訊息回覆的電子郵件帳戶。  
  
     ![郵件設定組態](./media/mail-settings-config.png "郵件設定組態")  
  
2.  您可以使用 HTML 檔案，以自訂和設計從系統傳送的電子郵件。 用於範本的 HTML 檔案應該包含下列項目︰  
  
    -   所有範本 CSS 都應內嵌在範本中。  
  
    -   範本中應該有三個無法編輯的預留位置︰  
  
         %%logo%% - 在 [一般設定] 頁面中已上傳之公司標誌的 URL。  
  
         %%title%% - 電子郵件標題的預留位置，由原則所設定。  
  
         %%content%% - 針對一般使用者所包含內容的預留位置，其由原則所設定。  
  
     範例電子郵件範本如下︰ 
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

  
3.  Click **Upload a template...** and select the file you created.  
  
     Then, click **Send a test email** to send yourself a test email to see an example of the template you created.  
     The email will be sent to the account you used to log into the portal. In the test email you will be able to see the metadata fields, the template, the email subject, the title in the email body and the content.  
  
## Single sign-on  
Cloud App Security is coupled with Azure Active Directory for authentication, provisioning, and licensing related activities. For information on how to manage single sign-on, see [Azure Active Directory federation compatibility list: third-party identity providers that can be used to implement single sign-on](https://msdn.microsoft.com/library/azure/jj679342.aspx).  


> [!NOTE] 
> If you use ExpressRoute, Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance and security. There are no configuration steps required from the customer side.  
    For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  