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
description: Microsoft Teams ラーニング アプリを使用して、従業員が組織全体でコンテンツ ライブラリを共有、割り当て、学習できる学習のための中心的なハブを作成します。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285621"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="b6fd0-103">Teams ラーニング アプリのインストール、管理、アクセス許可の割り当て (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b6fd0-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="b6fd0-104">*この記事には、プライベート プレビューの Teams ラーニング アプリの暫定コンテンツが含まれている。*</span><span class="sxs-lookup"><span data-stu-id="b6fd0-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="b6fd0-105">Microsoft Teams ラーニング アプリ (プライベート プレビュー) を使用すると、組織内のチームや個人が 1 日の自然な部分で学習することができます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="b6fd0-106">このアプリは、Teams の中央ハブを作成し、従業員が組織全体のコンテンツ ライブラリを共有、割り当て、学習できる場所です。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="b6fd0-107">管理者は、アプリのアクセス許可を設定し、学習コンテンツ ソースを許可します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="b6fd0-108">学習コンテンツには、LinkedIn ラーニング、Microsoft Learn、Microsoft 365 のトレーニング、SharePoint Online に保存されている組織独自のコンテンツ、アプリでサポートされているサードパーティ プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="b6fd0-109">Teams ラーニング アプリ (プライベート プレビュー) をセットアップするには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="b6fd0-110">Teams 管理センターの管理</span><span class="sxs-lookup"><span data-stu-id="b6fd0-110">Teams admin center admin</span></span>
-   <span data-ttu-id="b6fd0-111">Microsoft 365 管理センターの管理 (グローバル管理者)</span><span class="sxs-lookup"><span data-stu-id="b6fd0-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="b6fd0-112">Teams 管理センターで Teams ラーニング アプリ (プライベート プレビュー) を管理する</span><span class="sxs-lookup"><span data-stu-id="b6fd0-112">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="b6fd0-113">Teams 管理者は、Teams ラーニング アプリ (プライベート プレビュー) をアプリ ストアからインストールし、Teams 管理センターからアプリのセットアップ、管理、アクセス許可のポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-113">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="b6fd0-114">Teams ラーニング アプリを管理する (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b6fd0-114">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="b6fd0-115">アプリの設定を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-115">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="b6fd0-116">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-116">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams アプリと [アプリの管理] セクションが表示された Teams 管理センターの左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="b6fd0-118">[アプリ **の管理] ページ** の検索ボックスに、Teams ラーニング アプリを検索する学習を入力します (プライベート プレビュー)。 </span><span class="sxs-lookup"><span data-stu-id="b6fd0-118">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![検索ボックスが表示されている Teams 管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="b6fd0-120">[学習] **ページで、次の方法を実行** します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-120">On the **Learning** page:</span></span>
   1. <span data-ttu-id="b6fd0-121">[ **状態]** で[ **許可] を選** び、アプリを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-121">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="b6fd0-122">[設定 **] タブ** の [ **アプリの設定** ] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-122">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![[状態] セクションと [アプリの設定] セクションが表示されている Teams 管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="b6fd0-124">アプリ **の設定を管理** した後、[アクセス許可とセットアップ ポリシー] に移動して、組織がプライベート プレビューに参加する一部としてアプリにアクセスする必要がある従業員にアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-124">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="b6fd0-125">組織が Teams TAP100 プログラムの一部としてリング 4.0 を使用している場合は、次の操作を行って、リング 3.0 の承認済みユーザーが Teams ラーニング アプリ (プライベート プレビュー) にアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-125">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="b6fd0-126">プライベート プレビューの一環として、Teams ラーニング アプリ (プライベート プレビュー) はリング 3.0 でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-126">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="b6fd0-127">組織がリング 4.0 の場合、アプリはアプリ ストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-127">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="b6fd0-128">アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、それを[すべてのアプリを許可する] に設定して、承認されたユーザーをリング 3.0 に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-128">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b6fd0-130">Microsoft 365 管理センターで学習コンテンツ ソースを構成する</span><span class="sxs-lookup"><span data-stu-id="b6fd0-130">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b6fd0-131">Microsoft 365 管理センターの管理者は、Teams ラーニング アプリ (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-131">The admins for the Microsoft 365 admin center can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="b6fd0-132">管理者は、アプリのユーザーが利用できる追加の学習コンテンツ ソース (SharePoint、サポートされているサードパーティ コンテンツ プロバイダー ソースなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-132">The admin can select which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of the app.</span></span> <span data-ttu-id="b6fd0-133">次に、管理者は、コンテンツが検索と検出が可能であり、アプリを使用する従業員が参照できるよう、これらのソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-133">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

> [!NOTE]
>  <span data-ttu-id="b6fd0-134">ユーザーは、ブラウザーまたは埋め込みビューアーで Microsoft および LinkedIn Learning Pro 以外の学習にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-134">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="b6fd0-135">この構成済みの学習は、ラーニング (プレビュー) 条項ではなく、組織と第三者の間の個別のライセンス、プライバシー、およびサービス条件の対象になります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-135">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Learning (Preview) terms.</span></span> <span data-ttu-id="b6fd0-136">学習 (プレビュー) でこの学習を選択する前に、組織とユーザーに対して契約が設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-136">Before selecting this learning in Learning (Preview), verify you have an agreement in place for your organization and users.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="b6fd0-137">アプリの学習コンテンツ ソースの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b6fd0-137">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="b6fd0-138">これらの手順は、Microsoft 365 管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-138">These steps are to be performed by the Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="b6fd0-139">Microsoft 365 管理センターの左側のナビゲーションで、[組織の設定 **] 設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-139">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="b6fd0-140">[設定 **] ページ** の [ **サービスとアドイン] &** で、[学習アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-140">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="b6fd0-142">[学習 **アプリ] パネル** で、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-142">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![コンテンツ ソースのオプションを表示する Microsoft 365 管理センターの [学習アプリ] パネル](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="b6fd0-144">存在するすべての学習ソースの中には、既定で有効になっているものがあります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-144">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="b6fd0-145">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-145">These include:</span></span>

- <span data-ttu-id="b6fd0-146">LinkedIn ラーニング (無料コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="b6fd0-146">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="b6fd0-147">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="b6fd0-147">Microsoft Learn</span></span>
- <span data-ttu-id="b6fd0-148">Microsoft 365 トレーニング</span><span class="sxs-lookup"><span data-stu-id="b6fd0-148">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="b6fd0-149">組織に LinkedIn ラーニング標準または Pro サブスクリプションがある場合、組織内の従業員のコンテンツ リポジトリのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-149">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="b6fd0-150">アクセス許可を持つ従業員だけがコンテンツ リポジトリ全体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-150">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="b6fd0-151">その他のソースは、手動で有効または構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-151">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="b6fd0-152">Microsoft から提供されていない学習資料のライセンスは、お客様の組織と第三者の間で別途ライセンスされます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-152">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="b6fd0-153">ユーザーの学習にサインアップしたユーザーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-153">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="b6fd0-154">学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-154">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="b6fd0-155">ソースが有効な場合は、チェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-155">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a><span data-ttu-id="b6fd0-156">学習コンテンツ ソースとして SharePoint を構成する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="b6fd0-156">Configure SharePoint as a learning content source (Coming Soon)</span></span>

<span data-ttu-id="b6fd0-157">Microsoft 365 管理センターで、Teams ラーニング アプリ (プライベート プレビュー) の学習コンテンツ ソースとして SharePoint を構成します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-157">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="b6fd0-158">概要</span><span class="sxs-lookup"><span data-stu-id="b6fd0-158">Overview</span></span>

<span data-ttu-id="b6fd0-159">管理者は、ラーニング サービスが構造化された SharePoint リストの形式で空の一元管理された学習コンテンツ リポジトリを作成できるサイト URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-159">The admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="b6fd0-160">このリストは、組織が学習コンテンツを含む会社間の SharePoint フォルダーへのリンクを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-160">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="b6fd0-161">管理者は、フォルダーの URL リストを収集し、管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-161">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="b6fd0-162">これらのフォルダーには、Teams ラーニング アプリ (プライベート プレビュー) で利用できるコンテンツのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-162">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="b6fd0-163">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b6fd0-163">Permissions</span></span>

<span data-ttu-id="b6fd0-164">フォルダー URL は、組織内のすべての SharePoint サイトから収集できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-164">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="b6fd0-165">これらのフォルダー内のコンテンツは検索できますが、アクセス許可を持つコンテンツのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-165">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="b6fd0-166">ラーニング サービス</span><span class="sxs-lookup"><span data-stu-id="b6fd0-166">Learning Service</span></span>

<span data-ttu-id="b6fd0-167">ラーニング サービスは、提供されたフォルダー URL を使用して、これらのフォルダーに保存されているすべてのコンテンツからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-167">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="b6fd0-168">一元管理されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員はアプリ内で会社のコンテンツを検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-168">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="b6fd0-169">リポジトリからのコンテンツの削除は、現時点ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-169">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="b6fd0-170">意図せず表示されたコンテンツは、Microsoft 365 管理センターで新しい SharePoint サイトの URL を指定することでのみ削除できます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-170">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="b6fd0-171">SharePoint をソースとして構成する</span><span class="sxs-lookup"><span data-stu-id="b6fd0-171">Configure SharePoint as a source</span></span>

<span data-ttu-id="b6fd0-172">これらの手順は、Microsoft 365 管理者が実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-172">These steps are to be performed by Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="b6fd0-173">Microsoft 365 管理センターの左側のナビゲーションで、[設定] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-173">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="b6fd0-174">[設定 **] ページ** の [ **サービスとアドイン] &** で、[学習アプリ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-174">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="b6fd0-176">[学習 **アプリ] パネル** で、アプリで一元管理されたリポジトリを作成する SharePoint サイトのサイト URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-176">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![SharePoint が選択されている Microsoft 365 管理センターの学習アプリ パネル](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="b6fd0-178">SharePoint リストは、指定された組織の SharePoint サイト内に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-178">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="b6fd0-179">SharePoint サイトの左側のナビゲーションで、[学習アプリ コンテンツ リポジトリ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-179">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![[学習アプリ コンテンツ リポジトリ] セクションが表示されている SharePoint の左のナビゲーション](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="b6fd0-181">[ラーニング アプリ **コンテンツ リポジトリ] ページ** で、SharePoint リストに学習コンテンツ フォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-181">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="b6fd0-182">[新規 **] を** 選び、[新しい **アイテム] パネルを表示** します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-182">Select **New** to view the **New item** panel.</span></span> 

   ![[新規] オプションが表示された SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="b6fd0-184">[新 **しいアイテム]** パネルの [ **タイトル** ] フィールドで、選択したディレクトリ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-184">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="b6fd0-185">[フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-185">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="b6fd0-186">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-186">Select **Save**.</span></span>

   ![SharePoint の [タイトル] フィールドと [フォルダーの URL] フィールドを示す新しいアイテム パネル](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="b6fd0-188">[学習アプリ コンテンツ リポジトリ] ページが更新され、新しい学習コンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6fd0-188">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![更新された情報を表示する SharePoint の [学習アプリ コンテンツ リポジトリ] ページ](media/learning-app-content-repository-populated.png)


 


