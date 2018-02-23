---
title: "Microsoft Teams でのゲスト アクセス"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: laal
description: "Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e5f062d52bc03c6bcd469e8ce33c8f794c00b6c
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2018
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="dcf80-103">Microsoft Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="dcf80-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="dcf80-104">ゲスト アクセスは Teams での新機能です。</span><span class="sxs-lookup"><span data-stu-id="dcf80-104">Guest Access is new in Teams.</span></span> <span data-ttu-id="dcf80-105">これは、ユーザーからの要望が最も強かった機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="dcf80-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="dcf80-106">Microsoft では、継続してこの機能を強化する作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-106">We’re still working on it, enhancing its capabilities.</span></span> <span data-ttu-id="dcf80-107">ゲスト アクセスの機能の開発状況に付いていくための方法と、その機能に関する意見や要望を提出するための方法を、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-107">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>
- <span data-ttu-id="dcf80-108">ゲスト アクセスに関して問題がある場合は、「[Microsoft Teams の既知の問題](Known-issues.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-108">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="dcf80-109">今後実装される新機能や更新された機能については、「[Teams のロードマップ](https://aka.ms/teamsroadmap)」で見つけてください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-109">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="dcf80-110">ご要望については、「[Teams UserVoice](https://aka.ms/TeamsUserVoice)」でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-110">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="dcf80-111">下にある [コメント] セクションでお客様ご自身のエクスペリエンスを共有してください。</span><span class="sxs-lookup"><span data-stu-id="dcf80-111">Share your experience in the Comments section below.</span></span>


<span data-ttu-id="dcf80-112">Microsoft Teams でのゲスト アクセスにより、組織内のチームは組織外の人にチームおよびチャネルへのアクセス権を付与することで、それらの人と共同作業することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="dcf80-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> 

<span data-ttu-id="dcf80-113">ゲスト アクセスは、Office 365 Business Premium、Office 365 Enterprise、Office 365 Education のすべてのサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dcf80-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="dcf80-114">追加の Office 365 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="dcf80-114">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="dcf80-115">ゲスト アクセスは Microsoft Teams ではテナントレベルの設定であり、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="dcf80-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span>


<span data-ttu-id="dcf80-116">ゲストとは、従業員、学生または組織の一員ではないユーザーを指します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-116">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="dcf80-117">ゲストは組織内での学校アカウントまたは職場アカウントを持ちません。</span><span class="sxs-lookup"><span data-stu-id="dcf80-117">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="dcf80-118">たとえば、ゲストにはパートナー、製造元、供給元、コンサルタントなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-118">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="dcf80-119">Azure Active Directory に対応する電子メール アドレス、または Office 365 の職場または学校アカウントを持つユーザーのみをゲスト ユーザーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-119">Only users who have an email address corresponding to an Azure Active Directory or Office 365 work or school account can be added as a guest user.</span></span>
  
       

<span data-ttu-id="dcf80-120">Teams では、企業データを完全に制御して保持しながら、チーム、ドキュメント、リソース、チャット、アプリケーションへの外部アクセスをパートナーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="dcf80-120">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span>

<span data-ttu-id="dcf80-121">Teams は、Office 365 グループに基づき構築されており、Office 365 グループの共有資産への新しいアクセス方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="dcf80-121">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="dcf80-122">Teams は、グループ/チーム メンバー間の常設チャットに最適なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="dcf80-122">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="dcf80-123">Office 365 グループは、SharePoint サイトや Power BI ダッシュボードなどの一連の共有チーム資産を利用するために、クロス アプリケーションのメンバーシップを提供し、チームが効果的かつ安全にコラボレーションできるようにするサービスです。</span><span class="sxs-lookup"><span data-stu-id="dcf80-123">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span>

    

## <a name="more-information"></a><span data-ttu-id="dcf80-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dcf80-124">More information</span></span>

 
  
    
  [<span data-ttu-id="dcf80-125">Microsoft Teams のサポート リソース</span><span class="sxs-lookup"><span data-stu-id="dcf80-125">Support resources for Microsoft Teams</span></span>](support-resources.md)  
 
  

    

  
|  |  |
|---------|---------|
| <span data-ttu-id="dcf80-126">Deep Dive into Guest Access (ゲスト アクセスの詳細)</span><span class="sxs-lookup"><span data-stu-id="dcf80-126">Deep Dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="dcf80-127">Microsoft Teams でのゲスト アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="dcf80-127">Enabling Guest Access in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/7T54KmlIHQk" frameborder="0" allowfullscreen></iframe>   |
 | <span data-ttu-id="dcf80-128">Microsoft Teams でのゲストの追加</span><span class="sxs-lookup"><span data-stu-id="dcf80-128">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

