---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: このチェックリストを使用すると、Microsoft Teams の設定が容易になります。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753322"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="d2963-103">Microsoft Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="d2963-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="d2963-104">このチェックリストを使用して、Microsoft Teams でゲストアクセスを有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d2963-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2963-105">変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d2963-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="d2963-106">手順 1: Teams の組織全体レベルでゲストアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="d2963-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="d2963-107">ゲストアクセスを有効にするには、 **Microsoft Teams 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2963-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="d2963-108">Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="d2963-109">**[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2963-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="d2963-111">この同じページで、ゲストの**通話**、**会議**、**メッセージ**設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="d2963-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="d2963-112">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2963-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="d2963-113">Azure Active Directory、SharePoint Online、Office 365 グループで既定の設定を使用している場合、ゲストアクセスの構成が完了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d2963-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="d2963-114">この場合は、残りの手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="d2963-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="d2963-115">不明な場合、または AAD、SharePoint Online、または Office 365 グループのカスタム設定を使用している場合は、このチェックリストの残りの手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="d2963-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="d2963-116">手順 2: Azure AD のビジネス対ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d2963-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="d2963-117">テナント管理者として[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2963-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="d2963-118">**Azure Active Directory** > **ユーザー** > の**ユーザー設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="d2963-119">[**外部ユーザー**] で、[**外部グループ作業設定の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="d2963-120">**外部コラボレーションの設定**は、[**組織関係**] ページからも利用できます。</span><span class="sxs-lookup"><span data-stu-id="d2963-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="d2963-121">Azure Active Directory で、[**管理**] の [**組織の関係** > の**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2963-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="d2963-122">[**外部コラボレーションの設定**] ページで、有効にするポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="d2963-123">**ゲストユーザーのアクセス許可は制限され**ます: このポリシーは、ディレクトリ内のゲストに対するアクセス許可を決定します。</span><span class="sxs-lookup"><span data-stu-id="d2963-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="d2963-124">ユーザー、グループ、またはその他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのゲストをブロックするには、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="d2963-125">[**いいえ**] を選択して、ディレクトリの通常ユーザーと同じアクセス権をゲストに与えます。</span><span class="sxs-lookup"><span data-stu-id="d2963-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="d2963-126">**ゲスト残っロールの管理者とユーザーは、招待でき**ます。 "ゲスト残っ" ロールの管理者とユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2963-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="d2963-127">**招待できるメンバー**: ディレクトリの管理者以外のメンバーにゲストの招待を許可するには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2963-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="d2963-128">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="d2963-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="d2963-129">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="d2963-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="d2963-130">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2963-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="d2963-131">ゲストアクセスが Teams で利用できるようにするには、**メンバーが** **[はい]** に招待できるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2963-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="d2963-132">**招待できる**ゲスト: ゲストが他のゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2963-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="d2963-133">現時点では、チームはゲスト残っの役割をサポートしていないため、ゲストが **[はい]** に**招待できる**ように設定した場合でも、ゲストは teams で他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="d2963-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="d2963-134">**ゲストのメールの1回限りのパスコードを有効にする (プレビュー)**: 1 回限りのパスコード機能の詳細については、「[ワンタイムパスコードの認証 (プレビュー)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="d2963-135">**共同作業の制限**: 特定のドメインへの招待の許可または禁止の詳細については、「[特定の組織からの B2B ユーザーへの招待を許可またはブロック](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="d2963-136">共同作業の制限については、「 [B2B の外部コラボレーションを有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="d2963-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="d2963-137">ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="d2963-138">手順 3: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="d2963-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="d2963-139">Microsoft 365 管理センターで、[**設定**] > [**サービスとアドイン**] > [**Office 365 グループ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2963-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="d2963-140">[**組織外部のグループ メンバーがグループ コンテンツにアクセスすることを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2963-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="d2963-141">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d2963-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="d2963-142">[**グループ所有者が組織外部のユーザーをグループに追加することを許可**] が [**オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2963-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="d2963-143">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="d2963-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="d2963-144">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2963-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![Office 365 グループの切り替えを示すスクリーンショット](media/guest-access-checklist-office365.png)

<span data-ttu-id="d2963-146">これらの設定を構成する詳細な手順については、「 [office 365 グループでゲストアクセスを管理](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)する」および「 [office 365 グループのゲストアクセスを制御](Teams-dependencies.md#control-guest-access-in-office-365-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="d2963-147">手順 4: Office 365 で共有を構成する</span><span class="sxs-lookup"><span data-stu-id="d2963-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="d2963-148">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2963-148">Make sure that users can add guests.</span></span> <span data-ttu-id="d2963-149">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-149">Here's how:</span></span>

1. <span data-ttu-id="d2963-150">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d2963-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="d2963-152">**[共有]** で **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-152">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="d2963-154">**[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2963-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="d2963-156">この設定は、Azure AD の [**ユーザー設定** > ] の [**外部ユーザー** ] で [**メンバーと招待でき**ます] 設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="d2963-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="d2963-157">手順 5: SharePoint で共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="d2963-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="d2963-158">これは、脳 teaser の1つです。</span><span class="sxs-lookup"><span data-stu-id="d2963-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="d2963-159">SharePoint 管理センターで [**組織外**との共有を許可しない] 設定が選択されている場合、Teams でのゲストアクセスが機能しません。</span><span class="sxs-lookup"><span data-stu-id="d2963-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="d2963-160">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2963-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="d2963-161">[**管理センター**] をクリックして [**SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d2963-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="d2963-162">SharePoint 管理センターで、[**共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d2963-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="d2963-163">[**組織外との共有を許可しない**] の選択が*解除*されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2963-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![スクリーンショットに Sparepoint Online の設定の切り替えの例が示されます。](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="d2963-165">手順 6: ゲストユーザーの権限を設定する</span><span class="sxs-lookup"><span data-stu-id="d2963-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="d2963-166">Teams アプリケーションの個々のチームレベルで、ゲストがチャネルを作成、更新、または削除できるかどうかを制御するゲストのアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="d2963-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="d2963-167">チーム管理者とチーム所有者は、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d2963-167">Teams admins as well as team owners can configure these settings.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="d2963-169">ゲストアクセスの詳細については、「 [teams のゲストアクセス](guest-access.md)」を参照して、「 [Microsoft teams へのゲストアクセスを有効または](set-up-guests.md)無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2963-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="d2963-170">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d2963-170">Troubleshooting</span></span>

<span data-ttu-id="d2963-171">ゲストアクセスの設定で問題が発生した場合、または Teams でゲストを追加した場合は、次のリソースを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="d2963-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="d2963-172">Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d2963-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="d2963-173">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d2963-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



