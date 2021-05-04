---
title: キャリア コーチの購入、構成、および有効化を行Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: キャリア コーチを購入、構成、および有効にする方法については、Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911f880ba817afff10acb2a347a5c8c776d059c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130029"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="4b6d8-103">キャリア コーチの購入、構成、および有効化を行Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b6d8-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="4b6d8-104">キャリア コーチは LinkedIn Microsoft Teams教育アプリの一部で、高等教育学生がキャリアの旅をナビゲートする個別のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="4b6d8-105">キャリア コーチは、学生がキャリア パスを発見し、現実世界のスキルを高め、ネットワークを 1 か所で構築するための統合されたキャリア ソリューションを教育機関に提供します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="4b6d8-106">キャリア コーチの [詳細については、 を参照してください](https://aka.ms/career-coach)。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d8-107">学生、教職員向けキャリア コーチの機能を有効にするには、このガイドのベスト プラクティスと役立つヒントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="4b6d8-108">クイック プランニング [ガイドに関する記事を参照](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) してください。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="4b6d8-109">要件を確認する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-109">Review the requirements</span></span>

<span data-ttu-id="4b6d8-110">教育機関でキャリア コーチを有効にするには、アプリを起動して実行するために必要な情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="4b6d8-111">**技術要件**</span><span class="sxs-lookup"><span data-stu-id="4b6d8-111">**Technical requirements**</span></span>

  - <span data-ttu-id="4b6d8-112">Office 365テナントとAzure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b6d8-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="4b6d8-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b6d8-113">Microsoft Teams</span></span>

  - <span data-ttu-id="4b6d8-114">LinkedIn アカウントの接続 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b6d8-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="4b6d8-115">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="4b6d8-115">**Licenses**</span></span>

  - <span data-ttu-id="4b6d8-116">教員</span><span class="sxs-lookup"><span data-stu-id="4b6d8-116">Faculty</span></span> 

  - <span data-ttu-id="4b6d8-117">学生</span><span class="sxs-lookup"><span data-stu-id="4b6d8-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d8-118">構成を完了するには、キャリア コーチ教員ライセンスを IT 管理者に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="4b6d8-119">**教育機関のデータとファイル**</span><span class="sxs-lookup"><span data-stu-id="4b6d8-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="4b6d8-120">コース カタログのデータ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-120">Course catalog data</span></span>

  - <span data-ttu-id="4b6d8-121">提供される研究分野</span><span class="sxs-lookup"><span data-stu-id="4b6d8-121">Fields of study offered</span></span>

  - <span data-ttu-id="4b6d8-122">教育機関の LinkedIn ページ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="4b6d8-123">LinkedIn Learning キャンパス サブスクリプション (優先)</span><span class="sxs-lookup"><span data-stu-id="4b6d8-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="4b6d8-124">キャリア コーチ のライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="4b6d8-125">キャリア コーチは、教育機関向けソリューション (EES)、クラウド サービス プロバイダー (CSP)、および Microsoft 365 管理センター (Web ダイレクト) を通じて、資格を持つ高等教育機関 (中国とロシアを除く) で世界中で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="4b6d8-126">アプリMicrosoft Teams、顧客は A3/A5 または Microsoft 365/A3/A5 Office 365 A1必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="4b6d8-127">ユーザーにアプリ ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4b6d8-127">Assign app licenses to users</span></span>

<span data-ttu-id="4b6d8-128">詳細な手順については、「ユーザーにライセンスを割り当てる [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-128">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="4b6d8-129">LinkedIn アカウント接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="4b6d8-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="4b6d8-130">キャリア コーチ **では、** 教育機関のユーザーが自分のアカウントをキャリア コーチ内でMicrosoft 365 LinkedIn アカウントに接続する機能を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="4b6d8-131">Azure AD [組織](https://aad.portal.azure.com/) のグローバル管理者であるアカウントを使用して、Azure ADにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="4b6d8-132">[ユーザー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-132">Select **Users**.</span></span>

3. <span data-ttu-id="4b6d8-133">[ユーザー] **ページで** 、[ユーザー設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="4b6d8-134">**[LinkedIn アカウント接続] で**、ユーザーが自分のアカウントを接続して、一部の Microsoft アプリ内の LinkedIn 接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="4b6d8-135">ユーザーが自分のアカウントの接続に同意するまで、データは共有できません。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="4b6d8-136">教育機関 **のすべてのユーザー** に対してサービスを有効にするには、[はい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="4b6d8-137">教育機関 **で選択した** ユーザーのグループにのみサービスを有効にするには、[選択したグループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="4b6d8-138">教育機関 **のすべてのユーザー** からの同意を取り消す場合は、[いいえ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="4b6d8-139">LinkedIn アカウント[接続をネットワークに統合する方法Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="4b6d8-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="4b6d8-140">管理センターでキャリア コーチをTeamsする</span><span class="sxs-lookup"><span data-stu-id="4b6d8-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="4b6d8-141">管理センターの管理者設定Microsoft Teams、教育機関用のキャリア コーチを構成し、ユーザーに対して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="4b6d8-142">キャリア コーチ アプリの設定にアクセスする</span><span class="sxs-lookup"><span data-stu-id="4b6d8-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="4b6d8-143">[アプリ[の管理] ページを](/microsoftteams/manage-apps)使用して、教育機関Teamsカタログのアプリのアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="4b6d8-144">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="4b6d8-145">左側のナビゲーションで、[アプリの管理] **Teamsを**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="4b6d8-146">ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="4b6d8-147">キャリア コーチを検索 **または参照します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="4b6d8-148">[**キャリア コーチ] を** 選択し、[キャリア コーチ **] を設定。**</span><span class="sxs-lookup"><span data-stu-id="4b6d8-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![[キャリア コーチ] アプリが選択され、次のオプションが表示設定表示されます。](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="4b6d8-150">キャリア コーチ アプリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="4b6d8-151">キャリア コーチには、次の 5 つの構成カテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="4b6d8-152">ブランドと設定</span><span class="sxs-lookup"><span data-stu-id="4b6d8-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="4b6d8-153">LinkedIn の構成</span><span class="sxs-lookup"><span data-stu-id="4b6d8-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="4b6d8-154">コース カタログ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="4b6d8-155">研究分野</span><span class="sxs-lookup"><span data-stu-id="4b6d8-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="4b6d8-156">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="4b6d8-157">学生、教職員向けアプリを効果的に有効にするには、ブランドと設定、LinkedIn 構成、コース カタログ、および学習フィールドが必要です。 </span><span class="sxs-lookup"><span data-stu-id="4b6d8-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="4b6d8-158">ブランドと設定</span><span class="sxs-lookup"><span data-stu-id="4b6d8-158">Brand and preferences</span></span>

<span data-ttu-id="4b6d8-159">ブランドと環境設定の設定ページで教育機関の名前、ロゴ、既定の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![管理センターのキャリア コーチ のブランド化セクション](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="4b6d8-161">教育機関のアイコン</span><span class="sxs-lookup"><span data-stu-id="4b6d8-161">Educational institution icon</span></span>

<span data-ttu-id="4b6d8-162">教育機関アイコンは、教育機関固有のコンテンツ、アプリ全体のコース カタログ リソース、ダッシュボードの実際のエクスペリエンス セクションで識別するために、キャリア コーチ全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="4b6d8-163">アイコンの形式は次の形式が最適です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="4b6d8-164">透過的な PNG</span><span class="sxs-lookup"><span data-stu-id="4b6d8-164">A transparent PNG</span></span>
 - <span data-ttu-id="4b6d8-165">縦横比 1:1</span><span class="sxs-lookup"><span data-stu-id="4b6d8-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="4b6d8-166">最大サイズは 64 ピクセル x 64 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="4b6d8-167">教育機関のサムネイル</span><span class="sxs-lookup"><span data-stu-id="4b6d8-167">Educational institution thumbnail</span></span>

<span data-ttu-id="4b6d8-168">教育機関のアイコンは、特定の画像がコースで使用できない場合に、アプリ全体のコース カタログ リソースに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="4b6d8-169">アイコンの形式は次の形式が最適です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="4b6d8-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="4b6d8-170">A PNG</span></span>
- <span data-ttu-id="4b6d8-171">縦横比 16:9</span><span class="sxs-lookup"><span data-stu-id="4b6d8-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="4b6d8-172">最大サイズは 360 ピクセル x 200 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="4b6d8-173">LinkedIn の構成</span><span class="sxs-lookup"><span data-stu-id="4b6d8-173">LinkedIn configuration</span></span>

<span data-ttu-id="4b6d8-174">LinkedIn 構成は、キャリア コーチと LinkedIn の一般卒業生データを接続します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d8-175">LinkedIn ページ接続が確認されていないと、キャリア コーチを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="4b6d8-176">LinkedIn ページを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="4b6d8-177">教育機関の LinkedIn ページを決定します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="4b6d8-178">LinkedIn で検索するか、キャリア サービスのスタッフ メンバーと接続して、使用する正しいページを決定して、LinkedIn ページを探します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="4b6d8-179">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="4b6d8-180">[アプリ **Teams**  >  **アプリの管理**  >  **] を選択して、キャリア コーチ**  >  **LinkedIn 接続を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="4b6d8-181">教育機関の LinkedIn ページ URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="4b6d8-182">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-182">Select **Apply**.</span></span>

4. <span data-ttu-id="4b6d8-183">確認 URL をコピーし、教育機関の LinkedIn ページ管理者 [LinkedIn ページ管理者ドキュメントと共有します](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="4b6d8-184">検証リンクの有効期限は 30 日後です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-184">The verification link expires after 30 days.</span></span>  

   ![キャリア コーチの linkedin 設定](media/linkedin.png)  

#### <a name="course-catalog"></a><span data-ttu-id="4b6d8-186">コース カタログ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-186">Course catalog</span></span>

<span data-ttu-id="4b6d8-187">コース カタログは、教育機関が学生に提供するコースとクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="4b6d8-188">これらのコースは、次の 2 つの領域でアプリ内で使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="4b6d8-189">コースは、学習リソースの一部として返されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="4b6d8-190">コースとコースのメタデータ (説明など) は、学生がトランスクリプトをアップロードするときに自分のスキルを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="4b6d8-191">コース カタログを作成するには、教育機関で教えられたすべてのコースの一覧をまとめ、CSV ファイルとしてアップロードします。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="4b6d8-192">このアプリはコース カタログから描画され、トランスクリプトから学生のスキルを特定し、受講するコースを提案します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b6d8-193">学生[情報の保護については、「Teams](location-of-data-in-teams.md)[のデータ](security-compliance-overview.md)の場所」と「セキュリティとコンプライアンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-193">See [Location of data in Teams](location-of-data-in-teams.md) and [Security and compliance](security-compliance-overview.md) for information about protecting of student information.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="4b6d8-194">コース カタログ ドキュメントの書式設定とスキーマ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-194">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="4b6d8-195">ドキュメントは、最大サイズが 18 MB の CSV 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-195">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="4b6d8-196">ドキュメントには、必須フィールドのコース タイトル、 **コース** **ID、コース** URL が **含まれている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-196">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="4b6d8-197">推奨されるフィールドを含め、より良い検索結果とスキル識別を返して、学生のエクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-197">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d8-198">開始するには、 [サンプル コース カタログドキュメント]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) から開始します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-198">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

##### <a name="sample-csv-file"></a><span data-ttu-id="4b6d8-199">サンプル .CSV ファイル</span><span class="sxs-lookup"><span data-stu-id="4b6d8-199">Sample .CSV file</span></span>

```
courseId,title,sourceLink,description,language,format,thumbnailLink,thumbnailAltText,educationLevel,topics
"AA-501","Analytics Foundations","https://example.com/course-id","This course equips the student with the knowledge and skills needed to conduct and present large-scale studies based on advanced analytics.","en-us","In-person","https://via.placeholder.com/360x200","Undergraduate","Alt text for the thumbnail","analytics, data science, data analysis, linear regression"
```

<span data-ttu-id="4b6d8-200">次の表は、コース カタログに含める項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-200">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="4b6d8-201">名前</span><span class="sxs-lookup"><span data-stu-id="4b6d8-201">Name</span></span>             | <span data-ttu-id="4b6d8-202">状態</span><span class="sxs-lookup"><span data-stu-id="4b6d8-202">Status</span></span>      | <span data-ttu-id="4b6d8-203">型</span><span class="sxs-lookup"><span data-stu-id="4b6d8-203">Type</span></span>   | <span data-ttu-id="4b6d8-204">説明</span><span class="sxs-lookup"><span data-stu-id="4b6d8-204">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="4b6d8-205">courseId</span><span class="sxs-lookup"><span data-stu-id="4b6d8-205">courseId</span></span>         | <span data-ttu-id="4b6d8-206">必須</span><span class="sxs-lookup"><span data-stu-id="4b6d8-206">Required</span></span>    | <span data-ttu-id="4b6d8-207">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-207">string</span></span> | <span data-ttu-id="4b6d8-208">通常、コース ID (通常はトランスクリプトで生成された値にマップされます)。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-208">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="4b6d8-209">タイトル</span><span class="sxs-lookup"><span data-stu-id="4b6d8-209">title</span></span>            | <span data-ttu-id="4b6d8-210">必須</span><span class="sxs-lookup"><span data-stu-id="4b6d8-210">Required</span></span>    | <span data-ttu-id="4b6d8-211">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-211">string</span></span> | <span data-ttu-id="4b6d8-212">通常、コースのタイトル。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-212">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="4b6d8-213">sourceLink</span><span class="sxs-lookup"><span data-stu-id="4b6d8-213">sourceLink</span></span>       | <span data-ttu-id="4b6d8-214">必須</span><span class="sxs-lookup"><span data-stu-id="4b6d8-214">Required</span></span>    | <span data-ttu-id="4b6d8-215">URL</span><span class="sxs-lookup"><span data-stu-id="4b6d8-215">URL</span></span>    | <span data-ttu-id="4b6d8-216">コース ページへの Web サイトのリンク。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-216">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="4b6d8-217">説明</span><span class="sxs-lookup"><span data-stu-id="4b6d8-217">description</span></span>      | <span data-ttu-id="4b6d8-218">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-218">Recommended</span></span> | <span data-ttu-id="4b6d8-219">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-219">string</span></span> | <span data-ttu-id="4b6d8-220">コースの概要テキスト。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-220">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="4b6d8-221">言語</span><span class="sxs-lookup"><span data-stu-id="4b6d8-221">language</span></span>         | <span data-ttu-id="4b6d8-222">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-222">Recommended</span></span> | <span data-ttu-id="4b6d8-223">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-223">string</span></span> | <span data-ttu-id="4b6d8-224">コースの言語。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-224">Language of the course.</span></span> <span data-ttu-id="4b6d8-225">標準の言語コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-225">Use standard language codes.</span></span>                           |
| <span data-ttu-id="4b6d8-226">書式</span><span class="sxs-lookup"><span data-stu-id="4b6d8-226">format</span></span>           | <span data-ttu-id="4b6d8-227">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-227">Recommended</span></span> | <span data-ttu-id="4b6d8-228">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-228">string</span></span> | <span data-ttu-id="4b6d8-229">教育のモード (オンライン、ビデオ、対人など)。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-229">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="4b6d8-230">thumbnailLink</span><span class="sxs-lookup"><span data-stu-id="4b6d8-230">thumbnailLink</span></span>    | <span data-ttu-id="4b6d8-231">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-231">Recommended</span></span> | <span data-ttu-id="4b6d8-232">URL</span><span class="sxs-lookup"><span data-stu-id="4b6d8-232">URL</span></span>    | <span data-ttu-id="4b6d8-233">コースイメージへのサムネイル リンク。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-233">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="4b6d8-234">thumbnailAltText</span><span class="sxs-lookup"><span data-stu-id="4b6d8-234">thumbnailAltText</span></span> | <span data-ttu-id="4b6d8-235">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-235">Recommended</span></span> | <span data-ttu-id="4b6d8-236">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-236">string</span></span> | <span data-ttu-id="4b6d8-237">画像のアクセシビリティ代替テキスト</span><span class="sxs-lookup"><span data-stu-id="4b6d8-237">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="4b6d8-238">educationLevel</span><span class="sxs-lookup"><span data-stu-id="4b6d8-238">educationLevel</span></span>   | <span data-ttu-id="4b6d8-239">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-239">Recommended</span></span> | <span data-ttu-id="4b6d8-240">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-240">string</span></span> | <span data-ttu-id="4b6d8-241">学習レベル(例)</span><span class="sxs-lookup"><span data-stu-id="4b6d8-241">Study level, ex.</span></span> <span data-ttu-id="4b6d8-242">学部/卒業。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-242">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="4b6d8-243">トピック</span><span class="sxs-lookup"><span data-stu-id="4b6d8-243">topics</span></span>           | <span data-ttu-id="4b6d8-244">推奨</span><span class="sxs-lookup"><span data-stu-id="4b6d8-244">Recommended</span></span> | <span data-ttu-id="4b6d8-245">文字列</span><span class="sxs-lookup"><span data-stu-id="4b6d8-245">string</span></span> | <span data-ttu-id="4b6d8-246">コースが教えるスキルに関連付けられているトピックまたはタグ。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-246">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="4b6d8-247">コース カタログを追加する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-247">Add the course catalog</span></span>

1. <span data-ttu-id="4b6d8-248">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-248">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="4b6d8-249">[アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し、[キャリア** &gt; **コーチ] 設定** &gt; **カタログを選択します**。  </span><span class="sxs-lookup"><span data-stu-id="4b6d8-249">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="4b6d8-250">アップロード CSV 形式のコースを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-250">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="4b6d8-251">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-251">Select **Apply**.</span></span>

   ![キャリア コーチ アプリのコース カタログ セクション](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="4b6d8-253">研究分野</span><span class="sxs-lookup"><span data-stu-id="4b6d8-253">Fields of study</span></span>

<span data-ttu-id="4b6d8-254">研究分野は、関心のある主要な分野、学術的専攻、および学位と同義です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-254">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="4b6d8-255">これらのタイトルは、学生がアプリの使用を開始し、パーソナライズされたプロファイルの設定を開始するときに参照されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-255">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="4b6d8-256">エンジニアリング、英語、ビジネスなど、学生が利用できるすべての学習フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-256">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="4b6d8-257">フィールドの一覧を使用すると、学生は興味のある分野を発見し、自分のプロフィールにフォーカス領域を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-257">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6d8-258">最初に、スタディ [ドキュメントのサンプル フィールドから始](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) める。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-258">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="4b6d8-259">調査のフィールドを追加する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-259">Add the fields of study</span></span>

1. <span data-ttu-id="4b6d8-260">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-260">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="4b6d8-261">[アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し**、[キャリア &gt; **コーチ設定** &gt; **フィールド] を選択します**。  </span><span class="sxs-lookup"><span data-stu-id="4b6d8-261">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="4b6d8-262">アップロードのフィールドを CSV 形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-262">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="4b6d8-263">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-263">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="4b6d8-264">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-264">Customization</span></span>

<span data-ttu-id="4b6d8-265">キャリア コーチは、教育機関に固有のカスタマイズが可能です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-265">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="4b6d8-266">カスタマイズでは、ダッシュボードへのエクスペリエンスの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-266">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="4b6d8-267">ジョブ ボード、イベント、キャリア サービス オフィス、キャリア関連イベント、学生クラブ、および学生が実際のエクスペリエンスを得るのに役立つその他のリソースへのリンクを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-267">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="4b6d8-268">カスタマイズされたエクスペリエンスを追加する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-268">Add customized experiences</span></span>

1. <span data-ttu-id="4b6d8-269">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-269">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="4b6d8-270">[アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し、[キャリア コーチ]**  >  **設定** &gt; **カスタマイズします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-270">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="4b6d8-271">各 URL、タイトル、および簡単な説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-271">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="4b6d8-272">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-272">Select **Apply**.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="4b6d8-273">アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="4b6d8-273">Enable the app</span></span>

<span data-ttu-id="4b6d8-274">構成が完了したら、学生とライセンスを取得したユーザーがキャリア コーチにアクセスできるアプリを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-274">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b6d8-275">管理者ロールのアクセス許可がTeams必要です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-275">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="4b6d8-276">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-276">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="4b6d8-277">[アプリ **のTeams** &gt; **アプリの管理キャリア コーチ]** &gt; **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-277">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="4b6d8-278">[状態] トグルを [許可] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-278">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="4b6d8-279">[許可] は、教育機関のユーザーがアプリを利用できるという意味です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-279">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="4b6d8-280">[ブロック] は、学生がアプリを利用できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-280">Blocked means that the app isn't available to students.</span></span>

#### <a name="pin-the-app"></a><span data-ttu-id="4b6d8-281">アプリをピン留めする</span><span class="sxs-lookup"><span data-stu-id="4b6d8-281">Pin the app</span></span>

<span data-ttu-id="4b6d8-282">キャリア コーチをピン留めすると、学生がアプリにアクセスしやすく表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-282">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="4b6d8-283">管理者センターに **サインインTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-283">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="4b6d8-284">[アプリ **Teams** &gt; **ポリシー] を** &gt; *選択します*。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-284">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

2. <span data-ttu-id="4b6d8-285">[固定 **されたアプリ] で**、[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-285">Under **Pinned apps**, choose **Add apps**.</span></span>

1. <span data-ttu-id="4b6d8-286">[キャリア コーチ] **を検索し**、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-286">Search for **Career Coach**, and then select **Add**.</span></span>

1. <span data-ttu-id="4b6d8-287">アプリが表示される順序を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-287">Choose the order for the app to appear and select **Save**.</span></span>

   <span data-ttu-id="4b6d8-288">学生には、キャリア コーチが固定Microsoft Teams通知されます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-288">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>  

## <a name="resources"></a><span data-ttu-id="4b6d8-289">リソース</span><span class="sxs-lookup"><span data-stu-id="4b6d8-289">Resources</span></span>

<span data-ttu-id="4b6d8-290">次のリソースは、キャリア コーチ アプリの計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b6d8-290">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="4b6d8-291">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="4b6d8-291">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="4b6d8-292">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="4b6d8-292">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="4b6d8-293">Microsoft Teams でのチームとチャネルの概要</span><span class="sxs-lookup"><span data-stu-id="4b6d8-293">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="4b6d8-294">管理センターでアプリMicrosoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-294">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="4b6d8-295">セキュリティ、プライバシー、コンプライアンスに関するMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b6d8-295">Security, privacy, and compliance in Microsoft Teams</span></span>](security-compliance-overview.md)

- [<span data-ttu-id="4b6d8-296">オンライン仮想向きキット</span><span class="sxs-lookup"><span data-stu-id="4b6d8-296">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="4b6d8-297">チャネルの制限とTeams仕様</span><span class="sxs-lookup"><span data-stu-id="4b6d8-297">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="4b6d8-298">Microsoft Teams のデータの場所</span><span class="sxs-lookup"><span data-stu-id="4b6d8-298">Location of data in Microsoft Teams</span></span>](location-of-data-in-teams.md)

- [<span data-ttu-id="4b6d8-299">管理者向けトレーニングの開始Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b6d8-299">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="4b6d8-300">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4b6d8-300">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="4b6d8-301">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="4b6d8-301">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
