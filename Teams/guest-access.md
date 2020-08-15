---
title: Microsoft Teams でのゲスト アクセス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761243"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="d3204-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="d3204-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="d3204-104">ゲスト アクセスにより、組織内のチームは組織外の人に Teams の既存のチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="d3204-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="d3204-105">Microsoft 365、Outlook、Gmail などのビジネス用またはコンシューマー用のメールアカウントを持っているユーザーは、チームのチャット、会議、ファイルに完全にアクセスできるゲストとして参加することができます。</span><span class="sxs-lookup"><span data-stu-id="d3204-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="d3204-106">Teams の管理者は、ゲストがチームで使用できる (使用できない) 機能を制御します、「[ゲスト アクセスの管理](manage-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3204-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="d3204-107">外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3204-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="d3204-108">ゲスト アクセスは Teams の組織全体の設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="d3204-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="d3204-109">( [機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を使用して、個々のチームへのゲストアクセスを制御することができます。)</span><span class="sxs-lookup"><span data-stu-id="d3204-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="d3204-110">ゲストを teams に招待する準備ができたら、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="d3204-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="d3204-111">一般に使用するために Teams のゲストアクセスを構成するには、「 [チームのゲストとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3204-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="d3204-112">Azure Active Directory を使用するパートナー組織と共同作業し、ゲストがチームアクセスを自己登録できるようにする方法については、「管理され [たゲストで B2B エクストラネットを作成](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3204-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="d3204-113">ゲスト アクセスは Azure AD および、Microsoft 365 または Office 365 のサービス制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="d3204-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3204-114">ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。</span><span class="sxs-lookup"><span data-stu-id="d3204-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="d3204-115">これは変更できません。</span><span class="sxs-lookup"><span data-stu-id="d3204-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="d3204-116">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="d3204-116">Licensing for guest access</span></span>

<span data-ttu-id="d3204-117">ゲスト アクセスは、Microsoft 365 Business Standard、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3204-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="d3204-118">追加の Microsoft 365 または Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="d3204-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="d3204-119">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d3204-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="d3204-120">ただし、テナントに追加できるゲストの総数は、Azure AD の有料機能によって制限される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d3204-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="d3204-121">詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3204-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="d3204-122">Exchange Online プラン 2 などのスタンドアロンの Microsoft 365 または Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="d3204-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="d3204-123">これらのユーザーが Teams を使用する場合は、Microsoft 365 Business Standard、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3204-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="d3204-124">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="d3204-124">Who is a guest?</span></span>

<span data-ttu-id="d3204-125">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="d3204-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="d3204-126">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="d3204-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="d3204-127">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3204-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="d3204-128">自分の組織に属していないユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d3204-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="d3204-129">これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d3204-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="d3204-130">ゲストができることとできないことの詳細については、「[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3204-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="d3204-131">または、[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3204-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="d3204-132">最後に、Teams のすべてのゲストは、他の Microsoft 365 と同じコンプライアンスおよび監査保護によってカバーされ、Azure AD 内で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d3204-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="d3204-133">ゲスト アクセスを使用する理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="d3204-133">Why use guest access?</span></span>

<span data-ttu-id="d3204-134">ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="d3204-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="d3204-135">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="d3204-135">Understand the limitations for guests</span></span>

<span data-ttu-id="d3204-136">ゲストのエクスペリエンスには、仕様上の制限がかかっています。</span><span class="sxs-lookup"><span data-stu-id="d3204-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="d3204-137">ゲストのエクスペリエンスを確実に理解して、実際の問題ではないことを修正する試みをしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d3204-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="d3204-138">Microsoft Teams のゲストで利用できない機能の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d3204-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="d3204-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d3204-139">OneDrive</span></span>
- <span data-ttu-id="d3204-140">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="d3204-140">People search outside of Teams</span></span>
- <span data-ttu-id="d3204-141">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="d3204-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="d3204-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="d3204-142">PSTN</span></span>
- <span data-ttu-id="d3204-143">組織図</span><span class="sxs-lookup"><span data-stu-id="d3204-143">Organization chart</span></span>
- <span data-ttu-id="d3204-144">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="d3204-144">Create or revise a team</span></span>
- <span data-ttu-id="d3204-145">チームの参照</span><span class="sxs-lookup"><span data-stu-id="d3204-145">Browse for a team</span></span>
- <span data-ttu-id="d3204-146">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="d3204-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="d3204-147">現時点では、チームは、[状態1と状態2のゲストユーザー](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d3204-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="d3204-148">ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3204-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="d3204-149">Microsoft 365 レベルでのゲストアクセスの詳細については、「 [組織外の人と共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)を行う」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3204-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="d3204-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d3204-150">Related topics</span></span>

[<span data-ttu-id="d3204-151">ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="d3204-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="d3204-152">3つのレベルの保護を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="d3204-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
