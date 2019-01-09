---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/18
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: マイクロソフト チームのゲスト アクセスでゲスト アクセスを設定するのには、このチェックリストを使用します。
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7fa7e7d7999bd42748e1997a4ec73b37ca14a67
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772770"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="370f7-103">チームのゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="370f7-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="370f7-104">有効にして、組織の基本設定に応じて、マイクロソフトのチームでゲスト アクセス機能を構成するためには、このチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="370f7-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="370f7-105">来園者の制限を理解します。</span><span class="sxs-lookup"><span data-stu-id="370f7-105">Understand the limitations for guests</span></span>

<span data-ttu-id="370f7-106">ゲストの経験では、設計によって制限があります。</span><span class="sxs-lookup"><span data-stu-id="370f7-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="370f7-107">問題ではないものを修理しようとしていないために、ゲストの経験を理解することを確認します。</span><span class="sxs-lookup"><span data-stu-id="370f7-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="370f7-108">ここでは一部のマイクロソフトのチームでゲストに使用できない機能の一覧です。</span><span class="sxs-lookup"><span data-stu-id="370f7-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="370f7-109">ビジネスの OneDrive</span><span class="sxs-lookup"><span data-stu-id="370f7-109">OneDrive for Business</span></span>
- <span data-ttu-id="370f7-110">チーム外の人の検索</span><span class="sxs-lookup"><span data-stu-id="370f7-110">People search outside of Teams</span></span>
- <span data-ttu-id="370f7-111">予定表、スケジュールされたミーティングの場合、またはミーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="370f7-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="370f7-112">PSTN</span><span class="sxs-lookup"><span data-stu-id="370f7-112">PSTN</span></span>
- <span data-ttu-id="370f7-113">組織図</span><span class="sxs-lookup"><span data-stu-id="370f7-113">Organization chart</span></span>
- <span data-ttu-id="370f7-114">作成またはチームを変更します。</span><span class="sxs-lookup"><span data-stu-id="370f7-114">Create or revise a team</span></span>
- <span data-ttu-id="370f7-115">チームを参照します。</span><span class="sxs-lookup"><span data-stu-id="370f7-115">Browse for a team</span></span>
- <span data-ttu-id="370f7-116">ユーザー間のチャットにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="370f7-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="370f7-117">詳細については、[ゲストの経験のように](guest-experience.md)、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="370f7-118">来園者には、ライセンスのエラーが表示される場合</span><span class="sxs-lookup"><span data-stu-id="370f7-118">If your guests are seeing license errors</span></span>

<span data-ttu-id="370f7-119">マイクロソフトのチームでのゲスト アクセスでは、作業中のディレクトリ ビジネス (B2b) に Azure とのライセンス ・ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="370f7-119">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="370f7-120">ライセンス エラーを表示している場合は、組織には、ユーザーが組織には、来園者を招待することができるように、ライセンス契約の要件を理解する B2B ライセンス ガイドを参照してくださいください。</span><span class="sxs-lookup"><span data-stu-id="370f7-120">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="370f7-121">いくつかの点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-121">A few things to remember:</span></span>

- <span data-ttu-id="370f7-122">Azure AD のライセンスをユーザーに割り当てられた各支払い済みの場合に、ユーザーが外部ユーザーの許可] の下には最大 5 つのゲスト ユーザーを招待できます。</span><span class="sxs-lookup"><span data-stu-id="370f7-122">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="370f7-123">来園者は、組織外のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="370f7-123">Guests are users outside your organization.</span></span> <span data-ttu-id="370f7-124">従業員、オンサイトの契約社員、オンサイト エージェント、およびようには、来園者として追加できません。</span><span class="sxs-lookup"><span data-stu-id="370f7-124">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="370f7-125">関連会社にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="370f7-125">The same applies to your affiliates.</span></span>
- <span data-ttu-id="370f7-126">ゲストのライセンスは、招待側の組織に対してカウントされます。</span><span class="sxs-lookup"><span data-stu-id="370f7-126">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="370f7-127">必要なライセンスの数を計算するときは、これを検討します。</span><span class="sxs-lookup"><span data-stu-id="370f7-127">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="370f7-128">招待されたゲストが別の Office 365 テナントに由来するか、個人用の電子メール アドレスを使用しているかどうかの組織に対するライセンスがカウントされます。</span><span class="sxs-lookup"><span data-stu-id="370f7-128">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="370f7-129">□ 手順 1: Azure AD ビジネス ツー ビジネスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="370f7-129">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="370f7-130">サインインするのにhttps://portal.azure.com。</span><span class="sxs-lookup"><span data-stu-id="370f7-130">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="370f7-131">**Azure Active directory**は、左側のウィンドウでクリックします。</span><span class="sxs-lookup"><span data-stu-id="370f7-131">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="370f7-132">[**管理**] で、**ユーザー設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370f7-132">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="370f7-133">[**外部のユーザー**を**外部の管理の共同作業の設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370f7-133">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="370f7-134">**外部コラボレーションの設定**] ページで**メンバーを招待できる**、 **Yes**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="370f7-134">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="370f7-135">スクリーン ショットでは、AAD の設定の表示/非表示の例を示します。</span><span class="sxs-lookup"><span data-stu-id="370f7-135">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="370f7-136">来園者をサポートするために**メンバーを招待**する必要がありますに設定する **[はい]**。</span><span class="sxs-lookup"><span data-stu-id="370f7-136">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="370f7-137">**なし**に**メンバーを招待できます**を設定し、Office 365 のグループとマイクロソフトのチームでのゲスト アクセスを有効にすると、管理者は、ディレクトリにゲストへの招待を制御できます。</span><span class="sxs-lookup"><span data-stu-id="370f7-137">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="370f7-138">来園者は、ディレクトリには後に、追加できますチームにチームの所有者は、管理者以外のメンバーで。</span><span class="sxs-lookup"><span data-stu-id="370f7-138">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="370f7-139">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="370f7-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="370f7-140">□ 手順 2: Office 365 のグループを構成します。</span><span class="sxs-lookup"><span data-stu-id="370f7-140">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="370f7-141">Microsoft 365 管理センターで、[**設定]** > **サービスおよびアドイン** > **Office 365 のグループ**です。</span><span class="sxs-lookup"><span data-stu-id="370f7-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="370f7-142">**グループ コンテンツには、組織のアクセス以外のグループのメンバー**になっている\*\*\*\* を確認します。</span><span class="sxs-lookup"><span data-stu-id="370f7-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="370f7-143">この設定をオフにすると、来園者は任意のグループのコンテンツにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="370f7-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="370f7-144">**オン**に設定 **、グループの所有者のグループを組織外のユーザーを追加**することを確認します。</span><span class="sxs-lookup"><span data-stu-id="370f7-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="370f7-145">この設定をオフにすると、チームの所有者は新しいゲストを追加するのにはできません。</span><span class="sxs-lookup"><span data-stu-id="370f7-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="370f7-146">最低限、この設定は、ゲスト アクセスをサポートするにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370f7-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![スクリーン ショットには Office 365 のグループの表示を切り替えます。](media/guest-access-checklist-office365.png)

<span data-ttu-id="370f7-148">これらの設定を構成する方法の詳細については、 [Office 365 のグループでのゲスト アクセスの管理](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)と Office 365 の「グループ」では、[マイクロソフト チームでのゲスト アクセス許可](Teams-dependencies.md)を] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="370f7-149">□ ステップ 3: テナントのレベルでのゲスト アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="370f7-149">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="370f7-150">最低限には、**ゲスト**のライセンスの種類のすべてのユーザーのマイクロソフト チームをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="370f7-150">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> 

1. <span data-ttu-id="370f7-151">チーム/Skype のビジネス管理センターで、**組織全体の設定**を選択します > **ゲスト アクセス**します。</span><span class="sxs-lookup"><span data-stu-id="370f7-151">In the Teams & Skype for Business Admin Center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="370f7-152">**マイクロソフトのチームでのゲスト アクセスを許可する**スイッチを**On**に設定します。</span><span class="sxs-lookup"><span data-stu-id="370f7-152">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![スクリーン ショットは、チームの設定の表示/非表示の例を示しています。](media/set-up-guests-image1.png)

3. <span data-ttu-id="370f7-154">この同じページで、必要なその他のゲスト設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="370f7-154">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="370f7-155">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370f7-155">Click **Save**.</span></span>

<span data-ttu-id="370f7-156">詳細については、[オンまたはオフは、マイクロソフトのチームへのゲスト アクセスを有効にする](set-up-guests.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-156">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="370f7-157">□ 手順 4: Office 365 の共有を構成します。</span><span class="sxs-lookup"><span data-stu-id="370f7-157">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="370f7-158">来園者を追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="370f7-158">Make sure that users can add guests.</span></span> <span data-ttu-id="370f7-159">ここではどのようにします。</span><span class="sxs-lookup"><span data-stu-id="370f7-159">Here's how:</span></span>

1. <span data-ttu-id="370f7-160">**設定**に移動し、Microsoft 365 管理センターで、 > **のセキュリティとプライバシー**。</span><span class="sxs-lookup"><span data-stu-id="370f7-160">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![スクリーン ショットは、サービスの設定の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="370f7-162">**共有**、**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="370f7-162">In **Sharing**, select **Edit**.</span></span>

     ![スクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="370f7-164">**ユーザーがこの組織に新しいゲストを追加できるように**設定**を**し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370f7-164">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![スクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="370f7-166">この設定は、**メンバーを招待できる\*\*\*\*ユーザー設定**の設定と同じ > Azure AD では、**外部のユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="370f7-166">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="370f7-167">□ ステップ 5: SharePoint の共有の設定を確認</span><span class="sxs-lookup"><span data-stu-id="370f7-167">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="370f7-168">Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="370f7-168">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="370f7-169">**管理センター**] をクリックし、 **SharePoint**を選択します。</span><span class="sxs-lookup"><span data-stu-id="370f7-169">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="370f7-170">SharePoint 管理センターでは、**共有**を選択します。</span><span class="sxs-lookup"><span data-stu-id="370f7-170">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="370f7-171">オプションの確認 **、組織外の共有を許可しない**が選択されて*いない*場合。</span><span class="sxs-lookup"><span data-stu-id="370f7-171">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーン ショットは、Sparepoint のオンライン設定の表示/非表示の例を示します。](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="370f7-173">□ ステップ 6: チャンネルの特定の設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="370f7-173">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="370f7-174">アプリケーションでは、チーム、個々 のチーム レベルでは、ゲスト アクセス許可を構成来園者が作成、更新、およびチャンネルを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="370f7-174">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="370f7-175">管理者、他チームの所有者は、この設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="370f7-175">In addition to admins,  team owners can configure this setting.</span></span>

![スクリーン ショットは、チームとチャネルの設定の表示/非表示の例を示しています。](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="370f7-177">操作方法のビデオを含む詳細については、[マイクロソフトのチームでのゲスト アクセス](guest-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-177">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="370f7-178">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="370f7-178">Troubleshooting</span></span>

<span data-ttu-id="370f7-179">マイクロソフトのチームで、来園者を追加すると問題がある場合は、[ゲスト アクセスのトラブルシューティング ガイド 』](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370f7-179">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


