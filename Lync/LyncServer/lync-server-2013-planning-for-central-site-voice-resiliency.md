---
title: 'Lync Server 2013: 中央サイトの音声の復元の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="92565-102">Lync Server 2013 での中央サイトの音声の復元の計画</span><span class="sxs-lookup"><span data-stu-id="92565-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92565-103">_**最終更新日:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="92565-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="92565-104">世界中に多数のサイトを持つ企業がますます増えています。</span><span class="sxs-lookup"><span data-stu-id="92565-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="92565-105">緊急サービスの管理、ヘルプデスクへのアクセス、および中央サイトがサービスを利用していないときに重要なビジネスタスクを実施する機能は、エンタープライズボイスの回復性ソリューションにとって不可欠です。</span><span class="sxs-lookup"><span data-stu-id="92565-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="92565-106">中央サイトを利用できなくなった場合、以下の条件を満たすことが求められます。</span><span class="sxs-lookup"><span data-stu-id="92565-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="92565-107">ボイス フェールオーバーを備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="92565-108">セントラルサイトのフロントエンドプールに通常登録したユーザーは、代替のフロントエンドプールを使って登録できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="92565-109">この操作を行うには、複数の DNS SRV レコードを作成します。各レコードは、それぞれのセントラルサイトのディレクタープールまたはフロントエンドプールに解決されます。</span><span class="sxs-lookup"><span data-stu-id="92565-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="92565-110">SRV レコードの優先度と重みを調整して、そのセントラルサイトによって提供されるユーザーが、他の SRV レコードで対応するディレクターとフロントエンドプールを事前に取得できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="92565-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="92565-111">他のサイトに存在するユーザーとの通話を、PSTN に再ルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="92565-112">このトピックでは、中央サイトの音声復元をセキュリティ保護するための推奨ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92565-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="92565-113">アーキテクチャおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="92565-113">Architecture and Topology</span></span>

<span data-ttu-id="92565-114">中央サイトでの音声回復性を計画するには、ボイスのフェールオーバーを有効にするために、Lync Server 2013 レジストラーで再生される中心的役割の基本を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="92565-115">Lync Server レジストラーは、クライアントの登録と認証を可能にし、ルーティングサービスを提供するサーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="92565-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="92565-116">Standard Edition server、フロントエンドサーバー、ディレクター、または Survivable Branch Appliance の他のコンポーネントと共に存在します。</span><span class="sxs-lookup"><span data-stu-id="92565-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="92565-117">レジストラープールは、フロントエンドプールで実行され、同じサイトに存在するレジストラーサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="92565-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="92565-118">フロントエンドプールは負荷分散されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="92565-119">DNS の負荷分散は推奨されますが、ハードウェアの負荷分散は受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="92565-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="92565-120">Lync クライアントは、次の検出メカニズムを使用して、フロントエンドプールを検出します。</span><span class="sxs-lookup"><span data-stu-id="92565-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="92565-121">DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="92565-121">DNS SRV record</span></span>

2.  <span data-ttu-id="92565-122">Autodiscovery Web Service (Lync Server 2013 での新規)</span><span class="sxs-lookup"><span data-stu-id="92565-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="92565-123">DHCP オプション 120</span><span class="sxs-lookup"><span data-stu-id="92565-123">DHCP option 120</span></span>

<span data-ttu-id="92565-124">Lync クライアントは、フロントエンドプールに接続した後、ロードバランサーによってプール内のいずれかのフロントエンドサーバーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="92565-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="92565-125">そのフロントエンドサーバーによって、プール内の優先レジストラーにクライアントがリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="92565-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="92565-126">エンタープライズ Voip が有効になっている各ユーザーは、特定のレジストラープールに割り当てられ、そのユーザーのプライマリレジストラープールになります。</span><span class="sxs-lookup"><span data-stu-id="92565-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="92565-127">サイトでは、数百人または数千人のユーザーが 1 つのプライマリ レジストラー プールを共有するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="92565-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="92565-128">プレゼンス、会議、またはフェールオーバーのために中央サイトに依存するブランチ サイトのユーザーによる中央サイトのリソース消費に対応するには、各ブランチ サイトのユーザーを、中央サイトに登録されたユーザーと同様に扱うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92565-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="92565-129">現時点では、Survivable Branch Appliance に登録されているユーザーを含む、ブランチサイトユーザーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="92565-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="92565-130">中央サイトの障害時に音声を確実に復元するには、プライマリ レジストラー プールで、別のサイトに配置された単一のバックアップ レジストラー プールを指定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="92565-131">バックアップを構成するには、トポロジビルダーの回復可能設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="92565-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="92565-132">2 つのサイト間の WAN リンクが復元できている場合、プライマリ レジストラー プールを使用できなくなったユーザーは自動的にバックアップ レジストラー プールにダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="92565-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="92565-133">以下のステップでは、クライアントの検出と登録のプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92565-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="92565-134">クライアントが DNS SRV レコードを通じて Lync サーバーを検出します。</span><span class="sxs-lookup"><span data-stu-id="92565-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="92565-135">Lync Server 2013 で、DNS SRV レコードを構成して、複数の FQDN を DNS SRV クエリに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="92565-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="92565-136">たとえば、企業 Contoso に 3 つの中央サイト (北米、欧州、およびアジア太平洋) があり、各中央サイトにディレクター プールがある場合、DNS SRV レコードで 3 つの各場所のディレクター プールの FQDN を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="92565-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="92565-137">いずれかの場所にあるディレクタープールが利用可能であれば、クライアントは第1ホップの Lync Server に接続できます。</span><span class="sxs-lookup"><span data-stu-id="92565-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92565-138">ディレクタープールの使用は任意です。</span><span class="sxs-lookup"><span data-stu-id="92565-138">Using a Director pool is optional.</span></span> <span data-ttu-id="92565-139">代わりに、フロントエンドプールを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="92565-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="92565-140">ディレクタープールは、ユーザーのプライマリレジストラープールとバックアップレジストラープールについて、Lync クライアントに通知します。</span><span class="sxs-lookup"><span data-stu-id="92565-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="92565-141">Lync クライアントは、最初にユーザーのプライマリレジストラープールに接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="92565-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="92565-142">プライマリ レジストラー プールが使用可能な場合、レジストラーは登録を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="92565-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="92565-143">プライマリレジストラープールを利用できない場合、Lync クライアントはバックアップレジストラープールへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="92565-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="92565-144">バックアップ レジストラー プールが使用可能であり、(指定したフェールオーバーの間隔でハートビートが送信されないことを検出して) ユーザーのプライマリ レジストラー プールを使用できないと判断された場合、バックアップ レジストラー プールはユーザーの登録を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="92565-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="92565-145">バックアップレジストラーによってプライマリレジストラーが再び利用可能であることが検出されると、バックアップレジストラープールによってフェールオーバー Lync クライアントがプライマリプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="92565-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="92565-146">次の図は、セントラルサイトの回復性を保証するための推奨されるトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="92565-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="92565-147">2つのサイトは、回復性のある WAN リンクによって接続されています。</span><span class="sxs-lookup"><span data-stu-id="92565-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="92565-148">セントラルサイトが利用できなくなった場合、そのプールに割り当てられているユーザーは、登録のためにバックアップサイトに転送されます。</span><span class="sxs-lookup"><span data-stu-id="92565-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="92565-149">**セントラルサイトのボイス回復性の推奨されるトポロジ**</span><span class="sxs-lookup"><span data-stu-id="92565-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="92565-150">![中央サイトのボイスチャットのトポロジ](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "中央サイトのボイスチャットのトポロジ")</span><span class="sxs-lookup"><span data-stu-id="92565-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="92565-151">要件と推奨事項</span><span class="sxs-lookup"><span data-stu-id="92565-151">Requirements and Recommendations</span></span>

<span data-ttu-id="92565-152">中央サイトで音声復元を実装するための以下に示す要件と推奨事項は、ほとんどの組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="92565-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="92565-153">プライマリおよびバックアップ レジストラー プールのあるサイトは、復元 WAN リンクで接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="92565-154">各中央サイトには、1 つ以上のレジストラーで構成されるレジストラー プールが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="92565-155">各レジストラー プールは、DNS 負荷分散かハードウェア負荷分散またはその両方を使用して負荷分散する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="92565-156">ロードバランシング構成の計画の詳細については、「 [Lync Server 2013 の負荷分散の要件](lync-server-2013-load-balancing-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92565-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="92565-157">各ユーザーは、Lync Server 管理シェル**セットのユーザー**コマンドレットまたは Lync Server コントロールパネルのいずれかを使用して、プライマリレジストラープールに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="92565-158">プライマリ レジストラー プールは、別の中央サイトに配置されたバックアップ レジストラー プールを 1 つ持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="92565-159">プライマリ レジストラー プールは、バックアップ レジストラー プールにフェールオーバーするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="92565-160">既定では、プライマリ レジストラーは 300 秒の間隔が経過した後でバックアップ レジストラー プールにフェールオーバーするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="92565-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="92565-161">Lync Server 2013 トポロジビルダーを使用して、この間隔を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="92565-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="92565-162">「計画ドキュメント」の「[Lync Server 2013 でのフェールオーバールートの構成](lync-server-2013-configuring-a-failover-route.md)」の説明に従って、フェールオーバールートを構成します。</span><span class="sxs-lookup"><span data-stu-id="92565-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="92565-163">ルートを構成する際、プライマリ ルートで指定されたゲートウェイとは別のサイトにあるゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="92565-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="92565-164">中央サイトにプライマリ管理サーバーがあり、サイトが長期間ダウンする可能性が高い場合、管理ツールをバックアップ サイトに再インストールする必要があります。このようにしないと、どの管理設定も変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="92565-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="92565-165">依存関係</span><span class="sxs-lookup"><span data-stu-id="92565-165">Dependencies</span></span>

<span data-ttu-id="92565-166">Lync Server は、次のインフラストラクチャとソフトウェアコンポーネントによって、ボイスの回復性を確保します。</span><span class="sxs-lookup"><span data-stu-id="92565-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92565-167"><strong>コンポーネント</strong></span><span class="sxs-lookup"><span data-stu-id="92565-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="92565-168"><strong>機能</strong></span><span class="sxs-lookup"><span data-stu-id="92565-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92565-169">DNS</span><span class="sxs-lookup"><span data-stu-id="92565-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="92565-170">SRV レコードおよび A レコードを解決して、サーバー間の接続およびサーバーとクライアント間の接続を確立</span><span class="sxs-lookup"><span data-stu-id="92565-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92565-171">Exchange および Exchange Web サービス (EWS)</span><span class="sxs-lookup"><span data-stu-id="92565-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="92565-172">コンタクト ストレージ、予定表データ</span><span class="sxs-lookup"><span data-stu-id="92565-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92565-173">Exchange ユニファイド メッセージングおよび Exchange Web サービス</span><span class="sxs-lookup"><span data-stu-id="92565-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="92565-174">通話ログ、ボイス メール一覧、ボイス メール</span><span class="sxs-lookup"><span data-stu-id="92565-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92565-175">DHCP オプション 120</span><span class="sxs-lookup"><span data-stu-id="92565-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="92565-176">DNS SRV を使用できない場合、クライアントは DHCP オプション 120 を使用してレジストラーの検出を試みます。</span><span class="sxs-lookup"><span data-stu-id="92565-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="92565-177">これを動作させるには、DHCP サーバーが構成されているか、Lync Server 2013 DHCP が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="92565-178">詳細については、「 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 でのブランチサイトの回復要件</a>」セクションの「ブランチサイトの回復性に関するハードウェアとソフトウェアの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92565-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="92565-179">存続可能な音声機能</span><span class="sxs-lookup"><span data-stu-id="92565-179">Survivable Voice Features</span></span>

<span data-ttu-id="92565-180">前述の要件と推奨事項が実装されている場合は、以下の音声機能がバックアップ レジストラー プールによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="92565-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="92565-181">PSTN 通話の発信</span><span class="sxs-lookup"><span data-stu-id="92565-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="92565-182">テレフォニー サービス プロバイダーがバックアップ サイトへのフェールオーバー機能をサポートしている場合は、PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="92565-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="92565-183">同じサイトおよび 2 つの異なるサイト間でのユーザー同士のエンタープライズ通話</span><span class="sxs-lookup"><span data-stu-id="92565-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="92565-184">通話の保留、取得、転送などの基本的な通話処理</span><span class="sxs-lookup"><span data-stu-id="92565-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="92565-185">2 者間のインスタント メッセージングおよび同じサイトでのユーザー間のオーディオとビデオの共有</span><span class="sxs-lookup"><span data-stu-id="92565-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="92565-186">着信の転送、エンドポイントの同時呼び出し、通話委任、およびチーム通話サービス。ただし、通話委任の両者または全チーム メンバーが同じサイトで構成されている場合のみ。</span><span class="sxs-lookup"><span data-stu-id="92565-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="92565-187">既存の電話およびクライアントは動作し続ける</span><span class="sxs-lookup"><span data-stu-id="92565-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="92565-188">通話詳細記録 (CDR)</span><span class="sxs-lookup"><span data-stu-id="92565-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="92565-189">認証と承認</span><span class="sxs-lookup"><span data-stu-id="92565-189">Authentication and authorization</span></span>

<span data-ttu-id="92565-190">プライマリ中央サイトがサービス停止になったときに以下の音声機能が動作するかどうかは、その構成方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="92565-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="92565-191">ボイス メールの預かりと取得</span><span class="sxs-lookup"><span data-stu-id="92565-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="92565-192">プライマリ中央サイトがサービス停止になっているときに Exchange UM を使用可能にするには、以下のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="92565-193">中央サイトの Exchange UM サーバーが別のサイトのバックアップ Exchange UM サーバーをポイントするように、DNS SRV レコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="92565-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="92565-194">中央サイトとバックアップサイトの両方に Exchange UM サーバーを含めるように、各ユーザーの Exchange UM ダイヤルプランを構成します。ただし、バックアップ Exchange UM サーバーを disabled として指定します。</span><span class="sxs-lookup"><span data-stu-id="92565-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="92565-195">プライマリサイトが利用できなくなった場合は、Exchange 管理者は、バックアップサイトで Exchange UM サーバーを有効としてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92565-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="92565-196">上記のどちらの解決方法も利用できない場合、Exchange UM は、セントラルサイトが利用できなくなった場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="92565-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="92565-197">すべての種類の会議</span><span class="sxs-lookup"><span data-stu-id="92565-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="92565-p116">バックアップ サイトにフェールオーバーしたユーザーは、プールを使用できる開催者によって作成またはホストされる会議に出席できますが、使用不可になった自身のプライマリ プールで会議を作成またはホストすることはできません。他のユーザーも、そのユーザーのプライマリ プールでホストされる会議に参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="92565-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="92565-200">以下の音声機能は、プライマリ中央サイトが停止しているときには動作しません。</span><span class="sxs-lookup"><span data-stu-id="92565-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="92565-201">会議自動アテンダント</span><span class="sxs-lookup"><span data-stu-id="92565-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="92565-202">プレゼンスおよび DND ベースのルーティング</span><span class="sxs-lookup"><span data-stu-id="92565-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="92565-203">着信の転送設定の更新</span><span class="sxs-lookup"><span data-stu-id="92565-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="92565-204">応答グループ サービスとコール パーク</span><span class="sxs-lookup"><span data-stu-id="92565-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="92565-205">新しい電話とクライアントのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="92565-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="92565-206">アドレス帳 Web 検索</span><span class="sxs-lookup"><span data-stu-id="92565-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92565-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="92565-207">See Also</span></span>


[<span data-ttu-id="92565-208">Lync Server 2013 ブランチ サイト VoIP の復元の計画</span><span class="sxs-lookup"><span data-stu-id="92565-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

