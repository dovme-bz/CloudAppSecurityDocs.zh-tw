---
title: 如何套用治理動作來控制連線的應用程式 | Microsoft Docs
description: 本主題列出並描述可在 Cloud App Security 中採用的所有治理動作，以及追蹤其所有動作的記錄訊息。
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3536c0a5-fa56-4931-9534-cc7cc4b4dfb0
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 77286bcf8981430369497b6fd306b43980b2e856
ms.sourcegitcommit: 0ac08ca7b3140b79f1d36ff7152476c188fa12b3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2018
ms.locfileid: "44144545"
---
*適用於：Microsoft Cloud App Security*


# <a name="governing-connected-apps"></a>治理連線的應用程式
治理可讓您即時控制各應用程式上的使用者活動。 對於連線的應用程式，您可以對檔案或活動套用治理動作。
治理動作是可以直接從 Microsoft Cloud App Security 對檔案或活動執行的一套動作，可即時控制各連線應用程式上的使用者活動。 

> [!NOTE]
> 當 Microsoft Cloud App Security 嘗試對檔案執行治理動作，但因檔案已鎖定而失敗時，會自動重試治理動作。 


### <a name="file-governance-actions"></a>檔案治理動作  

您可以對連線應用程式上的特定檔案、使用者執行下列治理動作，也可以利用特定原則達成相同的目的。

-   通知  

    -   警示 – 系統可以觸發警示，並根據嚴重性層級，透過電子郵件和文字訊息來傳播警示。  

    -   使用者電子郵件通知 – 您可自訂電子郵件訊息，並將其傳送給所有違規的檔案擁有者。  

    -   CC 管理員 – 也可以根據使用者的目錄整合，將電子郵件通知傳送給違反原則之人員的管理員。 (僅限 Salesforce)

-   通知特定使用者 – 將接收這些通知的電子郵件地址特定清單。  

-   通知上一位檔案編輯者 – 將通知傳送給上一位修改檔案的人員。  

-   應用程式中的治理動作  

     每個應用程式皆可強制執行細微的動作；特定動作因應用程式的術語而異。  

    -   變更共用  

        -   移除公用共用 - 僅允許指定的共同作業者進行存取；例如：移除 G Suite 的公用存取權與移除 Box 的直接共用連結。  

        -   移除外部使用者 – 只允許公司使用者進行存取。  

        -   私人使用 – 只有擁有者可以存取檔案，並會移除所有的共用。  

        -   移除共同作業者 – 從檔案中移除特定的共同作業者。  

        - 減少公用存取：將可公開取得的檔案設定為只能透過共用連結來取得。

    -   隔離  

        -   置入使用者隔離中 – 將檔案移至使用者控制的隔離資料夾中，以允許自助式服務。  

        -   置入系統管理隔離中 – 將檔案移至系統管理員磁碟的隔離中，而且必須由系統管理員核准。  

-   從父系繼承權限 - 此治理動作可讓您移除 Office 365 中檔案或資料夾的特定權限集，並還原為針對父資料夾所設定的權限。
-   資源回收筒 – 將檔案移至 [資源回收筒] 資料夾。

![policy_create 警示](./media/policy_create-alerts.png "policy_create 警示")  


### <a name="activity-governance-actions"></a>活動治理動作  

- 通知  

    -   警示 – 系統可以觸發警示，並根據嚴重性層級，透過電子郵件和文字訊息來傳播警示。  

    -   使用者電子郵件通知 – 您可自訂電子郵件訊息，並將其傳送給所有違規的檔案擁有者。  

    -   CC 管理員 – 也可以根據使用者的目錄整合，將電子郵件通知傳送給違反原則之人員的管理員。 (僅限 Salesforce)

    -   通知其他使用者 – 將接收這些通知的電子郵件地址特定清單。  

- 應用程式中的治理動作  

  - 每個應用程式皆可強制執行細微的動作；特定動作視應用程式的術語而異。  

  - 暫時停止使用者的權限 – 暫時停止使用者的應用程式權限。 
    > [!NOTE] 
    > 如果您的 Azure Active Directory 設定為與 Active Directory 內部部署環境中的使用者自動同步，內部部署環境中的設定將會覆寫 Azure AD 設定，而且會還原此治理動作。 

  - 使用者必須重新登入：將使用者登出並要求他們重新登入。  

    ![Cloud App Security 活動原則治理動作](./media/activity-policy-ref6.png "活動原則 ref6")  


### <a name="governance-conflicts"></a>治理衝突

建立多個原則之後，可能會出現多個原則中的治理動作重疊的狀況。 在此案例中，Cloud App Security 會如下所述處理治理動作：

#### <a name="conflicts-between-policies"></a>原則相衝突

- 若兩個原則包含彼此包含的動作 (例如，**設為私人**包含**移除外部共用**)，Cloud App Security 將會解決衝突，並強制執行更強大的動作。
- 如果其中的動作完全無關 (例如**通知擁有者**和**設為私用**)， 則這兩個動作皆會執行。
- 如果動作彼此衝突，(例如**變更擁有者為使用者 A** 和**變更擁有者為使用者 B**)，則每個相符項目可能會產生不同的結果。 建議您變更原則以避免發生衝突，因為這些衝突可能會導致磁碟機出現有害且很難偵測得到的變更。

#### <a name="conflicts-in-user-sync"></a>使用者同步衝突

- 如果您的 Azure Active Directory 設定為與 Active Directory 內部部署環境中的使用者自動同步，內部部署環境中的設定將會覆寫 Azure AD 設定，而且會還原此治理動作。 

### <a name="governance-log"></a>治理記錄
治理記錄會為每個設定執行 Cloud App Security 的工作提供一筆狀態記錄 (包括手動和自動工作)。 這些工作包含您在原則中設定的工作、在檔案和使用者上設定的治理動作，以及您設定 Cloud App Security 採取的任何其他動作。 治理記錄也會提供這些動作成敗的相關資訊。 您可以選擇重試或還原治理記錄中的一些治理動作。 

下列是 Cloud App Security 入口網站可讓您採取的完整動作清單。 如**位置**欄位中所述，整個主控台中有多處可以進行這些動作。 每項採取的治理動作都會列於治理記錄中。
如需原則衝突時如何處理治理動作的資訊，請參閱[原則衝突](control-cloud-apps-with-policies.md)。


|                              <strong>位置</strong>                              | <strong>目標目的類型</strong> |           <strong>治理動作</strong>            |                                                                                                                                <strong>描述</strong>                                                                                                                                |                      <strong>相關的連接器</strong>                       |
|-------------------------------------------------------------------------------------|-------------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
|                                      帳戶                                       |                檔案                 |              移除使用者的共同作業               |                                                                                           移除特定使用者對於所有檔案的所有共同作業 - 對於有人離開公司時很實用。                                                                                            |                                  Box、G Suite                                  |
|                                      帳戶                                       |               帳戶               |                     恢復使用者的權限                      |                                                                                                                                    恢復使用者的權限                                                                                                                                     |                        G Suite、Box、Office、Salesforce                        |
|                                      帳戶                                       |               帳戶               |                    帳戶設定                     |                                                                                                帶您前往特定應用程式 (例如，進入 Salesforce) 中的 [帳戶設定] 頁面。                                                                                                | 所有應用程式 - OneDrive 與 SharePoint 設定從 Office 內設定。 |
|                                      帳戶                                       |                檔案                 |              移轉所有檔案擁有權               |            您可以針對一個帳戶，將某位使用者的檔案全部移轉為由您所選的一位新的人員擁有。 先前的擁有者會成為編輯者，且再也無法變更共用設定。 新的擁有者會收到電子郵件通知，告知擁有權已變更。            |                                    G Suite                                     |
|                              帳戶、活動原則                              |               帳戶               |                      暫時停止使用者的權限                       |                                                                              將使用者設定為沒有任何存取權也無法登入 - 如果使用者在此設定情況下登入，會立即將其鎖住。                                                                              |                        G Suite、Box、Office、Salesforce                        |
|                              活動原則、帳戶                              |               帳戶               |              使用者必須重新登入              |                                         撤銷由使用者核發給應用程式的所有重新整理權杖及工作階段 Cookie。 這會禁止存取組織的任何資料，且會強制使用者要再次登入所有應用程式。                                         |                                    G Suite                                     |
|                              活動原則、帳戶                              |               帳戶               |                 撤銷系統管理員權限                 |                                                                      撤銷系統管理員帳戶的權限 - 例如，設定活動原則在登入嘗試失敗 10 後撤銷系統管理員權限。                                                                       |                                    G Suite                                     |
|                           應用程式儀表板 > 應用程式權限                           |             權限             |                       取消禁止應用程式                        |                             在 Google 和 Salesforce 中：移除應用程式的禁止設定，並允許使用者將權限授與其 Google 或 Salesforce 的第三方應用程式。 在 Office 365 中：還原協力廠商應用程式對 Office 的權限。                              |                          G Suite、Salesforce、Office                           |
|                           應用程式儀表板 > 應用程式權限                           |             權限             |                 撤銷應用程式權限                 |                                                  撤銷協力廠商應用程式對 Google、Salesforce 或 Office 的權限。 這是將針對所有現有權限執行的一次性動作，但無法防止未來的連線。                                                   |                          G Suite、Salesforce、Office                           |
|                           應用程式儀表板 > 應用程式權限                           |             權限             |                 授與應用程式權限                  |                                                   將第三方應用程式權限授與 Google、Salesforce 或 Office。 這是將針對所有現有權限執行的一次性動作，但無法防止未來的連線。                                                   |                          G Suite、Salesforce、Office                           |
|                           應用程式儀表板 > 應用程式權限                           |             權限             |                         禁止應用程式                         |                  在 Google 和 Salesforce 中：撤銷協力廠商應用程式對 Google 或 Salesforce 的權限，並禁止它之後接收權限。 在 Office 365 中：不允許協力廠商應用程式存取 Office 的權限，但未予以撤銷。                  |                          G Suite、Salesforce、Office                           |
|                           應用程式儀表板 > 應用程式權限                           |             權限             |                       撤銷應用程式                        |                                                      撤銷提供給 Google、Salesforce 或 Office 的第三方應用程式權限。 這是將針對所有現有權限執行的一次性動作，但無法防止未來的連線。                                                       |                              G Suite、Salesforce                               |
|                           應用程式儀表板 > 應用程式權限                           |               帳戶               |                  從應用程式撤銷使用者                   |                                                      按一下 [使用者] 下的號碼，即可撤銷特定的使用者。 此螢幕會顯示特定的使用者，您可使用 X 刪除任何使用者的權限。                                                      |                              G Suite、Salesforce                               |
|                    探索 > 探索應用程式/IP 位址/使用者                    |           雲端探索           |                  匯出探索資料                  |                                                                                                                           從探索資料建立 CSV。                                                                                                                           |                                   探索                                    |
|                                     檔案原則                                     |                檔案                 |                          資源回收筒                          |                                                                                                                             將檔案置於使用者的資源回收筒。                                                                                                                             |                             OneDrive, SharePoint                              |
|                                     檔案原則                                     |                檔案                 |                 通知前一位檔案編輯者                 |                                                                                                  傳送電子郵件通知編輯違反原則之檔案的前一位編輯者。                                                                                                   |                                  G Suite、Box                                  |
|                                     檔案原則                                     |                檔案                 |                    通知檔案擁有者                    |                                                      當檔案違反原則時，傳送電子郵件給檔案擁有者。 在 Dropbox 中，如果沒有擁有者與檔案相關聯，則會將通知傳送給您設定的特定使用者。                                                       |                                    所有應用程式                                    |
|                            檔案原則, 活動原則                             |           檔案, 活動            |              傳送副本給擁有者/使用者的主管              |                                                                當檔案擁有者收到電子郵件通知指出其檔案違反原則時，可選擇是否要通知檔案擁有者/使用者的主管。                                                                |                                   Salesforce                                   |
|                            檔案原則, 活動原則                             |           檔案, 活動            |                  通知特定使用者                  |                                                                                                        傳送電子郵件通知特定使用者有檔案違反了原則。                                                                                                        |                                    所有應用程式                                    |
|                           檔案原則與活動原則                           |           檔案, 活動            |                       通知使用者                       |                                                      傳送電子郵件給使用者，通知使用者他們所進行的作業，或他們自己所擁有的檔案違反了原則。 您可以加入自訂通知，讓使用者知道所違反的規定為何。                                                       |                                      全部                                       |
|                                檔案原則及檔案                                |                檔案                 |            移除編輯者的能力以進行共用             |                                                           在 Google 雲端硬碟中，檔案的預設編輯者權限也允許共用。 此治理動作會限制此選項，並限制檔案與擁有者共用。                                                           |                                    G Suite                                     |
|                                檔案原則及檔案                                |                檔案                 | [置於系統管理隔離中](use-case-admin-quarantine.md) |                                                           移除檔案具備的所有權限，並將檔案移至系統管理位置中的隔離資料夾。系統管理員如此即可檢閱該檔案，並加以移除。                                                            |               Office 365 SharePoint、商務用 OneDrive、Box                |
|                                檔案原則及檔案                                |                檔案                 |               套用分類標籤                |                                                                               根據原則中設定的條件自動將 Azure 資訊保護分類標籤套用至檔案。                                                                               |                           Box, OneDrive, SharePoint                           |
|                                檔案原則及檔案                                |                檔案                 |               移除分類標籤               |                                                                              根據原則中設定的條件自動移除檔案的 Azure 資訊保護分類標籤。                                                                              |                           Box, OneDrive, SharePoint                           |
|                        檔案原則、活動原則、警示                         |                 應用程式                 |             需要使用者重新登入              | 您可以要求使用者重新登入所有 Office 365 和 Azure AD 應用程式，以快速有效地修復可疑的使用者活動警示及遭盜用的帳戶。 您可以在 [原則設定] 和 [警示] 頁面中，於 [暫時停止使用者的權限] 選項旁找到新的治理動作。 |                              Office 365、Azure AD                              |
|                                        檔案                                        |                檔案                 |              從使用者隔離還原               |                                                                                                                          還原被隔離的使用者。                                                                                                                           |                                      方塊                                       |
|                                        檔案                                        |                檔案                 |            對自己授與讀取權限             |                                                                                 授與您自己檔案的讀取權限，讓您可以存取該檔案，並了解它是否有違規。                                                                                  |                                    G Suite                                     |
|                                        檔案                                        |                檔案                 |                 允許編輯者進行共用                  |                                           在 Google 雲端硬碟中，檔案的預設編輯者權限也允許共用。 此治理動作和移除編輯者能力 (共用及啟用編輯者以共用檔案) 相反。                                           |                                    G Suite                                     |
|                                        檔案                                        |                檔案                 |                         保護                         |                                                                                                   透過 Azure 資訊保護，套用組織範本來保護檔案。                                                                                                   |                      Office 365 (SharePoint 與 OneDrive)                      |
|                                        檔案                                        |                檔案                 |           撤銷自己的讀取權限           |                                                                       撤銷您自己對檔案的讀取權限，授與您自己有權限可了解檔案是否有違規情況之後，此項目相當實用。                                                                        |                                    G Suite                                     |
|                                 檔案、檔案原則                                  |                檔案                 |                 移轉檔案擁有權                 |                                                                                                               變更擁有者 - 在原則中選取特定的擁有者。                                                                                                               |                                    G Suite                                     |
|                                 檔案、檔案原則                                  |                檔案                 |                  減少公用存取                   |                                                                                                 讓您將可公開取得的檔案設定為只能透過共用連結來取得。                                                                                                  |                                    G Suite                                     |
|                                 檔案、檔案原則                                  |                檔案                 |                  移除共同作業者                  |                                                                                                                        移除檔案的特定共同作業者。                                                                                                                        |                      G Suite、Box、One Drive、SharePoint                       |
|                                 檔案、檔案原則                                  |                檔案                 |                      使其成為私人                       |                                                                                                   使其成為私人 - 不再有任何共同作業者或公用連結，不與任何人共用。                                                                                                   |                         G Suite、One Drive、SharePoint                         |
|                                 檔案、檔案原則                                  |                檔案                 |                  移除外部使用者                  |                                                                                                移除所有外部共同作業者 - 在 [設定] 中可將網域之外的共同作業者設定為內部共同作業者。                                                                                                |                                  G Suite、Box                                  |
|                                 檔案、檔案原則                                  |                檔案                 |             授與網域的讀取權限             |                          為整個網域或特定的網域，對指定的網域授與檔案的讀取權限。 對需要於該網域上進行工作的人員，授與該網域的存取之後，若想要移除公用存取，這項動作很實用。                          |                                    G Suite                                     |
|                                 檔案、檔案原則                                  |                檔案                 |                 置於使用者隔離中                  |                             移除檔案具備的所有權限，並將檔案移至使用者根磁碟機下的隔離資料夾。 使用者如此即可檢閱檔案，並加以移動。 如果手動將它移回，則不會還原檔案共用。                             |                           Box, OneDrive, SharePoint                           |
|                                 檔案、檔案原則                                  |                檔案                 |                  移除公用存取                   |                                                     如果是您的檔案而您將其置於公用存取，就只有設有該檔案存取權的人才可存取 - 取決於檔案所具備的存取種類。                                                     |                                    G Suite                                     |
|                                 檔案、檔案原則                                  |                檔案                 |                移除直接的共用連結                |                                                                                            移除為公用檔案所建立的連結，而只與特定人員共用。                                                                                             |                                      方塊                                       |
|                         設定 > 雲端探索設定                          |           雲端探索           |           重新計算雲端探索分數           |                                                                                                       變更分數計量之後，重新計算雲端應用程式類別目錄中的分數。                                                                                                        |                                   探索                                    |
|               設定 > 雲端探索設定 > 管理資料檢視                |           雲端探索           |     建立自訂雲端探索篩選資料檢視      |                                                                                        建立新的資料檢視，取得探索結果更細微的檢視。 例如，特定的 IP 範圍。                                                                                         |                                   探索                                    |
|                  設定 > 雲端探索設定 > 刪除資料                   |           雲端探索           |               刪除雲端探索資料               |                                                                                                                   刪除從探索來源收集來的所有資料。                                                                                                                   |                                   探索                                    |
| 設定 > 雲端探索設定 > 手動上傳記錄檔/自動上傳記錄檔 |           雲端探索           |               剖析雲端探索資料                |                                                                                                                       已剖析所有記錄資料的通知。                                                                                                                       |                                   探索                                    |

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   

[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  

