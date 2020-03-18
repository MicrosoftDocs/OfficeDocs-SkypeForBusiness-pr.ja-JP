---
title: Skype for Business のオンプレミス環境から Teams にアップグレードする - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business のオンプレミス環境から Teams にアップグレードする際の考慮事項。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4957b22b7fe00ed756c1e81c6bb7c8e2e982720f
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706677"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="8e2b9-103">Skype for Business オンプレミスから Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8e2b9-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="8e2b9-104">![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="8e2b9-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8e2b9-105">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="8e2b9-106">続行する前に、次の作業が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="8e2b9-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="8e2b9-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="8e2b9-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="8e2b9-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="8e2b9-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="8e2b9-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="8e2b9-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="8e2b9-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="8e2b9-114">Skype for Business Server または Microsoft Lync をオンプレミスで展開していて、組織が Teams にアップグレードする必要がある場合は、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="8e2b9-115">Office 365 テナントでハイブリッド接続を設定する必要があり、ユーザーを Teams に段階的に移行する場合は、共存の要件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-115">You need to set up hybrid connectivity with your Office 365 tenant, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="8e2b9-116">Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="8e2b9-117">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="8e2b9-118">アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="8e2b9-119">手順 1: ハイブリッド接続の構成</span><span class="sxs-lookup"><span data-stu-id="8e2b9-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="8e2b9-120">オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="8e2b9-121">まず、「 [ハイブリッド接続のプラン](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」をご覧になり、「[ハイブリッド接続の構成](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」で説明されているタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="8e2b9-122">手順 2: 移行中の共存モードを設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="8e2b9-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="8e2b9-123">Skype for Business、Teams クライアント、およびユーザーの間の共存と相互運用性は、Teams のアップグレード モードによって規定されます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="8e2b9-124">既定では、組織はアイランド モードになっており、ユーザーは Teams と Skype for Business の両方を併用できます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="8e2b9-125">Teams に移行する組織にとって、最終的にはすべてのユーザーを TeamsOnly モードにすることが目標ですが、TeamsOnly (またはその他のモード) を全員に同時に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="8e2b9-126">ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用するという選択肢があり、こうすることで、TeamsOnly モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="8e2b9-127">Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="8e2b9-128">ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="8e2b9-129">ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="8e2b9-130">同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="8e2b9-131">組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="8e2b9-132">詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="8e2b9-133">手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する</span><span class="sxs-lookup"><span data-stu-id="8e2b9-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="8e2b9-134">最終的には、ユーザーを TeamsOnly モードに移動します。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="8e2b9-135">現在のオンプレミス環境によっては、追加の手順がいくつか必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-135">This might involve one or two steps depending on your current on-premises environment.</span></span>  

<span data-ttu-id="8e2b9-136">詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 



## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="8e2b9-137">電話システムと Teams のアップグレード</span><span class="sxs-lookup"><span data-stu-id="8e2b9-137">Phone System and Teams upgrade</span></span>

<span data-ttu-id="8e2b9-138">Skype for Business の展開を通話プランを備えた電話システムに移行する場合、Microsoft は公衆交換電話網 (PSTN) プロバイダーになります。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-138">If you are transitioning your Skype for Business deployment to Phone System with Calling Plans, Microsoft will be your public switched telephone network (PSTN) provider.</span></span> <span data-ttu-id="8e2b9-139">電話番号の移植を完了したことを前提としています。ユーザーを Teams にアップグレードすると、着信 PSTN 通話が Teams に自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-139">Assuming that you've completed the phone number porting--upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="8e2b9-140">Skype for Business の展開を電話システムに移行しているが、通話プランを使用していない場合は、エンタープライズ VoIP 展開を Microsoft 電話システムのダイレクト ルーティングに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-140">If you are transitioning your Skype for Business deployment to Phone System but are not using Calling Plans, you  need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="8e2b9-141">詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e2b9-141">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>
