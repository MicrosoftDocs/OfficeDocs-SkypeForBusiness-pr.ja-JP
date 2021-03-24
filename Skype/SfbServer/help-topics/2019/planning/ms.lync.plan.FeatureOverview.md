---
title: 機能の概要 (計画ツール)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server Planning Tool
ms.openlocfilehash: 4084d263a693a064e06a814d2fab4542ca3142c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093325"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="4b023-103">機能の概要 (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="4b023-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="4b023-104">Skype for Business Server Planning Tool</span><span class="sxs-lookup"><span data-stu-id="4b023-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="4b023-105">計画ツールの **[中央サイト** ] ページを使用して、Skype for Business Server 展開を設計できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="4b023-106">2 つの集中展開または分散展開を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="4b023-107">一元的な展開には、組織内のすべての Skype for Business ユーザーを含む中央サイトが 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="4b023-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="4b023-108">分散展開には複数の中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="4b023-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="4b023-109">Skype for Business Server を複数の中央サイトに展開する場合は、計画ツールに各中央サイトのユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b023-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="4b023-110">中央サイトの定義を完了するには、まず次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b023-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="4b023-111">**サイト名** 中央サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b023-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="4b023-112">**ユーザー数** 中央サイトに拠点を持つブランチ サイトのユーザーを含む、ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b023-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="4b023-113">**クラウド ホーム ユーザー** Skype for Business Online から中央サイトに入っているユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b023-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="4b023-114">UI 要素</span><span class="sxs-lookup"><span data-stu-id="4b023-114">UI Elements</span></span>

<span data-ttu-id="4b023-115">残りの要素には、Get **Started** ウィザードで提示された質問に対して提供した回答が入力されています。またはウィザードをスキップした場合は、計画ツールによって自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b023-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="4b023-116">オンライン コラボレーション</span><span class="sxs-lookup"><span data-stu-id="4b023-116">Online Collaboration</span></span>

 <span data-ttu-id="4b023-117">**オンライン コラボレーションには** 、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b023-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="4b023-118">**IM and Presence**</span><span class="sxs-lookup"><span data-stu-id="4b023-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="4b023-119">インスタント メッセージング (IM) を使用すると、ユーザーはテキスト ベースのメッセージを使用して、コンピューター上でリアルタイムで相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="4b023-120">2 パーティとマルチパーティの両方の IM セッションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4b023-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="4b023-121">プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="4b023-122">ユーザーのプレゼンス状態は、ユーザーがオンラインであるかどうかを他のユーザーが判断し、ユーザーに最も適切に連絡する方法を判断するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="4b023-123">たとえば、会議に参加しているユーザーは、電子メールで最も良い連絡を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b023-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="4b023-124">**音声ビデオ会議**</span><span class="sxs-lookup"><span data-stu-id="4b023-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="4b023-125">音声/ビデオ (音声ビデオ) 会議では、リアルタイムの音声およびビデオ会議を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4b023-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="4b023-126">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="4b023-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="4b023-127">ダイヤルイン会議を使用すると、PSTN の電話から音声ビデオに参加できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="4b023-128">ダイヤルイン会議では、会議アテンダントおよび会議アナウンス サービス アプリケーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b023-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="4b023-129">**Web 会議**</span><span class="sxs-lookup"><span data-stu-id="4b023-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="4b023-130">Web 会議を使用すると、ファイアウォールの内部および外部のエンタープライズ ユーザーは、内部サーバーでホストされているリアルタイム会議を作成して参加できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="4b023-131">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="4b023-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="4b023-132">常設チャットを使用すると、複数のユーザーが、テキスト、リンク、ファイルなどの特定のトピックに関するコンテンツを投稿してアクセスする会話に参加できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="4b023-133">ユーザーはセッション中にリアルタイムで通信することができますが、各セッションのコンテンツは永続的です。つまり、セッションの終了後も引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="4b023-134">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4b023-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4b023-135">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="4b023-136">詳細については [、「Skype for Business to Microsoft Teams のアップグレード」を参照してください](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="4b023-136">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="4b023-137">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="4b023-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="4b023-138">ユーザー</span><span class="sxs-lookup"><span data-stu-id="4b023-138">Users</span></span>

 <span data-ttu-id="4b023-139">**ユーザーには** 、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b023-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="4b023-140">**内部組織**</span><span class="sxs-lookup"><span data-stu-id="4b023-140">**Internal organization**</span></span>
    
- <span data-ttu-id="4b023-141">**他の組織とのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="4b023-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="4b023-142">**以前のバージョンとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="4b023-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="4b023-143">**パブリック IM サービス プロバイダーとのフェデレーション** 組織内のユーザーが、MSN、Yahoo!、AOL などのパブリック インスタント メッセージング サービス プロバイダーとの通信を確立できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-143">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="4b023-144">パブリック インスタント メッセージング ネットワークとのフェデレーションを確立するには、別のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4b023-144">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="4b023-145">**XMPP ベースのサービス プロバイダーとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="4b023-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="4b023-146">Skype for Business Server 2015 では、完全に統合された XMPP プロキシ (エッジ サーバーに展開) と、フロントエンド サーバーに展開された XMPP ゲートウェイが導入されました。</span><span class="sxs-lookup"><span data-stu-id="4b023-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="4b023-147">[XMPP プロキシと XMPP ゲートウェイの追加と構成] を展開すると、Skype for Business Server ユーザーは、インスタント メッセージング (IM) とプレゼンスのために XMPP ベースのパートナーから連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="4b023-148">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="4b023-148">**Mobility**</span></span>
    
    <span data-ttu-id="4b023-149">Skype for Business Server Mobility Service を展開する場合、ユーザーはサポートされている Apple iOS、Android、Windows Phone、Nokia モバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="4b023-150">**W15 Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="4b023-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="4b023-151">Skype for Business Server を使用すると、ボイスメール メッセージを Exchange ユニファイド メッセージング (UM) に保存できます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b023-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b023-152">以前に知られている Exchange ユニファイド メッセージングは、Exchange 2019 では使用できなくなりましたが、電話システムを使用してボイスメール メッセージを録音してから、ユーザーの Exchange メールボックスに記録を残す方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="4b023-153">詳細については [、「Plan Cloud ボイスメール サービス](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b023-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="4b023-154">音声</span><span class="sxs-lookup"><span data-stu-id="4b023-154">Voice</span></span>

 <span data-ttu-id="4b023-155">**音声** には、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b023-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="4b023-156">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="4b023-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="4b023-157">エンタープライズ VoIP は、Microsft のソフトウェアベースの VoIP ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="4b023-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="4b023-158">エンタープライズ音声を使用すると、ユーザーは Skype for Business を使用してコンピューターから電話をかできます。</span><span class="sxs-lookup"><span data-stu-id="4b023-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="4b023-159">**Exchange ユニファイド メッセージング**</span><span class="sxs-lookup"><span data-stu-id="4b023-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="4b023-160">Exchange ユニファイド メッセージング (UM) は、ボイス メールと電子メールを単一のメッセージング インフラストラクチャに結合します。</span><span class="sxs-lookup"><span data-stu-id="4b023-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="4b023-161">Skype for Business Server 2015 では、Exchange UM を使用して通話応答、サブスクライバー アクセス、通話通知、自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="4b023-162">これらのサービスを使用する場合は、Exchange UM と Skype for Business Server を共有 Active Directory トポロジに統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b023-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b023-163">以前に知られている Exchange ユニファイド メッセージングは、Exchange 2019 では使用できなくなりましたが、電話システムを使用してボイスメール メッセージを録音してから、ユーザーの Exchange メールボックスに記録を残す方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="4b023-164">詳細については [、「Plan Cloud ボイスメール サービス](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b023-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="4b023-165">追加の展開オプション</span><span class="sxs-lookup"><span data-stu-id="4b023-165">Additional Deployment Options</span></span>

 <span data-ttu-id="4b023-166">**追加の展開オプションには** 、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b023-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="4b023-167">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="4b023-167">**High Availability**</span></span>
    
    <span data-ttu-id="4b023-168">高可用性により、スタンバイ サーバーはフェールオーバーのサポートを可能にします。</span><span class="sxs-lookup"><span data-stu-id="4b023-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="4b023-169">**障害復旧**</span><span class="sxs-lookup"><span data-stu-id="4b023-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="4b023-170">障害復旧対策を使用すると、2 つのデータセンターにあるフロントエンド プールをペアリングできます。</span><span class="sxs-lookup"><span data-stu-id="4b023-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="4b023-171">**監視**</span><span class="sxs-lookup"><span data-stu-id="4b023-171">**Monitoring**</span></span>
    
    <span data-ttu-id="4b023-172">監視は、通信セッションに関連する通話詳細レコードをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="4b023-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="4b023-173">また、参加者のエンドポイントで音声セッションとビデオ セッションからメトリックスを収集します。</span><span class="sxs-lookup"><span data-stu-id="4b023-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="4b023-174">監視サーバーは、使用状況の統計、傾向、およびメディア品質の統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="4b023-175">**アーカイブ**</span><span class="sxs-lookup"><span data-stu-id="4b023-175">**Archiving**</span></span>
    
    <span data-ttu-id="4b023-176">アーカイブでは、インスタント メッセージングの会話と会議が保存されます。</span><span class="sxs-lookup"><span data-stu-id="4b023-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="4b023-177">**Exchange アーカイブの統合**</span><span class="sxs-lookup"><span data-stu-id="4b023-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="4b023-178">Exchange にホームを持ち、そのメールボックスが In-Place Hold に設定されているユーザーがある場合は、Skype for Business Server ストレージを Exchange ストレージに統合するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="4b023-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="4b023-179">**IPv4**</span></span>
    
    <span data-ttu-id="4b023-180">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-180">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="4b023-181">世界中のデバイスの数が増えているので、使用可能な IPv4 アドレスが使い切っています。この理由から、多くの新しいデバイスが IPv6 アドレスの使用に移行しています。</span><span class="sxs-lookup"><span data-stu-id="4b023-181">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="4b023-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="4b023-182">**IPv6**</span></span>
    
    <span data-ttu-id="4b023-183">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b023-183">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="4b023-184">これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-184">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="4b023-185">**デバイス更新 Web サービス**</span><span class="sxs-lookup"><span data-stu-id="4b023-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="4b023-186">Device Update Web サービスは、組織外に展開されている Skype for Business for Windows Phone など、すべてのデバイスを自動的に更新する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="4b023-187">サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="4b023-187">Server Applications</span></span>

 <span data-ttu-id="4b023-188">**サーバー アプリケーションには、** 次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b023-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="4b023-189">**応答グループ**</span><span class="sxs-lookup"><span data-stu-id="4b023-189">**Response Group**</span></span>
    
    <span data-ttu-id="4b023-190">応答グループ アプリケーションは、使用可能なヘルプデスク エージェントに自動的に応答し、通話を配布します。</span><span class="sxs-lookup"><span data-stu-id="4b023-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="4b023-191">**アナウンス**</span><span class="sxs-lookup"><span data-stu-id="4b023-191">**Announcement**</span></span>
    
    <span data-ttu-id="4b023-192">電話番号を展開するエンタープライズ VoIP、ダイヤルされた番号が有効なのにユーザー共通領域に割り当てられていない場合に、電話の処理方法を構成できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4b023-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="4b023-193">管理者はアナウンス サービスを構成して、これらの通話が所定の宛先 (電話番号または SIP URI) に転送したり、音声アナウンスまたは両方を再生したりするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="4b023-194">アナウンス サービスを使用すると、発信者がビジー トーンを誤って聞こえるか、SIP クライアントがエラー メッセージを受信する状況が回避されます。</span><span class="sxs-lookup"><span data-stu-id="4b023-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="4b023-195">アナウンス サービスの機能は、一般的な PBX 機能です。</span><span class="sxs-lookup"><span data-stu-id="4b023-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="4b023-196">**コール パーク**</span><span class="sxs-lookup"><span data-stu-id="4b023-196">**Call Park**</span></span>
    
    <span data-ttu-id="4b023-197">通話パーク アプリケーションを使用すると、エンタープライズ VoIP ユーザーは 1 つの電話から通話を保留にしてから、通話を受信した電話のリソースを保持せずに別の電話から通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="4b023-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="4b023-198">コール パーク アプリケーションは、ユーザーが通話を転送する必要があるが、特定の受信者が不明な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b023-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="4b023-199">**会議アテンダント**</span><span class="sxs-lookup"><span data-stu-id="4b023-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="4b023-200">会議アテンダント アプリケーションは、サードパーティの電話会議プロバイダーのサービスを利用せずに電話ユーザーに電話会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b023-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="4b023-201">**会議のお知らせ**</span><span class="sxs-lookup"><span data-stu-id="4b023-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="4b023-202">会議アナウンス アプリケーションは、ユーザーが会議に参加または退出するときに通知するトーンと、ミュートまたはミュート解除時の電話ユーザーへの通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="4b023-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="4b023-203">**通話受付管理**</span><span class="sxs-lookup"><span data-stu-id="4b023-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="4b023-204">WAN 帯域幅管理とも呼ばれる通話受付管理 (CAC) は、利用可能な帯域幅に基づいて、許可するかどうか、および新しいリアルタイム通信セッションを確立するかどうかを決定することで、混雑したネットワーク上のユーザーのエクスペリエンスの質が低下するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b023-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4b023-205">CAC はリアルタイム トラフィックのみを制御し、データ トラフィックには影響しません。</span><span class="sxs-lookup"><span data-stu-id="4b023-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="4b023-206">新しい音声またはビデオ セッションが WAN に割り当てられた帯域幅制限を超えた場合、セッションはブロックまたは (電話の場合のみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4b023-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
