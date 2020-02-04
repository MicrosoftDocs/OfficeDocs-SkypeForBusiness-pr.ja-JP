---
title: 'Lync Server 2013: SIP トランキングのコンポーネントおよびトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="57b3a-102">Lync Server 2013 の SIP トランキングのコンポーネントおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="57b3a-102">Components and topologies for SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57b3a-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="57b3a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="57b3a-104">次の図は、Lync Server の SIP トランキングトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="57b3a-104">The following figure depicts the SIP trunking topology in Lync Server.</span></span>

<span data-ttu-id="57b3a-105">**SIP トランキングトポロジ**</span><span class="sxs-lookup"><span data-stu-id="57b3a-105">**SIP trunking topology**</span></span>

<span data-ttu-id="57b3a-106">![SIP トランキングのトポロジ](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP トランキングのトポロジ")</span><span class="sxs-lookup"><span data-stu-id="57b3a-106">![SIP Trunking Topology](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP Trunking Topology")</span></span>

<span data-ttu-id="57b3a-p101">図に示すように、エンタープライズ ネットワークと公衆交換電話網 (PSTN) サービス プロバイダーの間の接続には、IP 仮想プライベート ネットワーク (VPN) が使用されます。このプライベート ネットワークの目的は、IP 接続を提供し、セキュリティを強化し、(必要に応じて) サービス品質 (QoS) 保証を得ることです。VPN の性質により、SIP 信号トラフィックにトランスポート層セキュリティ (TLS) を使用したり、メディア トラフィックにセキュア リアルタイム転送プロトコル (SRTP) を使用したりする必要はありません。このため、企業とサービス プロバイダーの間の接続は、IP VPN を通じてトンネリングされる可能性のある SIP 用の普通の TCP 接続と、メディア用の普通のリアルタイム転送プロトコル (RTP) (over UDP) で構成されます。VPM ルーター間のすべてのファイアウォールのポートが開いていて VPN ルーターが通信できること、および VPN ルーターの外部エッジの IP アドレスがパブリック ルーティング可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="57b3a-p101">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57b3a-112">フェールオーバーを含め、高可用性のサポートを提供しているかどうかを確認するには、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="57b3a-112">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="57b3a-113">サポートしている場合、高可用性を設定する手順を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b3a-113">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="57b3a-114">たとえば、各仲介サーバーに1つの IP アドレスと1つの SIP トランクのみを構成する必要がある場合、または各仲介サーバーに複数の SIP trunks を構成する必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="57b3a-114">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span><BR><span data-ttu-id="57b3a-115">複数のセントラルサイトがある場合は、他のセントラルサイトとの接続を有効にする機能がサービスプロバイダーにあるかどうかも確認します。</span><span class="sxs-lookup"><span data-stu-id="57b3a-115">If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="57b3a-116">SIP トランクの場合は、スタンドアロンの仲介サーバーを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-116">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="57b3a-117">詳細については、展開ドキュメントの「 <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync Server 2013 での仲介サーバーの展開とピアの定義</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b3a-117">For details, see <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="57b3a-118">SIP トランキングを行うための仲介サーバーのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="57b3a-118">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="57b3a-p104">セキュリティ上の理由から、2 つの VPN ルーター間の各接続に仮想 LAN (VLAN) を設定する必要があります。VLAN の実際の設定プロセスは、ルーターの製造元によって異なります。詳細については、ルーター ベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="57b3a-p104">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="57b3a-122">次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-122">We recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="57b3a-123">仲介サーバーと境界ネットワーク内の VPN ルーターの間に仮想 LAN (VLAN) を設定します (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="57b3a-123">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

  - <span data-ttu-id="57b3a-124">ルーターから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。</span><span class="sxs-lookup"><span data-stu-id="57b3a-124">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

  - <span data-ttu-id="57b3a-125">ルーターからのトラフィックを仲介サーバー以外の場所にルーティングするルーティングルールはブロックします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-125">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="57b3a-126">VPN サーバーを使用する場合、次のガイドラインに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-126">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

  - <span data-ttu-id="57b3a-127">VPN サーバーと仲介サーバーの間に VLAN をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-127">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

  - <span data-ttu-id="57b3a-128">VPN サーバーから VLAN へのブロードキャストまたはマルチキャスト パケットの転送は許可しません。</span><span class="sxs-lookup"><span data-stu-id="57b3a-128">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

  - <span data-ttu-id="57b3a-129">VPN サーバートラフィックを仲介サーバー以外の場所にルーティングするルーティングルールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="57b3a-129">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

  - <span data-ttu-id="57b3a-130">Generic Routing Encapsulation (GRE) を使用して VPN 上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="57b3a-130">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

