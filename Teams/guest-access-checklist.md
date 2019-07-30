---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams の設定が容易になります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09a6ec1f60ca4bfc39dbeb5ba1829330c3413560
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925359"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="db3e7-103">Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="db3e7-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="db3e7-104">このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="db3e7-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="db3e7-105">共同作業の制限については[、「B2B 外部コラボレーションを有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="db3e7-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="db3e7-106">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="db3e7-106">Understand the limitations for guests</span></span>

<span data-ttu-id="db3e7-p101">ゲスト エクスペリエンスでは、デザインによる制限があります。問題ではないものを修正しようとしないために、必ずゲスト エクスペリエンスを理解してください。たとえば、Microsoft Teams のゲストが利用できない一部の機能を以下にリストします。</span><span class="sxs-lookup"><span data-stu-id="db3e7-p101">The guest experience has limitations by design. Make sure you understand the guest experience so you don't try to fix something that isn't a problem. For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="db3e7-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="db3e7-110">OneDrive for Business</span></span>
- <span data-ttu-id="db3e7-111">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="db3e7-111">People search outside of Teams</span></span>
- <span data-ttu-id="db3e7-112">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="db3e7-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="db3e7-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="db3e7-113">PSTN</span></span>
- <span data-ttu-id="db3e7-114">組織図</span><span class="sxs-lookup"><span data-stu-id="db3e7-114">Organization chart</span></span>
- <span data-ttu-id="db3e7-115">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="db3e7-115">Create or revise a team</span></span>
- <span data-ttu-id="db3e7-116">チームの参照</span><span class="sxs-lookup"><span data-stu-id="db3e7-116">Browse for a team</span></span>
- <span data-ttu-id="db3e7-117">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="db3e7-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="db3e7-118">ユーザーの完全なメール ID がわかっている場合でも、ゲストはユーザーを検索して検索できます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="db3e7-119">このようなことを防ぐため、IT 管理者は、ゲストを仮想 GAL に制限する機能を持つ、スコープ指定された[ディレクトリ検索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)などのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="db3e7-120">詳細については、「 [Office 365 グループで](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)の[ゲストエクスペリエンスの概要](guest-experience.md)」と「ゲストアクセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="db3e7-121">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="db3e7-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="db3e7-122">現時点では、Microsoft Teams はゲスト残っの役割をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="db3e7-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="db3e7-123">少なくとも、Microsoft Teams でのゲストアクセスを有効にするには、[メンバーが招待できる] トグルを [はい] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db3e7-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="db3e7-124">"メンバーは招待できます" を "いいえ" に設定して、Office 365 グループおよび Microsoft Teams でゲストアクセスを有効にすると、管理者はディレクトリへのゲストの招待を制御できます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="db3e7-125">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="db3e7-126">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="db3e7-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="db3e7-127">Microsoft Teams のゲストアクセスでは、Azure Active Directory (Azure AD) Business to Business (B2B) とライセンスモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="db3e7-128">ライセンスエラーが表示される場合は、組織のユーザーが組織にゲストを招待できるように、組織のライセンス要件を理解するために、 [B2B ライセンスガイダンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)をお読みください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="db3e7-129">次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-129">A few things to remember:</span></span>

- <span data-ttu-id="db3e7-130">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="db3e7-130">Guests are users outside your organization.</span></span> <span data-ttu-id="db3e7-131">社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="db3e7-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="db3e7-132">これは、関連会社にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="db3e7-133">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="db3e7-134">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="db3e7-135">招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。</span><span class="sxs-lookup"><span data-stu-id="db3e7-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="db3e7-136">□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="db3e7-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="db3e7-137">テナント管理者として[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="db3e7-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="db3e7-138">**Azure Active Directory** > **ユーザー** > の**ユーザー設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="db3e7-139">[**外部ユーザー**] で、[**外部グループ作業設定の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="db3e7-140">**外部コラボレーションの設定**は、[**組織関係**] ページからも利用できます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="db3e7-141">Azure Active Directory で、[**管理**] の [**組織の関係** > の**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="db3e7-142">[**外部コラボレーションの設定**] ページで、有効にするポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="db3e7-143">**ゲストユーザーのアクセス許可は制限され**ます: このポリシーは、ディレクトリ内のゲストに対するアクセス許可を決定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="db3e7-144">ユーザー、グループ、またはその他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのゲストをブロックするには、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="db3e7-145">[**いいえ**] を選択して、ディレクトリの通常ユーザーと同じアクセス権をゲストに与えます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="db3e7-146">**ゲスト残っロールの管理者とユーザーは、招待でき**ます。 "ゲスト残っ" ロールの管理者とユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="db3e7-147">**招待できるメンバー**: ディレクトリの管理者以外のメンバーにゲストの招待を許可するには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="db3e7-148">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="db3e7-149">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="db3e7-150">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="db3e7-151">**招待できる**ゲスト: ゲストが他のゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="db3e7-152">**ゲストのメールの1回限りのパスコードを有効にする (プレビュー)**: 1 回限りのパスコード機能の詳細については、「[ワンタイムパスコードの認証 (プレビュー)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="db3e7-153">**共同作業の制限**: 特定のドメインへの招待の許可または禁止の詳細については、「[特定の組織からの B2B ユーザーへの招待を許可またはブロック](allow-deny-list.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="db3e7-154">□ 手順 2: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="db3e7-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="db3e7-155">Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="db3e7-156">[**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="db3e7-157">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="db3e7-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="db3e7-158">[**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="db3e7-159">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="db3e7-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="db3e7-160">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db3e7-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![Office 365 グループの切り替えを示すスクリーンショット](media/guest-access-checklist-office365.png)

<span data-ttu-id="db3e7-162">これらの設定を構成する詳細な手順については、「 [office 365 グループでゲストアクセスを管理](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)する」および「 [office 365 グループのゲストアクセスを制御](Teams-dependencies.md#control-guest-access-in-office-365-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="db3e7-163">□ 手順 3: テナント レベルでのゲスト アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="db3e7-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="db3e7-164">少なくとも、microsoft **teams 管理センター**で microsoft teams のゲストアクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db3e7-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="db3e7-165">Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="db3e7-166">**[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="db3e7-168">この同じページで、必要な他のゲストの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="db3e7-169">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3e7-169">Click **Save**.</span></span>

<span data-ttu-id="db3e7-170">詳細な手順については、「 [Microsoft Teams へのゲストアクセスを有効または](set-up-guests.md)無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="db3e7-171">□  手順 4: Office 365 での共有を構成する</span><span class="sxs-lookup"><span data-stu-id="db3e7-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="db3e7-172">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-172">Make sure that users can add guests.</span></span> <span data-ttu-id="db3e7-173">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-173">Here's how:</span></span>

1. <span data-ttu-id="db3e7-174">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="db3e7-176">**[共有]** で **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-176">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="db3e7-178">**[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db3e7-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="db3e7-180">この設定は、Azure AD の [**ユーザー設定**] > [**外部ユーザー**] の [**メンバーが招待可能**] 設定と同等です。</span><span class="sxs-lookup"><span data-stu-id="db3e7-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="db3e7-181">□ 手順 5: SharePoint での共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="db3e7-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="db3e7-182">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="db3e7-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="db3e7-183">[**管理センター**] をクリックして [**SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="db3e7-184">SharePoint 管理センターで、[**共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="db3e7-185">[**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーンショットに Sparepoint Online の設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="db3e7-187">□ 手順 6: チャネルの特定の設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="db3e7-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="db3e7-188">Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除することができるようにゲストのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="db3e7-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="db3e7-189">管理者に加えて、チーム所有者もこの設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="db3e7-189">In addition to admins,  team owners can configure this setting.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="db3e7-191">詳細については、使い方ビデオを含む「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="db3e7-192">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="db3e7-192">Troubleshooting</span></span>

<span data-ttu-id="db3e7-193">Microsoft Teams でのゲストの追加に問題がある場合は、「[ゲスト アクセスのトラブルシューティング ガイド](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db3e7-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


