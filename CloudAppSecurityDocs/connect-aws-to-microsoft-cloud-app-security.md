---
title: "連接 AWS 與 Cloud App Security 以取得可見度及使用控制 | Microsoft Docs"
description: "本主題提供如何使用 API 連接器將 AWS 應用程式連接至 Cloud App Security 的資訊。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: bb0703442d3568556dc54df5e1bd7901906ca9b3
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/28/2017
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>將 AWS 連接至 Microsoft Cloud App Security
本節提供的指示說明如何使用連接器 API，將 Cloud App Security 連接至您現有的 Amazon Web Services 帳戶。  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>如何將 Amazon Web Services 連接至 Cloud App Security  
  
1.  在您 [Amazon Web Services 主控台](https://console.aws.amazon.com/)的 [Security, Identity & Compliance]\(安全性、身分識別及相容性) 下，按一下 [IAM]。  
  
     ![AWS 身分識別與存取](./media/aws-identity-and-access.png "AWS 身分識別與存取")  
  
2.  按一下 [使用者] 索引標籤，然後按一下 [新增使用者]。  
  
     ![AWS 使用者](./media/aws-users.png "AWS 使用者")      
  
4.  在 [Details] /(詳細資料/) 步驟中，提供新的 Cloud App Security 使用者名稱。 請確定已在 [Access type] \(存取類型\) 底下選取 [Programmatic access] \(以程式設計方式存取\)，然後按一下 [Next Permissions] \(下一步: 權限\)。  

     ![在 AWS 中建立使用者](./media/aws-create-user.png "AWS 中建立使用者")

5. 在 [權限] 步驟中，選取 [Attach existing policies directly]\(直接附加現有的原則)，然後按一下 [建立原則]。

   ![在 AWS 中附加使用者](./media/aws-attach-user-policy.png "在 AWS 中附加使用者原則")

6.  在 [建立原則] 下選取 [Create Your Own Policy]\(建立您自己的原則)。
 
    ![在 AWS 中建立您自己的原則](./media/aws-create-own-policy.png "在 AWS 中建立原則")
 
7.  在 [檢閱原則] 下提供 [原則名稱]，例如 CloudAppSecurityPolicy。

    ![AWS 中的檢閱原則](./media/aws-review-policy.png "AWS 中的檢閱原則")

8. 然後將下列內容貼入 [Policy Document] \(原則文件\) 欄位，然後按一下 [Create policy] \(建立原則\)：
  
    ```     
    {  
      "Version" : "2012-10-17",  
      "Statement" : [{  
          "Action" : [  
            "cloudtrail:DescribeTrails",  
            "cloudtrail:LookupEvents",  
            "cloudtrail:GetTrailStatus",  
            "cloudwatch:Describe*",  
            "cloudwatch:Get*",  
            "cloudwatch:List*",  
            "iam:List*",  
            "iam:Get*"  
          ],  
          "Effect" : "Allow",  
          "Resource" : "*"  
        }  
      ]  
     }  
  
    ```  
  
9. 回到 [Add user] \(新增使用者\) 畫面，視需要重新整理清單，並選取您剛才建立的使用者，然後按一下 [Next: Review] \(下一步: 檢閱\)。

   ![在 AWS 中檢閱使用者原則](./media/aws-review-user.png "檢閱 AWS 中的使用者")

10. 如果所有詳細資料都正確，請按一下 [建立使用者]。

    ![AWS 中的使用者權限](./media/aws-user-permissions.png "在 AWS 中檢閱使用者權限")

11. 當您取得成功訊息後，請按一下 [Download .csv] \(下載 .CSV\) 以儲存新使用者的認證複本，您稍後將會需要它們。  

    ![在 AWS 中下載 CSV](./media/aws-download-csv.png "在 AWS 中下載 CSV")
  
10. 在 AWS 主控台中按一下 [服務]，然後按一下 [管理工具] 下的 [CloudTrail]。  
  
     ![AWS CloudTrail](./media/aws-cloudtrail.png "AWS CloudTrail")  
  
    以前如果未曾使用過 CloudTrail，請按一下 [開始使用]，提供名稱並選取適當的 S3 陣列安來裝它，然後按一下 [開啟]。 為確保您擁有完整的涵蓋範圍，請將 [Apply to all regions]\(套用到所有區域) 設為 [是]。
  
       ![在 AWS 中開啟 CloudTrail](./media/aws-turnon-cloudtrail.png "在 AWS 中開啟 CloudTrail")
  
    [Trails]\(軌跡) 清單中應該會看到新的 CloudTrail 名稱。
    
      ![AWS 中的 CloudTrail 清單](./media/aws-cloudtrail-list.png "AWS 中的 CloudTrail 清單")
  
11. 在 Cloud App Security 入口網站中，依序按一下 [調查] 和 [連線應用程式]。  
  
12. 在 [App 連線程式] 頁面中，依序按一下加號及 [AWS]。  
  
     ![連接 AWS](./media/connect-aws.png "連接 AWS")  
  
13. 在快顯視窗中，將 CSV 檔案的**存取金鑰**及**祕密金鑰**貼入相關欄位，然後按一下 [連接]。  
   ![連接 AWS 應用程式](./media/aws-connect-app.png "連接 AWS 應用程式") 
  
14. 按一下 [測試 API] 確定連線成功。  
  
     測試可能需要幾分鐘的時間。 完成後，您會收到成功或失敗的通知。 收到成功通知之後，按一下 [完成]。  
  
連接 AWS 之後，您會收到連線前七天的事件。 如果您才剛啟用 CloudTrail，則會收到從啟用 CloudTrail 開始的所有事件。
  
## <a name="see-also"></a>另請參閱  
[使用原則來控制雲端應用程式](control-cloud-apps-with-policies.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面](http://support.microsoft.com/oas/default.aspx?prid=16031)  \(英文\)。  
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  
  