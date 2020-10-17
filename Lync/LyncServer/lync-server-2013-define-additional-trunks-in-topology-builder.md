---
title: 'Lync Server 2013: トポロジビルダーでの追加トランクの定義'
description: 'Lync Server 2013: トポロジビルダーで追加のトランクを定義します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57983d3e4d6a47c14f2dcdc153fe6872a33eb6e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567563"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="d6cb1-103">Lync Server 2013 のトポロジビルダーでの追加トランクの定義</span><span class="sxs-lookup"><span data-stu-id="d6cb1-103">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6cb1-104">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d6cb1-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d6cb1-105">次の手順に従って、トポロジビルダーを使用して、 *ピア* を仲介サーバーに関連付けることができる追加のトランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-105">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="d6cb1-106">ピアは、公衆交換電話網 (PSTN) への接続を備えたエンタープライズ Voip が有効なユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-106">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d6cb1-107">ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="d6cb1-108">トランクは、仲介サーバーとピア間のこの接続を定義します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-108">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="d6cb1-109">仲介サーバーごとに複数のトランクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-109">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="d6cb1-110">仲介サーバーは、複数のピアと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-110">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="d6cb1-111">トランクとは、仲介サーバーと、組で一意に識別されるゲートウェイとの間の論理接続のことです。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-111">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="d6cb1-112">{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP および FQDN、ゲートウェイリッスンポート}</span><span class="sxs-lookup"><span data-stu-id="d6cb1-112">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6cb1-113">このトピックでは、展開に関するドキュメントの「 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 のトポロジを定義</A> する」の説明に従って、少なくとも1つの併置またはスタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバーまたはプールを持つ、PSTN ゲートウェイとルートトランクをセットアップしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-113">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d6cb1-114">このトピックでは、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front end pool Or Standard edition 2013 server</A> 」の説明に従って、少なくとも1つの中央サイトに少なくとも1つのフロントエンドプールまたは standard edition サーバーを設定していることを前提 <A href="lync-server-2013-publish-the-topology.md">2013</A> としています。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-114">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="d6cb1-115">仲介サーバーとゲートウェイピアの間に追加のトランクを定義するには</span><span class="sxs-lookup"><span data-stu-id="d6cb1-115">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="d6cb1-116">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d6cb1-117">[Lync Server 2013] の下にあるサイト名、[ **共有コンポーネント**] で、 **トランク** ノードを右クリックし、[ **新しいトランク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-117">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="d6cb1-118">![Lync Server トポロジビルダーのファイル構造画面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server トポロジビルダーのファイル構造画面")</span><span class="sxs-lookup"><span data-stu-id="d6cb1-118">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="d6cb1-119">[**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-119">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="d6cb1-120">2 つのトランクに同じ名前を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-120">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6cb1-121">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに、FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-121">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="d6cb1-122">[**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-122">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="d6cb1-123">![トランクの PSTN ゲートウェイピアのプロパティ設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "トランクの PSTN ゲートウェイピアのプロパティ設定")</span><span class="sxs-lookup"><span data-stu-id="d6cb1-123">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="d6cb1-124">[ **Pstn ゲートウェイのリスニングポート**] で、このトランクに関連付けられる仲介サーバーからのピア (pstn ゲートウェイ、ip-pbx、または SBC) が SIP メッセージを受信するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-124">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="d6cb1-125">既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-125">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="d6cb1-126">既定の存続可能 Branch Appliance ポートは、TCP の場合は5081、TLS の場合は5082です。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-126">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="d6cb1-127">[**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-127">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6cb1-128">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-128">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="d6cb1-129">[ **関連付けられている仲介サーバー**] で、仲介サーバープールを選択して、このピアのルートトランクに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-129">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="d6cb1-130">[ **関連付けられている仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-130">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6cb1-131">Lync Server 2013 で複数のトランクがサポートされている場合、2つのトランクが同じ<STRONG>関連付けられた仲介サーバーのポート</STRONG>と、 <STRONG>IP/PSTN ゲートウェイのリスニングポート</STRONG>で構成できません。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-131">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6cb1-132">Lync Server 2013 で複数のトランクがサポートされている場合、複数のピアと通信するために、複数の SIP 信号ポートを仲介サーバーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-132">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="d6cb1-133">トランクを定義する場合、 <STRONG>関連する仲介サーバーのポート</STRONG> 番号は、仲介サーバーによって許可されている各プロトコルのリスニングポートの範囲内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-133">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="d6cb1-134">このポート範囲は、「Lync Server 2013 および仲介サーバープール」で定義されています。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-134">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="d6cb1-135">関連する仲介サーバープールを右クリックし、[ <STRONG>プロパティの編集</STRONG>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-135">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="d6cb1-136">[<STRONG>リッスン ポート</STRONG>] フィールドでポート範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-136">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="d6cb1-137">[ \*\*OK \*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6cb1-137">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6cb1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6cb1-138">See Also</span></span>


[<span data-ttu-id="d6cb1-139">Lync Server 2013 のトポロジビルダーでのトランクの変更</span><span class="sxs-lookup"><span data-stu-id="d6cb1-139">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

