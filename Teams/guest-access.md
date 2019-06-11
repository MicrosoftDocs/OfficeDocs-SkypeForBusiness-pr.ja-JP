---
title: Microsoft Teams でのゲスト アクセス
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e9bf9993311ae723557b8d6f8c5ab777ebccd7c
ms.sourcegitcommit: 21a5550e3c0feafaa57dbcdc428ed13eedd276b8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2019
ms.locfileid: "34748389"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="eb48a-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="eb48a-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="eb48a-104">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="eb48a-104">Guest access overview</span></span>

<span data-ttu-id="eb48a-105">ゲスト アクセスは、ユーザーからの要望が最も多かった機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="eb48a-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="eb48a-106">ゲスト アクセスの進捗状況に対応する方法と、その機能に関する意見や要望を知らせる方法は、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="eb48a-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="eb48a-107">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="eb48a-108">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="eb48a-109">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="eb48a-110">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="eb48a-111">ゲスト アクセスにより、組織内のチームは、1 つまたは複数のテナントでの既存のチームやチャネルにアクセス権を組織外のユーザーに付与することで、共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="eb48a-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="eb48a-112">Outlook、Gmail などの勤務先または通常のメール アカウントを持っている全てのユーザーは、チーム チャット、会議、ファイルにフル アクセス権を持つゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="eb48a-113">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれており、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="eb48a-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="eb48a-114">テナントでライセンスされたユーザーごとに、5 人のゲストまでを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="eb48a-115">ライセンスに関する詳細については、[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/ja-JP/azure/active-directory/b2b/licensing-guidance)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="eb48a-116">ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="eb48a-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="eb48a-117">ゲスト アクセスは Azure AD および Office 365 のサービス制限に適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="eb48a-118">Exchange Online プラン 2 などのスタンドアロン Office 365 サブスクリプションプランのみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="eb48a-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="eb48a-119">Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb48a-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="eb48a-120">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="eb48a-120">Who is a guest?</span></span>

<span data-ttu-id="eb48a-121">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="eb48a-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="eb48a-122">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="eb48a-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="eb48a-123">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="eb48a-124">自分の組織に属していないユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="eb48a-125">これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または通常のメール アカウント (Outlook.com、Gmail.com、他) を持つすべてのユーザーが、チームとチャネルの操作や機能にフル アクセスできるゲストとして、Teams に参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="eb48a-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="eb48a-126">([Microsoft Teams でのゲスト アクセスを承認する](teams-dependencies.md)をご覧ください。) Teams のすべてのゲストは、Office 365と同じように同じコンプライアンスと監査の保護の対象となり、Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="eb48a-127">ゲスト アクセスを使用する理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="eb48a-127">Why use guest access?</span></span>

<span data-ttu-id="eb48a-128">ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへの外部アクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="eb48a-129">Teams のすべてのゲストは、Office 365 と同様のコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="eb48a-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="eb48a-130">Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb48a-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="eb48a-131">Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="eb48a-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="eb48a-132">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="eb48a-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="eb48a-133">ゲスト アクセスを外部アクセス (フェデレーション) と比べるとどのような違いがありますか?</span><span class="sxs-lookup"><span data-stu-id="eb48a-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="eb48a-134">詳細情報</span><span class="sxs-lookup"><span data-stu-id="eb48a-134">More information</span></span>
    
<span data-ttu-id="eb48a-135">[ビジネス製品についてサポートに問い合わせる - 管理者ヘルプ](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="eb48a-135">[Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and we'll walk you through the options.</span></span>  
<span data-ttu-id="eb48a-136">
  [Office 365 グループのゲスト アクセス](https://support.office.com/ja-JP/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="eb48a-136">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="eb48a-137">Introduction to guest access (ゲスト アクセスの概要)</span><span class="sxs-lookup"><span data-stu-id="eb48a-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="eb48a-138">Deep dive into Guest Access (ゲスト アクセスの詳細)</span><span class="sxs-lookup"><span data-stu-id="eb48a-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="eb48a-139">Adding guests in Microsoft Teams (Microsoft Teams でのゲストの追加)</span><span class="sxs-lookup"><span data-stu-id="eb48a-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

