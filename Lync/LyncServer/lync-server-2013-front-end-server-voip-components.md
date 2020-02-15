---
title: 'Lync Server 2013: フロントエンドサーバーの VoIP コンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2439099b6dd6da8ef03c7f811848ee590caaf20a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="edad9-102">Lync Server 2013 のフロントエンドサーバーの VoIP コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edad9-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="edad9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="edad9-104">フロントエンドサーバーにある VoIP コンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="edad9-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="edad9-105">変換サービス</span><span class="sxs-lookup"><span data-stu-id="edad9-105">Translation Service</span></span>

  - <span data-ttu-id="edad9-106">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-106">Inbound Routing component</span></span>

  - <span data-ttu-id="edad9-107">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-107">Outbound Routing component</span></span>

  - <span data-ttu-id="edad9-108">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="edad9-109">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="edad9-110">Lync Server 2013 の仲介サーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="edad9-111">変換サービス</span><span class="sxs-lookup"><span data-stu-id="edad9-111">Translation Service</span></span>

<span data-ttu-id="edad9-p101">変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="edad9-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="edad9-114">着信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-114">Inbound Routing Component</span></span>

<span data-ttu-id="edad9-115">着信ルーティングコンポーネントは、エンタープライズ Voip クライアントでユーザーによって指定された設定に基づいて、着信呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="edad9-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="edad9-116">着信ルーティング コンポーネントはまた、ユーザーが設定した場合に、代理人着信および同時着信を行います。</span><span class="sxs-lookup"><span data-stu-id="edad9-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="edad9-117">たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知に記録するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="edad9-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="edad9-118">着信の転送が有効になっている場合、ユーザーは、応答のない通話を別の番号に転送するか、通話応答を提供するように構成された Exchange UM サーバーに転送するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="edad9-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="edad9-119">着信ルーティングコンポーネントは、すべての Standard Edition サーバーとフロントエンドサーバーに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="edad9-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="edad9-120">発信ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-120">Outbound Routing Component</span></span>

<span data-ttu-id="edad9-121">発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="edad9-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="edad9-122">発信者に、ユーザーの音声ポリシーに定義された通話の承認ルールが適用され、それぞれの発信のルーティングに対して最適な PSTN ゲートウェイが決定されます。</span><span class="sxs-lookup"><span data-stu-id="edad9-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="edad9-123">送信ルーティングコンポーネントは、すべての Standard Edition サーバーとフロントエンドサーバーに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="edad9-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="edad9-124">発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。</span><span class="sxs-lookup"><span data-stu-id="edad9-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="edad9-125">Exchange UM ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="edad9-126">Exchange UM ルーティングコンポーネントは、lync Server と Exchange ユニファイドメッセージング (UM) を実行しているサーバーとの間のルーティングを処理して、Lync Server とユニファイドメッセージング機能を統合します。</span><span class="sxs-lookup"><span data-stu-id="edad9-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="edad9-127">Exchange um ルーティングコンポーネントは、Exchange UM サーバーが利用できない場合に、PSTN を介したボイスメールの再ルーティングも処理します。</span><span class="sxs-lookup"><span data-stu-id="edad9-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="edad9-128">中央サイトへの復元可能な WAN リンクを持たない支社サイトにエンタープライズ Voip ユーザーがいる場合、ブランチサイトに展開する存続可能ブランチアプライアンスは、WAN の停止時にブランチユーザーにボイスメール存続性を提供します。</span><span class="sxs-lookup"><span data-stu-id="edad9-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="edad9-129">WAN リンクを使用できない場合は、存続可能ブランチ アプライアンスは次を行います。</span><span class="sxs-lookup"><span data-stu-id="edad9-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="edad9-130">セントラル サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="edad9-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="edad9-131">ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="edad9-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="edad9-132">不在着信通知をキューに入れ、WAN リンクが回復した時に Exchange UM サーバーへそれらをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="edad9-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="edad9-133">ボイスメールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) を構成してメッセージのみを受け入れるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edad9-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="edad9-134">これらの機能の詳細については、「lync server [2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「 [lync server 2013 でのエンタープライズ voip の復元の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edad9-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="edad9-135">内部クラスター ルーティング コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-135">Intercluster Routing Component</span></span>

<span data-ttu-id="edad9-p105">内部クラスター ルーティング コンポーネントは、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。 それが不可能な場合、コンポーネントは、通話を呼び出し先のバックアップ レジストラー プールにルーティングします。 呼び出し先のプライマリ レジストラー プールおよびバックアップ レジストラー プールが IP ネットワークを介して到達不能の場合、内部クラスター ルーティング コンポーネントは PSTN を介して通話をユーザーの電話番号へ再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="edad9-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="edad9-139">VoIP に必要なその他のフロントエンド サーバー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="edad9-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="edad9-140">フロントエンドサーバーまたはディレクターに搭載されているその他のコンポーネントは、VoIP のサポートを提供しますが、それ自体は VoIP コンポーネントではありません。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="edad9-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="edad9-141">**ユーザー サービス。**</span><span class="sxs-lookup"><span data-stu-id="edad9-141">**User Services.**</span></span> <span data-ttu-id="edad9-142">各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。</span><span class="sxs-lookup"><span data-stu-id="edad9-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="edad9-143">この情報を使用して、着信ルーティング コンポーネントはユーザーの登録 SIP エンドポイントに通話を分散します。</span><span class="sxs-lookup"><span data-stu-id="edad9-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="edad9-144">ユーザーサービスは、すべてのフロントエンドサーバーおよびディレクターのコアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="edad9-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="edad9-145">**ユーザー レプリケーター。**</span><span class="sxs-lookup"><span data-stu-id="edad9-145">**User Replicator.**</span></span> <span data-ttu-id="edad9-146">Active Directory ドメインサービスからユーザーの電話番号を抽出し、それらを RTC データベースのテーブルに書き込みます。これは、ユーザーサービスとアドレス帳サーバーで利用できます。</span><span class="sxs-lookup"><span data-stu-id="edad9-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="edad9-147">ユーザーレプリケーターは、すべてのフロントエンドサーバー上のコアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="edad9-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="edad9-148">**アドレス帳サーバー。**</span><span class="sxs-lookup"><span data-stu-id="edad9-148">**Address Book Server.**</span></span> <span data-ttu-id="edad9-149">Active Directory ドメインサービスから Lync Server クライアントへのグローバルアドレス一覧情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="edad9-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="edad9-150">また、RTC データベースからのユーザー情報と連絡先情報を取得し、その情報をアドレス帳ファイルに書き込んだ後、それらのファイルを、Lync クライアントによってダウンロードされる共有フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="edad9-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="edad9-151">アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。このデータベースは、アドレス帳 Web クエリサービスによって、Microsoft Lync 2010 Mobile からのユーザー検索クエリに応答するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edad9-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="edad9-152">必要に応じて、Lync でユーザーの連絡先をプロビジョニングする目的で RTC データベースに書き込まれるエンタープライズユーザーの電話番号を正規化します。</span><span class="sxs-lookup"><span data-stu-id="edad9-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="edad9-153">既定では、すべてのフロントエンドサーバーにアドレス帳サービスがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="edad9-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="edad9-154">既定では、アドレス帳 Web クエリサービスは各フロントエンドサーバー上の Web サービスと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="edad9-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

