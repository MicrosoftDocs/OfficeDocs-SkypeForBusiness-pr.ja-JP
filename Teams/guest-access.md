---
title: Microsoft Teams でのゲスト アクセス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
ms.openlocfilehash: 59e0fd09721e488a1806cc7a4ffcf527d34b029a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112423"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="a23b6-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="a23b6-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="a23b6-104">ゲストアクセスを使用すると、企業データの管理を維持しながら、チーム、チャネル内のドキュメント、リソース、チャット、およびアプリケーションへのアクセスを組織外の人々に提供できます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

> [!NOTE]
> <span data-ttu-id="a23b6-105">ただ他の組織の人々を見つけ、電話をかけ、チャットし、会議を設定する場合は、[外部アクセス](manage-external-access.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-105">If you just want to find, call, chat, and set up meetings with people in other organizations, use [external access](manage-external-access.md).</span></span>

<span data-ttu-id="a23b6-106">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-106">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="a23b6-107">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="a23b6-107">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="a23b6-108">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-108">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="a23b6-109">自分の組織に属していないユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-109">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="a23b6-110">これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にアクセスできるゲストとして、Teams に参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-110">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="a23b6-111">Teams のゲストは、Microsoft 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストを Azure AD 内で管理できます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-111">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="a23b6-112">ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="a23b6-113">ゲストのエクスペリエンスには、仕様上の制限があります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-113">The guest experience has limitations by design.</span></span> <span data-ttu-id="a23b6-114">ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-114">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a23b6-115">ゲストは、共存アップグレード モードの Teams の組織全体の設定に従います。</span><span class="sxs-lookup"><span data-stu-id="a23b6-115">Guests follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="a23b6-116">これは変更できません。</span><span class="sxs-lookup"><span data-stu-id="a23b6-116">This can't be changed.</span></span>

<span data-ttu-id="a23b6-117">ゲスト アクセスを設定する方法については、「[チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-117">To set up guest access, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span> 

<span data-ttu-id="a23b6-118">外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-118">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="a23b6-119">ゲスト アクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="a23b6-119">Set up guest access</span></span>

<span data-ttu-id="a23b6-120">Teams でのゲスト アクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 の他の設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-120">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="a23b6-121">ゲストを Teams に招待する準備ができている場合は、次のいずれかをお読みください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-121">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="a23b6-122">一般的な使用のためにチームのゲスト アクセスを構成する方法については、「 [チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-122">To configure guest access for Teams for general use, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="a23b6-123">Azure Active Directory を使用するパートナー組織とコラボレーションし、ゲストがチーム アクセスに自己登録できるようにするには、「[管理されたゲストで B2B エクストラネットを作成する](/microsoft-365/solutions/b2b-extranet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-123">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="a23b6-124">Teams でのゲスト アクセスは組織全体の設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="a23b6-124">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="a23b6-125">[機密ラベル](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲスト アクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-125">You can control guest access to individual teams by using [sensitivity labels](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="a23b6-126">ゲストをチームのメンバーにする方法</span><span class="sxs-lookup"><span data-stu-id="a23b6-126">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="a23b6-127">チーム所有者または Microsoft 365 管理者は[チームにゲストを追加](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-127">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="a23b6-128">ゲストが、チームに関する情報と、チームのメンバーとして要求される事項が記載されたようこそメールを、チーム所有者から受信します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-128">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="a23b6-129">ゲストが招待を承諾します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-129">The guest accepts the invitation.</span></span>
  <span data-ttu-id="a23b6-130">Azure Active Directory の職場や学校のアカウントを持っているゲストは、招待を承諾して、直接認証を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-130">Guests who have a work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="a23b6-131">他のユーザーには、ID を検証するためのワンタイム パスコードが送信されます ([ワンタイム パスコード認証](/azure/active-directory/external-identities/one-time-passcode)が必要です)。</span><span class="sxs-lookup"><span data-stu-id="a23b6-131">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="a23b6-132">招待を承諾すると、ゲストは [チームやチャネルへの参加](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、チャネル メッセージに対する受信や応答、[チャネル内のファイルへのアクセス](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加、会議への参加、ドキュメントでの共同作業などを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-132">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="a23b6-133">Teams では、ゲストは明確に特定されます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-133">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="a23b6-134">ゲスト の名前にはラベル **(ゲスト)** が含まれていて、チャネルにはチームにゲストがいることを示すアイコンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a23b6-134">A guest's name includes the label **(Guest)**, and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="a23b6-135">詳しくは、「[ゲストのエクスペリエンスについて](guest-experience.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-135">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="a23b6-136">ゲストは Teams 内からいつでもチームを去ることができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-136">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="a23b6-137">詳しくは、「[チームから脱退する方法を教えてください。](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-137">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="a23b6-138">チームから脱退しても、組織/ディレクトリからゲスト アカウントを削除したことにはなりません。</span><span class="sxs-lookup"><span data-stu-id="a23b6-138">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="a23b6-139">これは、Microsoft 365 グローバル管理者または Azure AD 管理者が行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-139">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="a23b6-140">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="a23b6-140">Licensing for guest access</span></span>

<span data-ttu-id="a23b6-141">ゲスト アクセスは、Microsoft 365 Business Standard、Microsoft 365 Enterprise、Microsoft 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="a23b6-141">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="a23b6-142">追加の Microsoft 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="a23b6-142">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="a23b6-143">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a23b6-143">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="a23b6-144">ただし、テナントに追加できるゲストの総数は、Azure AD の有料機能によって制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-144">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="a23b6-145">詳細については、「[Azure AD External Identities の課金モデル](/azure/active-directory/b2b/licensing-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-145">For more information, see [Billing model for Azure AD External Identities](/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="a23b6-146">Exchange Online プラン 2 などのスタンドアロンの Microsoft 365 サブスクリプション プランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="a23b6-146">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="a23b6-147">これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a23b6-147">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="a23b6-148">ゲスト アクセス レビュー</span><span class="sxs-lookup"><span data-stu-id="a23b6-148">Guest access reviews</span></span>

<span data-ttu-id="a23b6-149">Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-149">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="a23b6-150">反復的なアクセス レビューを作成することで、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-150">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="a23b6-151">アプリケーションやチームにアクセスできるユーザー、またはメンバーのグループであるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-151">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="a23b6-152">ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a23b6-152">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="a23b6-153">ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a23b6-153">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="a23b6-154">詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a23b6-154">For more information, see [Manage guest access with Azure AD access reviews](/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a23b6-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="a23b6-155">Related topics</span></span>

[<span data-ttu-id="a23b6-156">組織外部のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="a23b6-156">Collaborating with people outside your organization</span></span>](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="a23b6-157">特定の Microsoft 365 グループまたは Microsoft Teams チームにゲストが追加されないようにする</span><span class="sxs-lookup"><span data-stu-id="a23b6-157">Block guests from a specific Microsoft 365 group or Microsoft Teams team</span></span>](/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="a23b6-158">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="a23b6-158">Create a secure guest sharing environment</span></span>](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="a23b6-159">ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a23b6-159">Contact support for business products - Admin Help</span></span>](/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="a23b6-160">3 層の保護を使って Teams を構成する</span><span class="sxs-lookup"><span data-stu-id="a23b6-160">Configure Teams with three tiers of protection</span></span>](/microsoft-365/solutions/configure-teams-three-tiers-protection)