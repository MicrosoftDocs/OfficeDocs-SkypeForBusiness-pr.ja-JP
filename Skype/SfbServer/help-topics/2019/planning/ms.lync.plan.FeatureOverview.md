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
ms.openlocfilehash: f317b2963e6db83e733a3f0b259a6d0bfe466c9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819827"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="7c6bf-103">機能の概要 (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="7c6bf-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="7c6bf-104">Skype for Business Server Planning Tool</span><span class="sxs-lookup"><span data-stu-id="7c6bf-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="7c6bf-105">計画ツールの [ **中央サイト** ] ページを使用して、Skype for Business Server 展開を設計できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="7c6bf-106">2 つの一元展開または分散展開を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="7c6bf-107">一元展開には、組織内のすべての Skype for Business ユーザーが所属する中央サイトが 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="7c6bf-108">分散展開には、複数の中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="7c6bf-109">複数の中央サイトに Skype for Business Server を展開する場合は、計画ツールの各中央サイトのユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="7c6bf-110">セントラル サイトの定義を完了するには、まず次の情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="7c6bf-111">**サイト名** 中央サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="7c6bf-112">**ユーザー数** 中央サイトにホームを持つブランチ サイトのユーザーを含む、ユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="7c6bf-113">**クラウド ホーム ユーザー** Skype for Business Online から中央サイトにホームとして登録されているユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="7c6bf-114">UI 要素</span><span class="sxs-lookup"><span data-stu-id="7c6bf-114">UI Elements</span></span>

<span data-ttu-id="7c6bf-115">残りの要素には、開始ウィザードに表示される質問に対する回答が入力されています。または、ウィザードを省略した場合は、計画ツールによって自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="7c6bf-116">オンライン コラボレーション</span><span class="sxs-lookup"><span data-stu-id="7c6bf-116">Online Collaboration</span></span>

 <span data-ttu-id="7c6bf-117">**オンライン コラボレーションには** 、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="7c6bf-118">**IM とプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="7c6bf-119">インスタント メッセージング (IM) を使用すると、ユーザーはテキスト ベースのメッセージを使用して、コンピューター上でリアルタイムで相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="7c6bf-120">2 パーティとマルチパーティの両方の IM セッションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="7c6bf-121">プレゼンスは、ネットワーク上の他のユーザーの状態に関する情報をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="7c6bf-122">ユーザーのプレゼンス状態は、ユーザーがオンラインかどうかを他のユーザーが判断するのに役立つ情報と、ユーザーに最適な連絡方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="7c6bf-123">たとえば、会議中のユーザーは、メールで連絡を取るのが最適です。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="7c6bf-124">**音声ビデオ会議**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="7c6bf-125">音声ビデオ (A/V) 会議では、リアルタイムの音声ビデオ会議が可能です。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="7c6bf-126">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="7c6bf-127">ダイヤルイン会議を使用すると、ユーザーは PSTN 上の電話から音声ビデオに参加できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="7c6bf-128">ダイヤルイン会議では、会議アテンダントおよび会議アナウンス サービス アプリケーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="7c6bf-129">**Web 会議**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="7c6bf-130">Web 会議を使用すると、ファイアウォールの内側と外側のエンタープライズ ユーザーは、内部サーバーでホストされているリアルタイムの会議を作成して参加できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="7c6bf-131">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="7c6bf-132">常設チャットを使用すると、複数のユーザーが会話に参加し、テキスト、リンク、ファイルなど、特定のトピックに関するコンテンツを投稿してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="7c6bf-133">ユーザーはセッション中にリアルタイムで通信することができますが、各セッションのコンテンツは永続的です。つまり、セッションが終了した後も引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="7c6bf-134">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7c6bf-135">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="7c6bf-136">詳細については [、「Skype for Business から Microsoft Teams へのアップグレード」を参照してください](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-136">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="7c6bf-137">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="7c6bf-138">ユーザー</span><span class="sxs-lookup"><span data-stu-id="7c6bf-138">Users</span></span>

 <span data-ttu-id="7c6bf-139">**ユーザー** には、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="7c6bf-140">**内部組織**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-140">**Internal organization**</span></span>
    
- <span data-ttu-id="7c6bf-141">**他の組織とのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="7c6bf-142">**以前のバージョンとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="7c6bf-143">**パブリック IM サービス プロバイダーとのフェデレーション** 組織内のユーザーが MSN、Yahoo!、AOL などのパブリック インスタント メッセージング サービス プロバイダーとの通信を確立できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-143">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="7c6bf-144">パブリック インスタント メッセージング ネットワークとのフェデレーションを確立するには、別のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-144">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="7c6bf-145">**XMPP ベースのサービス プロバイダーとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="7c6bf-146">Skype for Business Server 2015 では、完全に統合された XMPP プロキシ (エッジ サーバーに展開) と、フロントエンド サーバーに展開された XMPP ゲートウェイが導入されました。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="7c6bf-147">XMPP プロキシと XMPP ゲートウェイの追加と構成を展開すると、Skype for Business Server ユーザーはインスタント メッセージング (IM) およびプレゼンス用に XMPP ベースのパートナーから連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="7c6bf-148">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-148">**Mobility**</span></span>
    
    <span data-ttu-id="7c6bf-149">Skype for Business Server Mobility Service を展開すると、ユーザーはサポートされている Apple iOS、Android、Windows Phone、または Nokia モバイル デバイスを使用して、インスタント メッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="7c6bf-150">**W15 Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="7c6bf-151">Skype for Business Server を使用すると、ボイスメール メッセージを Exchange ユニファイド メッセージング (UM) に保存できます。これらのボイスメール メッセージは、ユーザーの受信トレイに電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c6bf-152">Exchange 2019 では、以前に知られている Exchange ユニファイド メッセージングは使用できなくなりましたが、引き続き電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="7c6bf-153">詳細 [については、「クラウド ボイスメール サービスを計画](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="7c6bf-154">音声</span><span class="sxs-lookup"><span data-stu-id="7c6bf-154">Voice</span></span>

 <span data-ttu-id="7c6bf-155">**音声** には、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="7c6bf-156">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="7c6bf-157">エンタープライズ VoIP は、Microsft のソフトウェアベースの VoIP ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="7c6bf-158">エンタープライズ ボイスを使用すると、ユーザーは Skype for Business を使用してコンピューターから電話をかけ付けできます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="7c6bf-159">**Exchange ユニファイド メッセージング**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="7c6bf-160">Exchange ユニファイド メッセージング (UM) は、ボイス メールと電子メールを 1 つのメッセージング インフラストラクチャに結合します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="7c6bf-161">Skype for Business Server 2015 は Exchange UM を使用して、通話応答、サブスクライバー アクセス、通話通知、および自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="7c6bf-162">これらのサービスを使用する場合は、Exchange UM と Skype for Business Server を共有 Active Directory トポロジに統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c6bf-163">Exchange 2019 では、以前に知られている Exchange ユニファイド メッセージングは使用できなくなりましたが、引き続き電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="7c6bf-164">詳細 [については、「クラウド ボイスメール サービスを計画](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="7c6bf-165">追加の展開オプション</span><span class="sxs-lookup"><span data-stu-id="7c6bf-165">Additional Deployment Options</span></span>

 <span data-ttu-id="7c6bf-166">**追加の展開オプションには** 、次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="7c6bf-167">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-167">**High Availability**</span></span>
    
    <span data-ttu-id="7c6bf-168">高可用性を使用すると、スタンバイ サーバーでフェールオーバーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="7c6bf-169">**障害復旧**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="7c6bf-170">障害復旧対策を使用すると、2 つのデータセンターに配置されたフロントエンド プールをペアにできます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="7c6bf-171">**監視**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-171">**Monitoring**</span></span>
    
    <span data-ttu-id="7c6bf-172">監視は、通信セッションに関連する通話詳細記録をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="7c6bf-173">また、参加者のエンドポイントで音声およびビデオ セッションから測定基準を収集します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="7c6bf-174">監視サーバーは、利用状況統計、傾向、およびメディア品質統計を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="7c6bf-175">**アーカイブ**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-175">**Archiving**</span></span>
    
    <span data-ttu-id="7c6bf-176">アーカイブには、インスタント メッセージングの会話と会議が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="7c6bf-177">**Exchange アーカイブ統合**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="7c6bf-178">Exchange にホームとして設定されているユーザーがいて、そのメールボックスが In-Place Hold に設定されている場合は、Skype for Business Server ストレージと Exchange ストレージを統合するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="7c6bf-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-179">**IPv4**</span></span>
    
    <span data-ttu-id="7c6bf-180">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-180">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="7c6bf-181">世界中でデバイスの数が増えているので、使用可能な IPv4 アドレスが使い切れなっています。この理由から、多くの新しいデバイスが IPv6 アドレスの使用に移行しています。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-181">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="7c6bf-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-182">**IPv6**</span></span>
    
    <span data-ttu-id="7c6bf-183">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-183">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="7c6bf-184">これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-184">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="7c6bf-185">**デバイス更新 Web サービス**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="7c6bf-186">デバイス更新 Web サービスは、組織外に展開されている Skype for Business for Windows Phone などのすべてのデバイスを自動的に更新する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="7c6bf-187">サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7c6bf-187">Server Applications</span></span>

 <span data-ttu-id="7c6bf-188">**サーバー アプリケーションには、** 次のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="7c6bf-189">**応答グループ**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-189">**Response Group**</span></span>
    
    <span data-ttu-id="7c6bf-190">応答グループ アプリケーションは、使用可能なヘルプデスク エージェントに通話に自動的に応答し、配布します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="7c6bf-191">**お知らせ**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-191">**Announcement**</span></span>
    
    <span data-ttu-id="7c6bf-192">エンタープライズ VoIP の展開を計画している場合は、ダイヤルされた番号が有効で、ユーザーの共通領域に割り当てられていない場合に、電話の処理方法を構成できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="7c6bf-193">管理者は、これらの通話が事前に定義された宛先 (電話番号または SIP URI) に転送したり、音声アナウンスを再生したり、その両方を再生したりするようにアナウンス サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="7c6bf-194">アナウンス サービスを使用すると、発信者が誤って話し中音を聞く、または SIP クライアントがエラー メッセージを受信する状況を回避できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="7c6bf-195">アナウンス サービス機能は、一般的な PBX 機能です。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="7c6bf-196">**コール パーク**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-196">**Call Park**</span></span>
    
    <span data-ttu-id="7c6bf-197">コール パーク アプリケーションを使用すると、エンタープライズ VoIP ユーザーは 1 つの電話から通話を保留にした後、通話を受信した電話のリソースを引き離さずに別の電話から通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="7c6bf-198">コール パーク アプリケーションは、ユーザーが通話を転送する必要があるが、特定の受信者が不明な場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="7c6bf-199">**会議アテンダント**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="7c6bf-200">会議アテンダント アプリケーションは、サードパーティの電話会議プロバイダーのサービスを利用せずに電話ユーザーに電話会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="7c6bf-201">**会議アナウンス**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="7c6bf-202">会議アナウンス アプリケーションは、ユーザーが会議に参加または退出するときに通知するトーンと、ミュートまたはミュート解除時の電話ユーザーへの通知を生成します。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="7c6bf-203">**通話受付管理**</span><span class="sxs-lookup"><span data-stu-id="7c6bf-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="7c6bf-204">WAN 帯域幅管理とも呼ばれる通話受付管理 (CAC) は、使用可能な帯域幅に基づいて、許可するかどうか、および新しいリアルタイム通信セッションを確立するかどうかを決定することにより、混雑したネットワーク上のユーザーの低品質のエクスペリエンスを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7c6bf-205">CAC はリアルタイム トラフィックのみを制御し、データ トラフィックには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="7c6bf-206">新しい音声またはビデオ セッションが WAN に割り当てられた帯域幅制限を超えた場合、セッションはブロックまたは (電話の場合のみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="7c6bf-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

