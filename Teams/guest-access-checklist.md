---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams のゲスト アクセスが設定しやすくなります。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 404754c373d46b9b6e5578107415d61bbb87f97e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463469"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="cb23e-103">Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="cb23e-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="cb23e-104">このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="cb23e-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="cb23e-105">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="cb23e-105">Understand the limitations for guests</span></span>

<span data-ttu-id="cb23e-106">The guest experience has limitations by design.</span><span class="sxs-lookup"><span data-stu-id="cb23e-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="cb23e-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span><span class="sxs-lookup"><span data-stu-id="cb23e-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="cb23e-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="cb23e-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="cb23e-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cb23e-109">OneDrive for Business</span></span>
- <span data-ttu-id="cb23e-110">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="cb23e-110">People search outside of Teams</span></span>
- <span data-ttu-id="cb23e-111">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="cb23e-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="cb23e-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="cb23e-112">PSTN</span></span>
- <span data-ttu-id="cb23e-113">組織図</span><span class="sxs-lookup"><span data-stu-id="cb23e-113">Organization chart</span></span>
- <span data-ttu-id="cb23e-114">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="cb23e-114">Create or revise a team</span></span>
- <span data-ttu-id="cb23e-115">チームの参照</span><span class="sxs-lookup"><span data-stu-id="cb23e-115">Browse for a team</span></span>
- <span data-ttu-id="cb23e-116">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="cb23e-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="cb23e-117">詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md)」および「[Office 365 グループのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="cb23e-118">ゲスト アクセスと外部アクセス (フェデレーション)</span><span class="sxs-lookup"><span data-stu-id="cb23e-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="cb23e-119">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="cb23e-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="cb23e-120">Microsoft Teams のゲスト アクセスではAzure Active Directory ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="cb23e-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="cb23e-121">ライセンスのエラーが表示される場合は、B2B ライセンスのガイダンスを必ず読んで自分の組織でのライセンスの要件を理解して、自分たちのユーザーが自分の組織でゲストを招待することができる状態になるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="cb23e-122">次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-122">A few things to remember:</span></span>

- <span data-ttu-id="cb23e-123">ユーザーに割り当てた有料の Azure AD ライセンスの場合、1 つのライセンスで 5 人までのゲスト ユーザーを外部ユーザー無料利用分として招待することができます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="cb23e-124">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="cb23e-124">Guests are users outside your organization.</span></span> <span data-ttu-id="cb23e-125">社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="cb23e-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="cb23e-126">これは、関連会社にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="cb23e-127">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="cb23e-128">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="cb23e-129">招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。</span><span class="sxs-lookup"><span data-stu-id="cb23e-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="cb23e-130">□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="cb23e-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="cb23e-131">https://portal.azure.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="cb23e-132">左ペインで **Azure Active Directory** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="cb23e-133">[**管理**] の下で、[**ユーザー設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="cb23e-134">[**外部ユーザー**] の下で、[**外部コラボレーションの設定を管理します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="cb23e-135">[**外部コラボレーションの設定**] ページで [**メンバーが招待可能**] が [**はい**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="cb23e-136">スクリーンショットに AAD 設定の切り替えの例が示されます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-136">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="cb23e-137">ゲストをサポートするために、[**メンバーが招待可能**] を [**はい**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb23e-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="cb23e-138">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="cb23e-139">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="cb23e-140">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="cb23e-141">□ 手順 2: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="cb23e-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="cb23e-142">Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="cb23e-143">[**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="cb23e-144">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb23e-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="cb23e-145">[**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="cb23e-146">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="cb23e-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="cb23e-147">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb23e-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Office 365 グループの切り替えスイッチを示すスクリーンショット](media/guest-access-checklist-office365.png)

<span data-ttu-id="cb23e-149">これらの設定の構成方法の詳細については、「[Office 365 グループのゲスト アクセスを管理する](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)」と、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」の「Office 365 グループ」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="cb23e-150">□ 手順 3: テナント レベルでのゲスト アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="cb23e-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="cb23e-151">最低限には、**マイクロソフトのチーム管理センター**] の [Microsoft チームのゲスト アクセスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb23e-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="cb23e-152">チーム管理センターで、**組織全体の設定**を選択します > **ゲスト アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="cb23e-153">[**Microsoft Teams でのゲスト アクセスを許可**] の切り替えスイッチを [**オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/set-up-guests-image1.png)

3. <span data-ttu-id="cb23e-155">この同じページで、必要な他のゲストの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="cb23e-156">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-156">Click **Save**.</span></span>

<span data-ttu-id="cb23e-157">詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="cb23e-158">□  手順 4: Office 365 での共有を構成する</span><span class="sxs-lookup"><span data-stu-id="cb23e-158">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="cb23e-159">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-159">Make sure that users can add guests.</span></span> <span data-ttu-id="cb23e-160">方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb23e-160">Here's how:</span></span>

1. <span data-ttu-id="cb23e-161">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="cb23e-163">[**共有**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-163">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="cb23e-165">[**ユーザーがこの組織に新しいゲストを追加できるようにする**] を [**オン**] にしてから、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="cb23e-167">この設定は、Azure AD の [**ユーザー設定**] > [**外部ユーザー**] の [**メンバーが招待可能**] 設定と同等です。</span><span class="sxs-lookup"><span data-stu-id="cb23e-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="cb23e-168">□ 手順 5: SharePoint での共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="cb23e-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="cb23e-169">Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="cb23e-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="cb23e-170">[**管理センター**] をクリックして [**SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="cb23e-171">SharePoint 管理センターで、[**共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="cb23e-172">[**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーンショットに Sparepoint Online の 設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="cb23e-174">□ 手順 6: チャネルの特定の設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="cb23e-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="cb23e-175">Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除することができるようにゲストのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb23e-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="cb23e-176">管理者に加えて、チーム所有者もこの設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cb23e-176">In addition to admins,  team owners can configure this setting.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="cb23e-178">詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="cb23e-179">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cb23e-179">Troubleshooting</span></span>

<span data-ttu-id="cb23e-180">Microsoft Teams でのゲストの追加に問題がある場合は、「[ゲスト アクセスのトラブルシューティング ガイド](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb23e-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


