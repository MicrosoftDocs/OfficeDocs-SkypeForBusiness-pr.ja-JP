---
title: Microsoft Teams でのゲスト アクセス
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8db3f5e451e9b1a68588af637f10a908f7fa5ff9
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674506"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="5ef79-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="5ef79-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="5ef79-104">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="5ef79-104">Guest access overview</span></span>

<span data-ttu-id="5ef79-105">ゲスト アクセスは、お客様が、ほとんどの機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="5ef79-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="5ef79-106">ゲスト アクセスの進展に対応し、ご意見をお聞かせする方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="5ef79-107">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5ef79-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="5ef79-108">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="5ef79-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="5ef79-109">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="5ef79-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="5ef79-110">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="5ef79-110">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="5ef79-111">ゲスト アクセスでは、既存のチームと、テナントの 1 つ以上のチャネルへのアクセスに付与することによって、組織外のユーザーと共同作業を行う組織でチームを許可します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="5ef79-112">ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="5ef79-113">ゲスト アクセスに含まれていない追加のライセンス要件を持つすべての Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育の購読。</span><span class="sxs-lookup"><span data-stu-id="5ef79-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="5ef79-114">テナントのライセンスを受けたユーザーあたり 5 つまでの来園者を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="5ef79-115">ライセンスの詳細については、 [Azure Active Directory B2B コラボレーションのライセンス ガイド](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ef79-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="5ef79-116">ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="5ef79-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="5ef79-117">Azure AD は、ゲスト アクセス、Office 365 サービスの制限です。</span><span class="sxs-lookup"><span data-stu-id="5ef79-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="5ef79-118">チームがこれらのユーザーに同じ組織に属していると見なされるために、組織にゲストとして Exchange オンライン計画 2 などだけでは、スタンドアロンの Office 365 サブスクリプション プランを持つ、組織内のユーザーを招待できません。</span><span class="sxs-lookup"><span data-stu-id="5ef79-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="5ef79-119">チームを使用するこれらのユーザーに割り当てる必要があります、Office 365 のビジネス プレミアム、Office 365 の企業、または Office 365 の教育のサブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="5ef79-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="5ef79-120">ゲストは誰ですか。</span><span class="sxs-lookup"><span data-stu-id="5ef79-120">Who is a guest?</span></span>

<span data-ttu-id="5ef79-121">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="5ef79-122">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="5ef79-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="5ef79-123">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="5ef79-124">チームでは、ゲストとしては、すべての組織の一部ではないユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="5ef79-125">これは、ビジネス アカウント (つまり、Azure Active Directory) または (Outlook.com、Gmail.com またはその他のユーザー) とコンシューマーの電子メール アカウントを持つユーザーがチームへのフル アクセスを持つ、チームのゲストとして参加できるし、チャネルが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="5ef79-126">(確認できるのゲストの制限では、[マイクロソフトのチームでのゲスト アクセスを許可](teams-dependencies.md)します。)来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span> <span data-ttu-id="5ef79-127">来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-127">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="5ef79-128">ゲスト アクセスを使用する理由</span><span class="sxs-lookup"><span data-stu-id="5ef79-128">Why use guest access?</span></span>
      
<span data-ttu-id="5ef79-129">ゲスト アクセス権を持つチームを使用している組織は、独自の企業データを完全に制御を維持しながらチーム、チャネル、リソース、チャット、および、パートナーでは、アプリケーション内のドキュメントへの外部アクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-129">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="5ef79-130">来園者は Azure AD 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は、来園者はチームで対応します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-130">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="5ef79-131">チームでは、Office 365 のグループが適用され、Office 365 のグループの共有アセットにアクセスするための新しい方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5ef79-131">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="5ef79-132">Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="5ef79-132">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="5ef79-133">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="5ef79-133">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a><span data-ttu-id="5ef79-134">ゲスト アクセスはフェデレーション (外部アクセス) にどのような比較をするでしょうか。</span><span class="sxs-lookup"><span data-stu-id="5ef79-134">How does guest access compare to federation (external access)?</span></span>

<span data-ttu-id="5ef79-135">フェデレーションまたは外部からのアクセスでは、外部ユーザーですることが 1 対 1 のチャットと通話別の組織内のユーザーとチームまたは Skype のいずれかを使用してビジネスの。</span><span class="sxs-lookup"><span data-stu-id="5ef79-135">With federation or external access, an external user can have 1:1 chats and calls with a user in another organization by using either Teams or Skype for Business.</span></span> <span data-ttu-id="5ef79-136">フェデレーション ユーザーは、チーム リソースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5ef79-136">The federated user cannot access any team resources.</span></span> <span data-ttu-id="5ef79-137">ゲスト アクセスと比べると、外部からのアクセスは、明示的な招待状のない組織の間の通信 (ポリシーで許可されている) 場合が、チャットにのみに限定されます。</span><span class="sxs-lookup"><span data-stu-id="5ef79-137">Compared to guest access, external access allows cross organization communication (if permitted by policies) without an explicit invitation, but is limited to chat and call only.</span></span>

## <a name="more-information"></a><span data-ttu-id="5ef79-138">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5ef79-138">More information</span></span>
    
[<span data-ttu-id="5ef79-139">Microsoft Teams のサポート リソース</span><span class="sxs-lookup"><span data-stu-id="5ef79-139">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="5ef79-140">Office 365 のグループでのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="5ef79-140">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="5ef79-141">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="5ef79-141">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="5ef79-142">ゲスト アクセスを掘り下げ</span><span class="sxs-lookup"><span data-stu-id="5ef79-142">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="5ef79-143">マイクロソフトのチームで、来園者を追加します。</span><span class="sxs-lookup"><span data-stu-id="5ef79-143">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

