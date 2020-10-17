---
title: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック
description: Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137910d71de1d6177356e0b7bacbd6d17022d71d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567723"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="6fa6f-103">Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="6fa6f-103">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fa6f-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6fa6f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6fa6f-105">フェデレーションをホストしていたエッジ プールが障害から復旧してオンライに戻ったら、その復旧されたエッジ プールが再び使用されるように、以下の手順を使って Lync Server フェデレーション ルート または XMPP フェデレーション ルート (あるいはこの両方) をフェールバックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-105">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="6fa6f-106">復旧されたエッジ プールにフェデレーションをフェールバックする</span><span class="sxs-lookup"><span data-stu-id="6fa6f-106">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="6fa6f-107">再び使用できるようになったエッジ プールで、エッジ サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-107">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="6fa6f-108">復旧されたエッジ サーバーが使用されるように Lync Server フェデレーション ルートをフェールバックするには以下を行います。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-108">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="6fa6f-p101">フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーション用に構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="6fa6f-p102">[**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をクリアします。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="6fa6f-p103">[**エッジ プール**] を展開し、フェデレーションに再び使用する元のエッジ サーバーまたはエッジ サーバー プールを右クリックします。[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="6fa6f-p104">[**プロパティの編集**] の [**全般**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] を選択します。[\*\*OK \*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="6fa6f-p105">[**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="6fa6f-p106">エッジ サーバーで、Lync Server 展開ウィザードを開きます。[**Lync Server システムのインストールまたは更新**]、[**Lync Server コンポーネントのセットアップまたは削除**] の順にクリックします。[**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="6fa6f-p107">[Lync Server コンポーネントのセットアップ] で、[**次へ**] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。[**完了**] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="6fa6f-128">復旧されたエッジ サーバーが使用されるように XMPP フェデレーション ルートをフェールバックするには以下を行います。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-128">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="6fa6f-129">以下のコマンドレットを実行して、XMPP フェデレーション ルートが、XMPP フェデレーションをホストするようになるエッジ プール (この例では、EdgeServer1) を再び指すようにします。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-129">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="6fa6f-130">この例では、Site1 は XMPP フェデレーション ルートをホストするようになるエッジ プールを含むサイトです。EdgeServer1.contoso.com はそのプール内のエッジ サーバーの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-130">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="6fa6f-p108">XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="6fa6f-133">外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-133">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="6fa6f-134">XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-134">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="6fa6f-135">障害発生後に復旧されたエッジ プールを含むサイトで、フロントエンド プールが実行を続けていた場合は、それらのフロントエンド プール上の Web 会議サービスおよび音声ビデオ会議サービスを更新して、ローカル サイトのエッジ プールが再び使用されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-135">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="6fa6f-136">詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-136">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="6fa6f-137">停止したエッジ プールと同じサイトでフロントエンド プールも停止していた場合は、Invoke–CsPoolFailback を使ってフロントエンド プールをフェールバックできます。</span><span class="sxs-lookup"><span data-stu-id="6fa6f-137">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fa6f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fa6f-138">See Also</span></span>


[<span data-ttu-id="6fa6f-139">Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="6fa6f-139">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="6fa6f-140">Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="6fa6f-140">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="6fa6f-141">Lync Server 2013 でのエッジサーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="6fa6f-141">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

