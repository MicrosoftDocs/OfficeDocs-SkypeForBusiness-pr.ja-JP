---
title: Microsoft Teams でのゲスト アクセス
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 415066ef24eb83713c44c67cebe1fe0d6cdccb7c
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23859092"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="b9d73-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="b9d73-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="b9d73-104">ゲスト アクセスは Teams での新機能です。</span><span class="sxs-lookup"><span data-stu-id="b9d73-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="b9d73-105">これは、ユーザーからの要望が最も強かった機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b9d73-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="b9d73-106">Microsoft では、継続してこの機能を強化する作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="b9d73-107">ゲスト アクセスの機能の開発状況に付いていくための方法と、その機能に関する意見や要望を提出するための方法を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b9d73-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="b9d73-108">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9d73-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="b9d73-109">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="b9d73-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="b9d73-110">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="b9d73-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="b9d73-111">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="b9d73-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="b9d73-112">Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9d73-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="b9d73-113">ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-113">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="b9d73-114">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9d73-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="b9d73-115">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="b9d73-115">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="b9d73-116">ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="b9d73-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>



<span data-ttu-id="b9d73-117">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="b9d73-117">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="b9d73-118">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="b9d73-118">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="b9d73-119">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-119">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="b9d73-120">すべてのユーザーは、マイクロソフトのチームでは、ゲストとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-120">Anyone can be added as guest in Microsoft Teams.</span></span> <span data-ttu-id="b9d73-121">これは、(Azure Active Directory アカウント) を使用して企業や消費者の電子メール アカウント (Outlook.com、Gmail.com またはその他のユーザー) を持つすべてのユーザーがチーム チャット、会議、およびファイルへのフル アクセスを持つチームにゲストとして参加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b9d73-121">This means that anyone with a business (with an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams with full access to teams chats, meetings and files.</span></span>
<span data-ttu-id="b9d73-122">来園者はチームでは、同じコンプライアンスと監査の保護として、Office 365 の残りの部分についてし、Azure AD 内で安全に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-122">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

> [!NOTE]
> <span data-ttu-id="b9d73-123">スタンドアロン Office 365 サブスクリプション プランを使用して組織内のユーザーのみ、Exchange オンライン計画 2 など招待できない組織には、ゲストとしてチームがこれらのユーザーに同じ組織に属していると見なされるためです。</span><span class="sxs-lookup"><span data-stu-id="b9d73-123">Users in your organization with standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guest to your organization since Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="b9d73-124">チームを使用するこれらのユーザーに割り当てる必要があります Office 365 のビジネス プレミアム、Office 365 の企業、および Office 365 の教育のサブスクリプションを持つ。</span><span class="sxs-lookup"><span data-stu-id="b9d73-124">For these users to use Teams, they must be assigned with Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span>  
      

<span data-ttu-id="b9d73-125">Teams では、企業データを完全に制御して保持しながら、チーム、ドキュメント、リソース、チャット、アプリケーションへの外部アクセスをパートナーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="b9d73-125">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="b9d73-126">来園者は Azure Active Directory 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は来園者はチームで対応します。</span><span class="sxs-lookup"><span data-stu-id="b9d73-126">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure Active Directory.</span></span>  

<span data-ttu-id="b9d73-127">Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9d73-127">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="b9d73-128">Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b9d73-128">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="b9d73-129">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="b9d73-129">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="b9d73-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b9d73-130">More information</span></span>

 
  
    
  [<span data-ttu-id="b9d73-131">Microsoft Teams のサポート リソース</span><span class="sxs-lookup"><span data-stu-id="b9d73-131">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="b9d73-132">Deep Dive into Guest Access (ゲスト アクセスの詳細)</span><span class="sxs-lookup"><span data-stu-id="b9d73-132">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="b9d73-133">Microsoft Teams でのゲスト アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="b9d73-133">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/g21Hcqdl5tI" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="b9d73-134">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="b9d73-134">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

