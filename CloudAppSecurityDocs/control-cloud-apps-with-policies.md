---
title: "在 Cloud App Security 中建立原則以控制雲端應用程式使用情況 | Microsoft Docs"
description: "本主題提供的資訊說明如何使用與設定原則，以控制雲端應用程式的使用方式。"
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/20/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 14d10238-0f61-43e9-ab96-71534a27d3d4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 2a87251a533a9e8fa68b8807966019c186d5669e
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2017
---
# <a name="control-cloud-apps-with-policies"></a>使用原則來控制雲端應用程式

原則可讓您定義使用者在雲端的行為舉止。 它們可讓您在雲端環境中，偵測到高風險的行為、違規或可疑的資料點和活動，必要時，也可整合修復工作流程，以完全降低風險。 有多種不同類型的原則，與您想要收集的雲端環境資訊以及您可能要採取的修復動作類型相互關聯。  
  
例如，如果您想要隔離資料違規威脅，您需要實施的原則，就會和您想要封鎖危險的雲端應用程式以讓您的組織無法使用它時所使用的原則類型不同。  
  
## <a name="policy-types"></a>原則類型  
當您查看 [原則] 頁面時，可以依據類型和圖示來分辨不同原則和範本，以了解哪些原則可供使用。 可用原則取決於資料來源以及您在 Cloud App Security 為組織啟用的內容，例如，如果您上傳了 Cloud Discovery 記錄，就會顯示與 Cloud Discovery 有關的原則。

可以建立下列類型的原則︰  
  
|原則類型圖示|原則類型|用法|  
|-----|-----------------|---------|  
|![活動原則圖示](./media/activity_policy.png)|活動原則|活動原則可讓您利用應用程式提供者的 API，強制執行各種不同的自動化程序。 這些原則可讓您監視由不同使用者執行的特定活動，或是追蹤意外高比率的某種特定類型活動。|  
|![異常偵測原則圖示](./media/anomaly_detection_policy.png)|異常偵測原則|異常偵測原則可讓您根據您在此處設定的風險因素，尋找雲端中的不尋常活動，在發生不同於組織基準或使用者一般活動的狀況時發出警示。|  
|![Cloud Discovery 原則圖示](./media/discovery_policy.png)|應用程式探索原則|應用程式探索原則可讓您設定警示，在您的組織內偵測到新的應用程式時通知您。|  
|![異常偵測原則圖示](./media/anomaly_detection_policy.png)|Cloud Discovery 異常偵測原則|Cloud Discovery 異常偵測原則會查看您用於探索雲端應用程式的記錄檔，並搜尋不尋常的發生事件。 例如，某位使用者從未使用過 Dropbox，突然上傳 600 GB 到 Dropbox，或是在特定應用程式上的交易比起平日超出許多。|  
|![檔案原則圖示](./media/file_policy.png)|檔案原則|檔案原則可讓您掃描雲端應用程式是否有指定的檔案/檔案類型 (共用、與外部網域共用) 及資料 (專屬資訊、PII、信用卡資訊等)，並可套用治理動作至檔案 (治理動作依據特定雲端應用程式而異)。|  
  
## <a name="identifying-risk"></a>識別風險  
Cloud App Security 可協助您降低雲端中的不同風險。 您可以設定任何原則和警示來與下列風險之一相關聯︰  
  
-   **存取控制︰**使用者從哪裡存取什麼？  
  
     持續監視行為，並偵測異常的活動，包括高風險的內部和外部攻擊，並且套用原則以針對任何應用程式或應用程式中的特定動作進行警示、封鎖或要求身分識別驗證。 依據使用者、裝置與地理位置，啟用內部部署與行動裝置存取控制原則，並搭配使用粗略式封鎖及細微檢視、編輯和封鎖功能。 偵測可疑的登入事件，包括多因素驗證失敗、已停用帳戶登入失敗，以及模擬事件。  
  
-   **相容性︰**是否違反您的相容性要求？  
  
     識別機密或管制資料並加以分類，包括共用每個檔案 (存放在檔案同步處理服務中) 的權限，以確保符合 PCI、SOX、HIPAA 等法規。  
  
-   **組態控制︰**正在對您的組態進行未經授權的變更嗎？  
  
     監視組態變更，包括遠端組態管理。  
  
-   **Cloud Discovery︰**您的組織是否正在使用新的應用程式？ 您是否有正在使用您不了解之 Shadow IT 應用程式的問題？  
  
     根據法規與業界認證及最佳做法，為各個雲端應用程式的整體風險評等，  
    讓您能夠監視每個雲端應用程式的使用者人數、活動、流量及  
    一般使用時數。  
  
-   **DLP：**是否公開共用專屬檔案？ 您需要隔離檔案嗎？  
  
     內部部署的 DLP 整合可使用現有的內部部署 DLP 解決方案，提供整合和良性循環的修復。  
  
-   **特殊權限帳戶︰**需要監視管理員帳戶嗎？  
  
     特殊權限使用者和管理員的即時活動監視和報告。  
  
-   **共用控制︰**資料如何在您的雲端環境中共用？  
  
     檢查檔案的內容和雲端中的內容，並強制執行內部和外部共用原則。 監視共同作業，並強制執行共用原則，例如封鎖在組織外部共用檔案。  
  
-   **威脅偵測︰**是否有可疑活動正在威脅您的雲端環境？  
  
     針對任何原則違規或活動臨界值，透過簡訊或電子郵件接收即時通知。 藉由套用機器學習演算法，Cloud App Security 可讓您偵測可能表示使用者濫用資料的行為。  
  
## <a name="how-to-control-risk"></a>如何控制風險  
請遵循此程序，使用原則來控制風險︰  
  
1.  從範本或查詢建立原則。  
  
2.  微調原則以達到預期的結果。  
  
3.  新增自動化動作，以便自動回應與補救風險。  
  
### <a name="create-a-policy"></a>建立原則  
您可以使用 Cloud App Security 的原則範本做為所有原則的基礎，或從查詢建立原則。  
  
原則範本可協助您設定正確的必要篩選和組態，偵測您環境內感興趣的特定事件。 範本包含所有類型的原則，而且可以適用於各種服務。  
  
若要從 [原則範本] 建立原則，請執行下列動作︰  
  
1.  在主控台中，依序按一下 [控制] 和 [範本]。  
  
     ![](./media/create-policy-from-template.png)  
  
2.  按一下您想要使用的範本資料列最右側的 **+**。 隨即開啟 [建立原則] 頁面，其中包含預先定義的設定範本。  
  
3.  視需要為您的自訂原則修改範本。 在這個以範本為基礎的新原則中，每個屬性和欄位都可以根據您的需求而修改。  
> [!NOTE] 
>使用原則篩選器時，**Contains** 將只搜尋完整文字 – 以逗點、句點、空格或底線隔開。 例如，如果您搜尋 **malware** 或 **virus**，它會找到 virus_malware_file.exe，但不會找到 malwarevirusfile.exe。 如果您搜尋 **malware.exe**，則會找到檔名中有 malware 或 exe 的所有檔案；如果您搜尋 **"malware.exe"** (加上引號)，將只會找到包含確切 "malware.exe" 的檔案。 
     **Equals** 僅會搜尋完整字串；例如，如果您搜尋 **malware.exe**，它會找到 malware.exe，但不會找到 malware.exe.txt。  
4.  依據範本建立好新原則之後，原則範本資料表 (位於原則所建立的來源範本旁) 中的 [連結的原則] 資料行即會出現新原則的連結。  
     您可以從每個範本建立想要的原則數目，它們將全部連結到原始的範本，讓您能夠追蹤使用相同範本建立的所有原則。  
  
或者，您可以**在調查期間建立原則**。 如果您正在調查 [活動記錄]、[檔案] 或 [帳戶]，而且您向下切入以搜尋特定事物，您可以隨時根據您的調查結果建立新的原則。  
  
例如，若您正在查看**活動記錄**，並從您辦公室 IP 位址外查看系統管理活動。

  
若要根據調查結果建立原則，請執行下列作業︰  
  
1.  在主控台中，按一下 [調查]，然後按一下 [活動記錄]、[檔案] 或 [帳戶]。  
  
2.  使用頁面頂端的篩選器將搜尋結果限為可疑區域，例如在 [活動記錄] 頁面中，按一下 [活動]，然後選取 [管理員登入]。 接著，在 [IP 位址]，選取 [類別] 並將值設為不包含您為已辨識的網域建立的 IP 位址類別，例如您的系統管理員、公司及 VPN IP 位址。  
  
     ![從調查建立檔案](./media/create-file-from-investigation.png)  
  
3.  在主控台的右上角，按一下 [從搜尋新增原則]![](./media/new-policy-from-search-button.png)。  
  
4.  隨即開啟 [建立原則] 頁面，其中包含您在調查中使用的篩選器。  
  
5.  視需要為您的自訂原則修改範本。 在這個以調查為基礎的新原則中，每個屬性和欄位都可以根據您的需求而修改。  
   
> [!NOTE] 
> 使用原則篩選器時，**Contains** 將只搜尋完整文字 – 以逗點、句點、空格或底線隔開。 例如，如果您搜尋 **malware** 或 **virus**，它會找到 virus_malware_file.exe，但不會找到 malwarevirusfile.exe。  
     **Equals** 僅會搜尋完整字串；例如，如果您搜尋 **malware.exe**，它會找到 malware.exe，但不會找到 malware.exe.txt。  
  
 
 
![從調查建立活動原則](./media/create-activity-policy-from-investigation.png)
 
 
  
> [!NOTE]  
>  如需設定原則欄位的詳細資訊，請參閱對應的原則文件︰  
>   
>  [使用者活動原則](user-activity-policies.md)  
>   
>  [資料保護原則](data-protection-policies.md)  
>   
>  [Cloud Discovery 原則](cloud-discovery-policies.md)  

  
### <a name="add-automated-actions-to-respond-and-remediate-risks-automatically"></a>新增自動化動作以自動回應與補救風險

如需每個應用程式的可用管理動作清單，請參閱[管理連線的應用程式](governance-actions.md)。

您也可以設定原則，在偵測到相符項目時，以電子郵件或簡訊向您傳送警示。 

請移至[自訂入口網站](general-setup.md)來設定通知喜好設定 
  
> [!NOTE] 
> 每個電話號碼每天透過簡訊傳送的警示數目上限是 10。 請注意，會根據 UTC 時區來計算日期。 


## <a name="enable-and-disable-policies"></a>啟用和停用原則

建立原則之後，您可以啟用或停用它。 這可避免在建立原則後，為了停止它而刪除原則。 相反地，若因故想要停止原則，只要停用它，直到您選擇再次啟用它為止。

- 若要啟用原則，請在 [原則] 頁面上按一下您想要啟用的原則資料列結尾的三個點，然後選取 [啟用]。 

![啟用原則](./media/enable-policy.png)

- 若要停用原則，請在 [原則] 頁面上按一下您想要停用的原則資料列結尾的三個點，然後選取 [停用]。

![停用原則](./media/disable-policy.png)

新原則建立之後，預設啟用。

## <a name="see-also"></a>另請參閱  
[可保護雲端環境的日常活動](daily-activities-to-protect-your-cloud-environment.md)   
[如需技術支援，請前往 Cloud App Security 的輔助支援頁面。](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier 客戶也可以直接從 Premier 支援入口網站選擇 Cloud App Security。](https://premier.microsoft.com/)  
  