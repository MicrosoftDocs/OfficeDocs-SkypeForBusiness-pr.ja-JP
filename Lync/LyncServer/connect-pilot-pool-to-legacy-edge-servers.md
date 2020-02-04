---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="050ea-102">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="050ea-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="050ea-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="050ea-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="050ea-104">Lync Server 2013 を展開した後、サイトのフェデレーションルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="050ea-104">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="050ea-105">Lync Server 2010 で使用されているフェデレーションルートを使用するには、Lync Server 2013 がこのルートを使用するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="050ea-105">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="050ea-106">Lync server 2013 サイトで Lync Server 2010 展開のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="050ea-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="050ea-107">トポロジビルダーを使用して従来のエッジプールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="050ea-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="050ea-108">**トポロジビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="050ea-108">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="050ea-109">**Lync Server**ノードのすぐ下にあるサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="050ea-109">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="050ea-110">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="050ea-110">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="050ea-111">左側のウィンドウで、[**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="050ea-111">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="050ea-112">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、lync server 2010 ディレクター、またはディレクターが表示されていない場合は Lync server 2010 エッジサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="050ea-112">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="050ea-113">![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="050ea-113">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="050ea-114">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="050ea-114">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="050ea-115">[トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="050ea-115">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="050ea-116">[**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="050ea-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="050ea-117">リストから、従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="050ea-117">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="050ea-118">![[プロパティの編集] ダイアログ、[旧端] の選択](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "[プロパティの編集] ダイアログ、[旧端] の選択")</span><span class="sxs-lookup"><span data-stu-id="050ea-118">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="050ea-119">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="050ea-119">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="050ea-120">[**トポロジビルダー**] で、最上位のノードである**Lync Server**を選択します。</span><span class="sxs-lookup"><span data-stu-id="050ea-120">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="050ea-121">[**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="050ea-121">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="050ea-122">**発行ウィザード**が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="050ea-122">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

