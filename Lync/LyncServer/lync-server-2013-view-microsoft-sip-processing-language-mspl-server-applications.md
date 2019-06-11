---
title: Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="e9906-102">Lync Server 2013 での Microsoft SIP 処理言語  (MSPL) サーバー アプリケーションの表示</span><span class="sxs-lookup"><span data-stu-id="e9906-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9906-103">_**最終更新日:** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="e9906-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="e9906-104">Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションは、Microsoft Lync 2010 API ではなく、スクリプト言語を使用するスクリプトのみのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e9906-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="e9906-105">MSPL は、特定のメッセージをトランザクションベースの SIP アプリケーションにディスパッチするための機能に加えて、フィルター処理とプロキシ動作をより細かく制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9906-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="e9906-106">MSPL は、特に SIP メッセージのフィルター処理とルーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e9906-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="e9906-107">MSPL アプリケーションは UserServices モジュールと同じプロセスで実行されますが、Lync 2010 API に基づくプログラムは別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e9906-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="e9906-108">Lync server コントロールパネルの [**トポロジ**] グループの [**サーバーアプリケーション**] ページを使用して、lync Server 2013 環境のフロントエンドサーバーで実行される MSPL Server アプリケーションの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e9906-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="e9906-109">一覧には、各プールで利用可能なスクリプトと、それらが有効または重要であるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9906-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="e9906-110">スクリプトは、一覧表示されている順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e9906-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="e9906-111">これらのスクリプトには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e9906-111">These scripts include the following:</span></span>

  - <span data-ttu-id="e9906-112">ClientVersionFilter を使うと、管理者はプールでサポートされているクライアントのバージョンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e9906-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="e9906-113">クライアントバージョンフィルターはクライアントのバージョンを確認し、クライアントがログオンできないようにするか、サポートされていないクライアントを使っていることを示すメッセージをユーザーに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e9906-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="e9906-114">クライアントのバージョンフィルターを構成して、クライアントの最新のダウンロード可能バージョンの URL が含まれているユーザーにメッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9906-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="e9906-115">TranslationService は、管理者によって定義された正規化ルールに従って、ユーザーが E.i 番号にダイヤルする番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="e9906-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="e9906-116">詳細については、「 [Lync Server 2013 の翻訳ルール](lync-server-2013-translation-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9906-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="e9906-117">IncomingFederation は、テナント間の相互のフェデレーション検証を適用します。外部展開からのテナントと受信メッセージについては、この検証が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9906-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="e9906-118">UserServices は、フロントエンドサーバーの SIP レジストラー、プレゼンス、会議コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e9906-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="e9906-119">SIP プロキシの上に構築された、密接に統合された IM、プレゼンス、会議機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9906-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="e9906-120">InterClusterRouting は、呼び出し先のプライマリレジストラープールへの呼び出しをルーティングする責任を負います。</span><span class="sxs-lookup"><span data-stu-id="e9906-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="e9906-121">詳細については、「 [Lync Server 2013 のフロントエンドサーバー VoIP コンポーネント](lync-server-2013-front-end-server-voip-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9906-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="e9906-122">IIMFilter (インテリジェント IM フィルター) は、クリック可能な Url を含むメッセージをブロックするか、ファイル転送を開始しようとします。</span><span class="sxs-lookup"><span data-stu-id="e9906-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="e9906-123">IIMFilter は、サーバーの代わりにクライアントバージョンも確認します。</span><span class="sxs-lookup"><span data-stu-id="e9906-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="e9906-124">IIMFilter は、Lync Server または Communicator を使用して開始されたファイル転送に影響します。</span><span class="sxs-lookup"><span data-stu-id="e9906-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="e9906-125">既定では、クリック可能なリンクは、リンクの最初の文字の前にアンダースコア文字を追加することで無効になります。</span><span class="sxs-lookup"><span data-stu-id="e9906-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="e9906-126">管理者はこの動作を変更して、リンクがブロックされるようにすることができます。この場合、クリック可能な Url が含まれているメッセージ、またはファイル転送を開始しようとしても、サーバーが意図した宛先に到達するまでブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e9906-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="e9906-127">IIMFilter は、Lync Server を実行しているすべてのサーバー (プロキシサーバーとアーカイブサーバーを除く) にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e9906-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="e9906-128">UserPinService を使用して、ダイヤルイン会議のユーザー暗証番号 (Pin) を確認します。</span><span class="sxs-lookup"><span data-stu-id="e9906-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="e9906-129">DefaultRouting は、Lync Server を実行しているサーバーの既定のルーティングアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e9906-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="e9906-130">既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e9906-130">It is enabled by default.</span></span> <span data-ttu-id="e9906-131">ルーティングアプリケーションは、すべての Standard Edition および Enterprise Edition サーバーにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e9906-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="e9906-132">「ExumRouting」では、Exchange Server ユニファイドメッセージング (UM) への通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="e9906-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="e9906-133">ExumRouting は、新しいボイスメールメッセージが送信されたときに、通話をルーティングする適切な Exchange UM サーバーを決定します。</span><span class="sxs-lookup"><span data-stu-id="e9906-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="e9906-134">ExumRouting は、自動応答とサブスクライバーアクセスへのルーティングなど、その他の Exchange UM 統合機能も処理します。</span><span class="sxs-lookup"><span data-stu-id="e9906-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="e9906-135">OutboundRouting は、ダイヤルされた番号とユーザーのダイヤル承認に従って、通話を電話番号にルーティングするゲートウェイを決定します。</span><span class="sxs-lookup"><span data-stu-id="e9906-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="e9906-136">また、OutboundRouting は、ゲートウェイが通話を処理できない場合に、通話の再ルーティングも処理します。</span><span class="sxs-lookup"><span data-stu-id="e9906-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="e9906-137">QoEAgent は、SIP サービス要求によってエンドポイントから Quality of Experience (QoE) データレポートを受け取り、そのデータを監視サーバー上の送信先キューまたは HTTP POST を使ってサードパーティのコンシューマーに送信します。</span><span class="sxs-lookup"><span data-stu-id="e9906-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="e9906-138">詳細については、「 [Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9906-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="e9906-139">OutgoingFederation は、対象の外部展開に移動するメッセージに対して、テナントレベルのフェデレーション検証を適用します。</span><span class="sxs-lookup"><span data-stu-id="e9906-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="e9906-140">AcpRouting プロキシは、電話会議プロバイダーに宛てた要求を電話会議プロバイダーのゲートウェイに招待します。</span><span class="sxs-lookup"><span data-stu-id="e9906-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="e9906-141">エッジサーバー上で実行されるスクリプトには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="e9906-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="e9906-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="e9906-142">IIMFilter</span></span>

  - <span data-ttu-id="e9906-143">[オプション] は、要求が現在のサーバーを対象としている場合は、着信オプション要求に対して**200 OK**を返します。</span><span class="sxs-lookup"><span data-stu-id="e9906-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="e9906-144">これは、トポロジの検証に使われます。</span><span class="sxs-lookup"><span data-stu-id="e9906-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e9906-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9906-145">See Also</span></span>


[<span data-ttu-id="e9906-146">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) サーバーアプリケーションを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e9906-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="e9906-147">Lync Server 2013 で Microsoft SIP 処理言語 (MSPL) アプリケーションを critical または critical としてマークする</span><span class="sxs-lookup"><span data-stu-id="e9906-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

