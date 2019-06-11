---
title: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e5a7d-102">Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="e5a7d-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a7d-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e5a7d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e5a7d-104">フェデレーションをホストするために使用された、失敗したエッジプールをオンラインに戻した後、次の手順を実行して、Lync Server フェデレーションルートまたは XMPP フェデレーションルートをフェイルバックし、この復元されたエッジプールを再び使用します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="e5a7d-105">復元されたエッジプールへのフェデレーションのフェイルバック</span><span class="sxs-lookup"><span data-stu-id="e5a7d-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="e5a7d-106">もう一度使用できるようになったエッジプールで、エッジサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="e5a7d-107">復元されたエッジサーバーを使用するために Lync Server フェデレーションルートをフェイルバックする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e5a7d-108">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="e5a7d-109">[ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="e5a7d-110">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e5a7d-111">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="e5a7d-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="e5a7d-113">[ **Edge プール**] を展開し、もう一度フェデレーションに使用する元のエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="e5a7d-114">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e5a7d-115">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="e5a7d-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="e5a7d-117">[**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="e5a7d-118">**トポロジの発行**を求められたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="e5a7d-119">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="e5a7d-120">エッジサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="e5a7d-121">[ **Lync Server System のインストールまたは更新**] をクリックし、[ **lync Server コンポーネントのセットアップまたは削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="e5a7d-122">[**実行] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="e5a7d-123">Lync Server コンポーネントのセットアップで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="e5a7d-124">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="e5a7d-125">展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="e5a7d-126">[**完了**] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="e5a7d-127">復元されたエッジサーバーを使用するために XMPP フェデレーションルートをフェイルバックする場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e5a7d-128">次のコマンドレットを実行して、xmpp フェデレーションルートを Edge プールに再ポイントします。これにより、XMPP フェデレーションがホストされます (この例では EdgeServer1)。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="e5a7d-129">この例では、Site1 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer1.contoso.com はそのプールのエッジサーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="e5a7d-130">Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="e5a7d-131">この SRV レコードには、5269のポート値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="e5a7d-132">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="e5a7d-133">XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="e5a7d-134">フロントエンドプールが、失敗して復元されたエッジプールが含まれているサイトでまだ実行されている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、もう一度ローカルサイトでエッジプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="e5a7d-135">詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="e5a7d-136">障害が発生したエッジプールと同じサイトのフロントエンドプールでもエラーが発生する場合は、CsPoolFailback を使ってフロントエンドプールをフェールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5a7d-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5a7d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5a7d-137">See Also</span></span>


[<span data-ttu-id="e5a7d-138">Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="e5a7d-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="e5a7d-139">Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="e5a7d-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="e5a7d-140">Lync Server 2013 でのエッジ サーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="e5a7d-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

