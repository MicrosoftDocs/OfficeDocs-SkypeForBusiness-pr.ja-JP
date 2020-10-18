---
title: 'Lync Server 2013: ネットワークアダプターの構成'
description: 'Lync Server 2013: ネットワークアダプターの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fa6aaa76c7815c3c14f711bf79eca82c44551ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577593"
---
# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="91076-103">Lync Server 2013 でネットワークアダプターを構成する</span><span class="sxs-lookup"><span data-stu-id="91076-103">Configure network adapters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91076-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="91076-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="91076-105">外部ネットワーク アダプターに 1 つ以上の IP アドレス、および内部ネットワーク アダプターに少なくとも 1 つの IP アドレスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="91076-105">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="91076-106">次の手順では、Forefront Threat Management Gateway (TMG) 2010 または Internet Information Server アプリケーション要求ルーティングのいずれかを実行しているサーバーに、次の2つのネットワークアダプターがあります。</span><span class="sxs-lookup"><span data-stu-id="91076-106">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="91076-107">パブリック (外部) ネットワーク アダプター。(通常はインターネット経由で) Web サイトに接続しようとするクライアント用。</span><span class="sxs-lookup"><span data-stu-id="91076-107">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="91076-108">Web サービスをホストしている Lync Server を実行している内部サーバーの場合は、プライベートまたは内部ネットワークインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="91076-108">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="91076-109">エッジサーバーと同様に、外部ネットワークアダプターにのみ既定のゲートウェイを設定します。</span><span class="sxs-lookup"><span data-stu-id="91076-109">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="91076-110">デフォルト ゲートウェイは、トラフィックをインターネットに送るルーターまたは外部ファイアウォールの IP アドレスになります。</span><span class="sxs-lookup"><span data-stu-id="91076-110">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="91076-111">リバース プロキシから内部ネットワーク アダプターに送られるトラフィックについては、Web 公開ルールによって参照されるサーバーが含まれているすべてのサブネットの内部インターフェイスに対して固定の静的ルートを使用する必要があります (Windows Server の route コマンドなど)。</span><span class="sxs-lookup"><span data-stu-id="91076-111">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="91076-112">常設ルートを設定しても、コンピューターがルーターになることはありません。</span><span class="sxs-lookup"><span data-stu-id="91076-112">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="91076-113">IP 転送が有効になっていない場合、コンピューターは、別のネットワーク宛ての特定のトラフィックを適切なインターフェイスに転送することのみを行います。</span><span class="sxs-lookup"><span data-stu-id="91076-113">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="91076-114">これは基本的に2つのゲートウェイを設定しています。これは、1つは外部ネットワークを指す既定値、もう1つは内部インターフェイスへのトラフィックとルーターまたはその他のネットワークに向かうトラフィック用です。</span><span class="sxs-lookup"><span data-stu-id="91076-114">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="91076-p102">ただし、ネットワークのルーターがルートの要約を示すように構成されている場合は、すべてのサブネットに対して固定ルートを作成する必要がないこともあります。ルーターが定義されているネットワークへの固定ルートを作成し、そのルーターをデフォルト ゲートウェイとして使用してください。ネットワークがどのように構成されているのかはっきりせず、どんな固定ルートを作成する必要があるのか知りたい場合は、社内のネットワーク エンジニアに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="91076-p102">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes. Create a persistent route to the network where the router is defined and use the router as the default gateway. If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="91076-118">リバースプロキシは、内部ディレクターまたはフロントエンドサーバー、および web 公開ルールで使用される次ホッププールの Fqdn の DNS ホスト (A) レコードを解決できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="91076-118">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="91076-119">エッジサーバーと同様に、セキュリティ上の理由から、内部ネットワーク内の DNS サーバーを使用するためにリバースプロキシを構成しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91076-119">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="91076-120">これは、境界に DNS サーバーが必要であるか、これらの FQDN のそれぞれをサーバーの内部 IP アドレスに解決するリバース プロキシの HOSTS ファイル エントリが必要であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="91076-120">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="91076-121">リバース プロキシ コンピューターのネットワーク アダプター カードを構成するには</span><span class="sxs-lookup"><span data-stu-id="91076-121">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="91076-122">リバースプロキシとして実行している Windows Server 2008、Windows server 2008 R2、Windows Server 2012、または Windows 2012 Server 2008 R2 サーバーで、[**スタート**] をクリックし、[**コントロールパネル**] をポイントし、[**ネットワークと共有センター**] をクリックし、[**アダプターの設定の変更**] をクリックして、[**アダプター設定の変更**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="91076-122">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="91076-123">外部インターフェイスに使用する外部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91076-123">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="91076-124">[**プロパティ**] ページの [**ネットワーク**] タブをクリックし、[**この接続は次の項目を使用します**] ボックスの一覧の [**インターネット プロトコル Version 4 (TCP/IPv4)**] をクリックして、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91076-124">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="91076-125">[**インターネット プロトコル (TCP/IP) のプロパティ**] ページで、ネットワーク アダプターの接続先のネットワーク サブネットに対応した IP アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="91076-125">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91076-126">リバースプロキシが HTTPS/TCP/443 を使用する他のアプリケーションによって既に使用されている場合は、Outlook Web Access を公開する場合は、既存のルールや Web リスナーに影響を及ぼすことなく、既存の証明書を HTTPS/TCP/443 に公開するために、別の IP アドレスを追加する必要があります。または、既存の証明書を、サブジェクト2013の別名に新しい外部 FQDN 名を追加するものに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="91076-126">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="91076-127">[ **Ok**] をクリックし、[ **ok**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91076-127">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="91076-128">[**ネットワーク接続**] で、内部インターフェイスに使用する内部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91076-128">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="91076-129">ステップ 3. ～ 5. を繰り返して内部ネットワーク接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="91076-129">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

