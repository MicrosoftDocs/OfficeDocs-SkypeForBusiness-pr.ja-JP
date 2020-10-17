---
title: 'Lync Server 2013: トポロジビルダーでの仲介サーバーの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 368dc6d5e19adede1752c148c661c1c04788a9b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516474"
---
# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="a6120-102">Lync Server 2013 のトポロジビルダーでの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="a6120-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6120-103">_**トピックの最終更新日:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="a6120-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="a6120-104">このトピックの手順に従って、トポロジビルダーを使用して、まだエンタープライズ Voip を展開していないサイトで、スタンドアロンの仲介サーバーまたはフロントエンドプールと併置されているプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6120-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="a6120-105">Administrators グループのメンバーであるアカウントを使用して、トポロジを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="a6120-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="a6120-106">フロントエンドプールに併置された仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="a6120-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="a6120-107">このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズ Voip がまだ展開されていないサイトのフロントエンドプールに併置された仲介サーバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6120-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="a6120-108">仲介サーバーをフロントエンドプールに追加するには</span><span class="sxs-lookup"><span data-stu-id="a6120-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="a6120-109">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a6120-110">トポロジビルダーのコンソールツリーで、フロントエンドプールを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6120-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="a6120-111">コンソールツリーで、目的のフロントエンドプールの種類を右クリックし、[ **新しいフロントエンドプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="a6120-112">[**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義**ウィザードを進めます。</span><span class="sxs-lookup"><span data-stu-id="a6120-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="a6120-113">**[併置**されたサーバーの役割の選択] で、[**仲介サーバーの検索**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6120-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="a6120-114">選択したフロントエンドプールの種類が Enterprise Edition の場合は、そのフロントエンドプールのすべてのフロントエンドサーバーに仲介サーバーコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6120-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a6120-115">仲介サーバーで使用される <STRONG>次ホッププール</STRONG> は、仲介サーバーが併置されているフロントエンドプールです。</span><span class="sxs-lookup"><span data-stu-id="a6120-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a6120-116">仲介サーバーで使用される <STRONG>エッジプール</STRONG> は、仲介サーバーが併置されているフロントエンドプールに関連付けられているものと同じエッジプールになります。</span><span class="sxs-lookup"><span data-stu-id="a6120-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="a6120-117">Microsoft Office Communications Server 2007 R2 から PSTN への通話をルーティングするには、[ **既定** にする] をクリックして、このフロントエンドプールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6120-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="a6120-118">1つ以上のピアのフロントエンドプールへの関連付けが終了したら、[ **完了** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6120-119">エンタープライズ Voip 展開プロセスの次の手順に進む前に、仲介サーバープール (つまり、仲介サーバーコンポーネントがあるフロントエンドプール) が、指定した Fqdn を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6120-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="a6120-120">次に、展開ガイドのドキュメントの「 [Lync server 2013 のトポロジを公開](lync-server-2013-publish-the-topology.md) する」の手順に従って仲介サーバーをトポロジに追加してから、必要に応じて仲介サーバーのリッスンポートを変更する次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="a6120-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="a6120-121">トポロジビルダーを使用してトポロジを定義または変更するたびに、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6120-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="a6120-122">スタンドアロンの仲介サーバーの定義</span><span class="sxs-lookup"><span data-stu-id="a6120-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="a6120-123">このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズ Voip がまだ展開されていないサイトで、スタンドアロンの仲介サーバーまたはプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6120-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="a6120-124">このサイトでフロントエンドプールに併置された仲介サーバーを既に展開している場合は、このセクションをスキップして、lync server 2013 での [仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md) を実行してから、 [lync server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="a6120-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6120-125">このセクションでは、「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</A> 」の説明に従って、少なくとも1つのフロントエンドプールを事前にセットアップし、展開ガイドのドキュメントの「 <A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A> することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a6120-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="a6120-126">仲介サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="a6120-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="a6120-127">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a6120-128">トポロジビルダーのコンソールツリーで、仲介サーバーを定義するサイトの名前を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6120-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="a6120-129">コンソールツリーで、[ **仲介プール** ] ノードを右クリックし、[ **仲介サーバープール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="a6120-130">[ **新しい仲介プールの定義**] で、仲介サーバープールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6120-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="a6120-131">次に、以下のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6120-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="a6120-132">プールに複数の仲介サーバーを展開して高可用性を提供する場合は、[ **複数のコンピュータープール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6120-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a6120-133">複数の仲介サーバーがある仲介サーバープールをサポートするには、DNS 負荷分散を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6120-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="a6120-134">詳細については、「計画」のドキュメントの「Using dns Load balancing on <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A> 」の「dns 負荷分散を使用する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6120-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="a6120-135">高可用性を必要としないためにプールに仲介サーバーを1つだけ展開する場合は、[ **単一コンピューターのプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6120-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="a6120-136">以下のステップは省略してください。</span><span class="sxs-lookup"><span data-stu-id="a6120-136">Skip the following step.</span></span>

6.  <span data-ttu-id="a6120-137">前の手順で [ **複数のコンピュータープール** ] を選択した場合は、[ **このプール内のコンピューターの定義** ] 項目の [ **コンピューターの fqdn**] をクリックし、プール内の各サーバーの fqdn を入力して、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="a6120-138">プールに追加するその他のすべての仲介サーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a6120-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="a6120-139">プール内のすべてのコンピューターを定義したら、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="a6120-140">[ **次ホップの選択** ] ページで、[ **次ホッププール**] をクリックし、この仲介サーバープールを使用するフロントエンドプールの FQDN をクリックして、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="a6120-141">[**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6120-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a6120-142">エンタープライズ Voip が有効になっている外部ユーザーに PSTN 接続を提供する場合は、[ **この仲介サーバーで使用されるエッジプールを選択して**ください] で、この仲介サーバープールを使用してこれらの外部ユーザーに pstn 接続を提供するエッジサーバープールの FQDN をクリックし、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a6120-143">外部ユーザーのエンタープライズ Voip を有効にする予定がない場合、または内部ネットワークの外部にいるときにユーザーに PSTN 接続を提供しない場合は、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="a6120-144">次に、展開に関するドキュメントの「 [Lync server 2013 のトポロジを公開](lync-server-2013-publish-the-topology.md) する」の手順に従って、仲介サーバーをトポロジに追加します。</span><span class="sxs-lookup"><span data-stu-id="a6120-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="a6120-145">トポロジビルダーを使用してトポロジを構築または変更するたびに、トポロジを公開する必要があります。これにより、データを使用して、Lync Server を実行しているサーバーのファイルをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6120-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="a6120-146">次のステップに進み、必要に応じて仲介サーバー上のリッスン ポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="a6120-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="a6120-147">仲介サーバーのリッスンポートの定義</span><span class="sxs-lookup"><span data-stu-id="a6120-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="a6120-148">このトピックの手順に従って、トポロジビルダーを使用して、仲介サーバーまたはプールがゲートウェイピアからの着信接続を受け入れるリスニングポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6120-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="a6120-149">仲介サーバーのリッスンポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="a6120-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="a6120-150">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a6120-151">トポロジビルダーのコンソールツリーで、[ **仲介プール** ] ノードを展開し、以前に作成した仲介サーバーを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a6120-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="a6120-152">既定では、仲介サーバー上の SIP リスニングポートは、Lync Server からの tls トラフィック用の5070です。5067は、ピア (ゲートウェイ、PBXes、または sbc) からの TLS トラフィック用です。</span><span class="sxs-lookup"><span data-stu-id="a6120-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="a6120-153">TCP ポートは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a6120-153">TCP port is disabled by default.</span></span> <span data-ttu-id="a6120-154">TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6120-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="a6120-155">必要な TLS または TCP リッスンポートの範囲を指定します。仲介サーバーは、PSTN ゲートウェイからの着信接続を受け付けます。</span><span class="sxs-lookup"><span data-stu-id="a6120-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6120-156">[<STRONG>TCP ポートの有効化</STRONG>] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6120-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="a6120-157">この設定はオプションです。</span><span class="sxs-lookup"><span data-stu-id="a6120-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="a6120-158">次に、「lync server [2013 の仲介サーバーのファイルをインストールする](lync-server-2013-install-the-files-for-mediation-server.md)」の手順に従って、 [lync server 2013 の [トポロジビルダー] でゲートウェイを定義](lync-server-2013-define-a-gateway-in-topology-builder.md)し、各仲介サーバーにファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6120-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

