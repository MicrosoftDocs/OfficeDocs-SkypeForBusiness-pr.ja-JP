---
title: 患者アプリを FHIR の Azure API に接続する
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft Teams の患者アプリと FHIR の Azure API への接続方法について説明します (ファースト医療の相互運用性リソース)。
ms.openlocfilehash: 92c5b033215b0e5520b0321042d52579dfb019bf
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827725"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="32d99-103">患者アプリを FHIR の Azure API に接続する</span><span class="sxs-lookup"><span data-stu-id="32d99-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="32d99-104">Microsoft Teams の患者アプリが FHIR インスタンス用の Azure API にアクセスできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32d99-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="32d99-105">この記事では、 [FHIR インスタンス用の AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/)がテナントに設定され、構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="32d99-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="32d99-106">テナントで FHIR インスタンスの Azure API をまだ作成していない場合は、「[クイックスタート: azure portal を使用して AZURE api FOR FHIR を展開](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d99-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="32d99-107">[ここ](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806)をクリックして、患者アプリの管理者の同意を付与します。</span><span class="sxs-lookup"><span data-stu-id="32d99-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="32d99-108">メッセージが表示されたら、テナント管理者またはグローバル管理者の資格情報を使用してサインインし、[**承諾**] をクリックして、必要なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="32d99-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="32d99-110">承諾したら、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="32d99-110">After you accept, close the window.</span></span> <span data-ttu-id="32d99-111">次のようなページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32d99-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="32d99-112">このページのエラーメッセージは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="32d99-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="32d99-113">これは無害であり、承諾が許可されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="32d99-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="32d99-114">(この URL については、よりわかりやすいページで作業しています。</span><span class="sxs-lookup"><span data-stu-id="32d99-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="32d99-115">常にご期待ください)</span><span class="sxs-lookup"><span data-stu-id="32d99-115">Stay tuned!)</span></span>

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="32d99-117">管理者の資格情報で[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="32d99-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="32d99-118">左側のナビゲーションで、[ **Azure Active Directory**] を選び、[**エンタープライズアプリケーション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="32d99-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="32d99-119">"**患者 (dev)**" という名前の行を探し、[**オブジェクト ID** ] 列の値をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="32d99-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="32d99-120">![Azure ポータルの [患者 (dev)] 行のスクリーンショット](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="32d99-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="32d99-121">患者アプリ (検索するか、リソースを参照するか) を接続する、FHIR リソースインスタンスの Azure API に移動して、そのインスタンスの設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="32d99-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure portal の FHIR インスタンス設定用 Azure API のスクリーンショット](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="32d99-123">[**認証**] をクリックし、手順3でコピーしたオブジェクト id を [**許可されたオブジェクト id** ] ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="32d99-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="32d99-124">これにより、患者アプリは FHIR サーバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="32d99-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="32d99-125">オブジェクト ID を貼り付けると、Azure Active Directory によって検証され、その横に緑のチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32d99-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure portal の認証設定のスクリーンショット](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="32d99-127">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32d99-127">Click **Save**.</span></span> <span data-ttu-id="32d99-128">これにより、インスタンスが redeploys ます。これには数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="32d99-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="32d99-129">[**概要**] をクリックし、 **fhir メタデータエンドポイント**から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="32d99-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="32d99-130">FHIR サーバーの URL を取得するには、メタデータタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="32d99-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="32d99-131">たとえば、とhttps://test02-teamshealth.azurehealthcareapis.com/します。</span><span class="sxs-lookup"><span data-stu-id="32d99-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure portal のメタデータエンドポイントのスクリーンショット](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="32d99-133">Teams で、チームに読み込まれている患者のアプリインスタンスに移動して、[**設定**] をクリックし、[**リンク**] ボックスに fhir サーバーエンドポイントの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="32d99-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="32d99-134">次に、[**接続**] をクリックして接続を確立し、検索して患者をリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="32d99-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Teams での患者のアプリ設定のスクリーンショット](../../media/patients-app-teams.png)
    
    <span data-ttu-id="32d99-136">この手順で Teams に接続したときにエラーが発生した場合は、エラーの詳細なスクリーンショットをメールで送信します。メールの件名[行に "](mailto:teamsforhealthcare@service.microsoft.com)患者のアプリ– emr モードのトラブルシューティング" と表示されます。 [Fiddler](https://www.telerik.com/download/fiddler)</span><span class="sxs-lookup"><span data-stu-id="32d99-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="32d99-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="32d99-137">Related topics</span></span>

- [<span data-ttu-id="32d99-138">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="32d99-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="32d99-139">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="32d99-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
