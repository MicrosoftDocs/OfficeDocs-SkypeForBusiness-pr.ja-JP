---
title: "Microsoft Teams でのゲスト アクセスを管理する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e8cce3faa65de9c0cbd5ffdbb4cb4a6f43a1229d
ms.sourcegitcommit: 1bc2abb2acabe0357d3770284b2710ed9c7f59ee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2017
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="4ef98-103">Microsoft Teams でのゲスト アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="4ef98-103">Manage guest access in Microsoft Teams</span></span>
======================================


# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="4ef98-104">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="4ef98-104">Manage guest access in Microsoft Teams</span></span>

<span data-ttu-id="4ef98-105">Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-105">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="4ef98-106">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-106">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="4ef98-107">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="4ef98-107">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="4ef98-108">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-108">For example, guests may include partners, vendors, suppliers, or consultants.</span></span>
  
    
    

<span data-ttu-id="4ef98-109">Microsoft Teams では、企業データを完全に制御して保持しながら、チーム、ドキュメント、リソース、チャット、アプリケーションへの外部アクセスをパートナーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-109">Organizations using Microsoft Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>
<span data-ttu-id="4ef98-110">Microsoft Teams は、Office 365 グループの上に構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-110">Microsoft Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="4ef98-111">Microsoft Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="4ef98-111">Microsoft Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="4ef98-112">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="4ef98-112">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>
  
    
    

### <a name="how-a-guest-joins-a-team"></a><span data-ttu-id="4ef98-113">ゲストがチームに参加する方法</span><span class="sxs-lookup"><span data-stu-id="4ef98-113">How a guest joins a team</span></span>


  
    
    
<span data-ttu-id="4ef98-114">Microsoft Teams でのチーム所有者は、Web またはデスクトップを介してチームにゲストを追加したり、チームのゲストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-114">A team owner in Microsoft Teams can add and manage guests in their teams via the web or desktop.</span></span> <span data-ttu-id="4ef98-115">Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-115">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="4ef98-116">ゲストがチームに参加するには、管理者が Microsoft Teams でゲスト アクセスを事前に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-116">Before guests can join a team, an admin must enable guest access in Microsoft Teams.</span></span> <span data-ttu-id="4ef98-117">この操作を行うには、Office 365 グローバル管理アカウントで[サインイン](https://portal.office.com/adminportal/home)します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-117">To do that,  [sign in](https://portal.office.com/adminportal/home) with your Office 365 global admin account.</span></span> <span data-ttu-id="4ef98-118">次に、[**設定**]  >  [**Services &amp; add-ins (サービスとアドイン)**]  >  [**Microsoft Teams**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-118">Then, choose **Settings** > **Services &amp; add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="4ef98-119">[**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択し、[**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] で [**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-119">Select **Guest** in **Select the user/license type you want to configure**, and select **On** in **Turn Microsoft Teams on or off for all users of this type**.</span></span> <span data-ttu-id="4ef98-120">設定が有効になるまで最長で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-120">It can take up to an hour for the settings to take effect.</span></span> <span data-ttu-id="4ef98-121">詳しくは、この記事の管理タブにある「Microsoft Teams のゲスト アクセスをオンまたはオフにする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-121">For more details, see "Turn on or off guest access for Microsoft Teams" on this article's Manage tab.</span></span> 
  
    
    

<span data-ttu-id="4ef98-122">ゲストをチームのメンバーにする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-122">Here's how a guest becomes a member of a team:</span></span>
  
    
    

- <span data-ttu-id="4ef98-123">**手順 1** チーム所有者または Office 365 管理者は[チームにゲストを追加します](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)。</span><span class="sxs-lookup"><span data-stu-id="4ef98-123">**Step 1** A team owner or an Office 365 admin [adds a guest to a team](https://support.office.com/en-us/article/adds-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests).</span></span>
    
  
- <span data-ttu-id="4ef98-124">**手順 2** Office 365 管理者またはチーム所有者は必要に応じてゲストが利用できる操作を管理します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-124">**Step 2** The Office 365 admin or the team owner can manage a guest's capabilities as necessary.</span></span> <span data-ttu-id="4ef98-125">たとえば、チャネルの追加または削除、ファイルへのアクセスの無効化といった操作をゲストに許可します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-125">For example, allowing a guest to add or delete channels or disabling access to files.</span></span>
    
  
- <span data-ttu-id="4ef98-126">**手順 3** ゲストは、チームへの参加を招待する「ようこそ」メールをチーム所有者から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-126">**Step 3** The guest receives a welcome email from the team owner, inviting them to join the team.</span></span> <span data-ttu-id="4ef98-127">招待状を受け取った後、ゲストは[チームやチャネルへの参加](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels)、メッセージの受信や返答、[チャネル内のファイルへのアクセス](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加を行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-127">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/en-us/article/participate-in-teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_channels), receive and respond to channel messages, [access files in channels](https://support.office.com/en-us/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), and participate in chat.</span></span> <span data-ttu-id="4ef98-128">Microsoft Teams の使用時には、すべてのユーザーがテキストとアイコンの組み合わせにより、チームにゲストが参加していることを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-128">While using Microsoft Teams, a combination of text and icons gives all team members clear indication of guest participation in a team.</span></span> <span data-ttu-id="4ef98-129">詳しくは、「[ゲストのエクスペリエンス](#guestexp)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-129">For more details, see [what the guest experience is like](#guestexp)</span></span>
    
  
<span data-ttu-id="4ef98-130">ゲストは Microsoft Teams の Web やデスクトップ クライアントを使っていつでもチームから脱退することができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-130">Guests can leave the team at any time via Microsoft Teams web and desktop clients.</span></span> <span data-ttu-id="4ef98-131">詳しくは、「[How do I leave a team? (チームから脱退する方法を教えてください。)](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-131">For details, see  [How do I leave a team?](https://support.office.com/en-us/article/How-do-I-leave-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoileaveateam)</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="4ef98-132">パートナーやコンサルタントなど組織外の人のみをゲストとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-132">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="4ef98-133">組織内のユーザーは通常のチーム メンバーとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-133">People from within your organization can join as regular team members.</span></span> 
  
    
    

<a name="guestexp"></a>
### <a name="what-the-guest-experience-is-like"></a><span data-ttu-id="4ef98-134">ゲストのエクスペリエンスについて</span><span class="sxs-lookup"><span data-stu-id="4ef98-134">What the guest experience is like</span></span>

<span data-ttu-id="4ef98-135">ゲストは、チームへの参加を招待されると、チームに関する情報とメンバーとして利用できる内容を記載する「ようこそ」メール メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-135">When a guest is invited to join a team, they receive a welcome email message that includes some information about the team and what to expect now that they're a member.</span></span> <span data-ttu-id="4ef98-136">ゲストは、メール メッセージの招待状と引き換えに、チームやそのチャネルにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-136">The guest must redeem the invitation in the email message before they can access the team and its channels.</span></span>
  
    
    

  
    
    
![Microsoft Teams のチーム所有者によってゲスト ユーザーに送信された「ようこそ」メール メッセージの例をスクリーンショットに示します。](media/bc0deb82-6394-4280-8fed-312645c8fefe.png)
  
    
    
<span data-ttu-id="4ef98-139">すべてのチーム メンバーは、チーム所有者がゲストを追加した旨およびそのゲストの名前を知らせるメッセージを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-139">All team members see a message in the channel thread announcing that the team owner has added a guest and providing the guest's name.</span></span> <span data-ttu-id="4ef98-140">チームのメンバー全員がゲストが誰であるかを簡単に判断できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-140">Everyone on the team can identify easily who is a guest.</span></span> <span data-ttu-id="4ef98-141">次のサンプル チームのスクリーンショットで示すように、バナーに「This team has guests (チームにゲストが参加しました)」と示され、各ゲストの名前の横に「ゲスト」ラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-141">As shown in the following screenshot of a sample team, a banner indicates "This team has guests" and a "GUEST" label appears next to each guest's name.</span></span>
  
    
    

  
    
    
![スクリーンショットは Northwind Traders の Marketing チャネルの一部を示しています。上部のバナーに「This team has guests (チームにゲストが参加しています)」と示され、ゲストのユーザーはその名前の横の「ゲスト」によって識別されます。](media/33394a31-7d10-4950-8b39-b7d9953397c3.png)
  
    
    
<span data-ttu-id="4ef98-143">次の表に、組織のチーム メンバーが利用できる Microsoft Teams の機能とチームのゲスト ユーザーが利用できる機能との比較を示します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-143">The following table compares the Microsoft Teams functionality available for an organization's team members to the functionality available for a guest user on the team.</span></span>
  
    
    


|<span data-ttu-id="4ef98-144">**Teams の機能**</span><span class="sxs-lookup"><span data-stu-id="4ef98-144">**Capability in Teams**</span></span>|<span data-ttu-id="4ef98-145">**組織の Teams ユーザー**</span><span class="sxs-lookup"><span data-stu-id="4ef98-145">**Teams user in the organization**</span></span>|<span data-ttu-id="4ef98-146">**ゲスト ユーザー**</span><span class="sxs-lookup"><span data-stu-id="4ef98-146">**Guest user**</span></span>|
|:-----|:-----|:-----|
||||
|<span data-ttu-id="4ef98-147">チャネルの作成</span><span class="sxs-lookup"><span data-stu-id="4ef98-147">Create a channel</span></span>  <br/>  <span data-ttu-id="4ef98-148">*この機能はチーム所有者によって制御されます。*</span><span class="sxs-lookup"><span data-stu-id="4ef98-148">*Team owners control this setting.*</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-151">プライベート チャットに参加する</span><span class="sxs-lookup"><span data-stu-id="4ef98-151">Participate in a private chat</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-154">チャネルの会話に参加する</span><span class="sxs-lookup"><span data-stu-id="4ef98-154">Participate in a channel conversation</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-157">メッセージを投稿、削除、編集する</span><span class="sxs-lookup"><span data-stu-id="4ef98-157">Post, delete, and edit messages</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-160">チャネル ファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="4ef98-160">Share a channel file</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-163">チャット ファイルを共有する</span><span class="sxs-lookup"><span data-stu-id="4ef98-163">Share a chat file</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="4ef98-165">アプリ (タブ、ボット、コネクタ) を追加する</span><span class="sxs-lookup"><span data-stu-id="4ef98-165">Add apps (tabs, bots, or connectors)</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="4ef98-167">テナント全体およびチーム/チャネルのゲスト アクセス ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="4ef98-167">Create tenant-wide and teams/channels guest access policies</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="4ef98-169">Office 365 テナントのドメイン外のユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="4ef98-169">Invite a user outside the Office 365 tenant's domain</span></span>  <br/> ||![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)|
|<span data-ttu-id="4ef98-171">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="4ef98-171">Create a team</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="4ef98-173">パブリック チームを検出して参加する</span><span class="sxs-lookup"><span data-stu-id="4ef98-173">Discover and join a public team</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
|<span data-ttu-id="4ef98-175">組織図を表示する</span><span class="sxs-lookup"><span data-stu-id="4ef98-175">View organization chart</span></span>  <br/> |![チェックマーク](media/5277fbec-0a8f-4bd0-b906-d6ddee85a46c.png)||
   

    
> [!NOTE]
> <span data-ttu-id="4ef98-177">ゲストが利用できる機能は Office 365 の管理者によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-177">Office 365 admins control the features available to guests.</span></span> 
  
    
###<a name="manage-guests"></a><span data-ttu-id="4ef98-178">ゲストを管理する</span><span class="sxs-lookup"><span data-stu-id="4ef98-178">Manage guests</span></span>


<span data-ttu-id="4ef98-179">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ef98-179">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="4ef98-180">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="4ef98-180">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="4ef98-181">Microsoft Teams ゲスト アクセスはテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="4ef98-181">Microsoft Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="4ef98-182">管理者は Office 365 管理センターでゲスト アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-182">Admins can manage guest access via the Office 365 admin center.</span></span> <span data-ttu-id="4ef98-183">詳しくは、「[Microsoft Teams へのゲスト アクセスを管理する](#manageguest)」と「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-183">For more details, see [Manage guest access to Microsoft Teams](#manageguest) and [Control guest access to Microsoft Teams](#controlguest).</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="4ef98-184">Microsoft Teams ゲスト アクセスのテナント設定はゲストのサインインのみを拒否します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-184">The Microsoft Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="4ef98-185">チーム所有者は、所有するチームに新しいゲストを招待したり、既存のディレクトリ ゲスト ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-185">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="4ef98-186">Microsoft Teams は、テナントへのゲスト ユーザーの追加の許可または拒否において、常に Azure Active Directory の外部設定を優先します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-186">As a reminder, Microsoft Teams always honor Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="4ef98-187">さらに、Azure Active Directory ポータルを使用して、ゲストの管理、Office 365 や Microsoft Teams のリソースへのゲスト アクセスの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-187">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Microsoft Teams resources.</span></span> <span data-ttu-id="4ef98-188">Microsoft Teams ゲスト アクセスでは、Azure Active Directory ビジネス ツー ビジネス (B2B) コラボレーション機能を基本インフラストラクチャとして活用して、ID プロパティ、メンバーシップ、多要素認証設定といったセキュリティの原則情報を保管します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-188">Microsoft Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="4ef98-189">Azure Active Directory B2B について詳しくは、「[Azure AD B2B コラボレーションとは](https://go.microsoft.com/fwlink/p/?linkid=853011)」と「[Azure Active Directory B2B コラボレーションの FAQ](https://go.microsoft.com/fwlink/p/?linkid=853020)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-189">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  
    
    

#### <a name="related-key-services-and-dependencies"></a><span data-ttu-id="4ef98-190">関連する主要なサービスと依存関係</span><span class="sxs-lookup"><span data-stu-id="4ef98-190">Related key services and dependencies</span></span>

<span data-ttu-id="4ef98-191">Microsoft Teams は、SharePoint Online と OneDrive for Business を利用して、チャネルとチャット会話のファイルやドキュメントを保管します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-191">Microsoft Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="4ef98-192">さらに、Microsoft Teams は、Office 365 グループを利用して、チームのメンバーシップやチーム データ分類設定などのその他のプロパティを保管します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-192">In addition, Microsoft Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span>
  
    
    
<span data-ttu-id="4ef98-193">Microsoft Teams ゲスト アクセスの完全な操作性を有効にするため、Office 365 管理者は次の設定を**オン**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-193">To enable the full Microsoft Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="4ef98-194">SharePoint Online: **Only allow sharing with external users already in the directory (ディレクトリに既に存在する外部ユーザーのみとの共有を許可する)**</span><span class="sxs-lookup"><span data-stu-id="4ef98-194">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="4ef98-195">詳しくは、「[SharePoint Online 環境の外部共有を管理する](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-195">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="4ef98-196">Office 365 グループ: **Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**</span><span class="sxs-lookup"><span data-stu-id="4ef98-196">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="4ef98-197">詳しくは、「[Control guest access to Microsoft Teams (Microsoft Teams へのゲスト アクセスを制御する)](#controlguest)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-197">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
    
  

#### <a name="turn-on-or-off-guest-access-for-microsoft-teams"></a><span data-ttu-id="4ef98-198">Microsoft Teams のゲスト アクセスをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="4ef98-198">Turn on or off guest access for Microsoft Teams</span></span>
<span data-ttu-id="4ef98-199"><a name="bkmk_TurnonOrTurnOff"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-199"></span></span>


1. <span data-ttu-id="4ef98-200">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ef98-200">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="4ef98-201">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-201">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
     ![Office 365 にサインインし、Office 365 管理センターに移動して、[設定]、[Services &amp; add-ins (サービスとアドイン)] の順に選択します。](media/99e676d4-5b48-4525-9556-547031fa37d9.png)
  

  

  
3. <span data-ttu-id="4ef98-203">[**Microsoft Teams**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-203">Select **Microsoft Teams**.</span></span>
    
     ![次のスクリーンショットは、Office 365 管理センターで選択した Microsoft Teams アドインのオプションを示しています。](media/17ac5608-d212-4fa8-ae3a-e78c62003968.png)
  

  

  
4. <span data-ttu-id="4ef98-205">[**Select the user/license type you want to configure (構成するユーザー/ライセンスの種類を選択する)**] で [**ゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-205">In **Select the user/license type you want to configure**, select **Guest**.</span></span>
    
    
  
    
    
![Microsoft Teams アドインのスクリーンショットでは、ゲスト ライセンスが選択され、Microsoft Teams オプションがオンに設定されています。](media/92aabda5-431c-4fdd-803e-5ab49290f4f7.png)
  
    
    

  
    
    

  
    
    

    
  
5. <span data-ttu-id="4ef98-207">[**Turn Microsoft Teams on or off for all users of this type (この種類のすべてのユーザーについて Microsoft Teams をオンまたはオフにする)**] の横にあるトグルをクリックまたはタップして [**オン**] にして組織の Teams とゲスト アクセスをオンにし、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-207">Click or tap the toggle next to **Turn Microsoft Teams on or off for all users of this type** to **On** to turn on Teams and guest access for your organization, and then choose **Save**.</span></span> 
    
  

> [!NOTE]
> <span data-ttu-id="4ef98-208">設定が有効になるまで最長で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-208">It can take up to an hour for the settings to take effect.</span></span> 
  
    
    


#### <a name="control-adding-guest-users-to-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="4ef98-209">Microsoft Teams や Office 365 グループへのゲスト ユーザーの追加を制御する</span><span class="sxs-lookup"><span data-stu-id="4ef98-209">Control adding guest users to Microsoft Teams and Office 365 groups</span></span>
<span data-ttu-id="4ef98-210"><a name="bkmk_ControlAddingGuestUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-210"></span></span>


1. <span data-ttu-id="4ef98-211">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ef98-211">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="4ef98-212">ナビゲーション メニューで [**設定**] を選択し、[**Services &amp; add-ins (サービスとアドイン)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-212">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="4ef98-213">[**Office 365 グループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-213">Select **Office 365 Groups**.</span></span>
    
     ![Office 365 グループ](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="4ef98-215">組織外のチーム所有者やグループ所有者に Office 365 へのアクセスを許可するかどうかに応じて、[Office 365 グループ] ページのトグルを [**オン**] または [**オフ**] にします。</span><span class="sxs-lookup"><span data-stu-id="4ef98-215">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="4ef98-216">[**Let group owners add people outside the organization to groups (グループ所有者に組織外のユーザーをグループに追加させる)**] の横にあるトグルをクリックまたはタップして [**オン**] にします。</span><span class="sxs-lookup"><span data-stu-id="4ef98-216">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span>
    
    
  
    
    
![次のスクリーンショットは、組織外のグループ メンバーによるグループのコンテンツへのアクセス、グループ所有者による組織外のユーザーのグループへの追加のオプションをオンにした [Office 365 グループ] パネルを示しています。](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)
  
    
    

  
    
    

  
    
    

    
  
<span data-ttu-id="4ef98-218"><a name="controlguest"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-218"></span></span>
### <a name="turn-on-or-off-the-sharing-option-for-office-365"></a><span data-ttu-id="4ef98-219">Office 365 の [共有] オプションをオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="4ef98-219">Turn on or off the Sharing option for Office 365</span></span>


<span data-ttu-id="4ef98-220">[共有] オプションでは、組織へのゲストの追加を許可します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-220">The Sharing option allows guests to be added to your organization.</span></span> <span data-ttu-id="4ef98-221">既定では、[共有] オプションは有効です。</span><span class="sxs-lookup"><span data-stu-id="4ef98-221">By default, neither option is enabled.</span></span> <span data-ttu-id="4ef98-222">[共有] オプションをオフにする方法について詳しくは、「[[共有] オプションをオンまたはオフにする](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-222">For information about how to turn off the Sharing option, see [Turn on or off the Sharing option](https://support.office.com/en-us/article/Turn-on-or-off-the-Sharing-option-7c713d74-a144-4eab-92e7-d50df526ff96#bkmk_beforeyoubegin).</span></span>
  
    
    

> [!IMPORTANT]
> <span data-ttu-id="4ef98-223">[共有] オプションをオフにすると、ゲスト アクセスが利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-223">If you turn off the Sharing option, guest access isn't available.</span></span> 
  
    
    


#### <a name="use-powershell-to-control-guest-access"></a><span data-ttu-id="4ef98-224">PowerShell を使用してゲスト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="4ef98-224">Use PowerShell to control guest access</span></span>
<span data-ttu-id="4ef98-225"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-225"></span></span>

<span data-ttu-id="4ef98-226">Office 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-226">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="4ef98-227">PowerShell を使用すると、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-227">With PowerShell, you can do the following:</span></span>
  
    
    

- <span data-ttu-id="4ef98-228">すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="4ef98-228">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="4ef98-229">すべてのチームおよび Office 365 グループへのゲストの追加を許可する</span><span class="sxs-lookup"><span data-stu-id="4ef98-229">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="4ef98-230">特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="4ef98-230">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="4ef98-231">詳しくは、「[PowerShell を使用してゲスト アクセスを制御する](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-231">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="4ef98-232">PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-232">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="4ef98-233">たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-233">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="4ef98-234">Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-234">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="4ef98-235">詳しくは、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-235">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
    
    
<span data-ttu-id="4ef98-236"><a name="manageguest"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-236"></span></span>
### <a name="view-guest-users"></a><span data-ttu-id="4ef98-237">ゲスト ユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="4ef98-237">View guest users</span></span>



1. <span data-ttu-id="4ef98-238">Office 365 グローバル管理アカウントを使用して、[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ef98-238">Sign in with your Office 365 global admin account at  [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="4ef98-239">[**ユーザー**]  >  [**ゲスト ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-239">Go to **Users** > **Guest users**.</span></span>
    
    
  
    
    
![次のスクリーンショットは、Office 365 管理センターの [ユーザー] セクションで選択したゲスト ユーザー オプションを示しています。](media/95b83ff5-72ef-4668-b541-4e25b767620a.png)
  
    

#### <a name="invite-guest-users"></a><span data-ttu-id="4ef98-241">ゲスト ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="4ef98-241">Invite guest users</span></span>
<span data-ttu-id="4ef98-242"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-242"></span></span>

<span data-ttu-id="4ef98-243">チーム所有者や Office 365 管理者は、個別に[ゲストをチームに招待する](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)ことができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-243">A team owner or an Office 365 admin can [invite a guest to a team](https://support.office.com/en-us/article/invite-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) on an individual basis.</span></span> <span data-ttu-id="4ef98-244">ただし、管理者は Office 365 管理センターや Azure Active Directory ポータルを使用して一度の操作で複数のゲストを招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ef98-244">However, admins can't use the Office 365 admin center or the Azure Active Directory portal to invite multiple guests in one action.</span></span> <span data-ttu-id="4ef98-245">一元的にゲストを招待する場合に、Azure Active Directory B2B コラボレーション プレビューを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-245">To invite guests centrally, consider using the Azure Active Directory B2B collaboration preview.</span></span> <span data-ttu-id="4ef98-246">詳しくは、「[Azure AD B2B コラボレーション プレビューについて](https://go.microsoft.com/fwlink/p/?linkid=853011)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-246">For more information, see [About the Azure AD B2B collaboration preview](https://go.microsoft.com/fwlink/p/?linkid=853011).</span></span>
  
    
    

#### <a name="edit-guest-user-information"></a><span data-ttu-id="4ef98-247">ゲスト ユーザー情報を編集する</span><span class="sxs-lookup"><span data-stu-id="4ef98-247">Edit guest user information</span></span>
<span data-ttu-id="4ef98-248"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-248"></span></span>

<span data-ttu-id="4ef98-249">現時点では、Office 365 管理センターや Exchange 管理センターからゲスト情報を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ef98-249">Currently, you can't edit guest information from the Office 365 admin center or the Exchange admin center.</span></span> <span data-ttu-id="4ef98-250">ゲスト アカウントを編集するには (表示名やプロフィール写真など)、Azure Active Directory ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-250">To edit guest accounts (such as display name or profile photo), go to your Azure Active Directory portal.</span></span> <span data-ttu-id="4ef98-251">詳しくは、「[Office 365 ID と Azure Active Directory について](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-251">For more information, see [Understanding Office 365 identity and Azure Active Directory](https://support.office.com/en-us/article/Understanding-Office-365-Identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9).</span></span>
  
    
    
### <a name="frequently-asked-questions-for-admins"></a><span data-ttu-id="4ef98-252">管理についてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="4ef98-252">Frequently asked questions for admins</span></span>
<span data-ttu-id="4ef98-253"><a name="bkmk_UsePowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="4ef98-253"></span></span>

<span data-ttu-id="4ef98-254">Microsoft Teams のチームへの参加にゲストを招待することについて、Office 365 管理者が持つ一般的な質問を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-254">Here are common questions Office 365 admins have about inviting guests to join a team in Microsoft Teams.</span></span>
  
    
    

#### <a name="what-is-a-guest"></a><span data-ttu-id="4ef98-255">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-255">What is a template?</span></span>


  
    
    
<span data-ttu-id="4ef98-256">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-256">A guest is not an employee, student, or member of your organization.</span></span> <span data-ttu-id="4ef98-257">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="4ef98-257">They don't have a school or work account with your organization.</span></span>
  
    
    

  
    
    

#### <a name="who-can-be-added-as-a-guest-user"></a><span data-ttu-id="4ef98-258">ゲスト ユーザーとして追加できるユーザーを教えてください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-258">Who can be added as a guest user?</span></span>

<span data-ttu-id="4ef98-259">Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-259">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
    
    

#### <a name="can-users-add-people-within-my-organization-who-are-not-part-of-the-team-as-a-guest"></a><span data-ttu-id="4ef98-260">ユーザーはチームのメンバーでない組織内の人をゲストとして追加できますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-260">Can users add people within my organization who are not part of the team as a guest?</span></span>

<span data-ttu-id="4ef98-261">パートナーやコンサルタントなど組織外の人のみをゲストとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-261">Only people who are outside of your organization, such as partners or consultants, can be added as guests.</span></span> <span data-ttu-id="4ef98-262">ユーザーは、組織内の人を通常のチーム メンバーまたはサブスクライバーとして参加するように招待できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-262">Users can invite people from within your organization to join as regular team members or subscribers.</span></span>
  
    
    

#### <a name="why-does-a-user-get-the-message-contact-your-administrator-when-they-try-to-add-a-guest-to-their-team"></a><span data-ttu-id="4ef98-263">ユーザーがチームにゲストを追加しようとすると「Contact your administrator (管理者にお問い合わせください)」というメッセージを受信するのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-263">Why does a user get the message "Contact your administrator" when they try to add a guest to their team?</span></span>

<span data-ttu-id="4ef98-264">Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-264">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> <span data-ttu-id="4ef98-265">ユーザーがこのメッセージを受信する場合は、ゲスト機能が有効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-265">When a user sees that message, it's likely that the guest feature hasn't been enabled.</span></span>
  
    
    

#### <a name="how-can-a-global-admin-add-a-new-guest-user-to-the-organization"></a><span data-ttu-id="4ef98-266">グローバル管理者が組織に新しいゲスト ユーザーを追加する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-266">How can a global admin add a new guest user to the organization?</span></span>

<span data-ttu-id="4ef98-267">グローバル管理者は複数の方法で新しいゲスト ユーザーを組織に追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-267">As a global admin, you can add a new guest user to the organization in a couple ways:</span></span>
  
    
    

- <span data-ttu-id="4ef98-268">チームの所有者であるグローバル管理者は、Microsoft Teams デスクトップまたは Web クライアントのいずれかを使用して[チームにゲストを追加](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember)できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-268">Global admins who are owners of a team and owners of a team can [add a guest to a team](https://support.office.com/en-us/article/add-a-guest-to-a-team-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_howdoiaddateammember) through either the Microsoft Teams desktop or the web clients.</span></span>
    
  
- <span data-ttu-id="4ef98-269">Azure Active Directory B2B コラボレーションを使用して組織にゲストを追加します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-269">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="4ef98-270">Azure Active Directory B2B コラボレーションを使用すると、グローバル管理者は、2000 行以下のカンマ区切り (CSV) ファイルを B2B コラボレーション ポータルにアップロードすることで、複数の外部ユーザーを招待、承認できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-270">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="4ef98-271">詳しくは、「[Azure Active Directory B2B コラボレーション](https://go.microsoft.com/fwlink/p/?LinkId=826383)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="4ef98-271">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?LinkId=826383).</span></span>
    
  

#### <a name="is-there-a-way-to-block-individual-guest-users"></a><span data-ttu-id="4ef98-272">個別にゲスト ユーザーを拒否する方法はありますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-272">Is there a way to block individual guest users?</span></span>

<span data-ttu-id="4ef98-273">いいえ。個別にゲスト ユーザーを拒否することはできません。</span><span class="sxs-lookup"><span data-stu-id="4ef98-273">No, individual guest users can't be blocked.</span></span>
  
    
    

#### <a name="can-global-admins-block-guests-in-teams-and-still-allow-guests-to-access-sharepoint-sites"></a><span data-ttu-id="4ef98-274">グローバル管理者はチームでのゲストを拒否する一方でゲストによる SharePoint サイトへのアクセスを許可することはできますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-274">Can global admins block guests in teams and still allow guests to access SharePoint sites?</span></span>

<span data-ttu-id="4ef98-275">はい。グローバル管理者は、SharePoint の外部共有をオンに設定している場合に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの _AllowGuestAccessToGroups_ パラメータを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-275">Yes, global admins can use Azure Active Directory Powershell cmdlets to disable the  _AllowGuestAccessToGroups_ parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>
  
    
    

#### <a name="what-other-controls-are-available-to-it-admins-to-manage-guests-in-microsoft-teams"></a><span data-ttu-id="4ef98-276">IT 管理者が Microsoft Teams でのゲストを管理するために利用できるその他の制御操作を教えてください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-276">What other controls are available to IT admins to manage guests in Microsoft Teams?</span></span>

<span data-ttu-id="4ef98-277">IT 管理者は、テナントレベルでのゲストの追加、ゲスト ユーザー ポリシーと権限の設定と管理、ゲストを招待できるユーザーの判別、ゲスト ユーザーのアクティビティに関するレポートの取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-277">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="4ef98-278">これらの制御は Office 365 管理センターを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-278">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="4ef98-279">ゲスト ユーザーのコンテンツとアクティビティには、Office 365 の他の部分と同じコンプライアンスと監査保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-279">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

#### <a name="can-users-share-a-team-file-with-an-external-user-who-isnt-a-member-of-the-team"></a><span data-ttu-id="4ef98-280">ユーザーはチームのメンバーでない外部ユーザーとチーム ファイルを共有することができますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-280">Can users share a team file with an external user who isn't a member of the team?</span></span>

<span data-ttu-id="4ef98-281">いいえ。</span><span class="sxs-lookup"><span data-stu-id="4ef98-281">No.</span></span> <span data-ttu-id="4ef98-282">ユーザーは、チームへの参加を招待されたゲストとのみ Microsoft Teams ファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-282">Users can only share Microsoft Teams files with guests who have been invited to join the team.</span></span>
  
    
    

#### <a name="is-an-additional-office-365-license-required-for-guest-access"></a><span data-ttu-id="4ef98-283">ゲスト アクセスには追加の Office 365 ライセンスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-283">Is an additional Office 365 license required for guest access?</span></span>

<span data-ttu-id="4ef98-284">追加のライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="4ef98-284">No additional license is required.</span></span> <span data-ttu-id="4ef98-285">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ef98-285">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span>
  
    
    

#### <a name="do-office-365-and-azure-active-directory-service-limits-apply-to-guests"></a><span data-ttu-id="4ef98-286">Office 365 や Azure Active Directory サービスの制限はゲストに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-286">Do Office 365 and Azure Active Directory service limits apply to guests?</span></span>

<span data-ttu-id="4ef98-287">はい。ゲストにも [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) と [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) のサービスの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-287">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    

  
    
    

#### <a name="how-long-does-it-take-until-the-guest-user-settings-take-effect-in-the-office-365-organization"></a><span data-ttu-id="4ef98-288">ゲスト ユーザーの設定が Office 365 組織に反映されるまでどのくらいの時間がかかりますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-288">How long does it take until the guest user settings take effect in the Office 365 organization?</span></span>

<span data-ttu-id="4ef98-289">ゲスト設定は Azure Active Directory で設定します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-289">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="4ef98-290">その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-290">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span>
  
    
    

#### <a name="can-a-global-admin-manage-sharepoint-online-external-user-settings-for-the-teams-connected-team-site"></a><span data-ttu-id="4ef98-291">グローバル管理者は Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-291">Can a global admin manage SharePoint Online external user settings for the Teams connected team site?</span></span>

<span data-ttu-id="4ef98-292">はい。Teams で接続したチーム サイトの SharePoint Online 外部ユーザー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-292">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="4ef98-293">詳しくは、「[SharePoint チーム サイト設定を管理する](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-293">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
  
    
    

  
    
    

#### <a name="how-does-conditional-access-work-with-guest-access"></a><span data-ttu-id="4ef98-294">条件付きアクセスはゲスト アクセスに対してどのように作用しますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-294">How does conditional access work with guest access?</span></span>

<span data-ttu-id="4ef98-295">Azure Active Directory B2B コラボレーションでは、組織は B2B ユーザーに対して条件付きアクセスと多要素認証 (MFA) ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-295">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="4ef98-296">このポリシーは、フルタイムの従業員や組織のメンバーに対して有効にするのと同じ方法で、テナント レベル、アプリ レベルまたは個々のユーザー レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-296">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="4ef98-297">こうしたポリシーはリソース組織で実施します。</span><span class="sxs-lookup"><span data-stu-id="4ef98-297">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="4ef98-298">詳しくは、「[B2B コラボレーション ユーザーの条件付きアクセス](https://go.microsoft.com/fwlink/?linkid=857454)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-298">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span>
  
    
    

#### <a name="if-i-have-a-team-with-an-office-365-group-and-i-add-a-guest-to-the-group-does-that-user-automatically-get-access-to-the-team"></a><span data-ttu-id="4ef98-299">Office 365 グループとのチームを所有している場合に、そのグループにゲストを追加すると、ゲストはチームへのアクセスを自動的に取得しますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-299">If I have a team with an Office 365 group, and I add a guest to the group, does that user automatically get access to the team?</span></span>

<span data-ttu-id="4ef98-300">はい。そのユーザーはチームにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-300">Yes, the guest will get access to the team.</span></span> <span data-ttu-id="4ef98-301">Office 365 グループを介してゲストを追加すると、そのゲストへの招待状メールは生成されません。そのため、チームの他のユーザーがそのゲストに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef98-301">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>
  
    
    

#### <a name="what-event-appears-in-the-audit-log-to-indicate-a-guest-has-been-sent-an-invitation"></a><span data-ttu-id="4ef98-302">監査ログにおいて、ゲストに招待状が送信されたことを示すイベントを教えてください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-302">What event appears in the audit log to indicate a guest has been sent an invitation?</span></span>

<span data-ttu-id="4ef98-303">ゲストの追加は、Azure Active Directory または Office 365 セキュリティ &amp; コンプライアンス センターで追跡できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-303">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="4ef98-304">Microsoft Teams でのゲストの追加は監査され、「Added member to group (グループにメンバーを追加しました)」という Azure AD グループ管理アクティビティとして記録されます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-304">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="4ef98-305">詳しくは、「[B2B コラボレーション ユーザーの監査およびレポート](https://go.microsoft.com/fwlink/p/?linkid=858884)」と「[Office 365 のセキュリティ センターとコンプライアンス センターで監査ログを検索する](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4ef98-305">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>
  
    
    

#### <a name="if-i-have-existing-guest-users-that-were-added-via-azure-ad-b2b-office-365-groups-or-sharepoint-online-do-i-have-to-do-anything-else-with-them-for-microsoft-teams"></a><span data-ttu-id="4ef98-306">Azure AD B2B、Office 365 グループ、SharePoint Online を介して追加したゲスト ユーザーが存在する場合、そのユーザーのために Microsoft Teams でその他の操作を行う必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-306">If I have existing guest users that were added via Azure AD B2B, Office 365 Groups, or SharePoint Online, do I have to do anything else with them for Microsoft Teams?</span></span>

<span data-ttu-id="4ef98-307">Azure Active Directory B2B、Office 365 グループまたは SharePoint Online を介してすでに追加しているゲスト ユーザーはすぐに利用できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-307">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="4ef98-308">Office 365 管理者またはチーム所有者は所有するチームにこのゲストを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-308">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span>
  
    
    

#### <a name="if-external-accounts-are-available-does-that-mean-external-sharing-is-enabled"></a><span data-ttu-id="4ef98-309">外部アカウントを利用できるということは、外部共有が有効になっていることを意味しますか?</span><span class="sxs-lookup"><span data-stu-id="4ef98-309">If external accounts are available, does that mean external sharing is enabled?</span></span>

<span data-ttu-id="4ef98-310">管理者は、外部共有の設定から独立して、Azure Active Directory でゲスト アカウントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-310">Admins can create guest accounts in Azure Active Directory, independent from external sharing settings.</span></span> <span data-ttu-id="4ef98-311">外部共有がオフの場合、管理者のみがゲスト アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4ef98-311">If external sharing is off, only an admin can create guest accounts.</span></span>
  
    
    

  
    
    

## <a name="more-information"></a><span data-ttu-id="4ef98-312">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ef98-312">More information</span></span>

 [<span data-ttu-id="4ef98-313">Microsoft Teams の管理者設定</span><span class="sxs-lookup"><span data-stu-id="4ef98-313">Administrator settings for Microsoft Teams</span></span>](https://support.office.com/en-us/article/Administrator-settings-for-Microsoft-Teams-3966a3f5-7e0f-4ea9-a402-41888f455ba2)
  
    
    
 [<span data-ttu-id="4ef98-314">Microsoft Teams についてよく寄せられる質問 - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="4ef98-314">Frequently asked questions about Microsoft Teams - Admin Help</span></span>](https://support.office.com/en-us/article/Frequently-asked-questions-about-Microsoft-Teams-–-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)
  
    
    
 [<span data-ttu-id="4ef98-315">チームへのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="4ef98-315">Adding guests to teams</span></span>](https://support.office.com/en-us/article/Adding-guests-to-teams-df38ae23-8f85-46d3-b071-cb11b9de5499#bkmk_addingguests)
  
    
    
<span data-ttu-id="4ef98-316">ビデオ: [Deep Dive into Guest Access](https://go.microsoft.com/fwlink/p/?linkid=858791)</span><span class="sxs-lookup"><span data-stu-id="4ef98-316">Video:  [Deep Dive into Guest Access](https://go.microsoft.com/fwlink/p/?linkid=858791)</span></span>
  
    
    

