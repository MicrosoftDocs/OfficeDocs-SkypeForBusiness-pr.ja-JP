---
title: マイクロソフト チームのゲスト アクセスのチェックリスト
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: マイクロソフト チームのゲスト アクセスでゲスト アクセスを設定するのには、このチェックリストを使用します。
localization_priority: Priority
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9eec0425f7060597fc0d6a669a9b76821f141421
ms.sourcegitcommit: 0fa147c33b1d7b5790af8d93339700ab62939430
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "19744272"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="0c512-103">チームのゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="0c512-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="0c512-104">有効にして、組織の基本設定に応じて、マイクロソフトのチームでゲスト アクセス機能を構成するためには、このチェックリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c512-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="0c512-105">テナントのレベルで有効にするゲスト アクセスを □</span><span class="sxs-lookup"><span data-stu-id="0c512-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="0c512-106">最低限には、**ゲスト**のライセンスの種類のすべてのユーザーのマイクロソフト チームをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c512-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="0c512-107">詳細については、[オンまたはオフは、マイクロソフトのチームへのゲスト アクセスを有効にする](set-up-guests.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![スクリーン ショットは、チームの設定の表示/非表示の例を示しています。](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="0c512-109">□ は、チャネル固有の設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0c512-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="0c512-110">アプリケーションでは、チーム、個々 のチーム レベルでは、ゲスト アクセス許可を構成来園者が作成、更新、およびチャンネルを削除できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c512-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="0c512-111">管理者、他チームの所有者は、この設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c512-111">In addition to admins,  team owners can configure this setting.</span></span>

![スクリーン ショットは、チームとチャネルの設定の表示/非表示の例を示しています。](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="0c512-113">操作方法のビデオを含む詳細については、[マイクロソフトのチームでのゲスト アクセス](guest-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="0c512-114">□ は、Office 365 の共有を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c512-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="0c512-115">□ は、ユーザーは、来園者を追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c512-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="0c512-116">ここではどのようにします。</span><span class="sxs-lookup"><span data-stu-id="0c512-116">Here's how:</span></span>

1. <span data-ttu-id="0c512-117">**設定**に移動し、Office 365 管理センターで、 > **のセキュリティとプライバシー**。</span><span class="sxs-lookup"><span data-stu-id="0c512-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="0c512-118">![スクリーン ショットは、サービスの設定の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="0c512-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="0c512-119">**共有**、**編集**を選択します。![のスクリーン ショットは、共有の設定の編集] ボタンの例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="0c512-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="0c512-120">**ユーザーがこの組織に新しいゲストを追加できるように**設定**を**し、[**保存**] をクリックします。![のスクリーン ショットは、共有の設定の表示/非表示の例を示しています。](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="0c512-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="0c512-121">この設定は、同じことに、**メンバーを招待できる**ユーザーの設定で > Azure AD 内の外部のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0c512-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="0c512-122">□ は、Office 365 のグループを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c512-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="0c512-123">**設定**に移動し、Office 365 管理センターで、 > **サービスおよびアドイン** > **Office 365 のグループ**です。</span><span class="sxs-lookup"><span data-stu-id="0c512-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="0c512-124">**グループ コンテンツには、組織のアクセス以外のグループのメンバー**になっている**** を確認します。</span><span class="sxs-lookup"><span data-stu-id="0c512-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="0c512-125">この設定をオフにすると、来園者は任意のグループのコンテンツにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0c512-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="0c512-126">**オン**に設定 **、グループの所有者のグループを組織外のユーザーを追加**することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c512-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="0c512-127">この設定をオフにすると、チームの所有者は新しいゲストを追加するのにはできません。</span><span class="sxs-lookup"><span data-stu-id="0c512-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="0c512-128">最低限、この設定は guest アクセスをサポートするために"on"にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c512-128">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="0c512-129">これらの設定を構成する方法の詳細については、[マイクロソフトのチームでのゲスト アクセスを許可](Teams-dependencies.md)し、 [Office 365 のグループへのゲスト アクセスの許可/禁止](https://go.microsoft.com/fwlink/?linkid=869658)の「Office 365 グループ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="0c512-130">□ Azure AD の企業間 (B2B) の設定の構成</span><span class="sxs-lookup"><span data-stu-id="0c512-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="0c512-131">サインインするのにhttps://portal.azure.com。</span><span class="sxs-lookup"><span data-stu-id="0c512-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="0c512-132">**Azure Active directory**は、左側のウィンドウでクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c512-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="0c512-133">[**管理**] で、**ユーザー設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c512-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="0c512-134">**外部ユーザー**] の下の [**外部管理の共同作業の設定**] をクリックします</span><span class="sxs-lookup"><span data-stu-id="0c512-134">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="0c512-135">**外部コラボレーションの設定**] ページで**メンバーを招待できる**、 **Yes**に設定されていることを確認します。![のスクリーン ショットは、AAD の設定の表示/非表示の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c512-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="0c512-136">来園者をサポートするために少なくとも ► は、 **[はい]** に設定してください**メンバーを招待できます**。</span><span class="sxs-lookup"><span data-stu-id="0c512-136">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="0c512-137">**メンバーを招待****なし**に設定して Office 365 のグループとマイクロソフトのチームでのゲスト アクセスを有効にする場合、管理者はディレクトリへのゲストの招待状を制御できます。</span><span class="sxs-lookup"><span data-stu-id="0c512-137">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="0c512-138">来園者は、ディレクトリには後に、追加できますチームに管理者以外のメンバー (チーム所有者) によって。</span><span class="sxs-lookup"><span data-stu-id="0c512-138">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="0c512-139">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0c512-139">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="0c512-140">□ SharePoint での共有設定の確認</span><span class="sxs-lookup"><span data-stu-id="0c512-140">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="0c512-141">Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0c512-141">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="0c512-142">**管理センター**] をクリックし、 **SharePoint**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c512-142">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="0c512-143">SharePoint 管理センターでは、**共有**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c512-143">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="0c512-144">オプションの確認 **、組織外の共有を許可しない**が選択されて*いない*場合。![のスクリーン ショットは、Sparepoint のオンライン設定の表示/非表示の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c512-144">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="0c512-145">□ 検証アカウントのライセンスと種類</span><span class="sxs-lookup"><span data-stu-id="0c512-145">□ Verify account licenses and types</span></span>

- <span data-ttu-id="0c512-146">**チームのアカウントがライセンス**: ルートと他のいくつかの Office 365 テナントに実際のユーザー アカウント"Guest"アカウントの実際のユーザー アカウントがライセンスを保有チームの"Guest"のです。</span><span class="sxs-lookup"><span data-stu-id="0c512-146">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="0c512-147">**アカウントする必要があります Office 365 の学校かアカウント、またはアカウントの MSA の作業**: 現時点では、Azure Active Directory、Office 365 の作業時間や学校のアカウント、または Microsoft アカウント (MSA) に対応する電子メール アドレスを持つユーザーをゲスト ユーザーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="0c512-147">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="0c512-148">□ 構成環境</span><span class="sxs-lookup"><span data-stu-id="0c512-148">□ Configure environment</span></span>


<span data-ttu-id="0c512-149">来園者は、ホストのテナントで必要な場合、多要素認証 (MFA) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c512-149">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="0c512-150">詳細については、[識別情報モデルとマイクロソフトのチームでの認証](identify-models-authentication.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-150">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="0c512-151">来園者の □ 理解の制限事項</span><span class="sxs-lookup"><span data-stu-id="0c512-151">□ Understand limitations for guests</span></span>

<span data-ttu-id="0c512-152">ゲストの経験では、設計によって制限があります。</span><span class="sxs-lookup"><span data-stu-id="0c512-152">The guest experience has limitations by design.</span></span> <span data-ttu-id="0c512-153">問題ではないものを修理しようとしていないために、ゲストの経験を理解することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c512-153">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="0c512-154">ここでは一部のマイクロソフトのチームでゲストに使用できない機能の一覧です。</span><span class="sxs-lookup"><span data-stu-id="0c512-154">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="0c512-155">ビジネスの OneDrive</span><span class="sxs-lookup"><span data-stu-id="0c512-155">OneDrive for Business</span></span>
- <span data-ttu-id="0c512-156">チーム外の人の検索</span><span class="sxs-lookup"><span data-stu-id="0c512-156">People search outside of Teams</span></span>
- <span data-ttu-id="0c512-157">予定表、スケジュールされたミーティングの場合、またはミーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="0c512-157">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="0c512-158">PSTN</span><span class="sxs-lookup"><span data-stu-id="0c512-158">PSTN</span></span>
- <span data-ttu-id="0c512-159">組織図</span><span class="sxs-lookup"><span data-stu-id="0c512-159">Organization chart</span></span>
- <span data-ttu-id="0c512-160">作成またはチームを変更します。</span><span class="sxs-lookup"><span data-stu-id="0c512-160">Create or revise a team</span></span>
- <span data-ttu-id="0c512-161">チームを参照します。</span><span class="sxs-lookup"><span data-stu-id="0c512-161">Browse for a team</span></span>
- <span data-ttu-id="0c512-162">ユーザー間のチャットにファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0c512-162">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="0c512-163">詳細については、[ゲストの経験のように](guest-experience.md)、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-163">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="0c512-164">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0c512-164">Troubleshooting</span></span>

<span data-ttu-id="0c512-165">マイクロソフトのチームで、来園者を追加すると問題がある場合は、[ゲスト アクセスのトラブルシューティング ガイド 』](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c512-165">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


