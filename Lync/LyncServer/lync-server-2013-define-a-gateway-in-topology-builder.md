---
title: 'Lync Server 2013: トポロジビルダーでゲートウェイを定義する'
description: 'Lync Server 2013: トポロジビルダーでゲートウェイを定義します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8bf09f06f54d8988c8c9a9e385ef251a960bd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567803"
---
# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="54dd3-103">Lync Server 2013 のトポロジビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="54dd3-103">Define a gateway in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54dd3-104">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="54dd3-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="54dd3-105">次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip が有効なユーザーの公衆交換電話網 (PSTN) への接続を提供するための仲介サーバーを関連付けることができる *ピア* を定義します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-105">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="54dd3-106">仲介サーバーへのピアとは、PSTN ゲートウェイ、ip-pbx、または SIP トランクを構成して接続するインターネットテレフォニーサービスプロバイダー (ITSP) のセッションボーダーコントローラー (SBC) のことです。</span><span class="sxs-lookup"><span data-stu-id="54dd3-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54dd3-107">このトピックでは、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front end pool Or Standard edition 2013 2013 server</A> 」で説明されているように、少なくとも1つの中央サイトに、またはスタンドアロンの仲介サーバーを使用<A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A>して少なくとも1つの中央サイトに内部フロントエンドプールまたは standard edition サーバーをセットアップしていることを前提</span><span class="sxs-lookup"><span data-stu-id="54dd3-107">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="54dd3-108">また、このトピックでは、インフラストラクチャが lync server 2013 の「 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">エンタープライズ voip の前提</A> 条件」および「セキュリティと構成の前提条件」で説明されている前提条件を満たしていることを前提としています ( <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013 のエンタープライズ voip の</A>場合)。</span><span class="sxs-lookup"><span data-stu-id="54dd3-108">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="54dd3-109">仲介サーバーのピアを定義するには</span><span class="sxs-lookup"><span data-stu-id="54dd3-109">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="54dd3-110">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="54dd3-111">[Lync Server 2013] の下で、サイト名、[共有コンポーネント] の順にクリックし、[ **pstn** ゲートウェイ] ノードを右クリックして、[ **新しい pstn ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-111">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="54dd3-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="54dd3-112">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="54dd3-113">[**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-113">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="54dd3-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="54dd3-114">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54dd3-115">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに、FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54dd3-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="54dd3-116">新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-116">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="54dd3-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="54dd3-117">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="54dd3-118">PSTN ゲートウェイのルート トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-118">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="54dd3-119">トランクとは、仲介サーバーと、組で一意に識別されるゲートウェイとの間の論理接続のことです。</span><span class="sxs-lookup"><span data-stu-id="54dd3-119">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="54dd3-120">{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP および FQDN、ゲートウェイリッスンポート}</span><span class="sxs-lookup"><span data-stu-id="54dd3-120">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="54dd3-121">トポロジビルダーで PSTN ゲートウェイを定義するときは、PSTN ゲートウェイをトポロジに正常に追加するために、ルートトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54dd3-121">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="54dd3-122">ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。</span><span class="sxs-lookup"><span data-stu-id="54dd3-122">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="54dd3-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="54dd3-123">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="54dd3-124">[ **IP/PSTN ゲートウェイのリッスンポート**] の下に、PSTN ゲートウェイのルートトランクに関連付けられる仲介サーバーからの SIP メッセージに対して、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-124">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="54dd3-125">既定では、PSTN ゲートウェイ、PBX、または SBC のトランスポート層セキュリティ (TLS) には、伝送制御プロトコル (TCP) および5067のポートが5066になっています。</span><span class="sxs-lookup"><span data-stu-id="54dd3-125">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="54dd3-126">ブランチサイトの存続可能ブランチアプライアンスでは、既定のポートは TCP の場合は5081、TLS の場合は5082です。</span><span class="sxs-lookup"><span data-stu-id="54dd3-126">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="54dd3-127">[**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-127">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54dd3-128">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="54dd3-129">[ **関連付けられている仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="54dd3-130">[ **関連付けられている仲介サーバーのポート**] で、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54dd3-131">Lync Server 2013 で複数のトランクがサポートされている場合、複数の PSTN ゲートウェイとの通信に使用するために、複数の SIP シグナリングポートを仲介サーバーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="54dd3-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="54dd3-132">トランクを定義する場合、 <STRONG>関連する仲介サーバーのポート</STRONG> は、仲介サーバーによって許可されている各プロトコルのリッスンポートの範囲内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54dd3-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="54dd3-133">このポート範囲は、「Lync Server 2013 および仲介プール」で定義されています。</span><span class="sxs-lookup"><span data-stu-id="54dd3-133">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="54dd3-134">目的の仲介サーバープールを右クリックし、[ <STRONG>プロパティの編集</STRONG>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-134">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="54dd3-135">[<STRONG>リッスン ポート</STRONG>] フィールドでポート範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="54dd3-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="54dd3-136">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54dd3-136">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="54dd3-137">このステップを終了する前に、定義されたピアが実行中で、指定した FQDN または IP アドレスを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54dd3-137">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="54dd3-138">次に、トポロジにピアを追加するには、「展開」のドキュメントの「 [Publish the topology In Lync Server 2013](lync-server-2013-publish-the-topology.md) 」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="54dd3-138">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="54dd3-139">トポロジビルダーを使用してトポロジを構築または変更するたびに、トポロジを公開する必要があります。これにより、データを使用して、Lync Server を実行しているサーバーのファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="54dd3-139">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54dd3-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="54dd3-140">See Also</span></span>


[<span data-ttu-id="54dd3-141">Lync Server 2013 のトポロジビルダーでのトランクの変更</span><span class="sxs-lookup"><span data-stu-id="54dd3-141">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

