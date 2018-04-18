---
title: Microsoft Teams 用の Office 365 ライセンス
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2018
ms.topic: article
audience: Admin
ms.service: msteams
ms.reviewer: dearbeen, ninadara
localization_priority: Normal
description: さまざまな Office 365 ライセンスについて、どのライセンスで Microsoft Teams のユーザーが有効になるかについて、およびライセンスを有効にしたり無効にしたりする方法について説明します。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d9d3ae6a085881a3965a4e25a101172c5874b14
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a><span data-ttu-id="af4ff-103">Microsoft Teams 用の Office 365 ライセンス</span><span class="sxs-lookup"><span data-stu-id="af4ff-103">Office 365 licensing for Microsoft Teams</span></span>
========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="af4ff-104">以下の Office 365 サブスクリプションでは、チームのユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="af4ff-104">The following Office 365 subscriptions enable users for Teams.</span></span>

|<span data-ttu-id="af4ff-105">Small Business プラン</span><span class="sxs-lookup"><span data-stu-id="af4ff-105">Small Business Plans</span></span>  |<span data-ttu-id="af4ff-106">Enterprise プラン</span><span class="sxs-lookup"><span data-stu-id="af4ff-106">Enterprise Plans</span></span>  |<span data-ttu-id="af4ff-107">Education プラン</span><span class="sxs-lookup"><span data-stu-id="af4ff-107">Education Plans</span></span>  |<span data-ttu-id="af4ff-108">開発計画</span><span class="sxs-lookup"><span data-stu-id="af4ff-108">Developer Plans</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="af4ff-109">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="af4ff-109">Office 365 Business Essentials</span></span>     |<span data-ttu-id="af4ff-110">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="af4ff-110">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="af4ff-111">Office 365 Education</span><span class="sxs-lookup"><span data-stu-id="af4ff-111">Office 365 Education</span></span> |<span data-ttu-id="af4ff-112">Office 365 開発者</span><span class="sxs-lookup"><span data-stu-id="af4ff-112">Office 365 Developer</span></span>     |
|<span data-ttu-id="af4ff-113">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="af4ff-113">Office 365 Business Premium</span></span>     |<span data-ttu-id="af4ff-114">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="af4ff-114">Office 365 Enterprise E3</span></span>         |<span data-ttu-id="af4ff-115">Office 365 Education Plus</span><span class="sxs-lookup"><span data-stu-id="af4ff-115">Office 365 Education Plus</span></span>         |      |
|<span data-ttu-id="af4ff-116">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="af4ff-116">Office 365 Enterprise F1</span></span>     |<span data-ttu-id="af4ff-117">Office 365 Enterprise E4 (廃止)</span><span class="sxs-lookup"><span data-stu-id="af4ff-117">Office 365 Enterprise E4 (retired)</span></span>         |<span data-ttu-id="af4ff-118">Office 365 Education E3 (廃止)</span><span class="sxs-lookup"><span data-stu-id="af4ff-118">Office 365 Education E3 (retired)</span></span>         |  |
|     |<span data-ttu-id="af4ff-119">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="af4ff-119">Office 365 Enterprise E5</span></span>         |<span data-ttu-id="af4ff-120">Office 365 Education E5</span><span class="sxs-lookup"><span data-stu-id="af4ff-120">Office 365 Education E5</span></span>  | 



> [!NOTE]
> <span data-ttu-id="af4ff-121">Teams は非営利団体でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="af4ff-121">Teams is also available for non-profit organizations.</span></span> <span data-ttu-id="af4ff-122">政府機関のライセンスは現時点ではサポートされていませんが、将来的にサポートするための調査が実施されています。</span><span class="sxs-lookup"><span data-stu-id="af4ff-122">Government licensing is not currently supported but is being investigated for future support.</span></span>
        


<span data-ttu-id="af4ff-123">チームの中核的な機能、という点では、Office 365 サブスクリプションの違いはありません。</span><span class="sxs-lookup"><span data-stu-id="af4ff-123">In terms of Teams core functionalities, there are no differences between the  Office 365 subscriptions.</span></span> <span data-ttu-id="af4ff-124">コンプライアンス機能の利用可否は適切なサブスクリプション レベルに依存します。</span><span class="sxs-lookup"><span data-stu-id="af4ff-124">The availability of the compliance capabilities does rely on the correct subscription level.</span></span> <span data-ttu-id="af4ff-125">詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af4ff-125">To learn more, read [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>

<span data-ttu-id="af4ff-126">**クラウドの音声機能**: オーディオ会議は、組織は購入して、ダイヤルイン会議を設定する各ユーザーに電話会議のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af4ff-126">**Cloud voice features**: For Audio Conferencing, your organization will need to buy and assign an Audio Conferencing license to each user who will be setting up dial-in meetings.</span></span> <span data-ttu-id="af4ff-127">計画を呼び出すには、各ユーザーの電話システムと、国内または国内と国際の計画を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="af4ff-127">For Calling Plans, each user will need a Phone System plus a Domestic or Domestic and International Calling Plan.</span></span> <span data-ttu-id="af4ff-128">詳細については、 [Skype](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af4ff-128">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="af4ff-129">サポートされているすべてのサブスクリプション プランは、Teams の Web クライアント、デスクトップ クライアント、モバイル アプリにアクセスする資格を持ちます。</span><span class="sxs-lookup"><span data-stu-id="af4ff-129">All supported subscription plans are eligible for access to the Teams web client, desktop clients, and mobile apps.</span></span>

<span data-ttu-id="af4ff-130">Teams はスタンドアロンのサービスとして利用できません。</span><span class="sxs-lookup"><span data-stu-id="af4ff-130">Teams isn't available as a standalone service.</span></span>

> [!TIP]
> <span data-ttu-id="af4ff-131">ユーザー レベルのライセンスを管理するには、[マイクロソフトのチームへのユーザー アクセスの管理](user-access.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af4ff-131">To manage user-level licensing, see [Manage user access to Microsoft Teams](user-access.md).</span></span>
