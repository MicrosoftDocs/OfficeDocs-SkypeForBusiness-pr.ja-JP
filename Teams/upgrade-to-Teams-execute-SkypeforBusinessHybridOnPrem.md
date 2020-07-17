---
title: Skype for Business オンプレミスから Teams にアップグレードする
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business オンプレミスの展開から組織を Microsoft Teams にアップグレードする方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17420c93c883054d36c4ae2e1b323be9e589a2c2
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158675"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="57b2b-103">Skype for Business オンプレミスから Teams にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="57b2b-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="57b2b-104">![展開と実装に重点を置いた、アップグレードのフロー図](media/upgrade-banner-deployment.png "「展開と実装」段階が強調表示された、アップグレード行程の各段階")</span><span class="sxs-lookup"><span data-stu-id="57b2b-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="57b2b-105">この記事は、お客様のアップグレード手順における展開と実装の段階の一部を取り上げています。</span><span class="sxs-lookup"><span data-stu-id="57b2b-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="57b2b-106">続行する前に、次の作業が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="57b2b-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="57b2b-107">プロジェクトの関係者をリスト化した</span><span class="sxs-lookup"><span data-stu-id="57b2b-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="57b2b-108">プロジェクトの対象範囲を定義した</span><span class="sxs-lookup"><span data-stu-id="57b2b-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="57b2b-109">Skype for Business と Teams の共存と相互運用を理解した</span><span class="sxs-lookup"><span data-stu-id="57b2b-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="57b2b-110">アップグレードの手順を選択した</span><span class="sxs-lookup"><span data-stu-id="57b2b-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="57b2b-111">環境を準備した</span><span class="sxs-lookup"><span data-stu-id="57b2b-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="57b2b-112">組織を準備した</span><span class="sxs-lookup"><span data-stu-id="57b2b-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="57b2b-113">パイロットを実施した</span><span class="sxs-lookup"><span data-stu-id="57b2b-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="57b2b-114">Skype for Business Server または Microsoft Lync をオンプレミスで展開していて、組織が Teams にアップグレードする必要がある場合は、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="57b2b-115">ユーザーを段階的にチームに移行する場合は、Microsoft 365 または Office 365 組織とのハイブリッド接続をセットアップして、共存の要件を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b2b-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="57b2b-116">Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。それ以降、アクセスとサポートが終了します。</span><span class="sxs-lookup"><span data-stu-id="57b2b-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="57b2b-117">移行によるメリットを最大限に高め、アップグレード実施のための時間を組織で十分確保できるよう、Microsoft Teams への移行をすぐに開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57b2b-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="57b2b-118">アップグレードが成功すると、技術面およびユーザーの準備が整ったことになります。Microsoft Teams への移行を進める際には、必ずこのガイドを活用してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="57b2b-119">手順 1: ハイブリッド接続の構成</span><span class="sxs-lookup"><span data-stu-id="57b2b-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="57b2b-120">オンプレミスのユーザーを Teams にアップグレードするため主な前提条件は、Skype for Business Server のオンプレミス展開にハイブリッド接続を構成することです。</span><span class="sxs-lookup"><span data-stu-id="57b2b-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="57b2b-121">まず、「 [ハイブリッド接続のプラン](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」をご覧になり、「[ハイブリッド接続の構成](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)」で説明されているタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="57b2b-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="57b2b-122">手順 2: 移行中の共存モードを設定する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="57b2b-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="57b2b-123">Skype for Business、Teams クライアント、およびユーザーの間の共存と相互運用性は、Teams のアップグレード モードによって規定されます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="57b2b-124">既定では、組織はアイランド モードになっており、ユーザーは Teams と Skype for Business の両方を併用できます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="57b2b-125">Teams に移行する組織にとって、最終的にはすべてのユーザーを TeamsOnly モードにすることが目標ですが、TeamsOnly (またはその他のモード) を全員に同時に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="57b2b-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="57b2b-126">ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用するという選択肢があり、こうすることで、TeamsOnly モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="57b2b-127">Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。</span><span class="sxs-lookup"><span data-stu-id="57b2b-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="57b2b-128">ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="57b2b-129">ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="57b2b-130">同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="57b2b-131">組織の要件によりますが、組織が選択したアップグレード パスに基づいて適切な共存モードを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="57b2b-132">詳細については、「[Migration and interoperability guidance for organizations using Teams together with Skype for Business (Teams を Skype for Business と併用する組織向けの移行と相互運用に関するガイダンス)](migration-interop-guidance-for-teams-with-skype.md)」および「[共存およびアップグレードの設定 (Setting your coexistence and upgrade settings)](https://aka.ms/SkypeToTeams-SetCoexistence)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="57b2b-133">手順 3: ユーザーを Skype for Business オンプレミスから TeamsOnly に移動する</span><span class="sxs-lookup"><span data-stu-id="57b2b-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="57b2b-134">最終的には、ユーザーを TeamsOnly モードに移動します。</span><span class="sxs-lookup"><span data-stu-id="57b2b-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="57b2b-135">これには、オンプレミス環境に応じて、1つまたは2つの手順が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="57b2b-135">This might involve one or two steps depending on your on-premises environment.</span></span>  

<span data-ttu-id="57b2b-136">詳細については、「 [オンプレミスとクラウドの間でユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)」と「[オンプレミスから Teams にユーザーを移動する](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a><span data-ttu-id="57b2b-137">手順 4: ハイブリッドを無効にしてクラウドへの移行を完了する</span><span class="sxs-lookup"><span data-stu-id="57b2b-137">Step 4: Disable hybrid to complete your migration to the cloud</span></span>

<span data-ttu-id="57b2b-138">オンプレミスからクラウドにすべてのユーザーを移行した後で、オンプレミスの Skype for Business 展開を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="57b2b-138">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="57b2b-139">詳細については、「ハイブリッドを無効にする」を参照して[クラウドへの移行を完了](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-139">For more information, see [Disable hybrid to complete migration to the cloud](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md).</span></span>


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="57b2b-140">電話システムと PSTN の接続オプション</span><span class="sxs-lookup"><span data-stu-id="57b2b-140">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="57b2b-141">ユーザーが TeamsOnly モードになった後、Teams での電話システムはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57b2b-141">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="57b2b-142">(ユーザーが諸島モードの場合、電話システムは Skype for Business でのみサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="57b2b-142">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span> 

### <a name="pstn-connectivity-options"></a><span data-ttu-id="57b2b-143">PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="57b2b-143">PSTN connectivity options</span></span>

<span data-ttu-id="57b2b-144">公衆交換電話網 (PSTN) の接続オプションを検討するときは、次の2つのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="57b2b-144">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business on premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="57b2b-145">エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。</span><span class="sxs-lookup"><span data-stu-id="57b2b-145">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and using a Microsoft Calling plan.</span></span> <span data-ttu-id="57b2b-146">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b2b-146">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>  <span data-ttu-id="57b2b-147">詳細については、「 [Skype For Business Server on on-premises、エンタープライズ voip、Microsoft 通話プラン」を](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-147">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).</span></span>

- <span data-ttu-id="57b2b-148">エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザーのうち、オンラインに移行して、オンプレミスの PSTN 接続を維持するユーザー。</span><span class="sxs-lookup"><span data-stu-id="57b2b-148">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and keeping on-premises PSTN connectivity.</span></span> <span data-ttu-id="57b2b-149">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b2b-149">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> <span data-ttu-id="57b2b-150">詳細については、「 [Skype For Business Server のオンプレミスのエンタープライズ Voip から直接ルーティングする](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b2b-150">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).</span></span>

