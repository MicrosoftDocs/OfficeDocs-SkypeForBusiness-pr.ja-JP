---
title: 患者アプリを FHIR の Azure API に接続する
author: cichur
ms.author: v-cichur
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
description: Azure API for FHIR (Fast Healthcare Interoperability Resources) Microsoft Teamsで Patients アプリを Azure API に接続する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096269"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="4da08-103">患者アプリを FHIR の Azure API に接続する</span><span class="sxs-lookup"><span data-stu-id="4da08-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="4da08-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="4da08-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4da08-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4da08-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4da08-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4da08-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4da08-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="4da08-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4da08-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4da08-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4da08-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4da08-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4da08-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4da08-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4da08-111">次の手順に従って、Azure API for FHIR Microsoft Teamsにアクセスできる、Azure の Patients アプリを許可します。</span><span class="sxs-lookup"><span data-stu-id="4da08-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="4da08-112">この記事では、テナントに [Azure API for FHIR インスタンス](https://azure.microsoft.com/services/azure-api-for-fhir/) が設定され、構成されていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="4da08-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="4da08-113">テナントに Azure API for FHIR インスタンスをまだ作成していない場合は、「クイック スタート: Azure portal を使用して Azure API for FHIR をデプロイする」 [を参照してください](/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="4da08-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="4da08-114">ここを [クリックして](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 、Patients アプリの管理者の同意を付与します。</span><span class="sxs-lookup"><span data-stu-id="4da08-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="4da08-115">メッセージが表示されたら、テナント管理者またはグローバル管理者の資格情報を使用してサインインし、[同意] をクリックして必要なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="4da08-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Patients アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="4da08-117">承諾した後、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4da08-117">After you accept, close the window.</span></span> <span data-ttu-id="4da08-118">次のようなページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da08-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="4da08-119">ページのエラー メッセージは無視できます。</span><span class="sxs-lookup"><span data-stu-id="4da08-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="4da08-120">これは無害であり、同意が与えらたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4da08-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="4da08-121">(この URL のより使い分け的なページに取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="4da08-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="4da08-122">ご期待ください。</span><span class="sxs-lookup"><span data-stu-id="4da08-122">Stay tuned!)</span></span>

    ![Patients アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="4da08-124">管理者の資格情報 [を使用して Azure Portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4da08-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="4da08-125">左側のナビゲーションで 、[アプリケーション]**をAzure Active Directory** し、[アプリケーション] **Enterprise選択します**。</span><span class="sxs-lookup"><span data-stu-id="4da08-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="4da08-126">**Patients (dev) という名前の** 行を探し、[オブジェクト **ID]** 列の値をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4da08-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Azure portal の患者 (開発) 行のスクリーンショット](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="4da08-128">(検索するか、リソースを参照して) Patients アプリを接続する Azure API for FHIR リソース インスタンスに移動し、そのインスタンスの設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="4da08-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure portal での Azure API for FHIR インスタンス設定のスクリーンショット](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="4da08-130">[ **認証]** をクリックし、手順 3 でコピーしたオブジェクト ID を [許可された **オブジェクト ID] ボックスに貼り付** けます。</span><span class="sxs-lookup"><span data-stu-id="4da08-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="4da08-131">これにより、Patients アプリは FHIR サーバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4da08-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="4da08-132">オブジェクト ID を貼り付Azure Active Directory検証すると、その横に緑色のチェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4da08-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure portal の認証設定のスクリーンショット](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="4da08-134">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4da08-134">Click **Save**.</span></span> <span data-ttu-id="4da08-135">これにより、インスタンスが再デプロイされます。これには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4da08-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="4da08-136">[ **概要]** をクリックし、FHIR メタデータ エンドポイント **から URL をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="4da08-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="4da08-137">メタデータ タグを削除して、FHIR サーバーの URL を取得します。</span><span class="sxs-lookup"><span data-stu-id="4da08-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="4da08-138">たとえば、 `https://test02-teamshealth.azurehealthcareapis.com/` です。</span><span class="sxs-lookup"><span data-stu-id="4da08-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Azure portal のメタデータ エンドポイント](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="4da08-140">このTeams、チームに読み込まれている Patients アプリ インスタンスに移動し **、[設定]** をクリックし、[リンク] ボックスに FHIR サーバー エンドポイント URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4da08-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="4da08-141">次に **、[Connect]** をクリックして接続を確立し、患者を検索してリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="4da08-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="4da08-142">患者アプリの設定 (Teams</span><span class="sxs-lookup"><span data-stu-id="4da08-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="4da08-143">この手順で Teams に接続するときにエラーが発生した場合は、エラーの詳細なスクリーンショット[、Fiddler](https://www.telerik.com/download/fiddler)からのログ、その他の再現手順を電子メールに送信し、件名行に "Patients App – EMR mode troubleshooting" を teamsforhealthcare@service.microsoft.com に送信[します。](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4da08-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4da08-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4da08-144">Related topics</span></span>

- [<span data-ttu-id="4da08-145">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="4da08-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="4da08-146">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="4da08-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)