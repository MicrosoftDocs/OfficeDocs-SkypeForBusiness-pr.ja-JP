---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/18
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams のゲスト アクセスが設定しやすくなります。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: efb5b4394ae7659982a747e79ace2296dbdf2345
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326710"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="8a336-103">Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="8a336-103">Microsoft Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="8a336-104">このチェックリストを使用すると、自分の組織の基本設定に応じて Microsoft Teams のゲスト アクセス機能を有効にしたり、設定したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a336-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="8a336-105">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="8a336-105">Understand the limitations for guests</span></span>

<span data-ttu-id="8a336-106">ゲストのエクスペリエンスには、仕様上の制限がかかっています。</span><span class="sxs-lookup"><span data-stu-id="8a336-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="8a336-107">ゲストのエクスペリエンスを確実に理解して、実際の問題ではないことを修正する試みをしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8a336-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="8a336-108">例として、Microsoft Teams のゲストが利用することができない機能の一部のリストを示します。</span><span class="sxs-lookup"><span data-stu-id="8a336-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="8a336-109">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8a336-109">Access OneDrive for Business storage</span></span>
- <span data-ttu-id="8a336-110">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="8a336-110">People search outside of Teams</span></span>
- <span data-ttu-id="8a336-111">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="8a336-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="8a336-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="8a336-112">PSTN</span></span>
- <span data-ttu-id="8a336-113">組織図</span><span class="sxs-lookup"><span data-stu-id="8a336-113">Organization Chart</span></span>
- <span data-ttu-id="8a336-114">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="8a336-114">Create or revise a team</span></span>
- <span data-ttu-id="8a336-115">チームの参照</span><span class="sxs-lookup"><span data-stu-id="8a336-115">Browse for a team</span></span>
- <span data-ttu-id="8a336-116">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="8a336-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="8a336-117">詳細については、「[ゲストのエクスペリエンスについて](guest-experience.md)」および「[Office 365 グループのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="8a336-118">ゲストに対してライセンスのエラーが表示されている場合</span><span class="sxs-lookup"><span data-stu-id="8a336-118">If your guests are seeing license errors</span></span>

<span data-ttu-id="8a336-119">Microsoft Teams のゲスト アクセスではAzure Active Directory ビジネス ツー ビジネス (B2B) およびそのライセンス モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8a336-119">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="8a336-120">ライセンスのエラーが表示される場合は、B2B ライセンスのガイダンスを必ず読んで自分の組織でのライセンスの要件を理解して、自分たちのユーザーが自分の組織でゲストを招待することができる状態になるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8a336-120">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="8a336-121">次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-121">A few things to remember:</span></span>

- <span data-ttu-id="8a336-122">ユーザーに割り当てた有料の Azure AD ライセンスの場合、1 つのライセンスで 5 人までのゲスト ユーザーを外部ユーザー無料利用分として招待することができます。</span><span class="sxs-lookup"><span data-stu-id="8a336-122">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="8a336-123">ゲストとは、自分の組織の外部のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="8a336-123">Guests are users outside your organization.</span></span> <span data-ttu-id="8a336-124">社内の従業員、オンサイトの請負業者、オンサイトの代理業者などは、ゲストとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a336-124">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="8a336-125">これは、関連会社にも提供されます。</span><span class="sxs-lookup"><span data-stu-id="8a336-125">The same applies to your affiliates.</span></span>
- <span data-ttu-id="8a336-126">ゲスト ライセンスは、招待する組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="8a336-126">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="8a336-127">必要なライセンスの数を算出するときは、このことを考慮に入れます。</span><span class="sxs-lookup"><span data-stu-id="8a336-127">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="8a336-128">招待されたゲストが別の Office 365 テナントからのユーザーであろうと、個人のメール アドレスを使用していようと、ライセンスがカウントされる対象は自分の組織になります。</span><span class="sxs-lookup"><span data-stu-id="8a336-128">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="8a336-129">□  手順 1: Azure AD ビジネス ツー ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="8a336-129">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="8a336-130">https://portal.azure.com にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8a336-130">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="8a336-131">左ペインで **Azure Active Directory** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a336-131">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="8a336-132">[**管理**] の下で、[**ユーザー設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a336-132">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="8a336-133">[**外部ユーザー**] の下で、[**外部コラボレーションの設定を管理します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a336-133">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="8a336-134">[**外部コラボレーションの設定**] ページで [**メンバーが招待可能**] が [**はい**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a336-134">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="8a336-135">スクリーンショットに AAD 設定の切り替えの例が示されます。</span><span class="sxs-lookup"><span data-stu-id="8a336-135">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="8a336-136">ゲストをサポートするために、[**メンバーが招待可能**] を [**はい**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a336-136">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="8a336-137">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="8a336-137">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="8a336-138">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="8a336-138">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="8a336-139">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="8a336-140">□ 手順 2: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="8a336-140">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="8a336-141">Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a336-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="8a336-142">[**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a336-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="8a336-143">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a336-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="8a336-144">[**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a336-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="8a336-145">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="8a336-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="8a336-146">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a336-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![Office 365 グループの切り替えスイッチを示すスクリーンショット](media/guest-access-checklist-office365.png)

<span data-ttu-id="8a336-148">これらの設定の構成方法の詳細については、「[Office 365 グループのゲスト アクセスを管理する](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)」と、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」の「Office 365 グループ」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="8a336-149">□ 手順 3: テナント レベルでのゲスト アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="8a336-149">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="8a336-150">少なくとも、**Microsoft Teams および Skype for Business の管理センター**で Microsoft Teams のゲスト アクセスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a336-150">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams & Skype for Business Admin Center**.</span></span> 

1. <span data-ttu-id="8a336-151">Teams および Skype for Business の管理センターで、[**組織全体の設定**] > [**ゲスト アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a336-151">In the Teams & Skype for Business Admin Center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="8a336-152">[**Microsoft Teams でのゲスト アクセスを許可**] の切り替えスイッチを [**オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a336-152">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/set-up-guests-image1.png)

3. <span data-ttu-id="8a336-154">この同じページで、必要な他のゲストの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8a336-154">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="8a336-155">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a336-155">Click **Save**.</span></span>

<span data-ttu-id="8a336-156">詳細については、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-156">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="8a336-157">□  手順 4: Office 365 での共有を構成する</span><span class="sxs-lookup"><span data-stu-id="8a336-157">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="8a336-158">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a336-158">Make sure that users can add guests.</span></span> <span data-ttu-id="8a336-159">方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8a336-159">Here's how:</span></span>

1. <span data-ttu-id="8a336-160">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8a336-160">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="8a336-162">[**共有**] で、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a336-162">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="8a336-164">[**ユーザーがこの組織に新しいゲストを追加できるようにする**] を [**オン**] にしてから、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a336-164">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="8a336-166">この設定は、Azure AD の [**ユーザー設定**] > [**外部ユーザー**] の [**メンバーが招待可能**] 設定と同等です。</span><span class="sxs-lookup"><span data-stu-id="8a336-166">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="8a336-167">□ 手順 5: SharePoint での共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8a336-167">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="8a336-168">Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8a336-168">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="8a336-169">[**管理センター**] をクリックして [**SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8a336-169">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="8a336-170">SharePoint 管理センターで、[**共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a336-170">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="8a336-171">[**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a336-171">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーンショットに Sparepoint Online の 設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="8a336-173">□ 手順 6: チャネルの特定の設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="8a336-173">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="8a336-174">Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除することができるようにゲストのアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="8a336-174">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="8a336-175">管理者に加えて、チーム所有者もこの設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8a336-175">In addition to admins,  team owners can configure this setting.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="8a336-177">詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a336-177">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="8a336-178">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8a336-178">Troubleshooting</span></span>

<span data-ttu-id="8a336-179">Microsoft Teams でのゲストの追加に問題がある場合は、「[ゲスト アクセスのトラブルシューティング ガイド](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a336-179">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


