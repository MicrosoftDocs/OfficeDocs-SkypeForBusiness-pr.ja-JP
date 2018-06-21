---
title: 機能概要 (計画ツール)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: サーバー ツールの計画はビジネス用の Skype
ms.openlocfilehash: a5c482dadf2ffd39e8927e1924e50117dd13e1c8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974030"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="8f7cd-103">機能概要 (計画ツール)</span><span class="sxs-lookup"><span data-stu-id="8f7cd-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="8f7cd-104">サーバー ツールの計画はビジネス用の Skype</span><span class="sxs-lookup"><span data-stu-id="8f7cd-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="8f7cd-105">ビジネス サーバー配置の Skype を設計するのに計画ツールの**中心的なサイト**のページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="8f7cd-106">展開は、集中型または分散型の 2 種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="8f7cd-107">一元的な展開では、ビジネス ユーザーが組織内のすべての Skype が所属する 1 つのセントラル サイトのみがします。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="8f7cd-108">分散型の展開には複数のセントラル サイトが存在します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="8f7cd-109">Skype の複数の中央サイトでのビジネスのサーバーを展開する場合は、計画ツールで各中央サイトのユーザーの数を入力するされます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="8f7cd-110">セントラル サイトの定義を完了するには、まず以下の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="8f7cd-111">**サイト名**: セントラル サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="8f7cd-112">**ユーザー数**: セントラル サイトを所属先とするブランチ サイトのユーザーを含め、ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="8f7cd-113">**クラウドに所属しているユーザー**オンライン ビジネスのセントラル サイトに Skype からのホームとしているユーザーの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="8f7cd-114">UI 要素</span><span class="sxs-lookup"><span data-stu-id="8f7cd-114">UI Elements</span></span>

<span data-ttu-id="8f7cd-115">残りの要素は、作業の [**開始**] ウィザードに表示された質問への回答に従って設定されているか、ウィザードをスキップした場合は計画ツールによって自動的に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="8f7cd-116">オンライン グループ作業</span><span class="sxs-lookup"><span data-stu-id="8f7cd-116">Online Collaboration</span></span>

 <span data-ttu-id="8f7cd-117">[**オンライン グループ作業**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="8f7cd-118">**IM とプレゼンス**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="8f7cd-119">インスタント メッセージング (IM) を使用すると、ユーザーは各自のコンピューターでテキスト ベースのメッセージを使用して、リアルタイムで相互通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="8f7cd-120">2 パーティとマルチパーティの両方の IM セッションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="8f7cd-121">プレゼンスでは、ネットワーク上の他のユーザーの状態に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="8f7cd-122">ユーザーのプレゼンス状態は、ユーザーがオンラインかどうか、最適なユーザーに連絡する方法を決定する他のユーザーに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="8f7cd-123">たとえば、ユーザーが会議中の場合、そのユーザーへの最適な連絡方法は電子メールです。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="8f7cd-124">**音声ビデオ会議**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="8f7cd-125">音声/ビデオ (A/V) 会議を使用すると、リアルタイムの音声ビデオ会議を実現できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="8f7cd-126">**ダイヤルイン会議**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="8f7cd-p103">ダイヤルイン会議を使用すると、ユーザーは PSTN 上の電話から A/V に参加できます。ダイヤルイン会議を行うには、会議アテンダント アプリケーションと会議アナウンス サービス アプリケーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="8f7cd-129">**Web 会議**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="8f7cd-130">Web 会議を使用すると、ファイアウォールの内側および外側にいるエンタープライズ ユーザーは、内部のサーバーでホストされるリアルタイムの会議を作成したり、そのような会議に参加したりできます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="8f7cd-131">**常設チャット**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="8f7cd-p104">常設チャットを使用すると、複数のユーザーが会話に参加し、特定のトピックに関するコンテンツ (テキスト、リンク、ファイルなど) を投稿したり、それらにアクセスしたりできます。セッション中、ユーザーはリアルタイムで通信できますが、各セッションの内容は永続的に保持されます。そのため、セッション終了後も会話の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="8f7cd-134">ユーザー</span><span class="sxs-lookup"><span data-stu-id="8f7cd-134">Users</span></span>

 <span data-ttu-id="8f7cd-135">[**ユーザー**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="8f7cd-136">**内部組織**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-136">**Internal organization**</span></span>
    
- <span data-ttu-id="8f7cd-137">**他の組織とのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="8f7cd-138">**以前のバージョンとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="8f7cd-p105">**パブリック IM サービス プロバイダーとのフェデレーション**: 組織内のユーザーは、MSN、Yahoo!、AOL など、パブリック インスタント メッセージング サービス プロバイダーとの通信を確立できます。パブリック インスタント メッセージング ネットワークとのフェデレーションを確立するには、別のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-p105">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="8f7cd-141">**XMPP ベースのサービス プロバイダーとのフェデレーション**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="8f7cd-142">ビジネス サーバーの Skype では、(エッジ トランスポート サーバー上に展開される) 完全に統合された XMPP プロキシと、XMPP ゲートウェイは、フロント エンド サーバー上に展開を紹介します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-142">Skype for Business Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="8f7cd-143">XMPP プロキシの構成の追加と展開することができ、XMPP ゲートウェイが、Skype は、XMPP ベースのパートナーに対して、インスタント メッセージング (IM) とプレゼンスから連絡先を追加するのにはビジネスのサーバーのユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="8f7cd-144">**モビリティ**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-144">**Mobility**</span></span>
    
    <span data-ttu-id="8f7cd-145">ビジネス サーバー移動サービス、Skype を配置するとき、ユーザーは送信、インスタント メッセージを受信して、連絡先を表示するとプレゼンスを表示するには、このようなアクティビティを実行するのにはサポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイル デバイスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-145">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="8f7cd-146">**W15 Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="8f7cd-147">ビジネス サーバー用の Skype を使用すると、ボイスメールのメッセージを格納で Exchange ユニファイド メッセージング (UM)。ボイスメール メッセージは、ユーザーの受信トレイの電子メール メッセージとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-147">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="8f7cd-148">音声</span><span class="sxs-lookup"><span data-stu-id="8f7cd-148">Voice</span></span>

 <span data-ttu-id="8f7cd-149">[**音声**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="8f7cd-150">**エンタープライズ VoIP**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="8f7cd-151">エンタープライズ ボイスは、終了の VoIP ソリューションのソフトウェアを搭載します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="8f7cd-152">エンタープライズ ボイスでは、自分のコンピューターから電話をかけるときにビジネス用の Skype を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="8f7cd-153">**Exchange ユニファイド メッセージング**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="8f7cd-154">Exchange ユニファイド メッセージング (UM) 結合のボイス メールと電子メールを 1 つのメッセージング インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="8f7cd-155">ビジネス サーバー用の Skype を使用して、Exchange UM 通話応答、サブスクライバー アクセス、呼び出し通知、自動アテンダントのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-155">Skype for Business Server uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="8f7cd-156">これらのサービスを使用する場合は、ビジネスのサーバー共有の Active Directory トポロジでの Exchange UM と Skype を統合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="8f7cd-157">追加の展開オプション</span><span class="sxs-lookup"><span data-stu-id="8f7cd-157">Additional Deployment Options</span></span>

 <span data-ttu-id="8f7cd-158">[**追加の展開オプション**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="8f7cd-159">**高可用性**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-159">**High Availability**</span></span>
    
    <span data-ttu-id="8f7cd-160">高可用性を使用すると、スタンバイ サーバーが有効になり、フェールオーバーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="8f7cd-161">**障害復旧**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="8f7cd-162">災害復旧対策には、2 つのデータ センター内にあるペアのフロント エンド プールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="8f7cd-163">**監視**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-163">**Monitoring**</span></span>
    
    <span data-ttu-id="8f7cd-164">監視によって、通信セッションに関連する通話詳細記録が取得されます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="8f7cd-165">また、参加者のエンドポイントで音声ビデオ セッションからの指標も収集されます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="8f7cd-166">サーバーの監視は、使用状況の統計、トレンド、およびメディア品質の統計情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="8f7cd-167">**アーカイブ**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-167">**Archiving**</span></span>
    
    <span data-ttu-id="8f7cd-168">アーカイブでは、インスタント メッセージングの会話および会議が保管されます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="8f7cd-169">**Exchange とアーカイブの統合**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="8f7cd-170">Exchange のホーム サーバーはユーザーがあり、自分のメールボックスは、インプレース保持に格納されている場合は、Exchange の記憶域を持つビジネス サーバーの記憶域の Skype を統合するためのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-170">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="8f7cd-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-171">**IPv4**</span></span>
    
    <span data-ttu-id="8f7cd-p110">IPv4 アドレスは 32 ビットのアドレスで、これを使用することでコンピューターはインターネットを介して通信できます。世界中でデバイスの数が増加したため、利用できる IPv4 アドレスを使い果たしてしまいました。このため、多くの新しいデバイスでは IPv6 アドレスを使用するようになってきています。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-p110">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="8f7cd-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-174">**IPv6**</span></span>
    
    <span data-ttu-id="8f7cd-p111">IPv6 アドレスは、IPv4 アドレスと同じ機能 (および追加機能) を実行しますが、32 ビットだけではなく、128 ビットを使用します。これにより、新しいアドレス セットだけでなく、より多くのアドレスも提供できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-p111">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="8f7cd-177">**デバイス更新 Web サービス**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="8f7cd-178">デバイス更新 Web サービスは、Windows Phone のビジネス用の Skype など、別の組織に展開されてすべてのデバイスを更新する自動化された方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="8f7cd-179">サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8f7cd-179">Server Applications</span></span>

 <span data-ttu-id="8f7cd-180">[**サーバー アプリケーション**] には以下のオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="8f7cd-181">**応答グループ**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-181">**Response Group**</span></span>
    
    <span data-ttu-id="8f7cd-182">応答グループ アプリケーションは自動的に回答し、ヘルプデスクの利用可能なエージェントへの呼び出しを配布します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="8f7cd-183">**アナウンス**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-183">**Announcement**</span></span>
    
    <span data-ttu-id="8f7cd-184">エンタープライズ VoIP を展開する場合は、電話のダイヤルの番号が有効なユーザーの一般的な領域に割り当てられていない場合の処理方法を構成できるようにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="8f7cd-185">管理者は、これらの通話を事前に設定しておいた転送先 (電話番号または SIP URI) に転送するか、音声アナウンスを再生するか、またはその両方を行うようにアナウンス サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="8f7cd-186">アナウンス サービスを使用することで、誤ってダイヤルした発信者に話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="8f7cd-187">アナウンス サービス機能は、通常、PBX 機能です。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="8f7cd-188">**コール パーク**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-188">**Call Park**</span></span>
    
    <span data-ttu-id="8f7cd-189">コール パーク アプリケーションを有効に 1 つから呼び出しを配置するのには、エンタープライズ VoIP ユーザーが保持は、電話、および別の電話からの呼び出しを受信した携帯電話上のリソースを停止せず、呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="8f7cd-190">コール パーク アプリケーションは、ユーザーが、呼び出しを転送する必要がありますが、特定の受信者が不明の場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="8f7cd-191">**会議アテンダント**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="8f7cd-192">会議アテンダント アプリケーションでは、サード ・ パーティ製のオーディオ会議プロバイダーのサービスの電話ユーザーに電話会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="8f7cd-193">**会議アナウンス**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="8f7cd-194">アプリケーションとユーザー入力のままにする通知と同様に、会議では、電話ユーザーがミュートされているときやがミュート解除を通知するトーンを作成する会議のお知らせです。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="8f7cd-195">**通話受付管理**</span><span class="sxs-lookup"><span data-stu-id="8f7cd-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="8f7cd-196">WAN 帯域幅管理とも呼ばれる通話受付管理 (CAC) は、利用可能な帯域幅に基づいて新しいリアルタイム通信セッションの確立を許可するかどうかを判断することで、混雑したネットワークでの低品質なユーザー操作を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8f7cd-197">CAC はリアルタイム トラフィックのみを制御するので、データ トラフィックに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="8f7cd-198">新しい音声セッションまたはビデオ セッションが WAN に割り当てられている帯域幅制限を超えた場合、セッションはブロックされるか、(電話での通話のみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8f7cd-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

