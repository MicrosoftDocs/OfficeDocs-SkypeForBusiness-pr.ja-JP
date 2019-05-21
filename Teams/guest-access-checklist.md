---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: 833d79d16365a1b90e8cd35e88e43468f0e25fa8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280926"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="e2375-103">Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="e2375-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="e2375-104">このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e2375-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="e2375-105">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="e2375-105">Understand the limitations for guests</span></span>

<span data-ttu-id="e2375-p101">ゲスト エクスペリエンスでは、デザインによる制限があります。問題ではないものを修正しようとしないために、必ずゲスト エクスペリエンスを理解してください。たとえば、Microsoft Teams のゲストが利用できない一部の機能を以下にリストします。</span><span class="sxs-lookup"><span data-stu-id="e2375-p101">The guest experience has limitations by design. Make sure you understand the guest experience so you don't try to fix something that isn't a problem. For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="e2375-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e2375-109">OneDrive for Business</span></span>
- <span data-ttu-id="e2375-110">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="e2375-110">People search outside of Teams</span></span>
- <span data-ttu-id="e2375-111">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="e2375-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="e2375-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="e2375-112">PSTN</span></span>
- <span data-ttu-id="e2375-113">組織図</span><span class="sxs-lookup"><span data-stu-id="e2375-113">Organization chart</span></span>
- <span data-ttu-id="e2375-114">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="e2375-114">Create or revise a team</span></span>
- <span data-ttu-id="e2375-115">チームの参照</span><span class="sxs-lookup"><span data-stu-id="e2375-115">Browse for a team</span></span>
- <span data-ttu-id="e2375-116">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="e2375-116">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="e2375-117">ユーザーは、完全なメール ID がわかっている場合でも、チーム外のユーザーを検索して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e2375-117">Guests can still search and find users, outside their team, if they know their full email ID.</span></span> <span data-ttu-id="e2375-118">このようなことを防ぐため、IT 管理者は、ゲストを仮想 GAL に制限する機能を持つ、スコープ指定された[ディレクトリ検索](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search)などのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2375-118">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="e2375-119">詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md)」および「[Office 365 グループのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-119">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="e2375-120">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="e2375-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="e2375-121">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="e2375-121">If your guests are seeing license errors</span></span>

<span data-ttu-id="e2375-122">Microsoft Teams のゲスト アクセスではAzure Active Directory ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e2375-122">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="e2375-123">ライセンスのエラーが表示される場合は、B2B ライセンスのガイダンスを必ず読んで自分の組織でのライセンスの要件を理解して、自分たちのユーザーが自分の組織でゲストを招待することができる状態になるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e2375-123">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="e2375-124">次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-124">A few things to remember:</span></span>

- <span data-ttu-id="e2375-125">ユーザーに割り当てた有料の Azure AD ライセンスの場合、1 つのライセンスで 5 人までのゲスト ユーザーを外部ユーザー無料利用分として招待することができます。</span><span class="sxs-lookup"><span data-stu-id="e2375-125">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="e2375-126">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="e2375-126">Guests are users outside your organization.</span></span> <span data-ttu-id="e2375-127">社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="e2375-127">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="e2375-128">これは、関連会社にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="e2375-128">The same applies to your affiliates.</span></span>
- <span data-ttu-id="e2375-129">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e2375-129">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="e2375-130">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="e2375-130">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="e2375-131">招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。</span><span class="sxs-lookup"><span data-stu-id="e2375-131">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="e2375-132">□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e2375-132">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="e2375-133">サインインするにはhttps://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="e2375-133">Sign in to https://portal.azure.com</span></span>
2. <span data-ttu-id="e2375-134">左ペインで **Azure Active Directory** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2375-134">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="e2375-135">[**管理**] の下で、[**ユーザー設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2375-135">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="e2375-136">[**外部ユーザー**] の下で、[**外部コラボレーションの設定を管理します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2375-136">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="e2375-137">[**外部コラボレーションの設定**] ページで [**メンバーが招待可能**] が [**はい**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2375-137">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="e2375-138">スクリーンショットに AAD 設定の切り替えの例が示されます。</span><span class="sxs-lookup"><span data-stu-id="e2375-138">Screenshot shows an example of an AAD settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="e2375-139">ゲストをサポートするために、[**メンバーが招待可能**] を [**はい**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2375-139">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="e2375-140">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e2375-140">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="e2375-141">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="e2375-141">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="e2375-142">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-142">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="e2375-143">□ 手順 2: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="e2375-143">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="e2375-144">Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2375-144">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="e2375-145">[**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2375-145">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="e2375-146">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e2375-146">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="e2375-147">[**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2375-147">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="e2375-148">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="e2375-148">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="e2375-149">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2375-149">At a minimum, this setting must be On to support guest access.</span></span>

     ![Office 365 グループの切り替えスイッチを示すスクリーンショット](media/guest-access-checklist-office365.png)

<span data-ttu-id="e2375-151">これらの設定の構成方法の詳細については、「[Office 365 グループのゲスト アクセスを管理する](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)」と、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」の「Office 365 グループ」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-151">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="e2375-152">□ 手順 3: テナント レベルでのゲスト アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="e2375-152">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="e2375-153">少なくとも、**Microsoft Teams 管理センター**で Microsoft Teams のゲスト アクセスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2375-153">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="e2375-154">Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2375-154">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="e2375-155">**[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e2375-155">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="e2375-157">この同じページで、必要な他のゲストの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e2375-157">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="e2375-158">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2375-158">Click **Save**.</span></span>

<span data-ttu-id="e2375-159">詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-159">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="e2375-160">□  手順 4: Office 365 での共有を構成する</span><span class="sxs-lookup"><span data-stu-id="e2375-160">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="e2375-161">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2375-161">Make sure that users can add guests.</span></span> <span data-ttu-id="e2375-162">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="e2375-162">Here's how:</span></span>

1. <span data-ttu-id="e2375-163">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2375-163">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="e2375-165">**[共有]** で **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2375-165">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="e2375-167">**[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2375-167">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="e2375-169">この設定は、Azure AD の [**ユーザー設定**] > [**外部ユーザー**] の [**メンバーが招待可能**] 設定と同等です。</span><span class="sxs-lookup"><span data-stu-id="e2375-169">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="e2375-170">□ 手順 5: SharePoint での共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="e2375-170">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="e2375-171">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2375-171">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="e2375-172">[**管理センター**] をクリックして [**SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2375-172">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="e2375-173">SharePoint 管理センターで、[**共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2375-173">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="e2375-174">[**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e2375-174">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーンショットに Sparepoint Online の設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="e2375-176">□ 手順 6: チャネルの特定の設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="e2375-176">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="e2375-177">Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除することができるようにゲストのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2375-177">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="e2375-178">管理者に加えて、チーム所有者もこの設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e2375-178">In addition to admins,  team owners can configure this setting.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="e2375-180">詳細については、使い方ビデオを含む「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2375-180">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="e2375-181">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e2375-181">Troubleshooting</span></span>

<span data-ttu-id="e2375-182">Microsoft Teams でのゲストの追加に問題がある場合は、「[ゲスト アクセスのトラブルシューティング ガイド](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2375-182">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


