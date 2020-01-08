---
title: Microsoft Teams のゲスト アクセスのチェックリスト
author: lanachin
ms.author: v-lanac
manager: serdars
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
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962535"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="3020e-103">Microsoft Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="3020e-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="3020e-104">このチェックリストを使用して、Microsoft Teams でゲストアクセスを有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3020e-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="3020e-105">これらの変更を行うには、グローバル管理者またはチーム管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3020e-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3020e-106">変更が有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3020e-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="3020e-107">この短いビデオ (5:31 分) をご覧になり、チームを含む、Microsoft 365 全体でゲストアクセスを有効にする方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="3020e-108">手順 1: Teams の組織全体レベルでゲストアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="3020e-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="3020e-109">ゲストアクセスを有効にするには、 **Microsoft Teams 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3020e-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="3020e-110">Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="3020e-111">**[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3020e-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="3020e-113">この同じページで、ゲストの**通話**、**会議**、**メッセージ**設定をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="3020e-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="3020e-114">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3020e-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="3020e-115">Azure Active Directory、SharePoint Online、Office 365 グループで既定の設定を使用している場合、ゲストアクセスの構成が完了している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3020e-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="3020e-116">この場合は、残りの手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="3020e-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="3020e-117">不明な場合、または AAD、SharePoint Online、または Office 365 グループのカスタム設定を使用している場合は、このチェックリストの残りの手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="3020e-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="3020e-118">手順 2: Azure AD のビジネス対ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3020e-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="3020e-119">テナント管理者として[Azure ポータル](https://portal.azure.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3020e-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="3020e-120">**Azure Active Directory** > **ユーザー** > の**ユーザー設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="3020e-121">[**外部ユーザー**] で、[**外部グループ作業設定の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3020e-122">**外部コラボレーションの設定**は、[**組織関係**] ページからも利用できます。</span><span class="sxs-lookup"><span data-stu-id="3020e-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="3020e-123">Azure Active Directory で、[**管理**] の [**組織の関係** > の**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3020e-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="3020e-124">[**外部コラボレーションの設定**] ページで、有効にするポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="3020e-125">**ゲストユーザーのアクセス許可は制限され**ます: このポリシーは、ディレクトリ内のゲストに対するアクセス許可を決定します。</span><span class="sxs-lookup"><span data-stu-id="3020e-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="3020e-126">ユーザー、グループ、またはその他のディレクトリリソースを列挙するなど、特定のディレクトリタスクのゲストをブロックするには、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="3020e-127">[**いいえ**] を選択して、ディレクトリの通常ユーザーと同じアクセス権をゲストに与えます。</span><span class="sxs-lookup"><span data-stu-id="3020e-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="3020e-128">**ゲスト残っロールの管理者とユーザーは、招待でき**ます。 "ゲスト残っ" ロールの管理者とユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3020e-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="3020e-129">**招待できるメンバー**: ディレクトリの管理者以外のメンバーにゲストの招待を許可するには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3020e-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="3020e-130">[**メンバーが招待可能**] を [**いいえ**] に設定して、Office 365 グループおよび Microsoft Teams でのゲスト アクセスを有効にすると、自分のディレクトリへのゲストの招待を管理者が制御することができます。</span><span class="sxs-lookup"><span data-stu-id="3020e-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="3020e-131">ゲストはディレクトリに入った後、管理者ではない、チーム所有者としてのメンバーによってチームに追加されることができます。</span><span class="sxs-lookup"><span data-stu-id="3020e-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="3020e-132">詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3020e-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="3020e-133">ゲスト アクセスを Teams ですべて機能させるには、[**メンバーが招待できる**] を [**はい**] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3020e-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="3020e-134">**招待できる**ゲスト: ゲストが他のゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="3020e-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="3020e-135">現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="3020e-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="3020e-136">**ゲストのメールの1回限りのパスコードを有効にする (プレビュー)**: 1 回限りのパスコード機能の詳細については、「[ワンタイムパスコードの認証 (プレビュー)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="3020e-137">**共同作業の制限**: 特定のドメインへの招待の許可または禁止の詳細については、「[特定の組織からの B2B ユーザーへの招待を許可またはブロック](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="3020e-138">共同作業の制限については、「 [B2B の外部コラボレーションを有効にする」と「ゲストを招待できるユーザーを管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="3020e-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="3020e-139">ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="3020e-140">手順 3: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="3020e-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="3020e-141">Microsoft 365 管理センターで、[**設定** > **サービス & アドイン**] に移動し、[ **Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-141">In the Microsoft 365 admin center, go to **Settings** > **Services & add-ins**, and then select **Office 365 Groups**.</span></span>

     ![Office 365 グループの切り替えを示すスクリーンショット](media/guest-access-checklist-office365.png)
2. <span data-ttu-id="3020e-143">[**組織外のメンバーにグループのコンテンツをグループと**して使用する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3020e-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="3020e-144">この設定をオフにすると、ゲストはグループのコンテンツにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3020e-144">If this setting is not selected, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="3020e-145">[**グループの所有者に組織外のユーザーをグループに追加**することを許可する] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3020e-145">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="3020e-146">この設定をオフにすると、チームの所有者は新しいゲストを追加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3020e-146">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="3020e-147">少なくとも、ゲストアクセスをサポートするために、この設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3020e-147">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="3020e-148">これらの設定を構成する詳細な手順については、「 [office 365 グループでゲストアクセスを管理](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)する」および「 [office 365 グループのゲストアクセスを制御](Teams-dependencies.md#control-guest-access-in-office-365-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="3020e-149">手順 4: Office 365 で共有を構成する</span><span class="sxs-lookup"><span data-stu-id="3020e-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="3020e-150">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3020e-150">Make sure that users can add guests.</span></span> <span data-ttu-id="3020e-151">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-151">Here's how:</span></span>

1. <span data-ttu-id="3020e-152">Microsoft 365 管理センターで、[**設定**] > [**セキュリティとプライバシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="3020e-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="3020e-154">**[共有]** で **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3020e-154">In **Sharing**, select **Edit**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="3020e-156">**[ユーザーがこの組織に新しいゲストを追加できるようにする]** を **[オン]** に設定し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3020e-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="3020e-158">この設定は、Azure AD の [**ユーザー設定** > ] の [**外部ユーザー** ] で [**メンバーと招待でき**ます] 設定と同じです。</span><span class="sxs-lookup"><span data-stu-id="3020e-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="3020e-159">手順 5: SharePoint で共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="3020e-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="3020e-160">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3020e-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="3020e-161">[**管理センター**] で、[ **SharePoint**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3020e-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="3020e-162">新しい SharePoint 管理センターで、[**サイト**] の下にある [**アクティブサイト**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3020e-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 管理センターのアクティブなサイト](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="3020e-164">サイトを選択し、[**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3020e-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="3020e-165">このオプションが [**すべて**] または **[新規] および [既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3020e-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>
 
     ![SharePoint Online の設定のトグルの例を示すスクリーンショット](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="3020e-167">手順 6: ゲストユーザーの権限を設定する</span><span class="sxs-lookup"><span data-stu-id="3020e-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="3020e-168">Teams アプリケーションの個々のチームレベルで、ゲストがチャネルを作成、更新、または削除できるかどうかを制御するゲストのアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="3020e-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="3020e-169">チーム管理者とチーム所有者は、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3020e-169">Teams admins as well as team owners can configure these settings.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="3020e-171">ゲストアクセスの詳細については、「 [teams のゲストアクセス](guest-access.md)」を参照して、「 [Microsoft teams へのゲストアクセスを有効または](set-up-guests.md)無効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3020e-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="3020e-172">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3020e-172">Troubleshooting</span></span>

<span data-ttu-id="3020e-173">ゲストアクセスの設定で問題が発生した場合、または Teams でゲストを追加した場合は、次のリソースを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="3020e-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="3020e-174">Microsoft Teams でのゲストアクセスに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3020e-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="3020e-175">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3020e-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



