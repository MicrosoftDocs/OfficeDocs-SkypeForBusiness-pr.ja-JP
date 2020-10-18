---
title: 'Lync Server 2013: エッジトポロジの定義'
description: 'Lync Server 2013: エッジトポロジを定義します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4aa16ca23d24f0edd92189216030ef926fc841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572943"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="6790f-103">Lync Server 2013 でエッジトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="6790f-103">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6790f-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6790f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6790f-105">トポロジビルダーを使用してトポロジを構築する必要があります。また、エッジサーバーを展開する前に、少なくとも1つの内部フロントエンドプールまたは Standard Edition サーバーをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-105">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="6790f-106">次の手順を使用して、単一エッジサーバーのエッジトポロジを定義し、「Lync server [2013 でトポロジを公開](lync-server-2013-publish-your-topology.md) する」の手順を使用して、「 [lync server 2013 トポロジをエクスポートして外部メディアにコピー](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) する」で、トポロジを公開してエッジサーバーで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-106">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6790f-p102">内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。1 つのエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6790f-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="6790f-109">サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="6790f-110">サーバーの役割を追加するために必要な管理者の権限およびアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="6790f-110">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="6790f-111">詳細については、「Standard Edition サーバーまたは Enterprise Edition server 展開ドキュメント」の「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6790f-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="6790f-112">その他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要となります。</span><span class="sxs-lookup"><span data-stu-id="6790f-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="6790f-113">内部トポロジを定義して発行したときにエッジトポロジを定義し、以前に定義したエッジトポロジに変更が必要ない場合は、それを定義して再度発行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6790f-113">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="6790f-114">エッジトポロジを変更する必要がある場合にのみ、次の手順を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6790f-114">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="6790f-115">エッジサーバーでは、既に定義および公開されているトポロジを使用できるようにする必要があります。このためには、「 [Export The Lync Server 2013 topology」および「Export a external media to edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-115">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6790f-116">トポロジビルダーをエッジサーバーから実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="6790f-116">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="6790f-117">フロント エンド サーバーまたは Standard Edition サーバーから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-117">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="6790f-118">エッジサーバートポロジを定義するプロセスは、トポロジビルダーで行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-118">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="6790f-119">以下に、計画および構成する主要な 3 種類のエッジ サーバー トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="6790f-119">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="6790f-120">単一エッジ サーバーのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-120">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="6790f-121">負荷分散エッジ サーバー プールのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-121">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="6790f-122">ハードウェア負荷分散エッジ プールのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-122">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="6790f-123">単一エッジ サーバーのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-123">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="6790f-124">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-124">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6790f-125">コンソール ツリーで、エッジ サーバーを展開したいサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-125">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="6790f-126">[ **エッジプール**] を右クリックし、[ **新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-126">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="6790f-127">**[新しいエッジ プールの定義]** で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-127">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="6790f-128">[**エッジ プール FQDN の定義**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6790f-128">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-129">[**プール FQDN**] に、エッジ サーバーの内部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-129">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="6790f-130">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-130">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="6790f-131">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="6790f-131">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="6790f-132">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-132">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6790f-133">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-133">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6790f-134">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てるときは、標準文字 (A ～ Z、a ～ z、0 ～ 9、およびハイフンを含む) のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6790f-134">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="6790f-135">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6790f-135">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6790f-136">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="6790f-136">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="6790f-137">コンピューター名に DNS サフィックスを追加する方法の詳細については、「 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための dns の構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6790f-137">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-138">[**単一コンピューターのプール**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-138">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="6790f-139">[**機能の選択**] で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-139">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-140">SIP アクセスサービス、Lync Server 2013 Web 会議サービス、音声ビデオエッジサービスに単一の FQDN および IP アドレスを使用することを計画している場合は、[ **単一の fqdn と Ip アドレスを使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-140">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="6790f-141">フェデレーションを有効にする場合は、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-141">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p108">このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-146">展開で XMPP (Extensible Messaging and Presence Protocol) をサポートする場合は、[**XMPP フェデレーションを有効にする (ポート 5269)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-146">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="6790f-147">[**IP オプションの選択**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-147">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-148">**[内部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-148">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-149">**[内部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-149">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-150">**[外部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-150">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="6790f-151">**[外部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-151">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="6790f-152">また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6790f-152">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="6790f-153">そのためには、[**NAT を使用してこのエッジ プールの外部 IP アドレスを変換する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-153">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="6790f-154">[**外部 FQDN**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-154">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-155">[**機能の選択**] で SIP アクセス、Web 会議サービス、および音声ビデオ エッジ サービスに単一の FQDN と IP アドレスを使用するように選択している場合、[**SIP アクセス**] に外部 FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-155">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p110">このオプションを選択する場合、各エッジ サービスに異なるポート番号を指定する必要があります (推奨されるポート設定: アクセス エッジ サービスに 5061、Web 会議エッジ サービスに 444、音声ビデオ エッジ サービスに 443)。 このオプションを選択すると、潜在的な接続の問題を防ぐとともに、3 つのすべてのサービスに同じポート番号 (例、443) を使用することができるため、構成を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-158">[**機能の選択**] で単一の FQDN および IP アドレスの使用を選ばなかった場合、既定のポートのまま、[**SIP アクセス**]、[**Web 会議**] および [**音声ビデオ**] の外部 FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-158">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="6790f-159">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-159">Click **Next**.</span></span>

10. <span data-ttu-id="6790f-p111">[**内部 IP アドレスの定義**] で、必要に応じて [**内部 IPv4 アドレス**] および [**内部 IPv6 アドレス**] にエッジ サーバーの IP アドレスを入力します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="6790f-162">[**外部 IP アドレスの定義**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6790f-162">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-163">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選んだ場合、[**SIP アクセス**] にエッジ サーバーの外部 IPv4 アドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-163">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="6790f-164">IPv6 アドレスを使用する場合は、エッジ サーバーの外部 IPv6 アドレスを [**SIP アクセス**] に入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-164">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="6790f-165">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選ばなかった場合、[**SIP アクセス**]、[**Web 会議**]、および [**音声ビデオ会議**] にエッジ サーバーの外部 IPv4 アドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-165">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="6790f-166">IPv6 アドレスの使用を選択し、SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選ばなかった場合、[**SIP アクセス**]、[**Web 会議**]、および [**音声ビデオ会議**] にエッジ サーバーの外部 IPv6 アドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-166">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-167">IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6790f-167">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="6790f-p112">NAT を使用することを選んだ場合、ダイアログ ボックスが表示されます。[**音声ビデオ エッジ サービスに対するパブリック IPv4 アドレス**] に NAT によって変換されたパブリック IPv4 アドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-170">これは、音声ビデオ エッジ サービスの外部 IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="6790f-170">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="6790f-p113">NAT と IPv6 アドレスを使用することを選んだ場合、ダイアログ ボックスが表示されます。[**音声ビデオ エッジ サービスに対するパブリック IPv6 アドレス**] に NAT によって変換されたパブリック IPv6 アドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-173">これは、音声ビデオ エッジ サービスの外部 IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="6790f-173">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="6790f-p114">[**次ホップの定義**] の [**次ホップ プール**] で、フロントエンド プールまたは Standard Edition プールのいずれかである、内部プール名を選択します。または、展開にディレクターが含まれている場合、ディレクターを選択します。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="6790f-177">[**フロントエンド プールの関連付け**] で、サポートされる外部ユーザーとの通信にこのエッジ サーバーを使用する内部プールの名前を選択して、1 つ以上の内部プール (フロントエンド プールおよび Standard Edition サーバーを含めることが可能) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6790f-177">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-p115">1 つだけの負荷分散型エッジ プールまたは単一のエッジサーバーが音声ビデオ トラフィックの各内部プールに関連付けることができます。 エッジ プールまたはエッジ サーバーに関連付けられた内部プールがすでに存在する場合、内部プールがすでにエッジ プールまたはエッジ サーバーに関連付けられていることを示す警告が表示されます。 別のエッジ サーバーに既に関連付けられているプールを選択すると、その関連付けが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="6790f-181">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-181">Click **Finish**.</span></span>

17. <span data-ttu-id="6790f-182">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-182">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="6790f-183">DNS 負荷分散エッジ サーバー プールのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-183">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="6790f-184">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-184">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6790f-185">コンソール ツリーで、エッジ サーバーを展開するサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-185">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="6790f-186">[**エッジ プール**] を右クリックして、[**新しいエッジ プール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6790f-186">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="6790f-187">**[新しいエッジ プールの定義]** で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-187">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="6790f-188">**[エッジ プール FQDN の定義]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6790f-188">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-189">[**プールの FQDN**] に、エッジ プールの内部接続用の完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-189">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="6790f-190">プールに対して指定する名前は、内部エッジ プールの名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-190">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="6790f-191">この名前は、FQDN として定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-191">This must be defined as a FQDN.</span></span> <span data-ttu-id="6790f-192">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-192">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6790f-193">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、標準文字のみ (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="6790f-193">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="6790f-194">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6790f-194">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6790f-195">一般に、外部 DNS および CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="6790f-195">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-196">[**複数コンピューターのプール**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-196">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="6790f-197">**[機能の選択]** で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-197">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-198">SIP アクセス、Lync Server 2013 Web 会議サービス、音声ビデオエッジサービスに単一の FQDN と IP アドレスを使用することを計画している場合は、[ **単一の fqdn と Ip アドレスを使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-198">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="6790f-p117">フェデレーションを有効にする場合は、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックスをオンにします。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p118">このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-205">展開で XMPP (Extensible Messaging and Presence Protocol) をサポートする場合は、[**XMPP フェデレーションを有効にする (ポート 5269)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-205">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="6790f-206">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-206">Click **Next**.</span></span>

8.  <span data-ttu-id="6790f-207">[**IP オプションの選択**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-207">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-208">**[内部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-208">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-209">**[内部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-209">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-210">**[外部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-210">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="6790f-211">**[外部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-211">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="6790f-212">また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6790f-212">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="6790f-213">そのためには、[**NAT を使用してこのエッジ プールの外部 IP アドレスを変換する**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-213">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="6790f-214">[**外部 FQDN**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-214">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-215">[**機能の選択**] で SIP アクセス、Web 会議サービス、および音声ビデオ エッジ サービスに単一の FQDN と IP アドレスを使用するように選択している場合、[**SIP アクセス**] に外部 FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-215">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p120">このオプションを選択する場合、各エッジ サービスに異なるポート番号を指定する必要があります (推奨されるポート設定:アクセス エッジ サービスに 5061、Web 会議エッジ サービスに 444、音声ビデオ エッジ サービスに 443)。このオプションを選択すると、潜在的な接続の問題を防ぐとともに、3 つすべてのサービスに同じポート番号 (443 など) を使用できるため、構成を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-p121">[**機能の選択**] で、単一の FQDN と IP アドレスの使用を選択しなかった場合は、エッジ プールの公開側用に選択した FQDN を [**SIP アクセス**] に入力します。[**Web 会議**] に、エッジ プールの公開側用に選択した FQDN を入力します。[**オーディオ/ビデオ**] に、エッジ プールの公開側用に選択した FQDN を入力します。既定のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="6790f-222">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-222">Click **Next**.</span></span>

11. <span data-ttu-id="6790f-223">**[このプール内のコンピューターの定義]** で **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-223">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="6790f-224">[**内部 FQDN と IP アドレス**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-224">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-225">このプール内で作成する最初のエッジ サーバーの要件に応じて、[**内部 IPv4 アドレス**] に IPv4 アドレスを入力するか、[**内部 IPv6 アドレス**] に IPv6 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-225">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="6790f-226">このプール内で作成する最初のエッジ サーバーの FQDN を [**内部 FQDN**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-226">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-227">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-227">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="6790f-228">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="6790f-228">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="6790f-229">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-229">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6790f-230">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前には、DNS サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-230">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6790f-231">Lync Server、エッジ サーバー、プール、および配列の FQDN を割り当てる場合に使用できる文字は、標準文字のみ (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="6790f-231">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="6790f-232">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6790f-232">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6790f-233">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="6790f-233">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="6790f-234">コンピューター名に DNS サフィックスを追加する方法の詳細については、「 <A href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための dns の構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6790f-234">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="6790f-235">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-235">Click **Next**.</span></span>

14. <span data-ttu-id="6790f-236">**[外部 IP アドレスの定義]** で以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="6790f-236">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-237">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選んだ場合、**[SIP アクセス]** にエッジ サーバーの外部 IP アドレス を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-237">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="6790f-p123">SIP アクセス、Web 会議サービス、および音声ビデオ会議サービス用に単一の FQDN と IP アドレスを使用しない場合は、このエッジ プール サーバーの公開側用に選択した IP アドレスを [**SIP アクセス**] に入力します。[**Web 会議**] に、このエッジ プール サーバーの公開側用に選択した IP アドレスを入力します。[**音声ビデオ会議**] に、このエッジ プール サーバーの公開側用に選択した IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="6790f-241">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-241">Click **Next**.</span></span>

16. <span data-ttu-id="6790f-242">IPv6 アドレスを有効にする場合は、[**外部 IP アドレスの定義**] で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-242">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-243">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選んだ場合、[**SIP アクセス**] にエッジ サーバーの外部 IPv6 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-243">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="6790f-p124">SIP アクセス、Web 会議サービス、および音声ビデオ会議サービス用に単一の FQDN と IP アドレスを使用しない場合は、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを [**SIP アクセス**] に入力します。[**Web 会議**] に、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを入力します。[**音声ビデオ会議**] に、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-247">IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6790f-247">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="6790f-248">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-248">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-249"><STRONG>[このプール内のコンピューターの定義]</STRONG> ダイアログ ボックスに、プール内で作成した最初のエッジ サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-249">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="6790f-250">**[このプール内のコンピューターの定義]** で **[追加]** をクリックして、エッジ プールに追加する 2 番目のエッジ サーバーに対してステップ 11 ～ 14 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6790f-250">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="6790f-251">ステップ 11 ～ 14 を繰り返したら、**[このプール内のコンピューターの定義]** で **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-251">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-252">この時点で、プール内に両方のエッジ サーバーが確認できます。</span><span class="sxs-lookup"><span data-stu-id="6790f-252">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="6790f-p125">NAT を使用することを選んだ場合、ダイアログ ボックスが表示されます。[**パブリック IP アドレス**] に、NAT によって変換されるパブリック IPv4 または IPv6 アドレス (適切な方) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-255">これは、音声ビデオ エッジの外部 IP アドレスになります。</span><span class="sxs-lookup"><span data-stu-id="6790f-255">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="6790f-p126">**[次ホップの定義]** の **[次ホップ プール]** 一覧で、内部プールの名前を選択します。内部プールの名前はフロント エンド プールまたは Standard Edition プールのいずれかにすることができます。あるいは、展開にディレクターを含める場合は、ディレクターの名前を選択します。**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="6790f-259">**[フロント エンド プールの関連付け]** で、このエッジ サーバーに関連付ける 1 つ以上の内部プール (フロント エンド プールおよび Standard Edition サーバーを含めることが可能) を指定します。それには、サポート対象の外部ユーザーとの通信用にこのエッジ サーバーを使用する内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6790f-259">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-p127">音声ビデオ トラフィックの各内部プールに関連付けることができるのは、1 つの負荷分散型エッジ プールまたは単一のエッジサーバーのみです。内部プールが既にエッジ プールまたはエッジ サーバーに関連付けられている場合は、内部プールが既にエッジ プールまたはエッジ サーバーに関連付けられていることを示す警告が表示されます。別のエッジ サーバーに既に関連付けられているプールを選択すると、その関連付けが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="6790f-263">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-263">Click **Finish**.</span></span>

24. <span data-ttu-id="6790f-264">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-264">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="6790f-265">ハードウェア負荷分散エッジ サーバー プールのトポロジを定義するには</span><span class="sxs-lookup"><span data-stu-id="6790f-265">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="6790f-266">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-266">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="6790f-267">コンソール ツリーで、エッジ サーバーを展開するサイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-267">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="6790f-268">[ **エッジプール**] を右クリックし、[ **新しいエッジプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6790f-268">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="6790f-269">**[新しいエッジ プールの定義]** で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-269">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="6790f-270">**[エッジ プール FQDN の定義]** で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6790f-270">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-271">エッジ プールの内側用に選択した完全修飾名 (FQDN) を [**FQDN**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-271">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="6790f-272">プールに対して指定する名前は、内部エッジ プールの名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-272">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="6790f-273">この名前は、FQDN として定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6790f-273">This must be defined as a FQDN.</span></span> <span data-ttu-id="6790f-274">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-274">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6790f-275">Lync Server、エッジ サーバー、およびプールの FQDN を割り当てる場合に使用できる文字は、標準文字のみ (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="6790f-275">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="6790f-276">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6790f-276">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6790f-277">一般に、外部 DNS および公的 CA では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="6790f-277">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="6790f-278">[ **複数コンピューターのプール**] をクリックし、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-278">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="6790f-279">**[機能の選択]** で、次の操作を行ってください。</span><span class="sxs-lookup"><span data-stu-id="6790f-279">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="6790f-280">SIP アクセスサービス、Lync Server Web 会議サービス、音声ビデオエッジサービスに単一の FQDN と IP アドレスを使用することを計画している場合は、[ **単一の fqdn & Ip アドレスを使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-280">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="6790f-281">フェデレーションを有効にする場合は、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-281">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p129">このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-286">展開で XMPP (Extensible Messaging and Presence Protocol) をサポートする場合は、[**XMPP フェデレーションを有効にする (ポート 5269)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-286">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="6790f-287">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-287">Click **Next**.</span></span>

8.  <span data-ttu-id="6790f-288">[**IP オプションの選択**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-288">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-289">**[内部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-289">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-290">**[内部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-290">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="6790f-291">**[外部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-291">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="6790f-292">**[外部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6790f-292">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6790f-p130">[<STRONG>NAT を使用してこのエッジ プールの外部 IP アドレスを変換する</STRONG>] チェック ボックスはオンに<STRONG>しないでください</STRONG>。 ハードウェア負荷分散を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="6790f-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="6790f-295">[**外部 FQDN**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-295">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-296">[**機能の選択**] で SIP アクセス、Web 会議サービス、および音声ビデオ エッジ サービスに単一の FQDN と IP アドレスを使用するように選択している場合、[**SIP アクセス**] に外部 FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-296">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-p131">このオプションを選択する場合、各エッジ サービスに異なるポート番号を指定する必要があります (推奨されるポート設定:アクセス エッジ サービスに 5061、Web 会議エッジ サービスに 444、音声ビデオ エッジ サービスに 443)。 このオプションを選択すると、潜在的な接続の問題を防ぐとともに、3 つすべてのサービスに同じポート番号 (443 など) を使用できるため、構成を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="6790f-p132">[**機能の選択**] で、単一の FQDN と IP アドレスの使用を選択しなかった場合は、エッジ プールの公開側用に選択した FQDN を [**SIP アクセス**] に入力します。 [**Web 会議**] に、エッジ プールの公開側用に選択した FQDN を入力します。 [**オーディオ/ビデオ**] に、エッジ プールの公開側用に選択した FQDN を入力します。 既定のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6790f-303">これらのポートは、プールの公開側の仮想 IP (VIP) FQDN になります。</span><span class="sxs-lookup"><span data-stu-id="6790f-303">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="6790f-304">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-304">Click **Next**.</span></span>

11. <span data-ttu-id="6790f-305">[**このプール内のコンピューターの定義**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-305">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="6790f-306">[**外部 IP アドレスの定義**] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-306">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-307">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選んだ場合、[**SIP アクセス**] にエッジ サーバーの外部 IPv4 アドレスを入力します。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6790f-307">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="6790f-p133">SIP アクセス、Web 会議サービス、および音声ビデオ会議サービス用に単一の FQDN と IP アドレスを使用しない場合は、このエッジ プール サーバーの公開側用に選択した IP アドレスを [**SIP アクセス**] に入力します。[**Web 会議**] に、このエッジ プール サーバーの公開側用に選択した IP アドレスを入力します。[**音声ビデオ会議**] に、このエッジ プール サーバーの公開側用に選択した IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="6790f-311">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-311">Click **Next**.</span></span>

14. <span data-ttu-id="6790f-312">IPv6 アドレスを有効にする場合は、[**外部 IP アドレスの定義**] で次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6790f-312">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="6790f-313">SIP アクセス、Web 会議サービス、音声ビデオ エッジ サービスに単一の FQDN および IP アドレスを使用することを選んだ場合、[**SIP アクセス**] にエッジ サーバーの外部 IPv6 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-313">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="6790f-p134">SIP アクセス、Web 会議サービス、および音声ビデオ会議サービス用に単一の FQDN と IP アドレスを使用しない場合は、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを [**SIP アクセス**] に入力します。[**Web 会議**] に、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを入力します。[**音声ビデオ会議**] に、このエッジ プール サーバーの公開側用に選択した IPv6 アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6790f-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-317">IPv6 アドレスを有効にして割り当てることを選択しなかった場合、このダイアログ ボックスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6790f-317">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="6790f-318">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-318">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-319"><STRONG>[このプール内のコンピューターの定義]</STRONG> ダイアログ ボックスに、プール内で作成した最初のエッジ サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-319">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="6790f-320">[**このプール内のコンピューターの定義**] で [**追加**] をクリックして、エッジ プールに追加する 2 番目のエッジ サーバーに対してステップ 11. ～ 14. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6790f-320">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="6790f-321">ステップ 11 ～ 14 を繰り返したら、**[このプール内のコンピューターの定義]** で **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-321">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-322">ここまでの手順で、プール内の両方のエッジ サーバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-322">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="6790f-p135">**[次ホップの定義]** の **[次ホップ プール]** 一覧で、内部プールの名前を選択します。内部プールの名前はフロント エンド プールまたは Standard Edition プールのいずれかにすることができます。 あるいは、展開にディレクターを含める場合は、ディレクターの名前を選択します。**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="6790f-326">**[フロント エンド プールの関連付け]** で、このエッジ サーバーに関連付ける 1 つ以上の内部プール (フロント エンド プールおよび Standard Edition サーバーを含めることが可能) を指定します。それには、サポート対象の外部ユーザーとの通信用にこのエッジ サーバーを使用する内部プールの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="6790f-326">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6790f-p136">音声ビデオ トラフィックの各内部プールに関連付けることができるのは、1 つの負荷分散型エッジ プールまたは単一のエッジサーバーのみです。内部プールが既にエッジ プールまたはエッジ サーバーに関連付けられている場合は、内部プールが既にエッジ プールまたはエッジ サーバーに関連付けられていることを示す警告が表示されます。別のエッジ サーバーに既に関連付けられているプールを選択すると、その関連付けが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6790f-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="6790f-330">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6790f-330">Click **Finish**.</span></span>

21. <span data-ttu-id="6790f-331">トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="6790f-331">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

