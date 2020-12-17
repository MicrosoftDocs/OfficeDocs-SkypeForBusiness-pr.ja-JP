---
title: Teams ラーニング アプリのインストール、管理、アクセス許可の割り当て (プライベート プレビュー)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Microsoft Teams ラーニング アプリを使用して、従業員が組織全体のコンテンツ ライブラリを共有、割り当て、学習できる学習のための中心的なハブを作成します。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703458"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="4d95b-103">Teams ラーニング アプリのインストール、管理、アクセス許可の割り当て (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4d95b-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="4d95b-104">*この記事には、プライベート プレビューの Teams ラーニング アプリの暫定コンテンツが含まれている。*</span><span class="sxs-lookup"><span data-stu-id="4d95b-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="4d95b-105">Microsoft Teams ラーニング アプリ (プライベート プレビュー) を使用すると、組織内のチームや個人が 1 日の自然な部分で学習することができます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="4d95b-106">このアプリは、Teams の中央ハブを作成し、従業員が組織全体のコンテンツ ライブラリを共有、割り当て、学習できる場所です。</span><span class="sxs-lookup"><span data-stu-id="4d95b-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="4d95b-107">管理者は、アプリのアクセス許可を設定し、学習コンテンツ ソースを許可します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="4d95b-108">学習コンテンツには、LinkedIn ラーニング、Microsoft Learn、Microsoft 365 のトレーニング、SharePoint Online に保存されている組織独自のコンテンツ、アプリでサポートされているサードパーティ プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="4d95b-109">Teams ラーニング アプリ (プライベート プレビュー) をセットアップするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="4d95b-110">Teams 管理センターの管理</span><span class="sxs-lookup"><span data-stu-id="4d95b-110">Teams admin center admin</span></span>
-   <span data-ttu-id="4d95b-111">Microsoft 365 管理センターの管理 (グローバル管理者)</span><span class="sxs-lookup"><span data-stu-id="4d95b-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="4d95b-112">グローバル管理者 (IT 管理者または Microsoft 365 管理者とも呼ばれる) が組織内のすべてのユーザーに割り当て可能な、ナレッジ管理者 (Microsoft 365 管理センターの新しい役割)。</span><span class="sxs-lookup"><span data-stu-id="4d95b-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="4d95b-113">この役割は、Microsoft 365 管理センターを通じて組織の学習コンテンツ ソースを管理します)。</span><span class="sxs-lookup"><span data-stu-id="4d95b-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="4d95b-114">Teams 管理センターで Teams ラーニング アプリ (プライベート プレビュー) を管理する</span><span class="sxs-lookup"><span data-stu-id="4d95b-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="4d95b-115">Teams 管理者は、Teams ラーニング アプリ (プライベート プレビュー) をアプリ ストアからインストールし、Teams 管理センターからアプリのセットアップ、管理、アクセス許可のポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="4d95b-116">Teams ラーニング アプリを管理する (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4d95b-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="4d95b-117">アプリの設定を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="4d95b-118">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams アプリと [アプリの管理] セクションが表示されている Teams 管理センターの左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="4d95b-120">[アプリ **の管理] ページ** の検索ボックスに、Teams ラーニング アプリ (プライベート プレビュー) を検索する学習を入力します。 </span><span class="sxs-lookup"><span data-stu-id="4d95b-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![検索ボックスが表示されている Teams 管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="4d95b-122">[学習] **ページで、次の方法を実行** します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="4d95b-123">[ **状態]** で[ **許可] を選** び、アプリを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="4d95b-124">[設定 **] タブ** の [ **アプリの設定** ] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![[状態] セクションと [アプリの設定] セクションが表示されている Teams 管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="4d95b-126">アプリ **の設定を管理** した後、[アクセス許可とセットアップ ポリシー] に移動して、組織がプライベート プレビューに参加する一部としてアプリにアクセスできる必要がある従業員にアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="4d95b-127">組織が Teams TAP100 プログラムの一部としてリング 4.0 を使用している場合は、次の操作を行って、リング 3.0 の承認済みユーザーが Teams ラーニング アプリ (プライベート プレビュー) にアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="4d95b-128">プライベート プレビューの一環として、Teams ラーニング アプリ (プライベート プレビュー) はリング 3.0 でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="4d95b-129">組織がリング 4.0 の場合、アプリはアプリ ストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="4d95b-130">アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、それを[すべてのアプリを許可する] に設定して、承認されたユーザーをリング 3.0 に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4d95b-132">Microsoft 365 管理センターで学習コンテンツ ソースを構成する</span><span class="sxs-lookup"><span data-stu-id="4d95b-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="4d95b-133">Microsoft 365 管理センターの管理者は、自分自身または組織内の選択した個人にナレッジ管理者の役割を割り当て、Teams ラーニング アプリ (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="4d95b-134">知識管理者は、中程度の技術的な知識を持ち、既存の SharePoint 管理者資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員の経験に精通しているユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d95b-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="4d95b-135">管理者は、アプリで利用できる学習コンテンツ ソース (LinkedIn ラーニングや SharePoint など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="4d95b-136">次に、管理者は、コンテンツが検索と検出に使用できる情報であり、アプリを使用する従業員が参照できるよう、これらのソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="4d95b-137">サポート技術情報管理者の役割を割り当てる [オプション]</span><span class="sxs-lookup"><span data-stu-id="4d95b-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="4d95b-138">これらの手順は、Microsoft 365 管理センターの管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="4d95b-139">Microsoft 365 管理センターの左側のナビゲーションで、[ロール] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="4d95b-140">[ロール **] ページの** **[Azure** AD] タブで、[サポート技術情報の **管理者] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="4d95b-141">[サポート **技術情報の管理**] ページの [割り当てられた管理者] セクションで、[追加] を選択し、役割に選択したユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="4d95b-142">アプリの学習コンテンツ ソースの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="4d95b-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="4d95b-143">これらの手順は、Microsoft 365 管理者またはサポート技術情報の管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="4d95b-144">Microsoft 365 管理センターの左側のナビゲーションで、[組織の設定 **] 設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="4d95b-145">[設定 **] ページ** の [サービスとアドイン **] &** 学習アプリを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="4d95b-147">[学習 **アプリ] パネル** で、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![コンテンツ ソースのオプションを表示する Microsoft 365 管理センターの [学習アプリ] パネル](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="4d95b-149">存在するすべての学習ソースの中には、既定で有効になっているものがあります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="4d95b-150">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-150">These include:</span></span>

- <span data-ttu-id="4d95b-151">LinkedIn ラーニング (無料コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="4d95b-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="4d95b-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="4d95b-152">Microsoft Learn</span></span>
- <span data-ttu-id="4d95b-153">Microsoft 365 トレーニング</span><span class="sxs-lookup"><span data-stu-id="4d95b-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="4d95b-154">組織に LinkedIn ラーニング標準または Pro サブスクリプションがある場合、組織内の従業員のコンテンツ リポジトリのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="4d95b-155">アクセス許可を持つ従業員だけがコンテンツ リポジトリ全体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="4d95b-156">その他のソースは、手動で有効または構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="4d95b-157">Microsoft から提供されていない学習資料のライセンスは、お客様の組織と第三者の間で別途ライセンスされます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="4d95b-158">ユーザーの学習にサインアップしたユーザーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="4d95b-159">学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4d95b-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="4d95b-160">ソースが有効な場合は、チェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="4d95b-161">学習コンテンツ ソースとして SharePoint を構成する</span><span class="sxs-lookup"><span data-stu-id="4d95b-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="4d95b-162">Microsoft 365 管理センターで、Teams ラーニング アプリ (プライベート プレビュー) の学習コンテンツ ソースとして SharePoint を構成します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="4d95b-163">概要</span><span class="sxs-lookup"><span data-stu-id="4d95b-163">Overview</span></span>

<span data-ttu-id="4d95b-164">ナレッジ管理者は、ラーニング サービスが構造化された SharePoint リストの形式で空の一元管理された学習コンテンツ リポジトリを作成できるサイト URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="4d95b-165">このリストは、組織が学習コンテンツを含む会社間の SharePoint フォルダーへのリンクを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="4d95b-166">管理者は、フォルダーの URL リストを収集し、管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="4d95b-167">これらのフォルダーには、Teams ラーニング アプリ (プライベート プレビュー) で利用できるコンテンツのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="4d95b-168">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="4d95b-168">Permissions</span></span>

<span data-ttu-id="4d95b-169">フォルダー URL は、組織内のすべての SharePoint サイトから収集できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="4d95b-170">これらのフォルダー内のコンテンツは検索できますが、使用できるのは、個々の従業員がアクセス許可を持っているコンテンツのみです。</span><span class="sxs-lookup"><span data-stu-id="4d95b-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="4d95b-171">ラーニング サービス</span><span class="sxs-lookup"><span data-stu-id="4d95b-171">Learning Service</span></span>

<span data-ttu-id="4d95b-172">ラーニング サービスは、提供されたフォルダー URL を使用して、これらのフォルダーに保存されているすべてのコンテンツからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="4d95b-173">一元管理されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員はアプリ内で会社のコンテンツを検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="4d95b-174">リポジトリからのコンテンツの削除は、現時点ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4d95b-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="4d95b-175">意図せず表示されたコンテンツは、Microsoft 365 管理センターで新しい SharePoint サイトの URL を指定することでのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="4d95b-176">SharePoint をソースとして構成する</span><span class="sxs-lookup"><span data-stu-id="4d95b-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="4d95b-177">これらの手順は、Microsoft 365 管理者またはサポート技術情報の管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d95b-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="4d95b-178">Microsoft 365 管理センターの左側のナビゲーションで、[設定] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="4d95b-179">[設定 **] ページ** の [サービスとアドイン **] &** 学習アプリを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="4d95b-181">[学習 **アプリ] パネル** で、アプリで一元管理されたリポジトリを作成する SharePoint サイトのサイト URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![SharePoint が選択されている Microsoft 365 管理センターの [学習アプリ] パネル](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="4d95b-183">SharePoint リストは、指定された組織の SharePoint サイト内に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="4d95b-184">SharePoint サイトの左側のナビゲーションで、[学習アプリ コンテンツ リポジトリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4d95b-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![[学習アプリ コンテンツ リポジトリ] セクションが表示されている SharePoint の左のナビゲーション](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="4d95b-186">[ラーニング **アプリ コンテンツ リポジトリ] ページ** で、SharePoint リストに学習コンテンツ フォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="4d95b-187">[新規 **] を** 選び、[新しい **アイテム] パネルを表示** します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-187">Select **New** to view the **New item** panel.</span></span> 

   ![[新規] オプションが表示された SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="4d95b-189">[新 **しいアイテム]** パネルの [ **タイトル** ] フィールドで、選択したディレクトリ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="4d95b-190">[フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="4d95b-191">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d95b-191">Select **Save**.</span></span>

   ![SharePoint の [タイトル] フィールドと [フォルダーの URL] フィールドを示す新しいアイテム パネル](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="4d95b-193">[学習アプリ コンテンツ リポジトリ] ページが更新され、新しい学習コンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d95b-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![更新された情報を表示する SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-populated.png)


 


