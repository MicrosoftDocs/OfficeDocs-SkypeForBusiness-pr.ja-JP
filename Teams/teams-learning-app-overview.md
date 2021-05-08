---
title: Microsoft 楽楽学習 (プライベート プレビュー) のインストール、管理、アクセス許可の割り当て
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
description: Microsoft Central Learning (プライベート プレビュー) を使用して、従業員が組織全体でコンテンツ ライブラリを共有、割り当て、学習できる学習の中心ハブを作成します。
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
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="1c8d9-103">Microsoft 楽楽学習 (プライベート プレビュー) のインストール、管理、アクセス許可の割り当て</span><span class="sxs-lookup"><span data-stu-id="1c8d9-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="1c8d9-104">*この記事には、プライベート プレビュー段階にある、Microsoft の事前コンテンツが含まれているとします。*</span><span class="sxs-lookup"><span data-stu-id="1c8d9-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="1c8d9-105">Microsoft Learning (プライベート プレビュー) は、組織内のチームや個人が一日の自然な部分で学習を行える機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="1c8d9-106">このアプリは、組織内のコンテンツ ライブラリTeams共有、割り当て、学習できる中央ハブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="1c8d9-107">管理者は、アクセス許可を設定し、Learning Learning (プライベート プレビュー) の学習コンテンツ ソースを許可します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="1c8d9-108">学習コンテンツには、LinkedIn Learning、Microsoft Learn、Microsoft 365 トレーニング、SharePoint オンラインに保存されている組織独自のコンテンツ、およびInved Learning (プライベート プレビュー) でサポートされているサードパーティ プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="1c8d9-109">管理者ロール</span><span class="sxs-lookup"><span data-stu-id="1c8d9-109">Admin roles</span></span>

<span data-ttu-id="1c8d9-110">(プライベート プレビュー) に対して、次のアクセス許可を設定するには、次のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="1c8d9-111">Microsoft Teams管理者</span><span class="sxs-lookup"><span data-stu-id="1c8d9-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="1c8d9-112">Microsoft 365管理者または管理者SharePointする</span><span class="sxs-lookup"><span data-stu-id="1c8d9-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="1c8d9-113">ナレッジ管理者 - 組織内のすべてのユーザーに割り当てMicrosoft 365管理センターでの新しいロールです。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="1c8d9-114">このロールは、管理センターで組織のラーニング コンテンツ ソースMicrosoft 365管理します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="1c8d9-115">ナレッジ管理者は、中程度の技術的な知識を持ち、既存の SharePoint 管理者の資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員の経験に精通しているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="1c8d9-116">Teams 管理センターで、このビデオを使って、Teams Learning を管理します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="1c8d9-117">管理者Teamsアプリ ストアから、Teams Learning (プライベート プレビュー) をインストールした後、Teams 管理センターを通じてセットアップ、管理、およびアクセス許可ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="1c8d9-118">(プライベート プレビュー) の[楽楽学習] の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="1c8d9-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="1c8d9-119">これらのタスクを実行するには、管理センター Teams管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="1c8d9-120">楽楽学習の設定を管理するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="1c8d9-121">管理センターの左側のナビゲーションでTeamsアプリの管理Teams **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![[アプリの管理] Teams管理] セクションが表示Teams左側のナビゲーション](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="1c8d9-123">[アプリ **の管理] ページ** の検索ボックスに、「learning」と入力して、Teams ラーニング アプリ (プライベート プレビュー) を検索します。 </span><span class="sxs-lookup"><span data-stu-id="1c8d9-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![検索ボックスが表示されている Teams管理センターの [アプリの管理] ページ](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="1c8d9-125">[学習] **ページで、次の方法を** 実行します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="1c8d9-126">[ **状態]** で、[ **許可] を選択** してアプリを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="1c8d9-127">**[設定]** タブの [アプリの設定] セクションで、Microsoft 365 管理センターに移動して、学習コンテンツ ソースを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![[状態] セクションと [Teams設定] セクションが表示されている管理センターの [学習] ページ](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="1c8d9-129">[**アプリ設定の** 管理]の後、[アクセス許可とセットアップ ポリシー] に移動して、組織のプライベート プレビューへの参加の一環としてアプリにアクセスする必要がある従業員にアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="1c8d9-130">組織が Teams TAP100 プログラムの一部としてリング 4.0 に参加している場合は、Ring 3.0 で承認されたユーザーが Ring Learning (プライベート プレビュー) にアクセスするには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="1c8d9-131">プライベート プレビューの一環として、Ring 3.0 では、Ring Learning (プライベート プレビュー) がリリースされます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="1c8d9-132">組織が Ring 4.0 の場合は、アプリ ストアにアプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="1c8d9-133">アプリをテストするには、カスタム アプリのアクセス許可ポリシーを作成し、[すべてのアプリを許可する] に設定して、それを Ring 3.0 承認済みユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![[すべてのアプリを許可する] が選択されている TAP-AppsPermission-Plcy ページ](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1c8d9-135">管理センターで学習コンテンツ ソースMicrosoft 365構成する</span><span class="sxs-lookup"><span data-stu-id="1c8d9-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1c8d9-136">Microsoft 365 管理センターの管理者は、自分自身で、または組織内の選択した個人にナレッジ管理者ロールを割り当てる方法で、Learning Learning (プライベート プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="1c8d9-137">管理者は、追加の学習コンテンツ ソース (SharePoint やサポートされているサード パーティのコンテンツ プロバイダー ソースなど) を選択し、その他のコンテンツ ソースを、このユーザーに対して使用できます(プライベート プレビュー)。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="1c8d9-138">管理者は、これらのソースを構成して、コンテンツが検索と検出に使用可能であり、また、このコンテンツを、このユーザーが参照できるよう構成します(プライベート プレビュー)。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="1c8d9-139">ユーザーは、Microsoft および LinkedIn Learning 以外のユーザーにサインインProまたは埋め込みビューアーで学習を行います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="1c8d9-140">この構成済みの学習には、組織とサード パーティの間で個別のライセンス、プライバシー、サービス条項が適用されます。また、このライセンス条項 (プライベート プレビュー) 条項は適用されません。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="1c8d9-141">この種類の学習を選択する前に、組織とユーザーに対して契約が締結されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="1c8d9-142">ナレッジ管理者ロールを割り当てる [省略可能]</span><span class="sxs-lookup"><span data-stu-id="1c8d9-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="1c8d9-143">これらのタスクを実行するにはMicrosoft 365管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="1c8d9-144">Learning Learning のナレッジ管理者を割り当てるには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="1c8d9-145">管理センターの左側のナビゲーションMicrosoft 365、[ロール] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="1c8d9-146">[ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="1c8d9-147">[ナレッジ管理者 **] ページ** の[割り当て管理者] セクションで、[追加] を選択し、ロールに選択したユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="1c8d9-148">Learning Learning のラーニング コンテンツ ソースの設定を構成する (プライベート プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1c8d9-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="1c8d9-149">これらのタスクを実行するにはMicrosoft 365管理者またはナレッジ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="1c8d9-150">Learning Content Sources の設定を構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="1c8d9-151">管理センターの左側のナビゲーションMicrosoft 365、[組織の設定]**設定**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="1c8d9-152">[組織の **設定] ページ** の [サービス **] タブで** 、[学習アプリ (プレビュー) ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![設定表示されている Microsoft 365 管理センターの [学習] ページ](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="1c8d9-154">[ **学習アプリ (プレビュー)** ] パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![コンテンツ ソースのオプションをMicrosoft 365管理センターの学習パネル](media/learning-sharepoint-configure2.png)

<span data-ttu-id="1c8d9-156">存在するすべてのラーニング ソースの中で、既定で有効になっているものがあります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="1c8d9-157">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-157">These include:</span></span>

- <span data-ttu-id="1c8d9-158">LinkedIn Learning (無料コンテンツ)</span><span class="sxs-lookup"><span data-stu-id="1c8d9-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="1c8d9-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="1c8d9-159">Microsoft Learn</span></span>
- <span data-ttu-id="1c8d9-160">Microsoft 365トレーニング</span><span class="sxs-lookup"><span data-stu-id="1c8d9-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="1c8d9-161">組織に LinkedIn Learning Standard または Pro サブスクリプションがある場合は、組織内の従業員のコンテンツ リポジトリのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="1c8d9-162">アクセス許可を持つ従業員だけが、コンテンツ リポジトリ全体を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="1c8d9-163">その他のソースは、手動で有効または構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="1c8d9-164">Microsoft から提供されていないラーニング ソースは、お客様の組織と第三者の間で個別にライセンスされます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="1c8d9-165">ユーザーとユーザーの学習にサインアップ済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="1c8d9-166">学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="1c8d9-167">ソースが有効になっている場合は、チェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="1c8d9-168">学習SharePointソースとしてコンテンツ を構成する</span><span class="sxs-lookup"><span data-stu-id="1c8d9-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="1c8d9-169">組織のコンテンツSharePoint、組織独自のコンテンツを、Learning Learning (プライベート プレビュー) で利用できるよう、学習コンテンツ ソースとして構成できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="1c8d9-170">概要</span><span class="sxs-lookup"><span data-stu-id="1c8d9-170">Overview</span></span>

<span data-ttu-id="1c8d9-171">ナレッジ管理者 (またはグローバル管理者) は、Learning Service が空の一元化された場所 (Learning App コンテンツ リポジトリ) を構造化された SharePoint リストの形式で作成できるサイト URL を提供します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="1c8d9-172">このリストは、組織が、学習コンテンツを含む複数のSharePointリンクを保存するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="1c8d9-173">管理者は、フォルダーの URL の一覧を収集およびキュレーションする責任を負います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="1c8d9-174">これらのフォルダーには、同じコンテンツのみを含める必要があります。このコンテンツは、このフォルダーを含む必要があります。このコンテンツは、このフォルダーを含む必要があります(プライベート プレビュー)。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="1c8d9-175">「Learning Learning (プライベート プレビュー)」では、次のドキュメントの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="1c8d9-176">Word、PowerPoint、Excel、PDF</span><span class="sxs-lookup"><span data-stu-id="1c8d9-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="1c8d9-177">オーディオ (.m4a)</span><span class="sxs-lookup"><span data-stu-id="1c8d9-177">Audio (.m4a)</span></span>
- <span data-ttu-id="1c8d9-178">ビデオ (.mov、.mp4、.avi)</span><span class="sxs-lookup"><span data-stu-id="1c8d9-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="1c8d9-179">詳細については、オンライン のドキュメント[SharePoint参照してください](https://docs.microsoft.com/sharepoint/introductionlink)。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="1c8d9-180">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1c8d9-180">Permissions</span></span>

<span data-ttu-id="1c8d9-181">ドキュメント ライブラリ のフォルダー URL は、組織内のSharePointサイトから収集できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="1c8d9-182">既存のすべてのコンテンツ のアクセス許可に従って、このビデオ (プライベート プレビュー) を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="1c8d9-183">そのため、ユーザーがアクセス許可を持っているコンテンツだけが、検索可能であり、また、このコンテンツは、このコンテンツを、プライベート プレビュー (プライベート プレビュー) で検索および表示できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="1c8d9-184">これらのフォルダー内のコンテンツは検索可能ですが、個々の従業員がアクセス許可を持っているコンテンツのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="1c8d9-185">組織のリポジトリからのコンテンツの削除は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="1c8d9-186">意図せず表示されたコンテンツを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="1c8d9-187">ドキュメント ライブラリのアクセスを制限するには、[アクションの表示] **オプション** を選択し、[アクセスの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![[アクセスの管理] SharePoint表示されているドキュメント ライブラリ ページ。](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="1c8d9-189">ドキュメント ライブラリ内の元のドキュメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="1c8d9-190">詳細については、「最新のエクスペリエンスでの共有とアクセス許可[SharePoint参照してください](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="1c8d9-191">Learning Service</span><span class="sxs-lookup"><span data-stu-id="1c8d9-191">Learning Service</span></span>

<span data-ttu-id="1c8d9-192">Learning Service は、指定されたフォルダー URL を使用して、これらのフォルダーに格納されているすべてのコンテンツからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="1c8d9-193">一元化されたリポジトリにフォルダー URL を指定して 24 時間以内に、従業員は、組織のコンテンツを検索して、その組織のコンテンツを、InSved Learning (プライベート プレビュー) 内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="1c8d9-194">更新されたメタデータやアクセス許可を含むコンテンツに対する変更はすべて、24 時間以内に Learning Service にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="1c8d9-195">ソースSharePoint構成する</span><span class="sxs-lookup"><span data-stu-id="1c8d9-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="1c8d9-196">これらのタスクを実行するには、Microsoft 365管理者、SharePoint、またはナレッジ管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="1c8d9-197">「SharePoint Learning (プライベート プレビュー)」で学習コンテンツ ソースとして構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="1c8d9-198">管理センターの左側のナビゲーションMicrosoft 365、[組織の設定]**設定**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="1c8d9-199">[組織の **設定] ページ** の [サービス **] タブで** 、[学習アプリ (プレビュー) ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![設定ページに[Microsoft 365 Learning] と表示されます。](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="1c8d9-201">[Learning **app (Preview)] パネル** の **[SharePoint]** で、一元化されたリポジトリを作成する SharePoint サイトへのサイト URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![[管理センター] の [Microsoft 365] パネルで、選択したSharePoint表示されます。](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="1c8d9-203">指定SharePointリストは、指定されたサイト内にSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![新しく作成SharePointサイト内のSharePoint一覧。](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="1c8d9-205">サイトの左側のナビゲーションで、[サイト コンテンツSharePoint アプリ **コンテンツ** リポジトリ]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePointコンテンツ ナビゲーションと [Learning App Content Repository] セクションを表示する一覧を表示します。](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="1c8d9-207">[Learning **App Content Repository]** ページで、SharePointコンテンツ フォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="1c8d9-208">[新規 **] を** 選択して[新しい **アイテム] パネルを** 表示します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-208">Select **New** to view the **New item** panel.</span></span> 

       ![[新規] オプションが表示SharePointコンテンツ リポジトリの学習ページ。](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="1c8d9-210">[新 **しいアイテム]** パネルの [タイトル] **フィールドに** 、選択したディレクトリ名を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="1c8d9-211">[フォルダー **URL] フィールド** で、学習コンテンツ フォルダーに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="1c8d9-212">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-212">Select **Save**.</span></span>

       ![[タイトル] フィールドと [SharePoint URL] フィールドが表示されている新しいアイテム パネル。](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="1c8d9-214">[ **学習アプリ コンテンツ リポジトリ] ページ** が、新しい学習コンテンツで更新されます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![[学習コンテンツ リポジトリ] ページSharePoint情報が表示されます。](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="1c8d9-216">Learning App Content Repository へのより広範なアクセスを可能にするために、リストへのリンクは、ユーザーがアクセスを要求し、最終的にリストを設定するのに役立つ、近い間に、一覧へのリンクを、同じ Learning (プライベート プレビュー) インターフェイスで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="1c8d9-217">サイト所有者とグローバル管理者は、リストへのアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="1c8d9-218">Access はリストにのみ固有であり、リストが保存されているサイトには適用されません。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="1c8d9-219">フォルダー URL ドキュメント ライブラリのキュレーション</span><span class="sxs-lookup"><span data-stu-id="1c8d9-219">Folder URL document library curation</span></span>

<span data-ttu-id="1c8d9-220">Microsoft Graph API によって、既定のメタデータ (変更日、作成者、ドキュメント名、コンテンツ タイプ、組織名など) が自動的に、このメタデータが、自動的に「Learning」(プライベート プレビュー) に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="1c8d9-221">コンテンツの全体的な検出と検索の関連性を向上させるために、[説明] 列を追加することをお **勧** めします。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="1c8d9-222">ドキュメント ライブラリ ページ **に [説明]** 列を追加するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="1c8d9-223">[ドキュメント] **ページで、[** 列の追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="1c8d9-224">[アクションの **表示] オプションを** 選択し、[1 行 **のテキスト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![[ドキュメント] ページSharePoint行が強調表示された [アクションの表示] オプションが表示されます。](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="1c8d9-226">[列 **の作成] パネル** の [名前] **フィールドに** 、列のわかりやすい名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="1c8d9-227">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-227">Select **Save**.</span></span>

     ![[名前] と他のフィールドSharePoint列パネルを作成します。](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="1c8d9-229">[ドキュメント **] ページ** の [説明] **列** で、各アイテムのカスタム説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="1c8d9-230">説明が指定されていない場合は、既定のメッセージが表示され、コンテンツが独自のライブラリからの内容として強調表示SharePointされます。</span><span class="sxs-lookup"><span data-stu-id="1c8d9-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![[説明] 列SharePoint説明が表示されているドキュメント ページ。](media/learning-sharepoint-curation3.png)
 
