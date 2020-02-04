---
title: 'Lync Server 2013: ネットワーク アダプターの構成'
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
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a><span data-ttu-id="ddf14-102">Lync Server 2013 ネットワーク アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="ddf14-102">Configure network adapters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddf14-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ddf14-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ddf14-104">1つ以上の IP アドレスを外部ネットワークアダプターに割り当て、少なくとも1つの IP アドレスを内部ネットワークアダプターに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddf14-104">You must assign one or more IP addresses to the external network adapter and at least one IP address to the internal network adapter.</span></span>

<span data-ttu-id="ddf14-105">次の手順では、Forefront Threat Management Gateway (TMG) 2010 または Internet Information Server アプリケーション要求ルーティングのいずれかを実行しているサーバーに、2つのネットワークアダプターがあります。</span><span class="sxs-lookup"><span data-stu-id="ddf14-105">In the following procedures, the server running either Forefront Threat Management Gateway (TMG) 2010 or Internet Information Server Application Request Routing has two network adapters:</span></span>

  - <span data-ttu-id="ddf14-106">Web サイト (通常はインターネット経由) に接続しようとしているクライアントの場合は、パブリックまたは外部のネットワークアダプター。</span><span class="sxs-lookup"><span data-stu-id="ddf14-106">A public, or external, network adapter, for clients that attempt to connect to your website (that is, usually over the Internet).</span></span>

  - <span data-ttu-id="ddf14-107">Web サービスをホストしている Lync Server を実行している内部サーバーの場合は、プライベートまたは内部ネットワークインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="ddf14-107">A private, or internal, network interface, for internal servers running Lync Server that are hosting Web Services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ddf14-108">エッジサーバーの場合と同様に、外部ネットワークアダプターでのみ既定のゲートウェイを設定します。</span><span class="sxs-lookup"><span data-stu-id="ddf14-108">Similar to the Edge Servers, you set the default gateway on the external network adapter only.</span></span> <span data-ttu-id="ddf14-109">既定のゲートウェイは、インターネットへのトラフィックを指示するルーターまたは外部向けのファイアウォールの IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ddf14-109">The default gateway will be the IP address of the router or external facing firewall that directs traffic to the Internet.</span></span> <span data-ttu-id="ddf14-110">リバースプロキシから内部のネットワークアダプターへのトラフィックについては、web 発行ルールによって参照されるサーバーを含むすべてのサブネットに対して永続的な静的ルート (Windows Server の route コマンドなど) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddf14-110">For traffic that is destined from the reverse proxy to the internal facing network adaptor, you must use persistent static routes (such as the route command in Windows Server) for all subnets containing servers referenced by the web publishing rules.</span></span> <span data-ttu-id="ddf14-111">常設ルートを設定しても、コンピューターはルーターになりません。</span><span class="sxs-lookup"><span data-stu-id="ddf14-111">Setting a persistent route does not cause the computer to become a router.</span></span> <span data-ttu-id="ddf14-112">IP 転送が有効になっていない場合、そのコンピューターは、別のネットワークに送信される特定のトラフィックを適切なインターフェイスに転送するためだけに動作しています。</span><span class="sxs-lookup"><span data-stu-id="ddf14-112">If IP forwarding is not enabled, the computer is acting only to direct specific traffic destined for another network to the appropriate interface.</span></span> <span data-ttu-id="ddf14-113">これは、基本的に2つのゲートウェイを設定することです。1つは既定として外部ネットワークを指し、もう1つは内部インターフェイスとルーターなどのネットワークへのトラフィック用です。</span><span class="sxs-lookup"><span data-stu-id="ddf14-113">This is essentially setting two gateways – one as the default pointing to the external networks, and one for traffic destined to the internal interface and on to a router or other network.</span></span><BR><span data-ttu-id="ddf14-114">ただし、ネットワークのルーターがルートの概要として構成されている場合、すべてのサブネットに対して永続的なルートを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ddf14-114">However, creating persistent routes for all subnets may not be necessary if your network’s routers are configured to summarize routes.</span></span> <span data-ttu-id="ddf14-115">ルーターが定義されているネットワークへの常設ルートを作成し、そのルーターを既定のゲートウェイとして使用します。</span><span class="sxs-lookup"><span data-stu-id="ddf14-115">Create a persistent route to the network where the router is defined and use the router as the default gateway.</span></span> <span data-ttu-id="ddf14-116">ネットワークがどのように構成されていて、どの固定ルートを作成する必要があるかについてのガイダンスが必要な場合は、会社のネットワークエンジニアにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="ddf14-116">If you are not sure how your network is configured and need guidance on what persistent routes need to be created, consult with your company’s Network Engineers.</span></span><BR><span data-ttu-id="ddf14-117">リバースプロキシは、web 発行ルールで使われる内部ディレクターまたはフロントエンドサーバーと次ホッププールの Fqdn の DNS ホスト (A) レコードを解決できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddf14-117">The reverse proxy must be able to resolve the DNS host (A) records for the internal Director or Front End Server and next hop pool FQDNs used in the web publishing rules.</span></span> <span data-ttu-id="ddf14-118">エッジサーバーの場合と同様に、セキュリティ上の理由から、内部ネットワーク内にある DNS サーバーを使用するようにリバースプロキシを構成しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddf14-118">As with the Edge Servers, for security reasons, we recommend that you do not configure a reverse proxy to use a DNS server located in the internal network.</span></span> <span data-ttu-id="ddf14-119">つまり、境界に DNS サーバーが必要です。または、これらの各 Fqdn をサーバーの内部 IP アドレスに解決する逆プロキシの HOSTS ファイルエントリが必要です。</span><span class="sxs-lookup"><span data-stu-id="ddf14-119">This means you either need DNS servers in the perimeter, or you need HOSTS file entries on the reverse proxy that resolves each of these FQDNs to the internal IP address of the servers.</span></span>



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a><span data-ttu-id="ddf14-120">リバースプロキシコンピューターのネットワークアダプターカードを構成するには</span><span class="sxs-lookup"><span data-stu-id="ddf14-120">To configure the network adapter cards on the reverse proxy computer</span></span>

1.  <span data-ttu-id="ddf14-121">リバースプロキシとして実行されている windows server 2008、windows server 2008 R2、windows Server 2012、または Windows Server 2012 R2 サーバーで、[**スタート**] をクリックし、[**コントロールパネル**]、[**ネットワークと共有センター**] の順にクリックして、[**アダプターの設定の変更**] を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ddf14-121">On the Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 server running as the reverse proxy, open **Change Adapter Settings** by clicking **Start**, pointing to **Control Panel**, clicking **Network and Sharing Center**, and then clicking **Change Adapter Settings**.</span></span>

2.  <span data-ttu-id="ddf14-122">外部インターフェイスとして使用する外部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddf14-122">Right-click the external network connection that you want to use for the external interface, and then click **Properties**.</span></span>

3.  <span data-ttu-id="ddf14-123">[**プロパティ**] ページで、[**ネットワーク**] タブをクリックし、[**この接続は次の項目を使用**します] ボックスの一覧の [ **Internet Protocol Version 4 (TCP/IPv4)** ] をクリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddf14-123">On the **Properties** page, click the **Networking** tab, click **Internet Protocol Version 4 (TCP/IPv4)** in the **This connection uses the following items** list, and then click **Properties**.</span></span>

4.  <span data-ttu-id="ddf14-124">[ **Internet Protocol (tcp/ip) のプロパティ**] ページで、ネットワークアダプターを接続するネットワークサブネットに合わせて IP アドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ddf14-124">On the **Internet Protocol (TCP/IP) Properties** page, configure the IP addresses as appropriate for the network subnet to which the network adapter is attached.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ddf14-125">リバースプロキシが、HTTPS/TCP/443 を使用する他のアプリケーションによって既に使用されている場合は、Outlook Web Access を公開する場合、既存のルールや web リスナーに干渉しないように、別の IP アドレスを追加する必要があります。これにより、HTTPS/TCP/443 で Lync Server 2013 Web サービスを公開することができます。また、既存の証明書を新しい外部の FQDN 名に追加する証明書と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ddf14-125">If the reverse proxy is already being used by other applications that use HTTPS/TCP/443, such as for publishing Outlook Web Access, you either need to add another IP address so that you can publish the Lync Server 2013 Web Services on HTTPS/TCP/443 without interfering with the existing rules and web listeners, or you need to replace the existing certificate with one that adds the new external FQDN names to the subject alternative name.</span></span>

    
    </div>

5.  <span data-ttu-id="ddf14-126">[ **Ok**] をクリックし、[ **ok**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddf14-126">Click **OK**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ddf14-127">[**ネットワーク接続**] で、内部インターフェイスに使用する内部ネットワーク接続を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddf14-127">In **Network Connections**, right-click the internal network connection that you want to use for the internal interface, and then click **Properties**.</span></span>

7.  <span data-ttu-id="ddf14-128">手順3から5を繰り返して、内部ネットワーク接続を構成します。</span><span class="sxs-lookup"><span data-stu-id="ddf14-128">Repeat steps 3 through 5 to configure the internal network connection.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

