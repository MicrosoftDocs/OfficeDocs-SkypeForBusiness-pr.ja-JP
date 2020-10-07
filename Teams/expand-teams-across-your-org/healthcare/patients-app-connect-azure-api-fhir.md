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
ms.openlocfilehash: 3bd6cdc694eb197c1e8fd45d7e133576732cdc22
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367617"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="19534-103">患者アプリを FHIR の Azure API に接続する</span><span class="sxs-lookup"><span data-stu-id="19534-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19534-104">**2020年10月30日の有効な患者アプリは廃止され、ユーザーは Teams app store からインストールできなくなります。今すぐ Teams の [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) を使い始めることをお勧めします。**</span><span class="sxs-lookup"><span data-stu-id="19534-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="19534-105">患者のアプリデータは、チームをバックアップする Office 365 グループのグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="19534-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="19534-106">患者のアプリが廃止されると、そのアプリに関連付けられたデータはすべてこのグループに保持されますが、ユーザーインターフェイスを使ってアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="19534-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="19534-107">現在のユーザーは、 [リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使ってリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="19534-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="19534-108">[リストアプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)は、すべての Teams ユーザー用にプレインストールされており、すべてのチームとチャネルでタブとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="19534-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="19534-109">リストを使用すると、ケアチームは、組み込みの [患者] テンプレートを使用して、最初から、または Excel にデータをインポートして、患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="19534-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="19534-110">組織でのリストアプリの管理方法の詳細については、「 [リストアプリを管理](../../manage-lists-app.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19534-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="19534-111">Microsoft Teams の患者アプリが FHIR インスタンス用の Azure API にアクセスできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19534-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="19534-112">この記事では、 [FHIR インスタンス用の AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) がテナントに設定され、構成されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="19534-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="19534-113">テナントで FHIR インスタンスの Azure API をまだ作成していない場合は、「 [クイックスタート: azure portal を使用して AZURE api FOR FHIR を展開](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19534-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="19534-114">[ここ](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806)をクリックして、患者アプリの管理者の同意を付与します。</span><span class="sxs-lookup"><span data-stu-id="19534-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="19534-115">メッセージが表示されたら、テナント管理者またはグローバル管理者の資格情報を使用してサインインし、[ **承諾** ] をクリックして、必要なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="19534-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="19534-117">承諾したら、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="19534-117">After you accept, close the window.</span></span> <span data-ttu-id="19534-118">次のようなページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19534-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="19534-119">このページのエラーメッセージは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="19534-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="19534-120">これは無害であり、承諾が許可されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="19534-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="19534-121">(この URL については、よりわかりやすいページで作業しています。</span><span class="sxs-lookup"><span data-stu-id="19534-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="19534-122">常にご期待ください)</span><span class="sxs-lookup"><span data-stu-id="19534-122">Stay tuned!)</span></span>

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="19534-124">管理者の資格情報で [Azure ポータル](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="19534-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="19534-125">左側のナビゲーションで、[ **Azure Active Directory**] を選び、[ **エンタープライズアプリケーション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="19534-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="19534-126">" **患者 (dev)**" という名前の行を探し、[ **オブジェクト ID** ] 列の値をクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="19534-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="19534-127">![Azure ポータルの [患者 (dev)] 行のスクリーンショット](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="19534-127">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="19534-128">患者アプリ (検索するか、リソースを参照するか) を接続する、FHIR リソースインスタンスの Azure API に移動して、そのインスタンスの設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="19534-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure portal の FHIR インスタンス設定用 Azure API のスクリーンショット](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="19534-130">[ **認証**] をクリックし、手順3でコピーしたオブジェクト id を [ **許可されたオブジェクト id** ] ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="19534-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="19534-131">これにより、患者アプリは FHIR サーバーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="19534-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="19534-132">オブジェクト ID を貼り付けると、Azure Active Directory によって検証され、その横に緑のチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19534-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure portal の認証設定のスクリーンショット](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="19534-134">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19534-134">Click **Save**.</span></span> <span data-ttu-id="19534-135">これにより、インスタンスが redeploys ます。これには数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="19534-135">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="19534-136">[ **概要**] をクリックし、 **fhir メタデータエンドポイント**から URL をコピーします。</span><span class="sxs-lookup"><span data-stu-id="19534-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="19534-137">FHIR サーバーの URL を取得するには、メタデータタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="19534-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="19534-138">たとえば、と https://test02-teamshealth.azurehealthcareapis.com/ します。</span><span class="sxs-lookup"><span data-stu-id="19534-138">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure portal のメタデータエンドポイントのスクリーンショット](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="19534-140">Teams で、チームに読み込まれている患者のアプリインスタンスに移動して、[ **設定**] をクリックし、[ **リンク** ] ボックスに fhir サーバーエンドポイントの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="19534-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="19534-141">次に、[ **接続** ] をクリックして接続を確立し、検索して患者をリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="19534-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Teams での患者のアプリ設定のスクリーンショット](../../media/patients-app-teams.png)
    
    <span data-ttu-id="19534-143">この手順で Teams に接続したときにエラーが発生した場合は、エラーの詳細なスクリーンショットをメールで送信します。メールの件名[行に "](mailto:teamsforhealthcare@service.microsoft.com)患者のアプリ– emr モードのトラブルシューティング" と表示されます。 [Fiddler](https://www.telerik.com/download/fiddler)</span><span class="sxs-lookup"><span data-stu-id="19534-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19534-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="19534-144">Related topics</span></span>

- [<span data-ttu-id="19534-145">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="19534-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="19534-146">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="19534-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
