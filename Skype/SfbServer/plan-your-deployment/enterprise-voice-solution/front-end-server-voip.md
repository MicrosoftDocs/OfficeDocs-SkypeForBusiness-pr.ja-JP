---
title: Skype for Business Server のフロントエンド サーバー VoIP コンポーネント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 翻訳サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server のフロント エンド サーバー上にあるさまざまなコンポーネントについて説明します。
ms.openlocfilehash: 830f54e59e0d2135e3748fd03474b19e22741136
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101493"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="e8339-103">Skype for Business Server のフロントエンド サーバー VoIP コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="e8339-104">翻訳サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server のフロント エンド サーバー上にあるさまざまなコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e8339-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="e8339-105">フロント エンド サーバー上にある VoIP コンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e8339-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="e8339-106">変換サービス</span><span class="sxs-lookup"><span data-stu-id="e8339-106">Translation Service</span></span>

- <span data-ttu-id="e8339-107">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-107">Inbound Routing component</span></span>

- <span data-ttu-id="e8339-108">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-108">Outbound Routing component</span></span>

- <span data-ttu-id="e8339-109">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="e8339-110">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="e8339-111">Skype for Business Server の仲介サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="e8339-112">変換サービス</span><span class="sxs-lookup"><span data-stu-id="e8339-112">Translation Service</span></span>

<span data-ttu-id="e8339-p101">変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="e8339-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="e8339-115">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-115">Inbound Routing Component</span></span>

<span data-ttu-id="e8339-116">受信ルーティング コンポーネントは、クライアント上のユーザーが指定した基本設定に従って、着信呼び出しをエンタープライズ VoIPします。</span><span class="sxs-lookup"><span data-stu-id="e8339-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="e8339-117">着信ルーティング コンポーネントはまた、ユーザーが設定した場合に、代理人着信および同時着信を行います。</span><span class="sxs-lookup"><span data-stu-id="e8339-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="e8339-118">たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知に記録するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8339-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="e8339-119">通話転送が有効になっている場合、ユーザーは、応答されていない通話を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8339-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="e8339-120">受信ルーティング コンポーネントは、既定ですべての Standard Edition サーバーとフロントエンド サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8339-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="e8339-121">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-121">Outbound Routing Component</span></span>

<span data-ttu-id="e8339-122">発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e8339-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="e8339-123">ユーザーの音声ポリシーで定義されている通話承認ルールを発信者に適用し、各呼び出しをルーティングする最適な PSTN ゲートウェイを決定します。</span><span class="sxs-lookup"><span data-stu-id="e8339-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="e8339-124">送信ルーティング コンポーネントは、既定ですべての Standard Edition サーバーとフロントエンド サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8339-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="e8339-125">発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。</span><span class="sxs-lookup"><span data-stu-id="e8339-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="e8339-126">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="e8339-127">Exchange UM ルーティング コンポーネントは、Skype for Business Server と Exchange ユニファイド メッセージング (UM) を実行しているサーバー間のルーティングを処理し、Skype for Business Server とユニファイド メッセージング機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="e8339-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="e8339-128">Exchange UM ルーティング コンポーネントは、Exchange UM サーバーが使用できない場合に PSTN を使用してボイス メールの再ルーティングも処理します。</span><span class="sxs-lookup"><span data-stu-id="e8339-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="e8339-129">ブランチ サイトに回復力のある WAN リンクを持つブランチ サイトに エンタープライズ VoIP ユーザーがいる場合、ブランチ サイトに展開する存続可能ブランチ アプライアンスは、WAN の停止中にブランチ ユーザーにボイス メールの存続性を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8339-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="e8339-130">WAN リンクを使用できない場合は、存続可能ブランチ アプライアンスは次を行います。</span><span class="sxs-lookup"><span data-stu-id="e8339-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="e8339-131">セントラル サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e8339-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="e8339-132">ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e8339-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="e8339-133">不在着信通知をキューに入れ、WAN リンクが回復した時に Exchange UM サーバーへそれらをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e8339-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="e8339-134">ボイス メールの再ルーティングを有効にするには、Exchange 管理者がメッセージのみを受け入れる Exchange UM 自動応答 (AA) を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e8339-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="e8339-135">これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)」および「[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8339-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) and [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="e8339-136">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-136">Intercluster Routing Component</span></span>

<span data-ttu-id="e8339-137">Intercluster ルーティング コンポーネントは、呼び出し先のプライマリ レジストラー プールへの通話のルーティングを担当します。</span><span class="sxs-lookup"><span data-stu-id="e8339-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="e8339-138">使用できない場合、コンポーネントは呼び出し先のバックアップ レジストラー プールに呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e8339-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="e8339-139">呼び出し先のプライマリ およびバックアップ レジストラー プールが IP ネットワーク上で到達できない場合、Intercluster ルーティング コンポーネントは PSTN を使用してユーザーの電話番号に通話を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e8339-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="e8339-140">VoIP に必要なその他のフロントエンド サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e8339-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="e8339-141">VoIP に不可欠なサポートを提供するフロントエンド サーバーまたはディレクターに存在する他のコンポーネントですが、それ自体は VoIP コンポーネントではありません。次のコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8339-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="e8339-142">**ユーザー サービス。**</span><span class="sxs-lookup"><span data-stu-id="e8339-142">**User Services.**</span></span> <span data-ttu-id="e8339-143">各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。</span><span class="sxs-lookup"><span data-stu-id="e8339-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="e8339-144">この情報を使用して、受信ルーティング コンポーネントは、そのユーザーの登録済み SIP エンドポイントに呼び出しを配布します。</span><span class="sxs-lookup"><span data-stu-id="e8339-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="e8339-145">User Services は、すべてのフロントエンド サーバーとディレクターのコア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e8339-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="e8339-146">**ユーザー レプリケーター。**</span><span class="sxs-lookup"><span data-stu-id="e8339-146">**User Replicator.**</span></span> <span data-ttu-id="e8339-147">Active Directory ドメイン サービスからユーザーの電話番号を抽出し、RTC データベース内のテーブルに書き込み、ユーザー サービスとアドレス帳サーバーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8339-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="e8339-148">ユーザー レプリケーターは、すべてのフロントエンド サーバーのコア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e8339-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="e8339-149">**アドレス帳サーバー。**</span><span class="sxs-lookup"><span data-stu-id="e8339-149">**Address Book Server.**</span></span> <span data-ttu-id="e8339-150">Active Directory ドメイン サービスから Skype for Business Server クライアントへのグローバル アドレス一覧情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8339-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="e8339-151">また、RTC データベースからユーザーと連絡先情報を取得し、アドレス帳ファイルに情報を書き込み、Skype for Business クライアントがダウンロードする共有フォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e8339-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="e8339-152">アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。これは、Skype for Business モバイルからのユーザー検索クエリに応答するためにアドレス帳 Web クエリ サービスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8339-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="e8339-153">必要に応じて、Skype for Business でユーザー連絡先をプロビジョニングするために RTC データベースに書き込まれるエンタープライズ ユーザーの電話番号を正規化します。</span><span class="sxs-lookup"><span data-stu-id="e8339-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="e8339-154">アドレス帳サービスは、既定ですべてのフロントエンド サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8339-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="e8339-155">アドレス帳 Web クエリ サービスは、既定で各フロントエンド サーバー上の Web サービスと一緒にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e8339-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>