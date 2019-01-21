---
title: Microsoft Teams でのゲスト アクセス
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: b77af005130a4e3783f69c908184a8e19b44a9c5
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772794"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="b5507-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="b5507-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="b5507-104">ゲスト アクセスの概要</span><span class="sxs-lookup"><span data-stu-id="b5507-104">Guest access overview</span></span>

<span data-ttu-id="b5507-105">ゲスト アクセスは、ユーザーからの要望が最も強かった機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b5507-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="b5507-106">ゲスト アクセスの機能の開発状況に付いていくための方法と、その機能に関する意見や要望を提出するための方法を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b5507-106">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>

- <span data-ttu-id="b5507-107">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b5507-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="b5507-108">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="b5507-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="b5507-109">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="b5507-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="b5507-110">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="b5507-110">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="b5507-111">ゲスト アクセスにより、組織内のチームは組織外のユーザーに、1 つまたは複数のテナントでの既存のチームおよびチャネルに対するアクセス権を付与することで、それらのユーザーと共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5507-111">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="b5507-112">Outlook、Gmail などの勤務先または通常のメール アカウントを持っているユーザーは、チーム チャット、会議、ファイルに完全なアクセス権を持つゲストとして Teams に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b5507-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="b5507-113">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれており、追加でライセンスは必要となりません。</span><span class="sxs-lookup"><span data-stu-id="b5507-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="b5507-114">テナントでライセンスされたユーザーごとに、5 人のゲストまでを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b5507-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="b5507-115">ライセンスに関する詳細については、「[Azure Active Directory B2B コラボレーションのライセンスに関するガイダンス](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5507-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="b5507-116">ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="b5507-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="b5507-117">ゲスト アクセスは Azure AD および Office 365 のサービス制限に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5507-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="b5507-118">Exchange Online プラン 2 などの、スタンドアロンの Office 365 サブスクリプション計画のみを持っている組織内のユーザーは、Teams によって組織に属しているものと見なされるため、その同じ組織へのゲストとして招待されることはできません。</span><span class="sxs-lookup"><span data-stu-id="b5507-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="b5507-119">Teams を使用するこれらのユーザーの場合は、Office 365 Business Premium、Office 365 Enterprise、または Office 365 Education サブスクリプションが割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5507-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="b5507-120">ゲストとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="b5507-120">What is a guest?</span></span>

<span data-ttu-id="b5507-121">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="b5507-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="b5507-122">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="b5507-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="b5507-123">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5507-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="b5507-124">自分の組織に属していないすべてのユーザーを Teams のゲストとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b5507-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="b5507-125">これは、ビジネス アカウント (すなわち、Azure Active Directory アカウント) または、コンシューマー メール アカウント (Outlook.com、Gmail.com 他) を持つあらゆるユーザーが、チームおよびチャネルの操作や機能に完全にアクセスすることができるゲストとして、Teams に参加することができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b5507-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="b5507-126">(ゲストの制限事項については、「[Microsoft Teams でのゲスト アクセスを承認する](teams-dependencies.md)」をご覧ください。)Teams のすべてのゲストは、Office 365 の他の部分と同じコンプライアンスと監査による保護の対象となり、Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="b5507-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span> 

## <a name="why-use-guest-access"></a><span data-ttu-id="b5507-127">ゲスト アクセスを使用する理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="b5507-127">Why use guest access?</span></span>
      
<span data-ttu-id="b5507-128">ゲスト アクセスにより、Teams を使用している組織は、企業データに対する完全な制御を維持しながら、パートナーにチーム、チャネル内のドキュメント、リソース、チャット、アプリケーションへの外部アクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="b5507-128">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="b5507-129">Teams のすべてのゲストは、Office 365 の他の部分と同じコンプライアンスと監査による保護の対象となります。また、ゲストは Azure AD 内で安全に管理されます。</span><span class="sxs-lookup"><span data-stu-id="b5507-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="b5507-130">Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5507-130">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="b5507-131">Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b5507-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="b5507-132">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="b5507-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-federation-external-access"></a><span data-ttu-id="b5507-133">ゲスト アクセスをフェデレーション (外部アクセス) と比較するとどのようになりますか?</span><span class="sxs-lookup"><span data-stu-id="b5507-133">How does guest access compare to federation (external access)?</span></span>

<span data-ttu-id="b5507-134">フェデレーションまたは外部アクセスでは、外部ユーザーは Teams または Skype for Business を使用して別の組織のユーザーと 1 対 1 のチャットや、通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b5507-134">With federation or external access, an external user can have 1:1 chats and calls with a user in another organization by using either Teams or Skype for Business.</span></span> <span data-ttu-id="b5507-135">フェデレーションされたユーザーはチームのリソースにアクセスすることができません。</span><span class="sxs-lookup"><span data-stu-id="b5507-135">The federated user cannot access any team resources.</span></span> <span data-ttu-id="b5507-136">ゲスト アクセスと比較すると、外部アクセスでは、明示的な招待なしで、(ポリシーによって許可されている場合に) 組織間にわたる通信が許可されますが、チャットおよび通話のみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="b5507-136">Compared to guest access, external access allows cross organization communication (if permitted by policies) without an explicit invitation, but is limited to chat and call only.</span></span>

## <a name="more-information"></a><span data-ttu-id="b5507-137">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b5507-137">More information</span></span>
    
[<span data-ttu-id="b5507-138">Microsoft Teams のサポート リソース</span><span class="sxs-lookup"><span data-stu-id="b5507-138">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="b5507-139">Office 365 グループのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="b5507-139">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="b5507-140">Introduction to guest access (ゲスト アクセスの概要)</span><span class="sxs-lookup"><span data-stu-id="b5507-140">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="b5507-141">Deep dive into Guest Access (ゲスト アクセスの詳細)</span><span class="sxs-lookup"><span data-stu-id="b5507-141">Deep dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="b5507-142">Adding guests in Microsoft Teams (Microsoft Teams でのゲストの追加)</span><span class="sxs-lookup"><span data-stu-id="b5507-142">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

