---
title: Skype for Business オンプレミス展開から Teams にアップグレードする場合の PSTN に関する考慮事項
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Skype for Business から Teams にアップグレードする場合の音声に関する考慮事項
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686433"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a><span data-ttu-id="f66f5-103">オンプレミスの Skype for Business から Teams にアップグレードする場合の PSTN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f66f5-103">PSTN considerations for upgrading to Teams from Skype for Business on-premises</span></span>

<span data-ttu-id="f66f5-104">この記事では、Teams にアップグレードする際の公衆交換電話網 (PSTN) に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-104">This article describes Public Switched Telephone Network (PSTN) considerations when upgrading to Teams.</span></span>   


<span data-ttu-id="f66f5-105">さらに、次の記事では、アップグレードの重要な概念と共存動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-105">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f66f5-106">Teams と Skype for Business の共存</span><span class="sxs-lookup"><span data-stu-id="f66f5-106">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="f66f5-107">共存モード - リファレンス</span><span class="sxs-lookup"><span data-stu-id="f66f5-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f66f5-108">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="f66f5-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - <span data-ttu-id="f66f5-109">Teams での電話システムの使用は、ユーザーが TeamsOnly モードの場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-109">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span>  <span data-ttu-id="f66f5-110">ユーザーがアイランド モードの場合、電話システムは Skype for Business でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-110">If the user is in Islands mode, Phone System is only supported with Skype for Business.</span></span> 
 > - <span data-ttu-id="f66f5-111">Skype for Business からの呼び出しの転送、チーム呼び出しグループ、委任の設定は移行されないので、Teams 用に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-111">Any call forwarding, team-call group, and delegation settings from Skype for Business are not migrated and will need to be re-recreated for Teams.</span></span>
 > - <span data-ttu-id="f66f5-112">Microsoft Teams クラウド音声機能の概要と、組織に最適な Microsoft 音声ソリューションの決定に役立つ情報については [、「Teams](cloud-voice-landing-page.md)音声ソリューションを計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-112">For a general overview of Microsoft Teams cloud voice features, and help deciding which Microsoft voice solution is right for your organization, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>


## <a name="pstn-calling-scenarios"></a><span data-ttu-id="f66f5-113">PSTN 通話のシナリオ</span><span class="sxs-lookup"><span data-stu-id="f66f5-113">PSTN calling scenarios</span></span>

<span data-ttu-id="f66f5-114">TeamsOnly モードに移行する場合、次の 4 つの呼び出しシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-114">There are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="f66f5-115">[Microsoft 通話プランを使用している Skype for Business Online のユーザー](#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-115">[A user in Skype for Business Online, with a Microsoft Calling Plan](#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="f66f5-116">アップグレードすると、このユーザーは Microsoft 通話プランを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-116">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span>

- <span data-ttu-id="f66f5-117">[Skype for Business Online のユーザー](#from-skype-for-business-online-with-on-premises-voice) で、オンプレミスの Skype for Business または Cloud Connector Edition を介して、オンプレミスの音声機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-117">[A user in Skype for Business Online, with on-premises voice functionality](#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="f66f5-118">このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-118">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="f66f5-119">[オンラインに移行](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)し、オンプレミスの PSTN 接続を維持するエンタープライズ VoIPオンプレミスの Skype for Business ユーザー。</span><span class="sxs-lookup"><span data-stu-id="f66f5-119">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity.</span></span>  <span data-ttu-id="f66f5-120">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-120">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="f66f5-121">[エンタープライズ VoIP を使用している Skype for Business オンプレミスのユーザー](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)のうち、オンラインに移行して、Microsoft 通話プランを使用するユーザー。</span><span class="sxs-lookup"><span data-stu-id="f66f5-121">[A user in Skype for Business on-premises with Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan.</span></span>  <span data-ttu-id="f66f5-122">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-122">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="f66f5-123">この記事では、概要のみを説明します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-123">This article provides a high-level overview only.</span></span> <span data-ttu-id="f66f5-124">詳細については、「[電話システムのダイレクト ルーティング](direct-routing-landing-page.md)」および「[通話プラン](calling-plan-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-124">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md) and [Calling Plans](calling-plan-landing-page.md).</span></span> 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a><span data-ttu-id="f66f5-125">Microsoft 通話プランを使用している Skype for Business Online からの場合</span><span class="sxs-lookup"><span data-stu-id="f66f5-125">From Skype for Business Online with Microsoft Calling Plans</span></span> 

<span data-ttu-id="f66f5-126">これは、音声が関係する最も簡単なアップグレード シナリオです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-126">This is the simplest upgrade scenario involving voice.</span></span> 

1. <span data-ttu-id="f66f5-127">ユーザーに Teams ライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-127">Make sure users have been assigned a Teams license.</span></span> <span data-ttu-id="f66f5-128">既定では、Microsoft 365 または Office 365 ライセンスを割り当てると、Teams は有効になっているので、Teams ライセンスを以前に無効にしない限り、アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f66f5-128">By default, when you assign a Microsoft 365 or Office 365 license, Teams is enabled, so unless you previously disabled the Teams license, no action should be necessary.</span></span>

2.  <span data-ttu-id="f66f5-129">ユーザーが既に電話番号を指定して Microsoft 通話プランを使用している場合に必要な変更は、そのユーザーに TeamsUpgradePolicy で TeamsOnly モードを割り当てることのみです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-129">If users already have a Microsoft Calling Plan with a phone number, the only required change is to assign the user TeamsOnly mode in TeamsUpgradePolicy.</span></span>  <span data-ttu-id="f66f5-130">TeamsOnly モードを割り当てる前は、着信 PSTN 通話はユーザーの Skype for Business クライアントに配信されます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-130">Prior to assigning TeamsOnly mode, incoming PSTN calls will land in the user’s Skype for Business client.</span></span> <span data-ttu-id="f66f5-131">TeamsOnly モードにアップグレードすると、着信 PSTN 通話はユーザーの Teams クライアントに配信されます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-131">After the upgrade to TeamsOnly mode, incoming PSTN calls will land in the user’s Teams client.</span></span>  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a><span data-ttu-id="f66f5-132">オンプレミス音声を使用している Skype for Business Online からの場合</span><span class="sxs-lookup"><span data-stu-id="f66f5-132">From Skype for Business Online with on-premises voice</span></span>

<span data-ttu-id="f66f5-133">このシナリオでは、ユーザーは既に Skype for Business Online を使用していますが、PSTN 接続はオンプレミスで、ハイブリッド モードかクラウド コネクタ エディションの Skype for Business Server を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f66f5-133">In this scenario, the user is already in Skype for Business Online, but their PSTN connectivity is on-premises, either using Skype for Business Server in hybrid mode or Cloud Connector Edition.</span></span> <span data-ttu-id="f66f5-134">PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーにダイレクト ルーティングを許可することを意味します。ダイレクト ルーティングでは、PSTN トランクは、オンプレミス セッション ボーダー コントローラー (SBC) を介して、クラウドのダイレクト ルーティング サービスに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-134">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing, in which PSTN trunks connect directly to the Direct Routing service in the cloud, via your on-premises Session Border Controller (SBC).</span></span>

<span data-ttu-id="f66f5-135">基本的なステップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-135">The basic steps are listed below.</span></span>  <span data-ttu-id="f66f5-136">ステップ 1 から 4 は、提案されている順序で並んでいますが、任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-136">Steps 1-4 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="f66f5-137">重要なのは、これらすべてをステップ 5 の前に完了する必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-137">The key is that all of these should be completed before Step 5.</span></span>

1. <span data-ttu-id="f66f5-138">テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-138">If you are setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather any existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="f66f5-139">ダイレクト ルーティング用にテナントを構成します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-139">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="f66f5-140">「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-140">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

3. <span data-ttu-id="f66f5-141">必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-141">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="f66f5-142">この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly モードにアップグレードする前にこれを行なっておくのが最善です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-142">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly mode.</span></span>

4. <span data-ttu-id="f66f5-143">選択したユーザーに音声移行の準備をします。</span><span class="sxs-lookup"><span data-stu-id="f66f5-143">Prepare select users for voice migration:</span></span> 
   - <span data-ttu-id="f66f5-144">必要に応じて、Teams ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-144">If necessary, assign the Teams license.</span></span>  <span data-ttu-id="f66f5-145">ユーザーが既に Skype for Business Online のオンプレミス音声を使用できているなら、そのユーザーは Microsoft 電話システムだけでなく、Skype for Business プラン 2 も所有しています。</span><span class="sxs-lookup"><span data-stu-id="f66f5-145">Assuming the user is already functional in Skype for Business Online on-premises voice, the user already has Skype for Business Plan 2 as well as Microsoft Phone System.</span></span> <span data-ttu-id="f66f5-146">両方のプラン (Skype for Business Online プラン 2 のライセンスを含む) を有効なままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-146">Leave both those plans enabled, including the Skype for Business Online Plan 2 license.</span></span>  
   - <span data-ttu-id="f66f5-147">目的の OnlineVoiceRoutingPolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-147">Assign the desired OnlineVoiceRoutingPolicy.</span></span> 

5. <span data-ttu-id="f66f5-148">これらのステップは相互に合うように調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-148">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="f66f5-149">Microsoft 365 または Office 365 では、ユーザーを TeamsOnly モード (Grant-CsTeamsUpgradePolicy) にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f66f5-149">In Microsoft 365 or Office 365, upgrade the user to TeamsOnly mode (Grant-CsTeamsUpgradePolicy).</span></span>
   - <span data-ttu-id="f66f5-150">SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-150">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span>


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a><span data-ttu-id="f66f5-151">エンタープライズ VoIP を使用している Skype for Business Server オンプレミスからダイレクト ルーティングに移行する場合</span><span class="sxs-lookup"><span data-stu-id="f66f5-151">From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing</span></span>

<span data-ttu-id="f66f5-152">このシナリオでは、ユーザーは Skype for Business オンプレミスにまだ所属しており、PSTN 接続もオンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-152">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="f66f5-153">PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーにダイレクト ルーティングを許可して、クラウドに移行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-153">Migrating these users to TeamsOnly mode with PSTN functionality means enabling them for Direct Routing and then moving the user to the cloud.</span></span> 
 
<span data-ttu-id="f66f5-154">基本的なステップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-154">The basic steps are listed below.</span></span>  <span data-ttu-id="f66f5-155">ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-155">Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="f66f5-156">重要なのは、これらすべてをステップ 6 の前に完了する必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-156">The key is that all of these should be completed before Step 6.</span></span>

1. <span data-ttu-id="f66f5-157">テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-157">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span>

2. <span data-ttu-id="f66f5-158">まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-158">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span>

3. <span data-ttu-id="f66f5-159">ダイレクト ルーティング用にテナントを構成します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-159">Configure your tenant for Direct Routing.</span></span> <span data-ttu-id="f66f5-160">「[ダイレクト ルーティングのテナントごとの構成の概要](#summary-of-per-tenant-configuration-of-direct-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-160">See [Summary of per-tenant configuration of Direct Routing](#summary-of-per-tenant-configuration-of-direct-routing).</span></span>

4. <span data-ttu-id="f66f5-161">必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-161">If desired, configure various Teams policies for these users (e.g. TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="f66f5-162">この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly アップグレードする前にこれを行なっておくのが最善です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-162">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span>

5. <span data-ttu-id="f66f5-163">必要に応じて、Microsoft 365 または Office 365 ライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f66f5-163">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span>  <span data-ttu-id="f66f5-164">ユーザーは、電話システムに加えて、Teams と Skype for Business Online プラン 2 の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-164">The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="f66f5-165">Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f66f5-165">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

6. <span data-ttu-id="f66f5-166">これらのステップは相互に合うように調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-166">Upgrade the user: These steps should be coordinated.</span></span> 

   - <span data-ttu-id="f66f5-167">オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-167">Using the on-premises Skype for Business tools, run Move-CsUser with -MoveToTeams switch.</span></span> <span data-ttu-id="f66f5-168">-MoveToTeams スイッチをサポートしていないバージョンの Skype for Business Server を使用している場合は、まず Move-CsUser を実行してから、テナントのリモート PowerShell か Teams 管理コンソールで、TeamsOnly モードを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-168">If you are using a version of Skype for Business Server that does not support the -MoveToTeams switch, first run Move-CsUser and then assign TeamsOnly mode in tenant remote PowerShell or Teams Admin Console.</span></span>

   - <span data-ttu-id="f66f5-169">SBC で、通話をオンプレミスの仲介サーバーではなくダイレクト ルーティングに送信することにより、音声ルーティングが着信通話を許可するように構成します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-169">On the SBC, configure voice routing to enable incoming calls by sending calls to Direct Routing instead of to the on-premises Mediation Server.</span></span> 

   - <span data-ttu-id="f66f5-170">Microsoft 365 または Office 365 の場合: 関連する OnlineVoiceRoutingPolicy を割り当て、発信通話を有効にする。</span><span class="sxs-lookup"><span data-stu-id="f66f5-170">In Microsoft 365 or Office 365: Assign the relevant OnlineVoiceRoutingPolicy to enable outgoing calls.</span></span> 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a><span data-ttu-id="f66f5-171">エンタープライズ VoIP を使用している Skype for Business Server オンプレミスから Microsoft 通話プランに移行する場合</span><span class="sxs-lookup"><span data-stu-id="f66f5-171">From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan</span></span>

<span data-ttu-id="f66f5-172">このシナリオでは、ユーザーは Skype for Business オンプレミスにまだ所属しており、PSTN 接続もオンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-172">In this scenario, the user is still homed in Skype for Business on-premises, and their PSTN connectivity is also on-premises.</span></span> <span data-ttu-id="f66f5-173">PSTN 機能を使用してこれらのユーザーを TeamsOnly モードに移行することは、そのユーザーをクラウドに移行して、そのユーザーの番号を元の通信事業者から Microsoft 通話プランに移植するか、そのユーザーに新しい番号を割り当てるかを意味します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-173">Migrating these users to TeamsOnly mode with PSTN functionality means moving the user to the cloud and either porting their number from the old carrier to a Microsoft Calling plan or assigning the user a new number.</span></span> 

<span data-ttu-id="f66f5-174">基本的なステップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-174">The basic steps are listed below.</span></span><span data-ttu-id="f66f5-175">ステップ 1 から 5 は、提案されている順序で並んでいますが、任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-175">  Steps 1-5 are listed in the suggested sequence, but they can be done in any order.</span></span> <span data-ttu-id="f66f5-176">重要なのは、これらすべてをステップ 6 の前に完了する必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-176">The key is that all of these should be completed before Step 6.</span></span> 

1. <span data-ttu-id="f66f5-177">テナント全体のポリシーを Skype for Business のモードの 1 つに設定する予定の場合は、前述のように既存のアイランド ユーザーにアイランド モードを明示的に割り当てることにより、それらのユーザーを必ず grandfather 化してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-177">If you will be setting the tenant-wide policy to one of the Skype for Business modes, be sure to grandfather existing Islands users by explicitly assigning them Islands mode, as previously described.</span></span> 

2. <span data-ttu-id="f66f5-178">まだ構成していない場合は、[Skype for Business Hybrid 用に組織を構成](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-178">If you haven’t already done so, [configure the organization for Skype for Business hybrid](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).</span></span> 

3. <span data-ttu-id="f66f5-179">必要に応じて、これらのユーザーに対してさまざまな Teams ポリシーを構成します (TeamsMessagingPolicy や TeamsMeetingPolicy など)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-179">If desired, configure various Teams policies for these users (for example, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.).</span></span> <span data-ttu-id="f66f5-180">この操作はいつでも行えますが、ユーザーをアップグレードした時にユーザーが確実に正しく構成されているようにするには、ユーザーを TeamsOnly アップグレードする前にこれを行なっておくのが最善です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-180">This can be done at any time, but if you want to ensure that users have the correct configuration when they are upgraded, it’s best to do this before the user is upgraded to TeamsOnly.</span></span> 

4. <span data-ttu-id="f66f5-181">必要に応じて、Microsoft 365 または Office 365 ライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f66f5-181">Assign the Microsoft 365 or Office 365 licenses if necessary.</span></span><span data-ttu-id="f66f5-182">ユーザーは、電話システムに加えて、Teams と Skype for Business Online プラン 2 の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-182">  The user should have both Teams and Skype for Business Online Plan 2, as well as Phone System.</span></span> <span data-ttu-id="f66f5-183">Skype for Business Online プラン 2 が無効になっている場合は、もう一度有効にします。</span><span class="sxs-lookup"><span data-stu-id="f66f5-183">If the Skype for Business Online Plan 2 is disabled, re-enable it.</span></span>  

5. <span data-ttu-id="f66f5-184">ユーザーの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-184">Get phone numbers for your users.</span></span> <span data-ttu-id="f66f5-185">(詳細については、「[組織の電話番号を管理する](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-185">(For details see [Manage phone numbers for your organization](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)</span></span>

   - <span data-ttu-id="f66f5-186">番号を再利用する場合は、通信事業者に移植要求を提出します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-186">If you will be re-using the numbers, submit a porting request to your carrier.</span></span>  
   - <span data-ttu-id="f66f5-187">または、直接 Microsoft から新しい番号を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-187">Alternatively, you can acquire new numbers directly from Microsoft.</span></span> 

6. <span data-ttu-id="f66f5-188">ユーザーをアップグレードし、必要に応じて LineUri を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f66f5-188">Upgrade the user and if needed assign LineUri.</span></span> <span data-ttu-id="f66f5-189">オンプレミスの Skype for Business ツールを使用し、-MoveToTeams スイッチを指定して Move-CsUser を実行します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-189">Using the on-premises Skype for Business tools, run Move-CsUser with the -MoveToTeams switch.</span></span>  

    - <span data-ttu-id="f66f5-190">番号を Microsoft に移植する場合は、この操作のタイミングを調整して、ポートが発生するときに発生するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-190">If you are porting numbers to Microsoft, you should coordinate the timing of this operation to occur when the port occurs.</span></span> 

    - <span data-ttu-id="f66f5-191">Microsoft から新しい番号を取得して使用する場合は、そのユーザーの LineUri を変更することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-191">If you are using new numbers from Microsoft, you’ll need to change the LineUri for the user.</span></span> <span data-ttu-id="f66f5-192">これは、ユーザーが Set-CsOnlineVoiceUser を使用してオンラインに移動した後に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-192">This must be done after the user is moved online using Set-CsOnlineVoiceUser.</span></span>  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a><span data-ttu-id="f66f5-193">ダイレクト ルーティングのテナントごとの構成の概要</span><span class="sxs-lookup"><span data-stu-id="f66f5-193">Summary of per-tenant configuration of Direct Routing</span></span> 

1. <span data-ttu-id="f66f5-194">[このリスト](direct-routing-border-controllers.md)を確認して、ご利用のセッション ボーダー コントローラー (SBC) がダイレクト ルーティングでサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f66f5-194">Ensure that your Session Border Controller (SBC) is supported with Direct Routing by reviewing [this list](direct-routing-border-controllers.md).</span></span> <span data-ttu-id="f66f5-195">正しいバージョンのファームウェアを使用していることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-195">You must also ensure that you have correct version of firmware.</span></span>  

2. <span data-ttu-id="f66f5-196">オンプレミスの SBC と Teams のダイレクト ルーティング サービスをペアリングします。</span><span class="sxs-lookup"><span data-stu-id="f66f5-196">Pair your on-premises SBC with the Teams Direct Routing service.</span></span> <span data-ttu-id="f66f5-197">詳細については、「[SBC を電話システムのダイレクト ルーティング サービスにペアリングする](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-197">For details, see [Pair the SBC to the Direct Routing service of Phone System](direct-routing-configure.md).</span></span> 

3. <span data-ttu-id="f66f5-198">この構成は、実質的にオンプレミス構成のミラーです。</span><span class="sxs-lookup"><span data-stu-id="f66f5-198">This configuration is essentially a mirror of the on-premises configuration.</span></span> <span data-ttu-id="f66f5-199">オンライン構成は次の内容で構成されます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-199">The online configuration consists of:</span></span> 
   - <span data-ttu-id="f66f5-200">OnlineVoiceRoutingPolicy (Skype for Business Online のユーザーを移行する場合はオンプレミスの VoiceRoutingPolicy に基づき、エンタープライズ VoIP を使用してオンプレミスからユーザーを移行する場合は VoicePolicy に基づく)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-200">OnlineVoiceRoutingPolicy (based on the on-premises VoiceRoutingPolicy if migrating users from Skype for Business   Online, and based on VoicePolicy if migrating users from on-premises with Enterprise Voice).</span></span>
   - <span data-ttu-id="f66f5-201">OnlinePSTNUsage オブジェクト (オンプレミスの PSTN 使用法に基づく)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-201">OnlinePSTNUsage objects (based on on-premises PSTN usage).</span></span> 
   - <span data-ttu-id="f66f5-202">OnlineVoiceRoute オブジェクト (オンプレミスの VoiceRoute に基づく)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-202">OnlineVoiceRoute objects (based on-premises VoiceRoute).</span></span> 

<span data-ttu-id="f66f5-203">詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f66f5-203">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a><span data-ttu-id="f66f5-204">移行時に EnterpriseVoiceEnabled プロパティを管理する</span><span class="sxs-lookup"><span data-stu-id="f66f5-204">Manage EnterpriseVoiceEnabled property during migration</span></span> 

<span data-ttu-id="f66f5-205">ダイレクト ルーティングや Microsoft 通話プランを使用する場合、ユーザーは、PSTN 機能を利用できるようにするため、Azure AD で EnterpriseVoiceEnabled=true に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-205">Whether using Direct Routing or a Microsoft Calling plan, a user must have EnterpriseVoiceEnabled=true in Azure AD for the user to have PSTN functionality.</span></span>  <span data-ttu-id="f66f5-206">EnterpriseVoiceEnabled (EV-enabled) は、オンプレミスのディレクトリとクラウドの両方に存在するプロパティです (ポリシーではない)。</span><span class="sxs-lookup"><span data-stu-id="f66f5-206">EnterpriseVoiceEnabled (“EV-enabled”) is a property (not a policy) that exists in both an on-premises directory and in the cloud.</span></span> <span data-ttu-id="f66f5-207">Teams で重要なのは、クラウドの値です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-207">The value in the cloud is what matters for Teams.</span></span>  <span data-ttu-id="f66f5-208">EV-enabled がどのようにして true に設定されるかの正確なロジックは、次のシナリオによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-208">The exact logic for how EV-enabled gets set to true depends on the following scenario:</span></span> 

- <span data-ttu-id="f66f5-209">ユーザーがオンプレミスの Skype for Business Server で EV-enabled になっており、Move-CsUser を使用してそのユーザーをクラウドに移行する前に電話システムのライセンスがそのユーザーに割り当てられている場合、そのオンライン ユーザーは EV-enabled=true でプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="f66f5-209">If the user is EV-enabled in on-premises Skype for Business Server and a Phone System license is assigned to the user prior to moving the user to the cloud with Move-CsUser, the online user will be provisioned with EV-enabled=true.</span></span> 

- <span data-ttu-id="f66f5-210">既存の TeamsOnly または Skype for Business Online ユーザーに電話システムのライセンスが割り当てられる場合は、EV-enabled は既定では true に設定されません。</span><span class="sxs-lookup"><span data-stu-id="f66f5-210">If an existing TeamsOnly or Skype for Business Online user is assigned a Phone System license, EV-enabled is not set to true by default.</span></span>  <span data-ttu-id="f66f5-211">オンプレミスのユーザーが、電話システムのライセンスを割り当てる前にクラウドに移行される場合も同様です。</span><span class="sxs-lookup"><span data-stu-id="f66f5-211">This also is the case if an on-premises user is moved to the cloud prior to assigning the Phone System license.</span></span> <span data-ttu-id="f66f5-212">どちらの場合も、管理者は次のコマンドレットを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f66f5-212">In either case, the admin must specify the following cmdlet:</span></span> 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a><span data-ttu-id="f66f5-213">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f66f5-213">Related links</span></span>

[<span data-ttu-id="f66f5-214">Teams の音声ソリューションを計画する</span><span class="sxs-lookup"><span data-stu-id="f66f5-214">Plan your Teams voice solution</span></span>](cloud-voice-landing-page.md)

[<span data-ttu-id="f66f5-215">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="f66f5-215">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f66f5-216">Skype for Business Server と Microsoft 365 または Office 365 間のハイブリッド接続を構成する</span><span class="sxs-lookup"><span data-stu-id="f66f5-216">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f66f5-217">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="f66f5-217">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f66f5-218">共存およびアップグレードを設定する</span><span class="sxs-lookup"><span data-stu-id="f66f5-218">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f66f5-219">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f66f5-219">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f66f5-220">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="f66f5-220">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

