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
localization_priority: Normal
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
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030283"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="cc2bb-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="cc2bb-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="cc2bb-104">ゲストアクセスを使用すると、組織外のユーザーに対して、チーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができ、企業データを管理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

<span data-ttu-id="cc2bb-105">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="cc2bb-106">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="cc2bb-107">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="cc2bb-108">自分の組織に属していないユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-108">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="cc2bb-109">つまり、ビジネスアカウント (Azure Active Directory アカウント) またはコンシューマーのメールアカウント (Outlook.com、Gmail.com、他のアカウント) を持つユーザーは、teams でゲストとして参加し、チームとチャネルのエクスペリエンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-109">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="cc2bb-110">Teams の管理者は、 [ゲストが teams で使用できる (または使用できない) 機能を制御](manage-guests.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-110">As the Teams admin, you [control which features guests can (and can't) use in Teams](manage-guests.md).</span></span> <span data-ttu-id="cc2bb-111">Teams のゲストは、他の Microsoft 365 と同じコンプライアンスおよび監査保護によってカバーされ、Azure AD 内で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-111">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="cc2bb-112">ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="cc2bb-113">ゲストのエクスペリエンスには、仕様上の制限がかかっています。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-113">The guest experience has limitations by design.</span></span> <span data-ttu-id="cc2bb-114">チームでゲストができることとできないことの詳細については、「 [チームメンバーとゲストの機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-114">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc2bb-115">ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-115">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="cc2bb-116">これは変更できません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-116">This can't be changed.</span></span>

<span data-ttu-id="cc2bb-117">外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-117">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="cc2bb-118">ゲストアクセスを設定する</span><span class="sxs-lookup"><span data-stu-id="cc2bb-118">Set up guest access</span></span>

<span data-ttu-id="cc2bb-119">Teams のゲストアクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 でその他の設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-119">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="cc2bb-120">ゲストを teams に招待する準備ができたら、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-120">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="cc2bb-121">一般に使用するために Teams のゲストアクセスを構成するには、「 [チームのゲストとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-121">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="cc2bb-122">Azure Active Directory を使用するパートナー組織と共同作業し、ゲストがチームアクセスを自己登録できるようにする方法については、「管理され [たゲストで B2B エクストラネットを作成](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-122">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="cc2bb-123">Teams のゲストアクセスは組織全体の設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-123">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="cc2bb-124">[機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲストアクセスを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-124">You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="cc2bb-125">ゲストをチームのメンバーにする方法</span><span class="sxs-lookup"><span data-stu-id="cc2bb-125">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="cc2bb-126">チーム所有者または Microsoft 365 管理者が、 [ゲストをチームに追加](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-126">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="cc2bb-127">ゲストが、チームに関する情報と、チームのメンバーとして要求される事項が記載されたようこそメールを、チーム所有者から受信します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-127">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="cc2bb-128">ゲストが招待を承諾します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-128">The guest accepts the invitation.</span></span>
  <span data-ttu-id="cc2bb-129">Azure Active Directory で職場または学校のアカウントを使用しているゲストユーザーは、招待を承諾して直接認証することができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-129">Guest users who have an work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="cc2bb-130">他のユーザーは、1回限りのパスコードを送信して、身元を確認します ([1 回限りのパスコード認証](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) が必要です)。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-130">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="cc2bb-131">招待を承諾すると、ゲストは [チームやチャネルへの参加](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、チャネル メッセージに対する受信や応答、[チャネル内のファイルへのアクセス](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、チャットへの参加、会議への参加、ドキュメントでの共同作業などを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-131">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="cc2bb-132">Teams では、ゲストは明確に特定されます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-132">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="cc2bb-133">ゲスト ユーザーの名前にはラベル **(ゲスト)** が含まれていて、チャネルにはチームにゲストが存在していることを示すアイコンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-133">A guest user's name includes the label **(Guest)** , and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="cc2bb-134">詳しくは、「[ゲストのエクスペリエンスについて](guest-experience.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-134">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="cc2bb-135">ゲストは Teams 内からいつでもチームを去ることができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-135">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="cc2bb-136">詳しくは、「[チームから脱退する方法を教えてください。](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-136">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="cc2bb-137">チームから脱退しても、組織のディレクトリからゲストアカウントが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-137">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="cc2bb-138">これは、Microsoft 365 グローバル管理者または Azure AD 管理者が行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-138">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="cc2bb-139">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="cc2bb-139">Licensing for guest access</span></span>

<span data-ttu-id="cc2bb-140">ゲストアクセスは、すべての Microsoft 365 ビジネス標準、Microsoft 365 Enterprise、および Microsoft 365 エデュケーションサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-140">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="cc2bb-141">追加の Microsoft 365 ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-141">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="cc2bb-142">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-142">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="cc2bb-143">ただし、テナントに追加できるゲストの総数は、Azure AD の有料機能によって制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-143">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="cc2bb-144">詳細については、「 [AZURE AD の外部 id の課金モデル](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-144">For more information, see [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="cc2bb-145">Exchange Online Plan 2 などのスタンドアロンの Microsoft 365 サブスクリプションプランのみを使用している組織内のユーザーは、これらのユーザーが同じ組織に属していると見なされるため、組織のゲストとして招待することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-145">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="cc2bb-146">これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-146">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="cc2bb-147">ゲストアクセスのレビュー</span><span class="sxs-lookup"><span data-stu-id="cc2bb-147">Guest access reviews</span></span>

<span data-ttu-id="cc2bb-148">Azure AD を使用してアプリケーションに割り当てられたグループ メンバーまたはユーザーに対するアクセス レビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-148">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="cc2bb-149">反復的なアクセス レビューを作成することで、時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-149">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="cc2bb-150">アプリケーション、チーム、またはグループのメンバーにアクセスできるユーザーを定期的にレビューする必要がある場合は、それらのレビューの頻度を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-150">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="cc2bb-151">ゲスト アクセスのレビューを自分自身で実行したり、ゲストにメンバーシップのレビューを求めたり、アプリケーション所有者またはビジネス意思決定者に対してアクセス レビューを実行するよう求めたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-151">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="cc2bb-152">ゲスト アクセス レビューを実行するために、Azure ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-152">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="cc2bb-153">詳細については、「[Azure AD アクセス レビューでゲスト アクセスを管理する](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cc2bb-153">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc2bb-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc2bb-154">Related topics</span></span>

[<span data-ttu-id="cc2bb-155">組織外の人と共同作業する</span><span class="sxs-lookup"><span data-stu-id="cc2bb-155">Collaborating with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="cc2bb-156">特定の Microsoft 365 グループまたは Microsoft Teams チームからのゲストユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="cc2bb-156">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="cc2bb-157">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="cc2bb-157">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="cc2bb-158">ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="cc2bb-158">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="cc2bb-159">3つのレベルの保護を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="cc2bb-159">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
