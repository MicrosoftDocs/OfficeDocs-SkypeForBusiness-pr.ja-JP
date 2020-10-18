---
title: Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示
description: Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを表示します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d844acf542546a668c4fc086a07cd6a7bb4a8f5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577073"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="48fa8-103">Lync Server 2013 での Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="48fa8-103">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48fa8-104">_**トピックの最終更新日:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="48fa8-104">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="48fa8-105">Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API の代わりにスクリプト言語を使用するスクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="48fa8-105">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="48fa8-106">MSPL は、特定のメッセージをトランザクションベースの SIP アプリケーションにディスパッチするための機能に加えて、フィルター処理やプロキシ動作をより詳細に制御します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-106">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="48fa8-107">MSPL は、SIP メッセージのフィルター処理およびルーティングに特に使用されます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-107">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="48fa8-108">MSPL アプリケーションは UserServices モジュールと同じプロセスで動作しますが、Lync 2010 API に基づくプログラムは別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-108">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="48fa8-109">Lync server コントロールパネルの**トポロジ**グループの [**サーバーアプリケーション**] ページを使用して、lync server 2013 環境内のフロントエンドサーバーで実行される MSPL サーバーアプリケーションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-109">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="48fa8-110">この一覧には、各プールで使用できるスクリプトと、これらのスクリプトが有効になっているか、または重要と指定されているかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-110">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="48fa8-111">スクリプトは、一覧表示された順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-111">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="48fa8-112">これらのスクリプトには次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="48fa8-112">These scripts include the following:</span></span>

  - <span data-ttu-id="48fa8-p103">ClientVersionFilter では、プールによりサポートされるクライアントのバージョンを指定できます。クライアント バージョン フィルターを使用してクライアントのバージョンを確認し、クライアントがログオンできないようにするか、ユーザーがサポート対象外のクライアントを使用していることを知らせるメッセージを表示できます。最新バージョンのクライアントをダウンロードできる URL がメッセージとして表示されるように、クライアント バージョン フィルターを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="48fa8-116">TranslationService は、ユーザーがダイヤルした番号を、管理者によって定義された正規化ルールに従って E.164 番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-116">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="48fa8-117">詳細については、「 [Lync Server 2013 の変換ルール](lync-server-2013-translation-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48fa8-117">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="48fa8-118">IncomingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、テナント間のメッセージと外部展開から受信するメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-118">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="48fa8-p105">UserServices は、フロントエンド サーバーの SIP レジストラー、プレゼンス、および会議コンポーネントです。また、SIP プロキシ上に構築され、密接に統合された IM、プレゼンス、および電話会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="48fa8-121">InterClusterRouting は、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="48fa8-121">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="48fa8-122">詳細については、「 [Lync server 2013 のフロントエンドサーバー VoIP コンポーネント](lync-server-2013-front-end-server-voip-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48fa8-122">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="48fa8-123">IIMFilter (インテリジェント IM フィルター) は、クリック可能な Url を含むメッセージまたはファイル転送を開始しようとするメッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="48fa8-123">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="48fa8-124">IIMFilter は、サーバーに代わってクライアントバージョンも確認します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-124">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="48fa8-125">IIMFilter は、Lync Server または Communicator を使用して開始されるファイル転送に影響します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-125">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="48fa8-126">既定では、リンクの最初の文字の前にアンダースコア文字を追加することによって、クリック可能なリンクが無効になります。</span><span class="sxs-lookup"><span data-stu-id="48fa8-126">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="48fa8-127">管理者はこの動作を変更して、リンクがブロックされるようにすることができます。この場合、クリック可能な Url を含むメッセージまたはファイル転送を開始しようとするメッセージは、目的の宛先に到達してもサーバーによってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-127">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="48fa8-128">IIMFilter は、プロキシサーバーおよびアーカイブサーバーを除く、Lync Server を実行しているすべてのサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-128">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="48fa8-129">UserPinService は、ユーザーのダイヤルイン会議の暗証番号 (PIN) を確認するために使用します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-129">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="48fa8-130">DefaultRouting は、Lync Server を実行しているサーバーの既定のルーティングアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="48fa8-130">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="48fa8-131">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="48fa8-131">It is enabled by default.</span></span> <span data-ttu-id="48fa8-132">このルーティング アプリケーションは、すべての Standard Edition サーバーおよび Enterprise Edition サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-132">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="48fa8-p109">ExumRouting は、Exchange Server ユニファイド メッセージング (UM) の呼び出しをルーティングします。また、預かっている新しいボイス メール メッセージがあるときに適切な Exchange UM サーバーを決定し、通話をルーティングします。さらに、ExumRouting は Exchange UM 統合の他の機能 (自動応答、サブスクライバー アクセスへのルーティングなど) も処理します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="48fa8-p110">OutboundRouting は、ダイヤルされた番号およびユーザーのダイヤル承認に従って電話番号への通話をルーティングするゲートウェイを決定します。さらに、OutboundRouting は、ゲートウェイが通話を処理できない場合に通話の再ルーティングも処理します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="48fa8-138">QoEAgent は、SIP SERVICE 要求を使用してエンドポイントから QoE (Quality of Experience) データのレポートを受信し、HTTP POST を使用して、データを監視サーバー上の送信先キューまたはサードパーティのコンシューマーに送信します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-138">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="48fa8-139">詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48fa8-139">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="48fa8-140">OutgoingFederation は、テナントレベルのフェデレーション検証を強制的に実行して、対象となる外部展開に送信されるメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-140">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="48fa8-141">AcpRouting は、プロキシとして、電話会議プロバイダー宛ての INVITE 要求を電話会議プロバイダー ゲートウェイに代わりに送信します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-141">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="48fa8-142">エッジ サーバー上で実行されるスクリプトには次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="48fa8-142">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="48fa8-143">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="48fa8-143">IIMFilter</span></span>

  - <span data-ttu-id="48fa8-144">OptionsHandler は、現在のサーバー宛ての OPTIONS 要求を受信すると、**200 OK** で応答します。</span><span class="sxs-lookup"><span data-stu-id="48fa8-144">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="48fa8-145">これは、トポロジ検証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="48fa8-145">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="48fa8-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="48fa8-146">See Also</span></span>


[<span data-ttu-id="48fa8-147">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="48fa8-147">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="48fa8-148">Lync Server 2013 で、Microsoft SIP 処理言語 (MSPL) アプリケーションを重要または重要ではないとしてマークする</span><span class="sxs-lookup"><span data-stu-id="48fa8-148">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

