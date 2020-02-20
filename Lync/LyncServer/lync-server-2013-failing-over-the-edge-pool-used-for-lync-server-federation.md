---
title: 'Lync Server 2013: Lync Server フェデレーションに使用するエッジプールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e374337f261c6747bc1b147c9f2e02fa51efe3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="104d6-102">Lync Server 2013 での Lync Server フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="104d6-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="104d6-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="104d6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="104d6-104">Lync Server のフェデレーションが構成されているエッジ プールがダウンした場合、フェデレーションを動作させるには、別のエッジ プールを使用するようにフェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104d6-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="104d6-105">Lync Server のフェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="104d6-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="104d6-p101">フロントエンド サーバーでトポロジ ビルダーを開きます。[**エッジ プール**] を展開し、現在フェデレーションに構成されているエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="104d6-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="104d6-p102">[**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオフにします。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104d6-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="104d6-p103">[**エッジ プール**] を展開し、フェデレーションに使用するエッジ サーバーまたはエッジ サーバー プールを右クリックして、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="104d6-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="104d6-p104">[**全般**] の [**プロパティの編集**] で、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] をオンにします。[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="104d6-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="104d6-p105">[**アクション**] をクリックし、[**トポロジ**]、[**公開**] の順に選択します。[**トポロジの公開**] で入力を求められたら、[**次へ**] をクリックします。公開の終了後、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104d6-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="104d6-p106">エッジ サーバーで、Lync Server 展開ウィザードを開きます。[**Lync Server システムのインストールまたは更新**]、[**Lync Server コンポーネントのセットアップまたは削除**] の順にクリックします。[**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104d6-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="104d6-p107">[Lync Server コンポーネントのセットアップ] で、[**次へ**] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[**ログの表示**] をクリックして、参照できるログ ファイルを表示します。[**完了**] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="104d6-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="104d6-125">失敗したエッジ プールを含むサイトにまだ稼動中のフロントエンド サーバーがある場合は、まだ稼動中のリモート サイトのエッジ プールを使用するように、これらのフロントエンド プールの Web 会議サービスおよび音声ビデオ会議サービスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="104d6-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="104d6-126">詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104d6-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="104d6-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="104d6-127">See Also</span></span>


[<span data-ttu-id="104d6-128">Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="104d6-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="104d6-129">Lync server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジプールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="104d6-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="104d6-130">Lync Server 2013 でのエッジサーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="104d6-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

