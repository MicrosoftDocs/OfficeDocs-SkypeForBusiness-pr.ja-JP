---
title: 'Lync Server 2013: Web サービス URL の変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9eb2922913ee95bad11273b2e943812850da4402
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517820"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="f8cdd-102">Lync Server 2013 で Web サービスの URL を変更する</span><span class="sxs-lookup"><span data-stu-id="f8cdd-102">Change the Web Services URL in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8cdd-103">_**トピックの最終更新日:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="f8cdd-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="f8cdd-104">フロントエンドプールおよび Standard Edition サーバーをセットアップする際に、外部 Web ファームの完全修飾ドメイン名 (FQDN) と関連するポートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="f8cdd-105">Lync Server 展開ウィザードを実行したときにこの URL を構成しなかった場合は、これらの設定を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="f8cdd-106">通常、管理者はこれらの設定を変更する必要はありません。これらは推奨される既定のポートです。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8cdd-107">Standard Edition サーバーの構成中に次のスクリーンショットが実行されたため、[上書き FQDN] オプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="f8cdd-108">このオプションは、フロントエンドプールで Enterprise Edition サーバーを構成するときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="f8cdd-109">![Web サービスのプール設定の編集](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Web サービスのプール設定の編集")</span><span class="sxs-lookup"><span data-stu-id="f8cdd-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="f8cdd-110">Web サービスを構成するには</span><span class="sxs-lookup"><span data-stu-id="f8cdd-110">To configure web services</span></span>

1.  <span data-ttu-id="f8cdd-111">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="f8cdd-112">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="f8cdd-113">トポロジビルダーのコンソールツリーで、[ **Standard Edition フロントエンドサーバー**]、[ **Enterprise Edition フロントエンドプール**]、[ **ディレクトリプール**] の順にクリックし、プール名を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="f8cdd-114">名前を右クリックし、[ **プロパティの編集**]、[ **Web サービス**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="f8cdd-115">[ **外部 Web サービスの FQDN**] を追加または編集し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f8cdd-116">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="f8cdd-117">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を <STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに <STRONG>pool01.contoso.com</STRONG> を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="f8cdd-118">ディレクターを展開している場合は、ディレクターまたはディレクタープールに対して定義されている外部 Web サービスの FQDN が、他のすべてのディレクターまたはディレクタープールと、フロントエンドプールまたはフロントエンドサーバーとも一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="f8cdd-119">リッスンポートと公開ポートが環境に対して正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="f8cdd-120">環境内のすべての Standard Edition サーバー、フロントエンドプール、およびディレクタープールに対して、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="f8cdd-121">コンソールツリーで、[ **Lync Server 2013**] をクリックし、[ **操作** ] ウィンドウで [ **トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="f8cdd-122">リッスンポートと発行ポートを構成する際には、いくつかの要件を認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="f8cdd-123">表示されるリスニングポートは、各フロントエンドサーバー上のインターネットインフォメーションサービス (IIS) 用に構成されているポートです。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="f8cdd-124">内部および外部のリスニングポートは IIS で異なる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="f8cdd-125">外部リスニングポートについては、通常、内部 web トラフィック用のハードウェアロードバランサーを表し、もう1つは外部 web トラフィック用のリバースプロキシサーバーを表します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="f8cdd-126">フロントエンドプール、ディレクター、またはディレクタープールの内部 web サービスを上書きして、独自の FQDN を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f8cdd-127">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="f8cdd-128">公開ポートは、リバースプロキシまたはハードウェアロードバランサー上で、リッスンポートとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="f8cdd-129">フロントエンドプール (例には示されていません) の場合、web トラフィックはハードウェアロードバランサーを通過し、内部 SIP プールトラフィックは DNS ロードバランサーを経由するため、内部 SIP プールの FQDN は内部 web サービスの FQDN とは別のものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="f8cdd-130">この要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-130">This requirement must be met.</span></span>

  - <span data-ttu-id="f8cdd-131">Lync Server Standard Edition の展開では、このサーバーの負荷分散ができないため、内部 web サービスの FQDN を上書きする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="f8cdd-132">内部 SIP と web トラフィックの両方で使用している環境にハードウェアロードバランサーがある場合は、トポロジビルダーで区別することはできません。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="f8cdd-133">Web サービスの Fqdn は、相互に簡単に区別する必要があります。これにより、URL リダイレクトがクライアントを適切なサーバーに確実に参照できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="f8cdd-134">たとえば、2つの Fqdn がある場合は、1つの meeting.contoso.com とその他の conferencing.contoso.com に名前を付けることを検討します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="f8cdd-135">Meet1.contoso.com や meet2.contoso.com など、似た名前の Fqdn を使用している場合は、リダイレクトの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="f8cdd-136">外部 web サービスは、境界ネットワークのリバースプロキシと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="f8cdd-137">これらの web サービスを使用してクライアントに外部アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="f8cdd-138">ここで構成された Fqdn は、ユーザーがログオンしたときにクライアントに送信され、リモート接続時にリバースプロキシに HTTPS 接続を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="f8cdd-139">リバースプロキシサーバーは、外部 web サービスの FQDN を内部のハードウェアロードバランサーに転送するか、直接プールに転送します。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="f8cdd-140">リバースプロキシは、外部 web サービスの FQDN を内部 Web サーバーの IP アドレスに解決できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="f8cdd-141">外部 web サービスの FDQN、パブリックインターネットで解決可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="f8cdd-142">内部サーバーが Standard Edition サーバーの場合、内部 FQDN は Standard Edition サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="f8cdd-143">内部サーバーがフロントエンドプールの場合、FQDN は、内部 web ファームサーバーの負荷を分散するハードウェアロードバランサー仮想 IP (VIP) です。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="f8cdd-144">複数の Enterprise Edition サーバーを使用するフロントエンドプールには、ロードバランサー機器が必要です。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="f8cdd-145">Standard Edition サーバーまたは1つの Enterprise Edition フロントエンドサーバーでロードバランサーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f8cdd-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

