---
title: 'Lync Server 2013: Lync Server フェデレーションに使用するエッジ プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="f1041-102">Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f1041-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1041-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f1041-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f1041-104">Lync Server フェデレーションが構成されている Edge プールが停止している場合は、フェデレーションが機能するために別のエッジプールを使用するようにフェデレーションを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1041-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="f1041-105">Lync Server Federation に使用されるエッジプールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f1041-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="f1041-106">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="f1041-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="f1041-107">[ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="f1041-108">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f1041-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="f1041-109">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="f1041-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1041-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-110">Click **OK**.</span></span>

3.  <span data-ttu-id="f1041-111">[ **Edge プール**] を展開して、フェデレーションに使用するエッジサーバーまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="f1041-112">[**プロパティの編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f1041-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="f1041-113">[**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1041-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="f1041-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-114">Click **OK**.</span></span>

5.  <span data-ttu-id="f1041-115">[**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1041-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="f1041-116">**トポロジの発行**を求められたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="f1041-117">発行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="f1041-118">エッジサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1041-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="f1041-119">[ **Lync Server System のインストールまたは更新**] をクリックし、[ **lync Server コンポーネントのセットアップまたは削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="f1041-120">[**実行] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="f1041-121">Lync Server コンポーネントのセットアップで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1041-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="f1041-122">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1041-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="f1041-123">展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1041-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="f1041-124">[**完了**] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="f1041-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="f1041-125">問題のあるエッジプールを含むサイトにまだ実行されているフロントエンドサーバーが含まれている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、まだ実行中のリモートサイトでエッジプールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1041-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="f1041-126">詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1041-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1041-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1041-127">See Also</span></span>


[<span data-ttu-id="f1041-128">Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="f1041-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="f1041-129">Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック</span><span class="sxs-lookup"><span data-stu-id="f1041-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="f1041-130">Lync Server 2013 でのエッジ サーバーの障害復旧</span><span class="sxs-lookup"><span data-stu-id="f1041-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

