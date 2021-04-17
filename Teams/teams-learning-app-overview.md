---
title: Microsoft Viva Learning のインストール、管理、アクセス許可の割り当て (プライベート プレビュー)
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
description: Microsoft Viva Learning (プライベート プレビュー) を使用して、従業員が組織全体でコンテンツ ライブラリを共有、割り当て、学習できる学習の中心的なハブを作成します。
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880381"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="1a22c-103">Microsoft Viva Learning のインストール、管理、アクセス許可の割り当て (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a22c-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="1a22c-104">*この記事には、プライベート プレビューの Microsoft Viva Learning の暫定コンテンツが含まれている。*</span><span class="sxs-lookup"><span data-stu-id="1a22c-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="1a22c-105">Microsoft Viva Learning (プライベート プレビュー) を使用すると、組織内のチームや個人が一日の中で自然に学習することができます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="1a22c-106">このアプリでは、Teams の中央ハブが作成され、従業員は組織全体のコンテンツ ライブラリを共有、割り当て、学習できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="1a22c-107">管理者は、権限を設定し、Viva Learning (プライベート プレビュー) の学習コンテンツ ソースを許可します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="1a22c-108">学習コンテンツには、LinkedIn ラーニング、Microsoft Learn、Microsoft 365 のトレーニング、SharePoint Online に保存されている組織独自のコンテンツ、およびVv viva Learning (プライベート プレビュー) でサポートされているサードパーティ プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="1a22c-109">管理者ロール</span><span class="sxs-lookup"><span data-stu-id="1a22c-109">Admin roles</span></span>

<span data-ttu-id="1a22c-110">Viva Learning (プライベート プレビュー) を設定するには、次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1a22c-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="1a22c-111">Microsoft Teams 管理者</span><span class="sxs-lookup"><span data-stu-id="1a22c-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="1a22c-112">Microsoft 365 グローバル管理者または SharePoint 管理者</span><span class="sxs-lookup"><span data-stu-id="1a22c-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="1a22c-113">ナレッジ管理者 : これは、組織内のすべてのユーザーに割り当て可能な、Microsoft 365 管理センターの新しい役割です。</span><span class="sxs-lookup"><span data-stu-id="1a22c-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="1a22c-114">この役割は、Microsoft 365 管理センターを通じて組織の学習コンテンツ ソースを管理します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="1a22c-115">知識管理者は、中程度の技術的な知識を持ち、既存の SharePoint 管理者の資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員の経験に精通しているユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a22c-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="1a22c-116">Teams 管理センターで Viva Learning (プライベート プレビュー) を管理する</span><span class="sxs-lookup"><span data-stu-id="1a22c-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="1a22c-117">Teams 管理者はアプリ ストアから Viva Learning (プライベート プレビュー) をインストールし、Teams 管理センターからセットアップ、管理、アクセス許可のポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="1a22c-118">Viva Learning の設定を管理する (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a22c-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="1a22c-119">これらのタスクを実行するには、Teams 管理センターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="1a22c-120">Viva Learning の設定を管理するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="1a22c-121">Teams 管理センターの左側のナビゲーションで、Teams アプリの **[アプリの管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Teams アプリと [アプリの管理] セクションが表示されている Teams 管理センターの左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="1a22c-123">[アプリ **の管理] ページ** の検索ボックスに、Teams ラーニング アプリを検索する学習を入力します (プライベート プレビュー)。 </span><span class="sxs-lookup"><span data-stu-id="1a22c-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![検索ボックスが表示されている Teams 管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="1a22c-125">[学習] **ページで、次の方法を実行** します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="1a22c-126">[ **状態]** で[ **許可] を選** び、アプリを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="1a22c-127">[設定 **] タブ** の [ **アプリの設定** ] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![[状態] セクションと [アプリの設定] セクションが表示されている Teams 管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="1a22c-129">アプリ **の設定を管理** した後、[アクセス許可とセットアップ ポリシー] に移動して、組織がプライベート プレビューに参加する一部としてアプリにアクセスできる必要がある従業員にアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="1a22c-130">組織が Teams TAP100 プログラムの一部としてリング 4.0 を使用している場合は、次の操作を行って、リング 3.0 の承認済みユーザーが Viva Learning (プライベート プレビュー) にアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="1a22c-131">プライベート プレビューの一環として、Viva Learning (プライベート プレビュー) はリング 3.0 でリリースされます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="1a22c-132">組織がリング 4.0 の場合、アプリはアプリ ストアに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="1a22c-133">アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、それを[すべてのアプリを許可する] に設定して、承認されたユーザーをリング 3.0 に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1a22c-135">Microsoft 365 管理センターで学習コンテンツ ソースを構成する</span><span class="sxs-lookup"><span data-stu-id="1a22c-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1a22c-136">Microsoft 365 管理センターの管理者は、自分自身で、または組織内の選択した個人に知識管理者の役割を割り当て、Viva Learning (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="1a22c-137">管理者は、その他の学習コンテンツ ソース (SharePoint、サポートされているサードパーティ コンテンツ プロバイダー ソースなど) を、Viva Learning (プライベート プレビュー) のユーザーが利用できるコンテンツ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="1a22c-138">次に、管理者は、コンテンツが検索と検出が可能であり、Viva Learning (プライベート プレビュー) を使用する従業員が参照できるよう、これらのソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="1a22c-139">ユーザーは、ブラウザーまたは埋め込みビューアーで Microsoft および LinkedIn Learning Pro 以外の学習にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1a22c-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="1a22c-140">この構成済みの学習には、組織と第三者の間の個別のライセンス、プライバシー、サービス条件が適用され、Viva Learning (プライベート プレビュー) の条項は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1a22c-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="1a22c-141">この種類の学習を選択する前に、組織とユーザーに対して契約があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="1a22c-142">知識管理者の役割を割り当てる [オプション]</span><span class="sxs-lookup"><span data-stu-id="1a22c-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="1a22c-143">これらのタスクを実行するには、Microsoft 365 グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="1a22c-144">Viva Learning の知識管理者を割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="1a22c-145">Microsoft 365 管理センターの左側のナビゲーションで、[ロール] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="1a22c-146">[ロール **] ページの** **[Azure** AD] タブで、[サポート技術情報の **管理者] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="1a22c-147">[サポート **技術情報の管理**] ページの [割り当てられた管理者] セクションで、[追加] を選択し、役割に選択したユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="1a22c-148">Viva Learning の学習コンテンツ ソースの設定を構成する (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a22c-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="1a22c-149">これらのタスクを実行するには、Microsoft 365 グローバル管理者または知識管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="1a22c-150">Viva Learning で学習コンテンツ ソースの設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="1a22c-151">Microsoft 365 管理センターの左側のナビゲーションで、[組織の設定 **] 設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="1a22c-152">[組織の **設定] ページ** の [サービス **]** タブで、学習アプリ **(プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![学習アプリが表示されている Microsoft 365 管理センターの [設定] ページ](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="1a22c-154">学習アプリ **(プレビュー)** パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![コンテンツ ソースのオプションを表示する Microsoft 365 管理センターの [学習] パネル](media/learning-sharepoint-configure2.png)

<span data-ttu-id="1a22c-156">存在するすべての学習ソースの中には、既定で有効になっているものがあります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="1a22c-157">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-157">These include:</span></span>

- <span data-ttu-id="1a22c-158">LinkedIn ラーニング (無料コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="1a22c-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="1a22c-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="1a22c-159">Microsoft Learn</span></span>
- <span data-ttu-id="1a22c-160">Microsoft 365 トレーニング</span><span class="sxs-lookup"><span data-stu-id="1a22c-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="1a22c-161">組織に LinkedIn ラーニング標準または Pro サブスクリプションがある場合、組織内の従業員のコンテンツ リポジトリのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="1a22c-162">アクセス許可を持つ従業員だけがコンテンツ リポジトリ全体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="1a22c-163">その他のソースは、手動で有効または構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="1a22c-164">Microsoft から提供されていない学習資料のライセンスは、お客様の組織と第三者の間で別途ライセンスされます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="1a22c-165">ユーザーの学習にサインアップしたユーザーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="1a22c-166">学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a22c-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="1a22c-167">ソースが有効な場合は、チェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="1a22c-168">学習コンテンツ ソースとして SharePoint を構成する</span><span class="sxs-lookup"><span data-stu-id="1a22c-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="1a22c-169">組織独自のコンテンツを Viva Learning (プライベート プレビュー) で利用できるよう、SharePoint を学習コンテンツ ソースとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="1a22c-170">概要</span><span class="sxs-lookup"><span data-stu-id="1a22c-170">Overview</span></span>

<span data-ttu-id="1a22c-171">ナレッジ管理者 (またはグローバル管理者) は、ラーニング サービスが構造化された SharePoint リストの形式で空の一元管理された場所 (ラーニング アプリ コンテンツ リポジトリ) を作成できるサイト URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="1a22c-172">このリストは、組織が学習コンテンツを含む会社間の SharePoint フォルダーへのリンクを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="1a22c-173">管理者は、フォルダーの URL リストを収集し、管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="1a22c-174">これらのフォルダーには、Viva Learning (プライベート プレビュー) で利用できるコンテンツのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="1a22c-175">Viva Learning (プライベート プレビュー) では、次のドキュメントの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1a22c-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="1a22c-176">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="1a22c-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="1a22c-177">オーディオ (.m4a)</span><span class="sxs-lookup"><span data-stu-id="1a22c-177">Audio (.m4a)</span></span>
- <span data-ttu-id="1a22c-178">ビデオ (.mov、.mp4、.avi)</span><span class="sxs-lookup"><span data-stu-id="1a22c-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="1a22c-179">詳細については [、SharePoint Online のドキュメントを参照してください](https://docs.microsoft.com/sharepoint/introductionlink)。</span><span class="sxs-lookup"><span data-stu-id="1a22c-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="1a22c-180">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1a22c-180">Permissions</span></span>

<span data-ttu-id="1a22c-181">ドキュメント ライブラリ フォルダーの URL は、組織内の任意の SharePoint サイトから収集できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="1a22c-182">Viva Learning (プライベート プレビュー) は、既存のすべてのコンテンツのアクセス許可に従います。</span><span class="sxs-lookup"><span data-stu-id="1a22c-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="1a22c-183">そのため、ユーザーがアクセス許可を持っているコンテンツだけが、Viva Learning (プライベート プレビュー) 内で検索および表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="1a22c-184">これらのフォルダー内のコンテンツは検索できますが、使用できるのは、個々の従業員がアクセス許可を持っているコンテンツのみです。</span><span class="sxs-lookup"><span data-stu-id="1a22c-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="1a22c-185">現在、組織のリポジトリからのコンテンツの削除はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1a22c-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="1a22c-186">意図せず表示されたコンテンツを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="1a22c-187">ドキュメント ライブラリへのアクセスを制限するには、[アクションの表示] **オプションを** 選択し、[アクセスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![SharePoint のドキュメント ライブラリ ページに、[アクセスの管理] が表示された [アクションの表示] オプションが表示されています。](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="1a22c-189">ドキュメント ライブラリ内の元のドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="1a22c-190">詳細については、「SharePoint モダン エクスペリエンスでの共有とアクセス許可」 [を参照してください](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="1a22c-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="1a22c-191">ラーニング サービス</span><span class="sxs-lookup"><span data-stu-id="1a22c-191">Learning Service</span></span>

<span data-ttu-id="1a22c-192">ラーニング サービスは、提供されたフォルダー URL を使用して、これらのフォルダーに保存されているすべてのコンテンツからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="1a22c-193">一元管理されたリポジトリにフォルダー URL を指定すると、従業員は 24 時間以内に、Viva Learning (プライベート プレビュー) 内で組織のコンテンツを検索して使用できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="1a22c-194">更新されたメタデータやアクセス許可を含む、コンテンツに対する変更はすべて、24 時間以内にラーニング サービスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="1a22c-195">SharePoint をソースとして構成する</span><span class="sxs-lookup"><span data-stu-id="1a22c-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="1a22c-196">これらのタスクを実行するには、Microsoft 365 グローバル管理者、SharePoint 管理者、または知識管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="1a22c-197">Viva Learning (プライベート プレビュー) の学習コンテンツ ソースとして SharePoint を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="1a22c-198">Microsoft 365 管理センターの左側のナビゲーションで、[組織の設定 **] 設定に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="1a22c-199">[組織の **設定] ページ** の [サービス **]** タブで、学習アプリ **(プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![一覧表示されたVv viva Learning を示す Microsoft 365 管理センターの [設定] ページ。](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="1a22c-201">ラーニング アプリ **(プレビュー)** パネルの **SharePoint** で、一元的なリポジトリを作成する SharePoint サイトのサイト URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![SharePoint が選択された状態の Microsoft 365 管理センターの [学習] パネル。](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="1a22c-203">SharePoint リストは、指定された SharePoint サイト内に自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![SharePoint サイト内に新しく作成された SharePoint リスト。](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="1a22c-205">SharePoint サイトの左側のナビゲーションで、[サイト **コンテンツ学習** アプリ コンテンツ リポジトリ  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![[サイト コンテンツ] ナビゲーションと [学習アプリ コンテンツ リポジトリ] セクションを示す SharePoint リスト。](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="1a22c-207">[ラーニング アプリ **コンテンツ リポジトリ] ページ** で、SharePoint リストに学習コンテンツ フォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="1a22c-208">[新規 **] を** 選び、[新しい **アイテム] パネルを表示** します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-208">Select **New** to view the **New item** panel.</span></span> 

       ![[新規] オプションが表示された SharePoint の [ラーニング コンテンツ リポジトリ] ページ。](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="1a22c-210">[新 **しいアイテム]** パネルの [ **タイトル** ] フィールドで、選択したディレクトリ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="1a22c-211">[フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="1a22c-212">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-212">Select **Save**.</span></span>

       ![SharePoint の [タイトル] フィールドと [フォルダー URL] フィールドを示す新しいアイテム パネル。](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="1a22c-214">[ **学習アプリ コンテンツ リポジトリ]** ページが更新され、新しい学習コンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![更新された情報を表示する SharePoint の [ラーニング コンテンツ リポジトリ] ページ。](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="1a22c-216">ラーニング アプリ コンテンツ リポジトリへのより広範なアクセスを可能にするために、リストへのリンクは、ユーザーがアクセスを要求し、最終的にリストを作成するのに役立つ、Viva Learning (プライベート プレビュー) インターフェイスで間もなく利用できます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="1a22c-217">サイト所有者とグローバル管理者は、リストへのアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a22c-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="1a22c-218">Access はリストにのみ固有であり、リストが保存されているサイトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="1a22c-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="1a22c-219">フォルダー URL ドキュメント ライブラリのキュレーション</span><span class="sxs-lookup"><span data-stu-id="1a22c-219">Folder URL document library curation</span></span>

<span data-ttu-id="1a22c-220">既定のメタデータ (変更日、作成者、ドキュメント名、コンテンツ タイプ、組織名など) は、Microsoft Graph API によって自動的に Viva Learning (プライベート プレビュー) に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="1a22c-221">コンテンツの全体的な検出と検索の関連性を向上させるために、[説明] 列を追加 **することをお勧** めします。</span><span class="sxs-lookup"><span data-stu-id="1a22c-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="1a22c-222">ドキュメント ライブラリ ページに **[説明]** 列を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="1a22c-223">[ドキュメント] **ページで、[** 列の追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="1a22c-224">[アクションの **表示] オプションを** 選択し、[1 行 **テキスト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1a22c-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![[1 行テキスト] が強調表示された [アクションの表示] オプションを示す SharePoint の [ドキュメント] ページ。](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="1a22c-226">[列 **の作成] パネル** の [名前] **フィールドで** 、列のわかりやすい名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="1a22c-227">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-227">Select **Save**.</span></span>

     ![SharePoint で列パネルを作成し、[名前] などのフィールドを表示します。](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="1a22c-229">[ドキュメント **] ページの** [説明] **列** で、アイテムごとにユーザー設定の説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="1a22c-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="1a22c-230">説明が提供されていない場合、Viva Learning (プライベート プレビュー) には、コンテンツを独自の SharePoint ライブラリからの内容として強調表示する既定のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a22c-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![SharePoint の [ドキュメント] ページには、[説明] 列の説明が表示されます。](media/learning-sharepoint-curation3.png)
 
