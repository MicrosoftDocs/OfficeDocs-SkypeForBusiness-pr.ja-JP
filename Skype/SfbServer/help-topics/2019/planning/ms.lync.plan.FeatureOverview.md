---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype for Business Server 計画ツール
ms.openlocfilehash: 6b90f29e37b64bfe2b1b808a23e11f66a8758760
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689832"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="0c439-103">Feature Overview (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="0c439-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="0c439-104">Skype for Business Server 計画ツール</span><span class="sxs-lookup"><span data-stu-id="0c439-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="0c439-105">計画ツールの [**セントラルサイト**] ページを使用して、Skype For business Server の展開を設計することができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="0c439-106">展開は、集中型または分散型の 2 種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="0c439-107">一元展開には1つのセントラルサイトしかありません。これにより、組織内のすべての Skype for Business ユーザーがホームとなります。</span><span class="sxs-lookup"><span data-stu-id="0c439-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="0c439-108">分散型の展開には複数のセントラル サイトが存在します。</span><span class="sxs-lookup"><span data-stu-id="0c439-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="0c439-109">複数のセントラルサイトに Skype for Business Server を展開する場合は、計画ツールの各セントラルサイトでユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c439-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="0c439-110">セントラル サイトの定義を完了するには、まず以下の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c439-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="0c439-111">**サイト名**: セントラル サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c439-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="0c439-112">**ユーザー数**: セントラル サイトを所属先とするブランチ サイトのユーザーを含め、ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c439-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="0c439-113">**クラウドのホームユーザー**Skype for Business Online から中央サイトに置かれているユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c439-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="0c439-114">UI 要素</span><span class="sxs-lookup"><span data-stu-id="0c439-114">UI Elements</span></span>

<span data-ttu-id="0c439-115">残りの要素は、作業の [**開始**] ウィザードに表示された質問への回答に従って設定されているか、ウィザードをスキップした場合は計画ツールによって自動的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0c439-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="0c439-116">オンライン グループ作業</span><span class="sxs-lookup"><span data-stu-id="0c439-116">Online Collaboration</span></span>

 <span data-ttu-id="0c439-117">[**オンライン グループ作業**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c439-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="0c439-118">**IM とプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="0c439-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="0c439-119">インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="0c439-120">2 パーティとマルチパーティの両方の IM セッションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0c439-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="0c439-121">プレゼンスでは、ネットワーク上の他のユーザーの状態に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0c439-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="0c439-122">ユーザーのプレゼンス状態は、ユーザーがオンライン状態かどうかを他のユーザーが判断するのに役立つ情報と、ユーザーに対して最適な連絡先にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c439-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="0c439-123">たとえば、ユーザーが会議中の場合、そのユーザーへの最適な連絡方法は電子メールです。</span><span class="sxs-lookup"><span data-stu-id="0c439-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="0c439-124">**音声ビデオ会議**</span><span class="sxs-lookup"><span data-stu-id="0c439-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="0c439-125">音声/ビデオ (A/V) 会議を使用すると、リアルタイムの音声ビデオ会議を実現できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="0c439-126">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="0c439-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="0c439-p103">ダイヤルイン会議を使用すると、ユーザーは PSTN 上の電話から A/V に参加できます。ダイヤルイン会議を行うには、会議アテンダント アプリケーションと会議アナウンス サービス アプリケーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c439-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="0c439-129">**Web 会議**</span><span class="sxs-lookup"><span data-stu-id="0c439-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="0c439-130">Web 会議を使用すると、ファイアウォールの内側および外側にいるエンタープライズ ユーザーは、内部のサーバーでホストされるリアルタイムの会議を作成したり、そのような会議に参加したりできます。</span><span class="sxs-lookup"><span data-stu-id="0c439-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="0c439-131">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="0c439-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="0c439-p104">常設チャットを使用すると、複数のユーザーが会話に参加し、特定のトピックに関するコンテンツ (テキスト、リンク、ファイルなど) を投稿したり、それらにアクセスしたりできます。セッション中、ユーザーはリアルタイムで通信できますが、各セッションの内容は永続的に保持されます。そのため、セッション終了後も会話の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="0c439-134">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0c439-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0c439-135">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="0c439-136">詳細については、「 [Skype For business から Microsoft Teams へのアップグレード](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c439-136">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="0c439-137">常設チャットを使用する必要がある場合は、この機能が必要なユーザーを Teams に移行するか、Skype for Business Server 2015 を使い続けるかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="0c439-138">ユーザー</span><span class="sxs-lookup"><span data-stu-id="0c439-138">Users</span></span>

 <span data-ttu-id="0c439-139">[**ユーザー**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c439-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="0c439-140">**内部組織**</span><span class="sxs-lookup"><span data-stu-id="0c439-140">**Internal organization**</span></span>
    
- <span data-ttu-id="0c439-141">**他の組織とのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="0c439-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="0c439-142">**以前のバージョンとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="0c439-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="0c439-p106">**パブリック IM サービス プロバイダーとのフェデレーション**: 組織内のユーザーは、MSN、Yahoo!、AOL など、パブリック インスタント メッセージング サービス プロバイダーとの通信を確立できます。パブリック インスタント メッセージング ネットワークとのフェデレーションを確立するには、別のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0c439-p106">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="0c439-145">**XMPP ベースのサービス プロバイダーとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="0c439-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="0c439-146">Skype for Business Server 2015 では、完全に統合された XMPP プロキシ (エッジサーバーに展開) と、フロントエンドサーバーに XMPP ゲートウェイが導入されています。</span><span class="sxs-lookup"><span data-stu-id="0c439-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="0c439-147">XMPP プロキシと XMPP ゲートウェイを追加して構成することで、Skype for Business Server ユーザーは、インスタントメッセージング (IM) とプレゼンスのために、XMPP ベースのパートナーから連絡先を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="0c439-148">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="0c439-148">**Mobility**</span></span>
    
    <span data-ttu-id="0c439-149">Skype for Business Server Mobility Service を展開すると、サポートされている Apple iOS、Android、Windows Phone、Nokia のモバイルデバイスを使用して、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="0c439-150">**W15 Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="0c439-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="0c439-151">Skype for Business Server を使用すると、Exchange ユニファイドメッセージング (UM) でボイスメールメッセージを保存することができます。これらのボイスメールメッセージは、ユーザーの受信トレイにメールメッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c439-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c439-152">以前に認識されていた exchange ユニファイドメッセージングは Exchange 2019 では利用できなくなりましたが、電話システムを使ってボイスメールメッセージを録音し、ユーザーの Exchange メールボックスに記録を残すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="0c439-153">詳細については、「[クラウドボイスメールサービスの計画](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c439-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="0c439-154">音声</span><span class="sxs-lookup"><span data-stu-id="0c439-154">Voice</span></span>

 <span data-ttu-id="0c439-155">[**音声**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c439-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="0c439-156">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="0c439-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="0c439-157">エンタープライズボイスは、ソフトウェアを搭載した VoIP ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="0c439-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="0c439-158">エンタープライズボイスでは、ユーザーが Skype for Business を使用して、コンピューターから電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="0c439-159">**Exchange ユニファイド メッセージング**</span><span class="sxs-lookup"><span data-stu-id="0c439-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="0c439-160">Exchange ユニファイドメッセージング (UM) では、ボイスメールとメールが1つのメッセージングインフラストラクチャに組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="0c439-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="0c439-161">Skype for Business Server 2015 は Exchange UM を使って、通話応答、サブスクライバーアクセス、着信通知、自動応答サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c439-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="0c439-162">これらのサービスを使用する場合は、共有の Active Directory トポロジに Exchange UM と Skype for Business Server を統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c439-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c439-163">以前に認識されていた exchange ユニファイドメッセージングは Exchange 2019 では利用できなくなりましたが、電話システムを使ってボイスメールメッセージを録音し、ユーザーの Exchange メールボックスに記録を残すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="0c439-164">詳細については、「[クラウドボイスメールサービスの計画](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c439-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="0c439-165">追加の展開オプション</span><span class="sxs-lookup"><span data-stu-id="0c439-165">Additional Deployment Options</span></span>

 <span data-ttu-id="0c439-166">[**追加の展開オプション**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c439-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="0c439-167">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="0c439-167">**High Availability**</span></span>
    
    <span data-ttu-id="0c439-168">高可用性を使用すると、スタンバイ サーバーが有効になり、フェールオーバーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0c439-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="0c439-169">**障害復旧**</span><span class="sxs-lookup"><span data-stu-id="0c439-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="0c439-170">災害復旧の手段により、2つのデータセンターにあるフロントエンドプールをペアにできます。</span><span class="sxs-lookup"><span data-stu-id="0c439-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="0c439-171">**監視**</span><span class="sxs-lookup"><span data-stu-id="0c439-171">**Monitoring**</span></span>
    
    <span data-ttu-id="0c439-172">監視によって、通信セッションに関連する通話詳細記録が取得されます。</span><span class="sxs-lookup"><span data-stu-id="0c439-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="0c439-173">また、参加者のエンドポイントで音声ビデオ セッションからの指標も収集されます。</span><span class="sxs-lookup"><span data-stu-id="0c439-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="0c439-174">Monitoring Server は、利用統計情報、傾向、およびメディア品質の統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0c439-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="0c439-175">**アーカイブ**</span><span class="sxs-lookup"><span data-stu-id="0c439-175">**Archiving**</span></span>
    
    <span data-ttu-id="0c439-176">アーカイブでは、インスタント メッセージングの会話および会議が保管されます。</span><span class="sxs-lookup"><span data-stu-id="0c439-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="0c439-177">**Exchange とアーカイブの統合**</span><span class="sxs-lookup"><span data-stu-id="0c439-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="0c439-178">Exchange を使っているユーザーがいて、そのメールボックスがインプレース保持されている場合は、Skype for Business Server ストレージを Exchange ストレージに統合するためのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="0c439-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="0c439-179">**IPv4**</span></span>
    
    <span data-ttu-id="0c439-p113">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。世界中でデバイスの数が増加したため、利用できる IPv4 アドレスを使い果たしてしまいました。このため、多くの新しいデバイスでは IPv6 アドレスを使用するようになってきています。</span><span class="sxs-lookup"><span data-stu-id="0c439-p113">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="0c439-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="0c439-182">**IPv6**</span></span>
    
    <span data-ttu-id="0c439-p114">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-p114">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="0c439-185">**デバイス更新 Web サービス**</span><span class="sxs-lookup"><span data-stu-id="0c439-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="0c439-186">デバイス更新 Web サービスを利用すると、組織外に展開されている Windows Phone 用の Skype for Business など、すべてのデバイスを自動的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="0c439-187">サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0c439-187">Server Applications</span></span>

 <span data-ttu-id="0c439-188">[**サーバー アプリケーション**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c439-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="0c439-189">**応答グループ**</span><span class="sxs-lookup"><span data-stu-id="0c439-189">**Response Group**</span></span>
    
    <span data-ttu-id="0c439-190">応答グループアプリケーションは、利用可能なヘルプデスクエージェントに自動的に応答し、通話を配信します。</span><span class="sxs-lookup"><span data-stu-id="0c439-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="0c439-191">**アナウンス**</span><span class="sxs-lookup"><span data-stu-id="0c439-191">**Announcement**</span></span>
    
    <span data-ttu-id="0c439-192">エンタープライズ Voip の展開を計画している場合は、ダイヤルされた番号が有効であるが、ユーザーの共通領域に割り当てられていない場合、電話での通話の処理方法を構成できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c439-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="0c439-193">管理者は、これらの通話を事前に設定しておいた転送先 (電話番号または SIP URI) に転送するか、音声アナウンスを再生するか、またはその両方を行うようにアナウンス サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c439-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="0c439-194">アナウンス サービスを使用することで、誤ってダイヤルした発信者に話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="0c439-195">アナウンス サービス機能は、通常、PBX 機能です。</span><span class="sxs-lookup"><span data-stu-id="0c439-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="0c439-196">**コール パーク**</span><span class="sxs-lookup"><span data-stu-id="0c439-196">**Call Park**</span></span>
    
    <span data-ttu-id="0c439-197">[コールパーク] アプリケーションを使用すると、エンタープライズボイスユーザーは1つの電話から通話を保留にすることができ、通話を受信した電話のリソースを占有したまま別の電話から通話を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c439-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="0c439-198">コールパークアプリケーションは、ユーザーが通話を転送する必要があるが、特定の受信者が不明な場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0c439-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="0c439-199">**会議アテンダント**</span><span class="sxs-lookup"><span data-stu-id="0c439-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="0c439-200">電話会議は、サードパーティの電話会議プロバイダーのサービスを利用していない電話ユーザーに電話会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="0c439-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="0c439-201">**会議アナウンス**</span><span class="sxs-lookup"><span data-stu-id="0c439-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="0c439-202">会議アナウンスメントアプリケーションは、ユーザーが電話会議に参加したとき、または電話のユーザーがミュートまたはミュートしたときに通知するトーンを生成します。</span><span class="sxs-lookup"><span data-stu-id="0c439-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="0c439-203">**通話受付管理**</span><span class="sxs-lookup"><span data-stu-id="0c439-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="0c439-204">WAN 帯域幅管理とも呼ばれる通話受付管理 (CAC) は、利用可能な帯域幅に基づいて新しいリアルタイム通信セッションの確立を許可するかどうかを判断することで、混雑したネットワークでの低品質なユーザー操作を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0c439-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0c439-205">CAC はリアルタイム トラフィックのみを制御するので、データ トラフィックに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="0c439-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="0c439-206">新しい音声セッションまたはビデオ セッションが WAN に割り当てられている帯域幅制限を超えた場合、セッションはブロックされるか、(電話での通話のみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0c439-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

