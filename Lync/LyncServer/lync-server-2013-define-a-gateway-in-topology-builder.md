---
title: 'Lync Server 2013: トポロジビルダーでゲートウェイを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="4a3fc-102">Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="4a3fc-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a3fc-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4a3fc-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4a3fc-104">次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip を有効にしているユーザー向けに、仲介サーバーを関連付け、PSTN (公衆交換電話網) への接続を提供できる*ピア*を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="4a3fc-105">仲介サーバーへのピアは、SIP トランクを構成することによって、接続先のインターネットテレフォニーサービスプロバイダー (ITSP) の PSTN ゲートウェイ、IP PBX、またはセッション境界コントローラー (SBC) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a3fc-106">このトピックでは、次の説明に従って、少なくとも1つのセントラルサイトまたはスタンドアロンの仲介サーバーを持つ少なくとも1つのセントラルサイトに、少なくとも1つの内部のフロントエンドプールまたは Standard Edition サーバーを設定していることを前提としています。 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013</A>で、展開ドキュメントの<A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="4a3fc-107">また、このトピックでは、組織が lync のエンタープライズ voip の<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">ソフトウェア2013前提</A>条件を満たしていることを確認していることを前提としています。 lync<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">でのエンタープライズ voip のセキュリティと構成の前提条件について説明します。サーバー 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="4a3fc-108">仲介サーバーのピアを定義するには</span><span class="sxs-lookup"><span data-stu-id="4a3fc-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="4a3fc-109">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4a3fc-110">[Lync Server 2013、サイト名、共有コンポーネント] の順にクリックし、[ **Pstn ゲートウェイ**] ノードを右クリックして、[**新しい pstn ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="4a3fc-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="4a3fc-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="4a3fc-112">[**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="4a3fc-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="4a3fc-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a3fc-114">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="4a3fc-115">新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="4a3fc-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="4a3fc-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="4a3fc-117">PSTN ゲートウェイのルート トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="4a3fc-118">トランクは、仲介サーバーと、組で一意に識別されたゲートウェイの間の論理的な接続です。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="4a3fc-119">{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP と FQDN、ゲートウェイリッスンポート}</span><span class="sxs-lookup"><span data-stu-id="4a3fc-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="4a3fc-120">トポロジビルダーで PSTN ゲートウェイを定義する場合は、トポロジに PSTN ゲートウェイを正常に追加するためにルートトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="4a3fc-121">ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="4a3fc-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="4a3fc-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="4a3fc-123">[ **IP/PSTN ゲートウェイのリスニングポート**] に、PSTN ゲートウェイのルートトランクと関連付けられる仲介サーバーからの SIP メッセージについて、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="4a3fc-124">(既定では、ポートは、PSTN ゲートウェイ、PBX、または SBC 上のトランスポート層セキュリティ (TLS) 用の伝送制御プロトコル (TCP) および5067用の5066です。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="4a3fc-125">ブランチサイトの Survivable Branch Appliance では、既定のポートは TCP 用の5081で、TLS の場合は5082です。)</span><span class="sxs-lookup"><span data-stu-id="4a3fc-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="4a3fc-126">[**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a3fc-127">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="4a3fc-128">[**関連付けられた仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="4a3fc-129">[**関連付けられた仲介サーバーポート**] に、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a3fc-130">Lync Server 2013 で複数のトランクがサポートされている場合、複数の PSTN ゲートウェイとの通信に使用するために、複数の SIP シグナリングポートを仲介サーバーで定義できます。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="4a3fc-131">トランクを定義する場合、<STRONG>関連する仲介サーバーポート</STRONG>は、仲介サーバーで許可されている各プロトコルのリスニングポートの範囲内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="4a3fc-132">このポート範囲は、「Lync Server 2013 および仲介プール」に定義されています。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="4a3fc-133">対象の仲介サーバープールを右クリックし、[<STRONG>プロパティの編集</STRONG>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="4a3fc-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="4a3fc-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="4a3fc-135">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a3fc-136">この手順を完了する前に、定義したピアが実行されていて、指定した FQDN または IP アドレスを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="4a3fc-137">次に、トポロジにピアを追加するには、展開ドキュメントの「 [Lync Server 2013 でトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="4a3fc-138">トポロジビルダーを使用してトポロジを作成または変更するたびにトポロジを公開する必要があります。そのため、Lync Server を実行しているサーバーのファイルをインストールするためにデータを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4a3fc-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a3fc-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a3fc-139">See Also</span></span>


[<span data-ttu-id="4a3fc-140">Lync Server 2013 でのトポロジビルダーでのトランクの変更</span><span class="sxs-lookup"><span data-stu-id="4a3fc-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

