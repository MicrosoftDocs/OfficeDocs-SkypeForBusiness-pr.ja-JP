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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5470d9ec2ec2d22d8f3b66bac09ba6c67b9982f
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951502"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="33d89-103">Microsoft Teams のゲスト アクセスのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="33d89-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="33d89-104">このチェックリストは、Microsoft Teams のゲスト アクセスを有効にして、構成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33d89-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="33d89-105">これらの変更を行うには、グローバル管理者または Teams の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="33d89-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33d89-106">変更が有効になるまで最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33d89-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="33d89-107">この短いビデオ (5 分 31 秒) で、Teams を含む、Microsoft 365 全体でゲスト アクセスを有効する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33d89-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="33d89-108">手順 1: Teams の組織全体レベルでゲスト アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="33d89-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="33d89-109">ゲスト アクセスを有効にするには、**Microsoft Teams 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="33d89-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="33d89-110">Teams 管理センターで、**[組織全体の設定]** > **[ゲスト アクセス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="33d89-111">**[Microsoft Teams でのゲスト アクセスを許可]** のスイッチを **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="33d89-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="33d89-113">このページでは、ゲストの**通話**、**会議**、**メッセージング**を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="33d89-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="33d89-114">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33d89-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="33d89-115">Azure Active Directory、SharePoint Online、Office 365 グループで既定の設定を使用している場合は、ゲスト アクセスは構成済みの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33d89-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="33d89-116">この場合、残りの手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="33d89-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="33d89-117">はっきりしない場合、または AAD、SharePoint Online、Office 365 グループでカスタム設定を利用している場合は、このチェックリストの残りの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="33d89-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="33d89-118">手順 2: Azure AD ビジネス ツー ビジネスの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="33d89-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="33d89-119">これは、Teams のゲスト アクセスをサポートする Azure AD の設定です。</span><span class="sxs-lookup"><span data-stu-id="33d89-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="33d89-120">これらの設定を構成すると、Teams でゲストを[追加](add-guests.md)したり、[管理](manage-guests.md)したりできます。</span><span class="sxs-lookup"><span data-stu-id="33d89-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="33d89-121">テナント管理者として [Azure portal](https://portal.azure.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="33d89-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="33d89-122">**[Azure Active Directory]** > **[ユーザー]** > **[ユーザー設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="33d89-123">**[外部ユーザー]** で、**[外部コラボレーション設定の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="33d89-124">**外部コラボレーションの設定**は、**[組織の関係]** ページから利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="33d89-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="33d89-125">Azure Active Directory の **[管理]** で、**[組織の関係]** > **[設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="33d89-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="33d89-126">**[外部コラボレーションの設定]** ページで、有効にするポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="33d89-127">**[ゲスト ユーザーのアクセス許可を制限する]**: このポリシーによって、ディレクトリ内のゲストのアクセス許可を決定します。</span><span class="sxs-lookup"><span data-stu-id="33d89-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="33d89-128">**[はい]** を選択すると、ゲストは、特定のディレクトリ タスク (ユーザー、グループ、またはその他のディレクトリ リソースを列挙するなど) を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="33d89-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="33d89-129">**[いいえ]** を選択すると、ゲストには、ディレクトリ データに対して、ディレクトリ内の通常のユーザーと同じアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="33d89-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="33d89-130">**[管理者とゲスト招待元ロールのユーザーは招待ができる]**: 管理者と "ゲスト招待元" ロールのユーザーがゲストを招待できるようにするには、このポリシーを **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="33d89-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="33d89-131">[**メンバーが招待可能**]: ディレクトリの管理者以外のメンバーがゲストを招待できるようにするには、このポリシーを [**はい**] に設定します (推奨)。</span><span class="sxs-lookup"><span data-stu-id="33d89-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="33d89-132">管理者だけがゲストを追加できるようにする場合は、このポリシーを [**いいえ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="33d89-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="33d89-133">[**いいえ**] に設定すると、管理者以外の Teams 所有者のゲスト エクスペリエンスが制限され、管理者により AAD に追加されたゲストだけを Teams に追加できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="33d89-134">**[ゲストは招待ができる]**: ゲストが他のゲストを招待できるようにするには、このポリシー **[はい]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="33d89-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="33d89-135">現在、Teams はゲスト招待者の役割をサポートしていないため、[**ゲストが招待できる**] を [**はい**] に設定しても、ゲストは Teams 内の他のゲストを招待できません。</span><span class="sxs-lookup"><span data-stu-id="33d89-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="33d89-136">**[ゲストの電子メール ワンタイム パスコードを有効にする (プレビュー)]**: ワンタイム パスコード機能の詳細については、「[電子メール ワンタイム パスコード認証 (プレビュー)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="33d89-137">**[コラボレーションの制限]**: 特定のドメインへの招待の許可またはブロックの詳細については、「[B2B ユーザーに対する特定組織からの招待を許可またはブロックする](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="33d89-138">コラボレーションの制限については、「[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザー管理する](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="33d89-139">ゲストを招待できるユーザーの管理方法の詳細については、「[Azure Active Directory B2B コラボレーションの招待の委任](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="33d89-140">手順 3: Office 365 グループを構成する</span><span class="sxs-lookup"><span data-stu-id="33d89-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="33d89-141">Microsoft 365 管理センターの **[設定]** > **[設定]** に移動し、**[サービス]** をクリックし、**[Office 365 グループ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![Office 365 グループの設定を示すスクリーンショット](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="33d89-143">**[組織外のグループ メンバーがグループ コンテンツにアクセスできるようにします]** のチェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d89-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="33d89-144">この設定がオフになっていると、ゲストはどのグループ コンテンツにもアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="33d89-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Office 365 グループの設定を示すスクリーンショット](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="33d89-146">**[グループの所有者が組織外のユーザーをグループに追加できるようにします]** のチェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d89-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="33d89-147">この設定がオフになっていると、チームの所有者は新しいゲストを追加することができません。</span><span class="sxs-lookup"><span data-stu-id="33d89-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="33d89-148">少なくとも、ゲスト アクセスをサポートするためにこの設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33d89-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="33d89-149">これらの設定の構成方法の詳細については、「[Office 365 グループでゲスト アクセスを管理する](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150)」と、「[Office 365 グループでゲスト アクセスを管理する](Teams-dependencies.md#control-guest-access-in-office-365-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="33d89-150">手順 4: Office 365 での共有を構成する</span><span class="sxs-lookup"><span data-stu-id="33d89-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="33d89-151">ユーザーがゲストを追加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d89-151">Make sure that users can add guests.</span></span> <span data-ttu-id="33d89-152">次の操作を実行してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-152">Here's how:</span></span>

1. <span data-ttu-id="33d89-153">Microsoft 365 管理センターの **[設定]** > **[設定]** に移動し、**[セキュリティとプライバシー]** をクリックし、**[共有]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![サービスの設定の例を示すスクリーンショット](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="33d89-155">**[ユーザーがこの組織に新しいゲストを追加できるようにする]** のチェックボックスをオンにし、**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33d89-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![共有設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="33d89-157">この設定は、Azure AD の **[ユーザー設定]** > **[外部ユーザー]** の **[メンバーは招待ができる]** 設定と同等です。</span><span class="sxs-lookup"><span data-stu-id="33d89-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="33d89-158">手順 5: SharePoint での共有設定を確認する</span><span class="sxs-lookup"><span data-stu-id="33d89-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="33d89-159">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="33d89-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="33d89-160">**[管理センター]** で **[SharePoint]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="33d89-161">新しい SharePoint 管理センターの **[サイト]** で、**[アクティブなサイト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33d89-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 管理センターのアクティブなサイト](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="33d89-163">サイトを選び、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33d89-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="33d89-164">オプションが **[すべてのユーザー]** または **[新規および既存のゲスト]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d89-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![SharePoint Online の設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="33d89-166">手順 6: ゲスト ユーザーのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="33d89-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="33d89-167">Teams アプリケーションで、個人のチーム レベルにおいて、ゲストがチャネルを作成、更新、削除できるようにするかどうかを管理するゲストのアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="33d89-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="33d89-168">Teams の管理者とチームの所有者が、これらの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="33d89-168">Teams admins as well as team owners can configure these settings.</span></span>

![チーム/チャネルの設定の切り替えの例を示すスクリーンショット](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="33d89-170">ゲスト アクセスの詳細については、「[Microsoft Teams でのゲスト アクセス](guest-access.md)」、または、「[Microsoft Teams へのゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="33d89-171">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33d89-171">Troubleshooting</span></span>

<span data-ttu-id="33d89-172">ゲスト アクセスの設定、または Teams へのゲストの追加で問題が発生した場合は、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33d89-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="33d89-173">Microsoft Teams のゲスト アクセスのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33d89-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="33d89-174">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33d89-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
