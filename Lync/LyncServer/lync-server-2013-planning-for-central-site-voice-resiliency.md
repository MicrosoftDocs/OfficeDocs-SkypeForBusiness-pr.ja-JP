---
title: 'Lync Server 2013: 中央サイトの音声の復元の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a61a07ae14f004b406aa38ef783a1c873f2128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="ab800-102">Lync Server 2013 での中央サイトの音声の復元の計画</span><span class="sxs-lookup"><span data-stu-id="ab800-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab800-103">_**トピックの最終更新日:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="ab800-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="ab800-104">世界中に多数のサイトを持つ企業がますます増えています。</span><span class="sxs-lookup"><span data-stu-id="ab800-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="ab800-105">エンタープライズ Voip の復元ソリューションには、緊急サービスの維持、ヘルプデスクへのアクセス、および中央サイトがサービス停止しているときの重要なビジネスタスクの実施能力が重要です。</span><span class="sxs-lookup"><span data-stu-id="ab800-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="ab800-106">中央サイトを利用できなくなった場合、以下の条件を満たすことが求められます。</span><span class="sxs-lookup"><span data-stu-id="ab800-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="ab800-107">ボイス フェールオーバーを備えることが必要です。</span><span class="sxs-lookup"><span data-stu-id="ab800-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="ab800-108">通常、中央サイトのフロントエンドプールに登録するユーザーは、別のフロントエンドプールに登録できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="ab800-109">これを行うには、複数の DNS SRV レコードを作成します。各レコードは、各中央サイトのディレクタープールまたはフロントエンドプールに解決されます。</span><span class="sxs-lookup"><span data-stu-id="ab800-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="ab800-110">SRV レコードの優先度と重みを調整して、その中央サイトで提供されているユーザーが、対応するディレクターおよびフロントエンドプールを他の SRV レコードのより前に移動できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab800-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="ab800-111">他のサイトに存在するユーザーとの通話を、PSTN に再ルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="ab800-112">このトピックでは、中央サイトの音声復元をセキュリティ保護するための推奨ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ab800-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="ab800-113">アーキテクチャおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="ab800-113">Architecture and Topology</span></span>

<span data-ttu-id="ab800-114">中央サイトでの音声復元を計画するには、音声フェールオーバーを有効にするために Lync Server 2013 レジストラーによって実行される中央の役割に関する基本的な知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab800-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="ab800-115">Lync Server レジストラーは、クライアントの登録と認証を可能にし、ルーティングサービスを提供するサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="ab800-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="ab800-116">これは、Standard Edition サーバー、フロントエンドサーバー、ディレクター、または存続可能ブランチアプライアンス上の他のコンポーネントと一緒に存在します。</span><span class="sxs-lookup"><span data-stu-id="ab800-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="ab800-117">レジストラープールは、フロントエンドプールで実行され、同じサイトに存在するレジストラーサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab800-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="ab800-118">フロントエンドプールは負荷分散されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="ab800-119">DNS 負荷分散をお勧めしますが、ハードウェア負荷分散でも十分です。</span><span class="sxs-lookup"><span data-stu-id="ab800-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="ab800-120">Lync クライアントは、次の検出メカニズムを使用してフロントエンドプールを検出します。</span><span class="sxs-lookup"><span data-stu-id="ab800-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="ab800-121">DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="ab800-121">DNS SRV record</span></span>

2.  <span data-ttu-id="ab800-122">Autodiscovery Web サービス (Lync Server 2013 の新)</span><span class="sxs-lookup"><span data-stu-id="ab800-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="ab800-123">DHCP オプション 120</span><span class="sxs-lookup"><span data-stu-id="ab800-123">DHCP option 120</span></span>

<span data-ttu-id="ab800-124">Lync クライアントは、フロントエンドプールに接続した後、ロードバランサーによってプール内のフロントエンドサーバーの1つに転送されます。</span><span class="sxs-lookup"><span data-stu-id="ab800-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="ab800-125">そのフロントエンドサーバーは、プール内の優先レジストラーにクライアントをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="ab800-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="ab800-126">エンタープライズ Voip が有効になっている各ユーザーは、そのユーザーのプライマリレジストラープールになる特定のレジストラープールに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ab800-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="ab800-127">特定のサイトで、通常、数百人または数千人のユーザーが 1 つのプライマリ レジストラー プールを共有します。</span><span class="sxs-lookup"><span data-stu-id="ab800-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="ab800-128">プレゼンス、会議、またはフェールオーバーのために中央サイトに依存するブランチ サイトのユーザーによる中央サイトのリソース消費に対応するには、各ブランチ サイトのユーザーを、中央サイトに登録されたユーザーと同様に扱うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab800-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="ab800-129">現時点では、存続可能ブランチアプライアンスに登録されているユーザーを含む、ブランチサイトのユーザー数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ab800-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="ab800-130">中央サイトの障害時に音声を確実に復元するには、プライマリ レジストラー プールで、別のサイトに配置された単一のバックアップ レジストラー プールを指定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="ab800-131">バックアップは、トポロジビルダーの復元設定を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="ab800-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="ab800-132">2 つのサイト間の WAN リンクが復元できている場合は、プライマリ レジストラー プールを使用できなくなったユーザーは自動的にバックアップ レジストラー プールにダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="ab800-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="ab800-133">以下のステップでは、クライアントの検出と登録のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ab800-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="ab800-134">クライアントは、DNS SRV レコードを使用して Lync Server を検出します。</span><span class="sxs-lookup"><span data-stu-id="ab800-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="ab800-135">Lync Server 2013 では、dns srv レコードを構成して、DNS SRV クエリに複数の FQDN を戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab800-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="ab800-136">たとえば、企業 Contoso に 3 つの中央サイト (北米、欧州、およびアジア太平洋) があり、各中央サイトにディレクター プールがある場合、DNS SRV レコードで 3 つの各場所のディレクター プールの FQDN を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab800-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="ab800-137">いずれかの場所のディレクタープールが使用可能であれば、クライアントは最初のホップの Lync Server に接続できます。</span><span class="sxs-lookup"><span data-stu-id="ab800-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab800-138">ディレクタープールの使用はオプションです。</span><span class="sxs-lookup"><span data-stu-id="ab800-138">Using a Director pool is optional.</span></span> <span data-ttu-id="ab800-139">代わりに、フロントエンドプールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab800-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="ab800-140">ディレクタープールは、ユーザーのプライマリレジストラープールとバックアップレジストラープールについて、Lync クライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="ab800-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="ab800-141">Lync クライアントは、最初にユーザーのプライマリレジストラープールへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="ab800-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="ab800-142">プライマリ レジストラー プールが使用可能な場合、レジストラーは登録を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="ab800-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="ab800-143">プライマリレジストラープールを使用できない場合、Lync クライアントはバックアップレジストラープールへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="ab800-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="ab800-144">バックアップ レジストラー プールが使用可能であり、(指定したフェールオーバーの間隔でハートビートが送信されないことを検出して) ユーザーのプライマリ レジストラー プールを使用できないと判断された場合、バックアップ レジストラー プールはユーザーの登録を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="ab800-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="ab800-145">バックアップレジストラーがプライマリレジストラーが再度利用可能であることを検出すると、バックアップレジストラープールによってフェールオーバー Lync クライアントがプライマリプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="ab800-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="ab800-p110">以下の図に、中央サイトの復元を確実にするための推奨トポロジを示します。 2 つのサイトは復元 WAN リンクで接続されています。 中央サイトが使用できなくなると、そのプールに割り当てられているユーザーは、バックアップ サイトにダイレクトされて登録が行われます。</span><span class="sxs-lookup"><span data-stu-id="ab800-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="ab800-149">**中央サイトの音声復元を確保する推奨トポロジ**</span><span class="sxs-lookup"><span data-stu-id="ab800-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="ab800-150">![中央サイトのボイスサイクルのトポロジ](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央サイトのボイスサイクルのトポロジ")</span><span class="sxs-lookup"><span data-stu-id="ab800-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="ab800-151">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="ab800-151">Requirements and Recommendations</span></span>

<span data-ttu-id="ab800-152">中央サイトで音声復元を実装するための要件と推奨事項は、たいていの組織で適しています。</span><span class="sxs-lookup"><span data-stu-id="ab800-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="ab800-153">プライマリおよびバックアップ レジストラー プールのあるサイトは、復元 WAN リンクで接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="ab800-154">各中央サイトには、1 つ以上のレジストラーで構成されるレジストラー プールが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="ab800-155">各レジストラープールは、DNS 負荷分散、ハードウェア負荷分散、またはその両方を使用して負荷分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="ab800-156">負荷分散構成の計画の詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab800-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="ab800-157">各ユーザーは、Lync Server 管理シェル**セット、CsUser**コマンドレット、または Lync Server コントロールパネルのどちらかを使用して、プライマリレジストラープールに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="ab800-158">プライマリ レジストラー プールは、別の中央サイトに配置されたバックアップ レジストラー プールを 1 つ持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="ab800-159">プライマリ レジストラー プールは、バックアップ レジストラー プールにフェールオーバーするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="ab800-160">既定では、プライマリ レジストラーは 300 秒の間隔が経過した後でバックアップ レジストラー プールにフェールオーバーするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="ab800-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="ab800-161">この間隔は、Lync Server 2013 トポロジビルダーを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab800-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="ab800-162">「計画」のドキュメントの「[Lync Server でのフェールオーバールートの構成 2013](lync-server-2013-configuring-a-failover-route.md)」の説明に従って、フェールオーバールートを構成します。</span><span class="sxs-lookup"><span data-stu-id="ab800-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="ab800-163">ルートを構成する際、プライマリ ルートで指定されたゲートウェイとは別のサイトにあるゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab800-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="ab800-164">中央サイトにプライマリ管理サーバーがあり、サイトが長期間ダウンする可能性が高い場合、管理ツールをバックアップ サイトに再インストールする必要があります。そうしないと、どの管理設定も変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ab800-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="ab800-165">依存関係</span><span class="sxs-lookup"><span data-stu-id="ab800-165">Dependencies</span></span>

<span data-ttu-id="ab800-166">Lync Server は、次のインフラストラクチャおよびソフトウェアコンポーネントに依存して、音声の復元を保証します。</span><span class="sxs-lookup"><span data-stu-id="ab800-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab800-167"><strong>コンポーネント</strong></span><span class="sxs-lookup"><span data-stu-id="ab800-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="ab800-168"><strong>的</strong></span><span class="sxs-lookup"><span data-stu-id="ab800-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab800-169">DNS</span><span class="sxs-lookup"><span data-stu-id="ab800-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="ab800-170">SRV レコードおよび A レコードを解決して、サーバー間の接続およびサーバーとクライアント間の接続を確立</span><span class="sxs-lookup"><span data-stu-id="ab800-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab800-171">Exchange および Exchange Web サービス (EWS)</span><span class="sxs-lookup"><span data-stu-id="ab800-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="ab800-172">コンタクト ストレージ、予定表データ</span><span class="sxs-lookup"><span data-stu-id="ab800-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab800-173">Exchange ユニファイド メッセージングおよび Exchange Web サービス</span><span class="sxs-lookup"><span data-stu-id="ab800-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="ab800-174">通話ログ、ボイス メール一覧、ボイス メール</span><span class="sxs-lookup"><span data-stu-id="ab800-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab800-175">DHCP オプション 120</span><span class="sxs-lookup"><span data-stu-id="ab800-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="ab800-176">DNS SRV を使用できない場合、クライアントは DHCP オプション 120 を使用してレジストラーの検出を試みます。</span><span class="sxs-lookup"><span data-stu-id="ab800-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="ab800-177">これを動作させるには、DHCP サーバーを構成するか、Lync Server 2013 DHCP を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="ab800-178">詳細については、「 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチサイトの復元要件</a>」の「ハードウェア要件とソフトウェア要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab800-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="ab800-179">存続可能な音声機能</span><span class="sxs-lookup"><span data-stu-id="ab800-179">Survivable Voice Features</span></span>

<span data-ttu-id="ab800-180">前述の要件と推奨事項が実装されている場合は、以下の音声機能がバックアップ レジストラー プールによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="ab800-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="ab800-181">PSTN 通話の発信</span><span class="sxs-lookup"><span data-stu-id="ab800-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="ab800-182">テレフォニー サービス プロバイダーがバックアップ サイトへのフェールオーバー機能をサポートしている場合は、PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="ab800-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="ab800-183">同じサイトおよび 2 つの異なるサイト間でのユーザー同士のエンタプライズ通話</span><span class="sxs-lookup"><span data-stu-id="ab800-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="ab800-184">通話の保留、取得、転送などの基本的な通話処理</span><span class="sxs-lookup"><span data-stu-id="ab800-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="ab800-185">2 者間のインスタント メッセージングおよび同じサイトでのユーザー間のオーディオとビデオの共有</span><span class="sxs-lookup"><span data-stu-id="ab800-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="ab800-186">着信の転送、エンドポイントの同時呼び出し、通話委任、およびチーム通話サービス。ただし、通話委任の両者または全チーム メンバーが同じサイトで構成されている場合のみ。</span><span class="sxs-lookup"><span data-stu-id="ab800-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="ab800-187">既存の電話およびクライアントは動作し続けます。</span><span class="sxs-lookup"><span data-stu-id="ab800-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="ab800-188">通話詳細記録 (CDR)</span><span class="sxs-lookup"><span data-stu-id="ab800-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="ab800-189">認証と承認</span><span class="sxs-lookup"><span data-stu-id="ab800-189">Authentication and authorization</span></span>

<span data-ttu-id="ab800-190">プライマリ中央サイトがサービス停止になったときに以下の音声機能が動作するかどうかは、その構成方法によります。</span><span class="sxs-lookup"><span data-stu-id="ab800-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="ab800-191">ボイス メールの預かりと取得</span><span class="sxs-lookup"><span data-stu-id="ab800-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="ab800-192">プライマリ中央サイトがサービス停止になっているときに Exchange UM を使用可能にするには、以下のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="ab800-193">中央サイトの Exchange UM サーバーが別のサイトのバックアップ Exchange UM サーバーをポイントするように、DNS SRV レコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="ab800-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="ab800-194">中央サイトとバックアップサイトの両方に Exchange UM サーバーを含めるように各ユーザーの Exchange UM ダイヤルプランを構成します。ただし、バックアップ Exchange UM サーバーを無効に指定します。</span><span class="sxs-lookup"><span data-stu-id="ab800-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="ab800-195">プライマリサイトが使用できなくなった場合、Exchange 管理者は、バックアップサイトで Exchange UM サーバーを有効にしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab800-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="ab800-196">上記のどちらの解決策も実行できない場合は、中央サイトが使用できなくなったときに Exchange UM を使用できません。</span><span class="sxs-lookup"><span data-stu-id="ab800-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="ab800-197">すべての種類の会議</span><span class="sxs-lookup"><span data-stu-id="ab800-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="ab800-p116">バックアップ サイトにフェールオーバーしたユーザーは、プールを使用できる開催者によって作成またはホストされる会議に出席できますが、使用不可になった自身のプライマリ プールで会議を作成またはホストすることはできません。 他のユーザーも、そのユーザーのプライマリ プールでホストされる会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab800-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="ab800-200">以下の音声機能は、プライマリ中央サイトが停止しているときには動作しません。</span><span class="sxs-lookup"><span data-stu-id="ab800-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="ab800-201">会議自動アテンダント</span><span class="sxs-lookup"><span data-stu-id="ab800-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="ab800-202">プレゼンスおよび DND ベースのルーティング</span><span class="sxs-lookup"><span data-stu-id="ab800-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="ab800-203">着信の転送設定の更新</span><span class="sxs-lookup"><span data-stu-id="ab800-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="ab800-204">応答グループ サービスとコール パーク</span><span class="sxs-lookup"><span data-stu-id="ab800-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="ab800-205">新しい電話とクライアントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="ab800-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="ab800-206">アドレス帳 Web 検索</span><span class="sxs-lookup"><span data-stu-id="ab800-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab800-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab800-207">See Also</span></span>


[<span data-ttu-id="ab800-208">Lync Server 2013 でのブランチサイトの音声の復元の計画</span><span class="sxs-lookup"><span data-stu-id="ab800-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

