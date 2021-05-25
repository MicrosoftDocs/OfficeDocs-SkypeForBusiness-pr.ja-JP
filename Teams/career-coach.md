---
title: キャリア コーチを購入、構成、有効化Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: キャリア コーチを購入、構成、有効化する方法についてMicrosoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d2a5bc0f459bb9e7dac8878a5ad75911ba4b1b82
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628906"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a><span data-ttu-id="dedaa-103">キャリア コーチを購入、構成、有効化Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dedaa-103">Purchase, configure, and enable Career Coach for Microsoft Teams</span></span>

<span data-ttu-id="dedaa-104">キャリア コーチは、Microsoft Teamsをナビゲートするパーソナライズされたガイダンスを提供する LinkedIn を搭載した教育アプリの一部です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-104">Career Coach is a Microsoft Teams for Education app powered by LinkedIn that provides personalized guidance for higher education students to navigate their career journey.</span></span> <span data-ttu-id="dedaa-105">キャリア コーチは、学生がキャリア パスを発見し、現実世界のスキルを高め、ネットワークを 1 か所で構築するための統一されたキャリア ソリューションを教育機関に提供します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-105">Career Coach offers educational institutions a unified career solution for students to discover their career path, grow real-world skills, and build their network all in one place.</span></span>

<span data-ttu-id="dedaa-106">キャリア コーチの [詳細については、 を参照してください](https://aka.ms/career-coach)。</span><span class="sxs-lookup"><span data-stu-id="dedaa-106">Learn more about [Career Coach](https://aka.ms/career-coach).</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-107">このガイドのベスト プラクティスと役立つヒントを使用して、学生、教職員向けキャリア コーチの機能を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-107">Use the best practices and helpful tips in this guide to enable the capabilities of Career Coach for students, faculty, and staff.</span></span> <span data-ttu-id="dedaa-108">クイック プランニング [ガイドに関する記事を参照](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) してください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-108">See the [Quick planning guide](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) article.</span></span>

## <a name="review-the-requirements"></a><span data-ttu-id="dedaa-109">要件を確認する</span><span class="sxs-lookup"><span data-stu-id="dedaa-109">Review the requirements</span></span>

<span data-ttu-id="dedaa-110">教育機関でキャリア コーチを有効にするには、アプリを起動して実行するために必要なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-110">To enable Career Coach for your educational institution, review what you need to get the app up and running.</span></span>

<span data-ttu-id="dedaa-111">**技術要件**</span><span class="sxs-lookup"><span data-stu-id="dedaa-111">**Technical requirements**</span></span>

  - <span data-ttu-id="dedaa-112">Office 365を持つテナントAzure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dedaa-112">Office 365 tenant with Azure Active Directory</span></span>

  - <span data-ttu-id="dedaa-113">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dedaa-113">Microsoft Teams</span></span>

  - <span data-ttu-id="dedaa-114">Azure Active Directory の LinkedIn アカウント接続</span><span class="sxs-lookup"><span data-stu-id="dedaa-114">LinkedIn account connections in Azure Active Directory</span></span>

<span data-ttu-id="dedaa-115">**ライセンス**</span><span class="sxs-lookup"><span data-stu-id="dedaa-115">**Licenses**</span></span>

  - <span data-ttu-id="dedaa-116">Faculty</span><span class="sxs-lookup"><span data-stu-id="dedaa-116">Faculty</span></span> 

  - <span data-ttu-id="dedaa-117">学生</span><span class="sxs-lookup"><span data-stu-id="dedaa-117">Students</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-118">構成を完了するには、IT 管理者にキャリア コーチ教員ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-118">A Career Coach Faculty license must be assigned to the IT admin completing the configuration.</span></span>

<span data-ttu-id="dedaa-119">**教育機関からのデータとファイル**</span><span class="sxs-lookup"><span data-stu-id="dedaa-119">**Data and files from your educational institution**</span></span>

  - <span data-ttu-id="dedaa-120">コース カタログ データ</span><span class="sxs-lookup"><span data-stu-id="dedaa-120">Course catalog data</span></span>

  - <span data-ttu-id="dedaa-121">提供される研究分野</span><span class="sxs-lookup"><span data-stu-id="dedaa-121">Fields of study offered</span></span>

  - <span data-ttu-id="dedaa-122">教育機関の LinkedIn ページ</span><span class="sxs-lookup"><span data-stu-id="dedaa-122">Educational institution’s LinkedIn page</span></span>

  - <span data-ttu-id="dedaa-123">LinkedIn Learning Campus サブスクリプション (推奨)</span><span class="sxs-lookup"><span data-stu-id="dedaa-123">LinkedIn Learning campus subscription (preferred)</span></span>

## <a name="purchase-the-career-coach-licenses"></a><span data-ttu-id="dedaa-124">キャリア コーチ のライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="dedaa-124">Purchase the Career Coach licenses</span></span>

<span data-ttu-id="dedaa-125">キャリア コーチは、教育機関向けソリューション (EES)、クラウド サービス プロバイダー (CSP)、および Microsoft 365 管理センター (Web ダイレクト) を通じて、資格のある教育機関向け (中国とロシアを除く) で世界中で利用できます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-125">Career Coach is available worldwide (except China and Russia) for qualified higher education institutions through Enrollment for Education Solutions (EES), Cloud Service Providers (CSP), and Microsoft 365 admin center (web direct).</span></span> <span data-ttu-id="dedaa-126">アプリのMicrosoft Teams、顧客は A3/A5 または Microsoft 365/A3/A5 をOffice 365 A1必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-126">As a Microsoft Teams app, customers must have Microsoft 365 A3/A5 or Office 365 A1/A3/A5.</span></span>

### <a name="assign-app-licenses-to-users"></a><span data-ttu-id="dedaa-127">ユーザーにアプリ ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dedaa-127">Assign app licenses to users</span></span>

<span data-ttu-id="dedaa-128">詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="dedaa-128">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="turn-on-linkedin-account-connections"></a><span data-ttu-id="dedaa-129">LinkedIn アカウント接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="dedaa-129">Turn on LinkedIn account connections</span></span>

<span data-ttu-id="dedaa-130">キャリア コーチ **は**、教育機関のユーザーが、キャリア コーチ内で容易に使用できる LinkedIn アカウントに Microsoft 365 アカウントを接続する機能を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-130">Career Coach **requires** your educational institution’s users to have the ability to connect their Microsoft 365 account to their LinkedIn account that is facilitated within Career Coach</span></span>

1. <span data-ttu-id="dedaa-131">Azure AD [組織](https://aad.portal.azure.com/) のグローバル管理者であるアカウントを使用して、Azure ADします。</span><span class="sxs-lookup"><span data-stu-id="dedaa-131">Sign in to the [Azure AD admin center](https://aad.portal.azure.com/) with an account that's a global admin for the Azure AD organization.</span></span>

2. <span data-ttu-id="dedaa-132">[ユーザー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-132">Select **Users**.</span></span>

3. <span data-ttu-id="dedaa-133">[ユーザー] **ページで** 、[ユーザー設定] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-133">On the **Users** page, select **User settings**.</span></span>

4. <span data-ttu-id="dedaa-134">**[LinkedIn アカウント接続] で**、ユーザーが自分のアカウントを接続して、一部の Microsoft アプリ内の LinkedIn 接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-134">Under **LinkedIn account connections**, allow users to connect their accounts to access their LinkedIn connections within some Microsoft apps.</span></span> <span data-ttu-id="dedaa-135">ユーザーが自分のアカウントへの接続に同意するまで、データは共有しません。</span><span class="sxs-lookup"><span data-stu-id="dedaa-135">No data is shared until users consent to connect their accounts.</span></span>

   - <span data-ttu-id="dedaa-136">[ **はい]** を選択して、教育機関のすべてのユーザーに対してサービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="dedaa-136">Select **Yes** to enable the service for all users in your educational institution</span></span>

   - <span data-ttu-id="dedaa-137">[ **選択したグループ]** を選択して、教育機関で選択したユーザーのグループに対してのみサービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="dedaa-137">Select **Selected group** to enable the service for only a group of selected users in your educational institution</span></span>

   - <span data-ttu-id="dedaa-138">教育機関 **のすべてのユーザー** からの同意を取り消す場合は、[いいえ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-138">Select **No** to withdraw consent from all users in your educational institution</span></span>

<span data-ttu-id="dedaa-139">LinkedIn アカウント接続[を統合する方法について説明Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span><span class="sxs-lookup"><span data-stu-id="dedaa-139">Learn how to [Integrate LinkedIn account connections in Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)</span></span>

## <a name="configure-career-coach-in-the-teams-admin-center"></a><span data-ttu-id="dedaa-140">管理センターでキャリア コーチTeams構成する</span><span class="sxs-lookup"><span data-stu-id="dedaa-140">Configure Career Coach in the Teams admin center</span></span>

<span data-ttu-id="dedaa-141">Microsoft Teams 管理センターの管理者設定を使用して、教育機関用に Career Coach を構成し、ユーザーに対して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-141">Using the admin settings in the Microsoft Teams admin center, you can configure Career Coach for your educational institution and enable it for users.</span></span>

## <a name="access-the-career-coach-app-settings"></a><span data-ttu-id="dedaa-142">キャリア コーチ アプリの設定にアクセスする</span><span class="sxs-lookup"><span data-stu-id="dedaa-142">Access the Career Coach app settings</span></span>

<span data-ttu-id="dedaa-143">[アプリ[の管理] ページを](/microsoftteams/manage-apps)使用してTeamsのアプリ カタログ内のアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-143">Use the [Manage apps page](/microsoftteams/manage-apps) to view the Teams apps in your educational institution’s app catalog.</span></span>

1. <span data-ttu-id="dedaa-144">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-144">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="dedaa-145">左側のナビゲーションで、[アプリの管理] **Teams を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-145">In the left navigation, select **Teams apps** > **Manage apps**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="dedaa-146">ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-146">You must be a global admin or Teams service admin to access the page.</span></span>

3. <span data-ttu-id="dedaa-147">キャリア コーチ を検索 **または参照します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-147">Search or browse for **Career Coach**.</span></span>  

4. <span data-ttu-id="dedaa-148">[**キャリア コーチ] を** 選択し、[キャリア コーチ]**設定。**</span><span class="sxs-lookup"><span data-stu-id="dedaa-148">Select **Career Coach**, and then select **Settings.**</span></span>  

    ![は、[キャリア コーチ] アプリが選択され、設定表示されます。](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a><span data-ttu-id="dedaa-150">キャリア コーチ アプリの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="dedaa-150">Configure the Career Coach app settings</span></span>

<span data-ttu-id="dedaa-151">キャリア コーチには、次の 5 つの構成カテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-151">Career Coach has five configuration categories:</span></span>

- [<span data-ttu-id="dedaa-152">ブランドと基本設定</span><span class="sxs-lookup"><span data-stu-id="dedaa-152">Brand and preferences</span></span>](#brand-and-preferences)

- [<span data-ttu-id="dedaa-153">LinkedIn の構成</span><span class="sxs-lookup"><span data-stu-id="dedaa-153">LinkedIn configuration</span></span>](#linkedin-configuration)

- [<span data-ttu-id="dedaa-154">コース カタログ</span><span class="sxs-lookup"><span data-stu-id="dedaa-154">Course catalog</span></span>](#course-catalog)

- [<span data-ttu-id="dedaa-155">研究分野</span><span class="sxs-lookup"><span data-stu-id="dedaa-155">Fields of study</span></span>](#fields-of-study)

- [<span data-ttu-id="dedaa-156">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="dedaa-156">Customization</span></span>](#customization)

> [!NOTE]
> <span data-ttu-id="dedaa-157">学生、教職員向けアプリを効果的に有効にするには、ブランドと基本設定、LinkedIn 構成、コース カタログ、および研究分野が必要です。 </span><span class="sxs-lookup"><span data-stu-id="dedaa-157">Brand and preferences, LinkedIn configuration, Course catalog, and Fields of study are **required** to effectively enable the app for students, faculty, and staff.</span></span>

#### <a name="brand-and-preferences"></a><span data-ttu-id="dedaa-158">ブランドと基本設定</span><span class="sxs-lookup"><span data-stu-id="dedaa-158">Brand and preferences</span></span>

<span data-ttu-id="dedaa-159">ブランドと環境設定の設定ページで、教育機関の名前、ロゴ、既定の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-159">Set your educational institution’s name, logo, and default language on the brand and preferences settings page.</span></span>

![管理センターの [キャリア コーチ] ブランドセクション](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a><span data-ttu-id="dedaa-161">教育機関のアイコン</span><span class="sxs-lookup"><span data-stu-id="dedaa-161">Educational institution icon</span></span>

<span data-ttu-id="dedaa-162">教育機関アイコンは、教育機関に固有のコンテンツ、アプリ全体のコース カタログ リソース、ダッシュボードの実際のエクスペリエンス セクションを識別するために、キャリア コーチ全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-162">The educational institution icon is used throughout Career Coach to identify content unique to your educational institution, course catalog resources throughout the app, and on the real-world experiences section of the dashboard.</span></span> <span data-ttu-id="dedaa-163">アイコンの形式は次の形式が最適です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-163">The icon is best formatted as:</span></span>

 - <span data-ttu-id="dedaa-164">透過的な PNG</span><span class="sxs-lookup"><span data-stu-id="dedaa-164">A transparent PNG</span></span>
 - <span data-ttu-id="dedaa-165">縦横比 1:1</span><span class="sxs-lookup"><span data-stu-id="dedaa-165">Aspect ratio of 1:1</span></span>
 - <span data-ttu-id="dedaa-166">最大サイズは 64 ピクセル x 64 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="dedaa-166">Maximum size of 64 px x 64 px.</span></span>

##### <a name="educational-institution-thumbnail"></a><span data-ttu-id="dedaa-167">教育機関のサムネイル</span><span class="sxs-lookup"><span data-stu-id="dedaa-167">Educational institution thumbnail</span></span>

<span data-ttu-id="dedaa-168">教育機関アイコンは、特定の画像がコースで利用できない場合に、アプリ全体のコース カタログ リソースに使用されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-168">The educational institution icon will be used for course catalog resources throughout the app when a specific image isn't available for a course.</span></span> <span data-ttu-id="dedaa-169">アイコンの形式は次の形式が最適です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-169">The icon is best formatted as:</span></span>

- <span data-ttu-id="dedaa-170">A PNG</span><span class="sxs-lookup"><span data-stu-id="dedaa-170">A PNG</span></span>
- <span data-ttu-id="dedaa-171">縦横比 16:9</span><span class="sxs-lookup"><span data-stu-id="dedaa-171">Aspect ratio of 16:9</span></span>
- <span data-ttu-id="dedaa-172">最大サイズは 360 ピクセル x 200 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="dedaa-172">Maximum size of 360 px x 200 px.</span></span>

#### <a name="linkedin-configuration"></a><span data-ttu-id="dedaa-173">LinkedIn の構成</span><span class="sxs-lookup"><span data-stu-id="dedaa-173">LinkedIn configuration</span></span>

<span data-ttu-id="dedaa-174">LinkedIn 構成は、キャリア コーチと LinkedIn の一般の同窓生データを接続します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-174">The LinkedIn configuration connects Career Coach with public alumni data from LinkedIn.</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-175">LinkedIn ページ接続が確認されていないと、キャリア コーチを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dedaa-175">Career Coach can't be enabled without the LinkedIn page connection verified.</span></span>

##### <a name="add-and-confirm-the-linkedin-page"></a><span data-ttu-id="dedaa-176">LinkedIn ページを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="dedaa-176">Add and confirm the LinkedIn page</span></span>

<span data-ttu-id="dedaa-177">教育機関の LinkedIn ページを決定します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-177">Determine the educational institution's LinkedIn page.</span></span> <span data-ttu-id="dedaa-178">LinkedIn で検索するか、キャリア サービスのスタッフ メンバーと接続して、使用する正しいページを決定することで、LinkedIn ページを探します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-178">Find the LinkedIn page by searching on LinkedIn or connecting with a career services staff member to determine the correct page to use.</span></span>  
  
1. <span data-ttu-id="dedaa-179">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-179">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="dedaa-180">[アプリ **Teamsアプリの**  >  **管理**  >  **][キャリア コーチ**  >  **LinkedIn 接続] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-180">Select **Teams apps** > **Manage apps** > **Career Coach** > **LinkedIn connection**.</span></span>

2. <span data-ttu-id="dedaa-181">教育機関の LinkedIn ページ URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-181">Enter your educational institution's LinkedIn page URL.</span></span>  

3. <span data-ttu-id="dedaa-182">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-182">Select **Apply**.</span></span>

4. <span data-ttu-id="dedaa-183">確認 URL をコピーし、教育機関の LinkedIn ページ管理者 [LinkedIn ページ管理者ドキュメント と共有します](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)。</span><span class="sxs-lookup"><span data-stu-id="dedaa-183">Copy the verification URL and share it with your educational institution’s LinkedIn page admin [LinkedIn page admin documentation](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en).</span></span> <span data-ttu-id="dedaa-184">確認リンクは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-184">The verification link expires after 30 days.</span></span>  

   ![キャリア コーチの linkedin 設定](media/linkedin.png)  

#### <a name="course-catalog"></a><span data-ttu-id="dedaa-186">コース カタログ</span><span class="sxs-lookup"><span data-stu-id="dedaa-186">Course catalog</span></span>

<span data-ttu-id="dedaa-187">コース カタログは、教育機関が学生に提供するコースとクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-187">The course catalog represents the courses and classes offered to students by your educational institution.</span></span> <span data-ttu-id="dedaa-188">これらのコースは、アプリ内で次の 2 つの領域で使用されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-188">These courses are used within the app in two areas:</span></span>

- <span data-ttu-id="dedaa-189">コースは学習リソースの一部として返されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-189">Courses are returned as part of learning resources.</span></span>  

- <span data-ttu-id="dedaa-190">コースとコースのメタデータ (説明など) は、学生がトランスクリプトをアップロードするときにスキルを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-190">Courses and course meta data, like descriptions, are used to help students identify their skills when they upload a transcript.</span></span>  

<span data-ttu-id="dedaa-191">コース カタログを作成するには、教育機関で教えられたすべてのコースの一覧をまとめ、CSV ファイルとしてアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dedaa-191">To create the course catalog, put together a list of all courses taught at your educational institution and upload it as a CSV file.</span></span> <span data-ttu-id="dedaa-192">アプリは、トランスクリプトから学生のスキルを識別し、受講するコースを提案するために、コース カタログから描画します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-192">The app draws from the course catalog to identify a student’s skills from their transcript and to suggest courses to take.</span></span> 

> [!NOTE]
> <span data-ttu-id="dedaa-193">学生[情報の保護については、「Teams](location-of-data-in-teams.md)[のデータ](security-compliance-overview.md)の場所」と「セキュリティとコンプライアンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-193">See [Location of data in Teams](location-of-data-in-teams.md) and [Security and compliance](security-compliance-overview.md) for information about protecting of student information.</span></span> 

##### <a name="course-catalog-documents-formatting-and-schema"></a><span data-ttu-id="dedaa-194">コース カタログ ドキュメントの書式設定とスキーマ</span><span class="sxs-lookup"><span data-stu-id="dedaa-194">Course catalog documents formatting and schema</span></span>

<span data-ttu-id="dedaa-195">ドキュメントは、最大サイズが 18 MB の CSV 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-195">The document needs to be in CSV format with a maximum size of 18 MB.</span></span> <span data-ttu-id="dedaa-196">ドキュメントには、必須フィールドのコース **タイトル**、 **コース ID、** およびコース URL が **含まれている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-196">The document must contain the required fields **course title**, **course ID**, and **course URL**.</span></span> <span data-ttu-id="dedaa-197">推奨されるフィールドを含め、より良い検索結果とスキルの識別を返して、学生のエクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-197">Including the recommended fields improves the experience for students by returning better search results and skill identification.</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-198">開始するには、 [サンプル コース カタログ]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) ドキュメントから開始します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-198">Start with the [sample course catalog]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) document to get started.</span></span>

<span data-ttu-id="dedaa-199">次の表は、コース カタログに含める項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="dedaa-199">The following table shows the items to include in the course catalog:</span></span>


| <span data-ttu-id="dedaa-200">名前</span><span class="sxs-lookup"><span data-stu-id="dedaa-200">Name</span></span>             | <span data-ttu-id="dedaa-201">状態</span><span class="sxs-lookup"><span data-stu-id="dedaa-201">Status</span></span>      | <span data-ttu-id="dedaa-202">型</span><span class="sxs-lookup"><span data-stu-id="dedaa-202">Type</span></span>   | <span data-ttu-id="dedaa-203">説明</span><span class="sxs-lookup"><span data-stu-id="dedaa-203">Description</span></span>                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| <span data-ttu-id="dedaa-204">courseId</span><span class="sxs-lookup"><span data-stu-id="dedaa-204">courseId</span></span>         | <span data-ttu-id="dedaa-205">必須</span><span class="sxs-lookup"><span data-stu-id="dedaa-205">Required</span></span>    | <span data-ttu-id="dedaa-206">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-206">string</span></span> | <span data-ttu-id="dedaa-207">通常、コース ID (通常はトランスクリプトで生成された値にマップされます)。</span><span class="sxs-lookup"><span data-stu-id="dedaa-207">Usually the course id (Typically maps to what is generated in the transcript).</span></span> |
| <span data-ttu-id="dedaa-208">title</span><span class="sxs-lookup"><span data-stu-id="dedaa-208">title</span></span>            | <span data-ttu-id="dedaa-209">必須</span><span class="sxs-lookup"><span data-stu-id="dedaa-209">Required</span></span>    | <span data-ttu-id="dedaa-210">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-210">string</span></span> | <span data-ttu-id="dedaa-211">通常、コースのタイトル。</span><span class="sxs-lookup"><span data-stu-id="dedaa-211">Usually the course title.</span></span>                                                      |
| <span data-ttu-id="dedaa-212">sourceLink</span><span class="sxs-lookup"><span data-stu-id="dedaa-212">sourceLink</span></span>       | <span data-ttu-id="dedaa-213">必須</span><span class="sxs-lookup"><span data-stu-id="dedaa-213">Required</span></span>    | <span data-ttu-id="dedaa-214">URL</span><span class="sxs-lookup"><span data-stu-id="dedaa-214">URL</span></span>    | <span data-ttu-id="dedaa-215">コース ページへの Web サイト のリンク。</span><span class="sxs-lookup"><span data-stu-id="dedaa-215">Website link to the course page.</span></span>                                               |
| <span data-ttu-id="dedaa-216">description</span><span class="sxs-lookup"><span data-stu-id="dedaa-216">description</span></span>      | <span data-ttu-id="dedaa-217">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-217">Recommended</span></span> | <span data-ttu-id="dedaa-218">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-218">string</span></span> | <span data-ttu-id="dedaa-219">コースの概要テキスト。</span><span class="sxs-lookup"><span data-stu-id="dedaa-219">Introduction text for the course.</span></span>                                              |
| <span data-ttu-id="dedaa-220">language</span><span class="sxs-lookup"><span data-stu-id="dedaa-220">language</span></span>         | <span data-ttu-id="dedaa-221">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-221">Recommended</span></span> | <span data-ttu-id="dedaa-222">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-222">string</span></span> | <span data-ttu-id="dedaa-223">コースの言語。</span><span class="sxs-lookup"><span data-stu-id="dedaa-223">Language of the course.</span></span> <span data-ttu-id="dedaa-224">標準言語コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-224">Use standard language codes.</span></span>                           |
| <span data-ttu-id="dedaa-225">format</span><span class="sxs-lookup"><span data-stu-id="dedaa-225">format</span></span>           | <span data-ttu-id="dedaa-226">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-226">Recommended</span></span> | <span data-ttu-id="dedaa-227">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-227">string</span></span> | <span data-ttu-id="dedaa-228">学習モード (オンライン、ビデオ、対人など)。</span><span class="sxs-lookup"><span data-stu-id="dedaa-228">Mode of teaching, e.g., online, video, in-person.</span></span>                              |
| <span data-ttu-id="dedaa-229">thumbnailLink</span><span class="sxs-lookup"><span data-stu-id="dedaa-229">thumbnailLink</span></span>    | <span data-ttu-id="dedaa-230">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-230">Recommended</span></span> | <span data-ttu-id="dedaa-231">URL</span><span class="sxs-lookup"><span data-stu-id="dedaa-231">URL</span></span>    | <span data-ttu-id="dedaa-232">コースの画像へのサムネイル リンク。</span><span class="sxs-lookup"><span data-stu-id="dedaa-232">Thumbnail link to the course image.</span></span>                                            |
| <span data-ttu-id="dedaa-233">thumbnailAltText</span><span class="sxs-lookup"><span data-stu-id="dedaa-233">thumbnailAltText</span></span> | <span data-ttu-id="dedaa-234">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-234">Recommended</span></span> | <span data-ttu-id="dedaa-235">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-235">string</span></span> | <span data-ttu-id="dedaa-236">画像のアクセシビリティ代替テキスト</span><span class="sxs-lookup"><span data-stu-id="dedaa-236">Accessibility alt text for the image</span></span>                                           |
| <span data-ttu-id="dedaa-237">educationLevel</span><span class="sxs-lookup"><span data-stu-id="dedaa-237">educationLevel</span></span>   | <span data-ttu-id="dedaa-238">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-238">Recommended</span></span> | <span data-ttu-id="dedaa-239">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-239">string</span></span> | <span data-ttu-id="dedaa-240">研究レベル (例: )</span><span class="sxs-lookup"><span data-stu-id="dedaa-240">Study level, ex.</span></span> <span data-ttu-id="dedaa-241">学士/卒業者。</span><span class="sxs-lookup"><span data-stu-id="dedaa-241">Undergraduate/Graduate.</span></span>                                       |
| <span data-ttu-id="dedaa-242">topics</span><span class="sxs-lookup"><span data-stu-id="dedaa-242">topics</span></span>           | <span data-ttu-id="dedaa-243">推奨</span><span class="sxs-lookup"><span data-stu-id="dedaa-243">Recommended</span></span> | <span data-ttu-id="dedaa-244">string</span><span class="sxs-lookup"><span data-stu-id="dedaa-244">string</span></span> | <span data-ttu-id="dedaa-245">コースが教えるスキルに関連付けられているトピックまたはタグ。</span><span class="sxs-lookup"><span data-stu-id="dedaa-245">Topics or tags that are associated with the skills the courses teach.</span></span>          |

##### <a name="add-the-course-catalog"></a><span data-ttu-id="dedaa-246">コース カタログを追加する</span><span class="sxs-lookup"><span data-stu-id="dedaa-246">Add the course catalog</span></span>

1. <span data-ttu-id="dedaa-247">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-247">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="dedaa-248">[アプリ **Teamsアプリ** &gt; **の管理] を選択し** &gt; **、Career Coach** &gt; **設定** カタログ &gt; **を選択します**。  </span><span class="sxs-lookup"><span data-stu-id="dedaa-248">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Course catalog**.</span></span>

2. <span data-ttu-id="dedaa-249">アップロード CSV 形式のコースを作成します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-249">Upload courses in CSV format.</span></span>

4. <span data-ttu-id="dedaa-250">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-250">Select **Apply**.</span></span>

   ![キャリア コーチ アプリのコース カタログ セクション](media/course-catalog.png)

#### <a name="fields-of-study"></a><span data-ttu-id="dedaa-252">研究分野</span><span class="sxs-lookup"><span data-stu-id="dedaa-252">Fields of study</span></span>

<span data-ttu-id="dedaa-253">研究分野は、関心のある主な分野、学歴、および程度と同義です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-253">The fields of study are synonymous with major areas of interest, academic major, and degree.</span></span> <span data-ttu-id="dedaa-254">これらのタイトルは、学生がアプリの使用を開始し、パーソナライズされたプロファイルの設定を開始するときに参照されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-254">These titles are referenced by students when they start using the app and begin setting up their personalized profile.</span></span>

<span data-ttu-id="dedaa-255">エンジニアリング、英語、ビジネスなど、学生が利用できるすべての研究分野を追加します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-255">Add all fields of study available to students such as Engineering, English, Business, and so on.</span></span> <span data-ttu-id="dedaa-256">フィールドの一覧を使用すると、学生は興味のある研究分野を発見し、自分のプロファイルにフォーカス領域を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-256">The list of fields lets students discover fields of study that may interest them and add their area of focus to their profile.</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-257">最初に、 [サンプルの研究分野のドキュメントを参照](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) してください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-257">Start with the [sample field of study](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document.</span></span>
##### <a name="add-the-fields-of-study"></a><span data-ttu-id="dedaa-258">研究分野を追加する</span><span class="sxs-lookup"><span data-stu-id="dedaa-258">Add the fields of study</span></span>

1. <span data-ttu-id="dedaa-259">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-259">Sign in to the **Teams admin center**.</span></span>
1. <span data-ttu-id="dedaa-260">[アプリ **Teamsアプリ** &gt; **の管理** &gt; **] [キャリア コーチ] 設定** &gt;  &gt; **フィールド] を選択します**。  </span><span class="sxs-lookup"><span data-stu-id="dedaa-260">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** &gt; **Settings** &gt;  **Fields of study**.</span></span>

2. <span data-ttu-id="dedaa-261">アップロード CSV 形式の研究分野を作成します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-261">Upload field of study in CSV format.</span></span>

3. <span data-ttu-id="dedaa-262">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-262">Select **Apply**.</span></span>

#### <a name="customization"></a><span data-ttu-id="dedaa-263">カスタマイズ</span><span class="sxs-lookup"><span data-stu-id="dedaa-263">Customization</span></span>

<span data-ttu-id="dedaa-264">キャリア コーチは、教育機関に固有のカスタマイズが可能です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-264">Career Coach can be customized to be unique to your educational institution.</span></span> <span data-ttu-id="dedaa-265">カスタマイズでは、ダッシュボードへのエクスペリエンスの追加がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-265">The customization supports adding experiences to the dashboard.</span></span> <span data-ttu-id="dedaa-266">ジョブ ボード、イベント、キャリア サービス オフィス、キャリア関連イベント、学生クラブ、学生が実際のエクスペリエンスを得るために役立つその他のリソースへのリンクを追加する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dedaa-266">It's recommended to add links to job boards, events, career services office, career-related events, student clubs, and any other resources that help students gain real-world experience.</span></span>

##### <a name="add-customized-experiences"></a><span data-ttu-id="dedaa-267">カスタマイズされたエクスペリエンスを追加する</span><span class="sxs-lookup"><span data-stu-id="dedaa-267">Add customized experiences</span></span>

1. <span data-ttu-id="dedaa-268">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-268">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="dedaa-269">[アプリ **Teamsアプリ** &gt; **の管理]を選択し**、[ &gt; **キャリア**  >  **コーチ] 設定** &gt; **カスタマイズします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-269">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach** > **Settings** &gt; **Customization**.</span></span>

2. <span data-ttu-id="dedaa-270">各 URL、タイトル、および簡単な説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-270">Add each URL, a title, and short description.</span></span>  
  
3. <span data-ttu-id="dedaa-271">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-271">Select **Apply**.</span></span>

## <a name="making-career-coach-available-to-your-organization"></a><span data-ttu-id="dedaa-272">組織でキャリア コーチを利用できる</span><span class="sxs-lookup"><span data-stu-id="dedaa-272">Making Career Coach available to your organization</span></span>

<span data-ttu-id="dedaa-273">これで、組織に対してキャリア コーチが構成されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-273">Now that Career Coach has been configured for your organization.</span></span> <span data-ttu-id="dedaa-274">次の手順に従って、キャリア コーチが組織内の組織で使用Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="dedaa-274">Follow these steps to ensure that Career Coach is available to organization in Microsoft Teams.</span></span>

### <a name="enable-the-app"></a><span data-ttu-id="dedaa-275">アプリを有効にする</span><span class="sxs-lookup"><span data-stu-id="dedaa-275">Enable the app</span></span>

<span data-ttu-id="dedaa-276">構成が完了したら、学生とライセンスを取得したユーザーがキャリア コーチにアクセスできるアプリを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-276">After you complete the configuration, enable the app for students and licensed users so they'll have access to Career Coach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dedaa-277">グローバルロールまたは管理者ロールTeams必要があります。</span><span class="sxs-lookup"><span data-stu-id="dedaa-277">You must have Global or Teams admin role permissions.</span></span>

1. <span data-ttu-id="dedaa-278">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-278">Sign in to the **Teams admin center**.</span></span>

1. <span data-ttu-id="dedaa-279">[アプリ **Teamsアプリ** &gt; **の管理]** &gt; **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="dedaa-279">Select **Teams apps** &gt; **Manage apps** &gt; **Career Coach**.</span></span>

2. <span data-ttu-id="dedaa-280">[状態] トグルを [許可] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-280">Move the Status toggle to **Allowed**.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="dedaa-281">許可とは、教育機関のユーザーがアプリを利用できるという意味です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-281">Allowed means that the app is available for users in your educational institution.</span></span> <span data-ttu-id="dedaa-282">ブロックとは、アプリを学生が利用できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="dedaa-282">Blocked means that the app isn't available to students.</span></span>

### <a name="add-career-coach-as-an-installed-app"></a><span data-ttu-id="dedaa-283">インストールされているアプリとしてキャリア コーチを追加する</span><span class="sxs-lookup"><span data-stu-id="dedaa-283">Add Career Coach as an installed app</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-284">この手順により、1) 学生がキャリア コーチを見つける 1) 自分の組織に対してキャリア コーチが適切に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-284">This step ensures 1) that Career Coach is properly configured for your organization 2) that students find Career Coach.</span></span>

1. <span data-ttu-id="dedaa-285">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-285">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="dedaa-286">[アプリ **Teams** &gt; **ポリシーの設定]** &gt; *を選択します*。</span><span class="sxs-lookup"><span data-stu-id="dedaa-286">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="dedaa-287">[インストール済みアプリ] で、[アプリの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-287">Under Installed apps, select Add apps.</span></span>

4. <span data-ttu-id="dedaa-288">[インストール済みアプリの追加] ウィンドウで、ユーザーがアプリを起動するときに自動的にインストールするアプリTeams。</span><span class="sxs-lookup"><span data-stu-id="dedaa-288">In the Add installed apps pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="dedaa-289">アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-289">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="dedaa-290">アプリの一覧を選択したら、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dedaa-290">When you've chosen your list of apps, select Add.</span></span>

### <a name="pin-the-app"></a><span data-ttu-id="dedaa-291">アプリをピン留めする</span><span class="sxs-lookup"><span data-stu-id="dedaa-291">Pin the app</span></span>

<span data-ttu-id="dedaa-292">キャリア コーチをピン留めすると、アプリのアクセスがしやすく、学生に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-292">Pinning Career Coach will make the app more accessible and visible for students.</span></span>

1. <span data-ttu-id="dedaa-293">管理センター **にTeamsします**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-293">Sign in to the **Teams admin center**.</span></span>

2. <span data-ttu-id="dedaa-294">[アプリ **Teams** &gt; **ポリシーの設定]** &gt; *を選択します*。</span><span class="sxs-lookup"><span data-stu-id="dedaa-294">Select **Teams apps** &gt;**Setup policies** &gt; *Your policy*.</span></span> 

3. <span data-ttu-id="dedaa-295">[ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-295">Under **Pinned apps**, choose **Add apps**.</span></span>

4. <span data-ttu-id="dedaa-296">[キャリア コーチ **] を検索** し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-296">Search for **Career Coach**, and then select **Add**.</span></span>

5. <span data-ttu-id="dedaa-297">アプリを表示する順序を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dedaa-297">Choose the order for the app to appear and select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="dedaa-298">キャリア コーチがピン留めMicrosoft Teams学生に通知されます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-298">Students will be notified in Microsoft Teams that Career Coach has been pinned.</span></span>

<span data-ttu-id="dedaa-299">詳細については [、「Microsoft でアプリセットアップ ポリシーを管理](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dedaa-299">Reference [Manage app setup policies in Microsoft](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) for additional details.</span></span>

## <a name="resources"></a><span data-ttu-id="dedaa-300">リソース</span><span class="sxs-lookup"><span data-stu-id="dedaa-300">Resources</span></span>

<span data-ttu-id="dedaa-301">次のリソースは、キャリア コーチ アプリの計画に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dedaa-301">The following resources will help you plan your Career Coach app.</span></span>

- [<span data-ttu-id="dedaa-302">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="dedaa-302">Welcome to Microsoft Teams</span></span>](Teams-overview.md)

- [<span data-ttu-id="dedaa-303">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="dedaa-303">How to roll out Teams</span></span>](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [<span data-ttu-id="dedaa-304">Microsoft Teams でのチームとチャネルの概要</span><span class="sxs-lookup"><span data-stu-id="dedaa-304">Overview of teams and channels in Microsoft Teams</span></span>](teams-channels-overview.md)

- [<span data-ttu-id="dedaa-305">管理センターでのMicrosoft Teamsの管理</span><span class="sxs-lookup"><span data-stu-id="dedaa-305">Managing apps in Microsoft Teams Admin Center</span></span>](manage-apps.md)

- [<span data-ttu-id="dedaa-306">セキュリティ、プライバシー、コンプライアンスに関するMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="dedaa-306">Security, privacy, and compliance in Microsoft Teams</span></span>](security-compliance-overview.md)

- [<span data-ttu-id="dedaa-307">オンライン仮想向きキット</span><span class="sxs-lookup"><span data-stu-id="dedaa-307">Online Virtual Orientation Kit</span></span>](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [<span data-ttu-id="dedaa-308">チャネルの制限Teams仕様</span><span class="sxs-lookup"><span data-stu-id="dedaa-308">Limits and specification of Teams channels</span></span>](limits-specifications-teams.md)

- [<span data-ttu-id="dedaa-309">Microsoft Teams のデータの場所</span><span class="sxs-lookup"><span data-stu-id="dedaa-309">Location of data in Microsoft Teams</span></span>](location-of-data-in-teams.md)

- [<span data-ttu-id="dedaa-310">管理者向けトレーニングのMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="dedaa-310">Getting started with admin training for Microsoft Teams</span></span>](ITAdmin-readiness.md)

- [<span data-ttu-id="dedaa-311">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dedaa-311">Teams troubleshooting</span></span>](/microsoftteams/troubleshoot/teams-welcome)

- [<span data-ttu-id="dedaa-312">Microsoft Teams のアプリのアクセス許可ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="dedaa-312">Manage app permission policies in Microsoft Teams</span></span>](teams-app-permission-policies.md)
