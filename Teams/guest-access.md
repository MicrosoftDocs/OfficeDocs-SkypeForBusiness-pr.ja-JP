---
title: Microsoft Teams でのゲスト アクセス
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ccaf4cae1b82b206ebfd27b185dddaf2ab0eece
ms.sourcegitcommit: 9a6e59c0fa020656ed3e858d43e628c3122fc71a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "38746290"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="85fcf-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="85fcf-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="85fcf-104">ゲスト アクセスを使用すると、組織外の個々のユーザーを Microsoft Teams のチームとチャネルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="85fcf-105">外部アクセス (フェデレーション) とゲスト アクセスを比較する (および使用するアクセスを決定する) には、「[Teams の他の組織のユーザーと通信する](communicate-with-users-from-other-organizations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="85fcf-106">組織でゲスト アクセスをオンにする準備ができたら、「[ゲスト アクセスのチェックリスト](guest-access-checklist.md)」から始めます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="85fcf-107">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="85fcf-107">Guest access overview</span></span>

<span data-ttu-id="85fcf-108">ゲスト アクセスにより、組織内のチームは組織外の人に Teams の既存のチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="85fcf-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="85fcf-109">Outlook、Gmail などの勤務先または通常のメール アカウントを持っている全てのユーザーは、チーム チャット、会議、ファイルにフル アクセス権を持つゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="85fcf-110">Teams の管理者は、ゲストがチームで使用できる (使用できない) 機能を制御します、「[ゲスト アクセスの管理](manage-guests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="85fcf-111">ゲスト アクセスは Teams の組織全体の設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="85fcf-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="85fcf-112">ゲスト アクセスは Azure AD および Office 365 サービスの制限の対象になります。</span><span class="sxs-lookup"><span data-stu-id="85fcf-112">Guest access is subject to Azure AD and Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="85fcf-113">ゲスト ユーザーは、共存アップグレード モードの Teams の組織全体の設定に従います。</span><span class="sxs-lookup"><span data-stu-id="85fcf-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="85fcf-114">これは変更できません。</span><span class="sxs-lookup"><span data-stu-id="85fcf-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="85fcf-115">ゲスト アクセスのライセンス</span><span class="sxs-lookup"><span data-stu-id="85fcf-115">Licensing for guest access</span></span>

<span data-ttu-id="85fcf-116">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="85fcf-116">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="85fcf-117">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="85fcf-117">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="85fcf-118">Teams では追加することができるゲストの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="85fcf-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="85fcf-119">ただし、テナントに追加することができるゲストの合計数は、ご利用の Azure AD ライセンスによって許可されるものに基づきます。通常はライセンス ユーザーごとに 5 人です。</span><span class="sxs-lookup"><span data-stu-id="85fcf-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="85fcf-120">詳細については、「[Azure AD B2B コラボレーションのライセンス](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="85fcf-121">Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="85fcf-121">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="85fcf-122">Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85fcf-122">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="85fcf-123">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="85fcf-123">Who is a guest?</span></span>

<span data-ttu-id="85fcf-124">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="85fcf-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="85fcf-125">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="85fcf-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="85fcf-126">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="85fcf-127">自分の組織に属していないユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="85fcf-128">これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="85fcf-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="85fcf-129">ゲストができることとできないことの詳細については、「[Microsoft Teams でゲスト アクセスを許可する](teams-dependencies.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="85fcf-130">または、[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="85fcf-131">最後に、Teams のすべてのゲストは、その他の Office 365 と同じコンプライアンスと監査保護の対象になり、Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="85fcf-132">ゲスト アクセスを使用する理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-132">Why use guest access?</span></span>

<span data-ttu-id="85fcf-133">ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="85fcf-134">Teams のすべてのゲストは、Office 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="85fcf-135">ゲストに対する制限事項を理解する</span><span class="sxs-lookup"><span data-stu-id="85fcf-135">Understand the limitations for guests</span></span>

<span data-ttu-id="85fcf-p109">ゲスト エクスペリエンスでは、デザインによる制限があります。問題ではないものを修正しようとしないために、必ずゲスト エクスペリエンスを理解してください。たとえば、Microsoft Teams のゲストが利用できない一部の機能を以下にリストします。</span><span class="sxs-lookup"><span data-stu-id="85fcf-p109">The guest experience has limitations by design. Make sure you understand the guest experience so you don't try to fix something that isn't a problem. For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="85fcf-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="85fcf-139">OneDrive for Business</span></span>
- <span data-ttu-id="85fcf-140">Teams 外部のユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="85fcf-140">People search outside of Teams</span></span>
- <span data-ttu-id="85fcf-141">カレンダー、予約済みの会議、会議の詳細</span><span class="sxs-lookup"><span data-stu-id="85fcf-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="85fcf-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="85fcf-142">PSTN</span></span>
- <span data-ttu-id="85fcf-143">組織図</span><span class="sxs-lookup"><span data-stu-id="85fcf-143">Organization chart</span></span>
- <span data-ttu-id="85fcf-144">チームの作成または修正</span><span class="sxs-lookup"><span data-stu-id="85fcf-144">Create or revise a team</span></span>
- <span data-ttu-id="85fcf-145">チームの参照</span><span class="sxs-lookup"><span data-stu-id="85fcf-145">Browse for a team</span></span>
- <span data-ttu-id="85fcf-146">個人対個人のチャットへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="85fcf-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="85fcf-147">ゲストは、ユーザーの完全なメール ID が分かっていれば、引き続き (チーム外の) ユーザーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-147">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="85fcf-148">これを防ぐために、IT 管理者はゲストを自分の仮想 GAL に制限することができる[範囲指定ディレクトリ検索](teams-scoped-directory-search.md)などのパターンを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="85fcf-148">To prevent this, IT admins can use patterns like [scoped directory search](teams-scoped-directory-search.md) that have the ability to restrict guests to their own virtual GAL.</span></span>
- <span data-ttu-id="85fcf-149">現在、Teams は、[Azure B2B で定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)されている状態 1 および状態 2 のゲスト ユーザーのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="85fcf-149">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="85fcf-150">ゲストが Teams でできることとできないことの完全なリストについては、「[チーム メンバーとゲスト機能の比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)」表をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-150">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="85fcf-151">Office 365 レベルでのゲスト アクセスの詳細については、「[Office 365 グループへのゲストの追加](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85fcf-151">To learn more about guest access at the Office 365 level, read [Adding guests to Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="85fcf-152">More information</span><span class="sxs-lookup"><span data-stu-id="85fcf-152">More information</span></span>

[<span data-ttu-id="85fcf-153">ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="85fcf-153">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="85fcf-154">Office 365 グループのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="85fcf-154">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
