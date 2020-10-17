---
title: パイロット プールのレガシ エッジ サーバーへの接続
description: パイロットプールを従来のエッジサーバーに接続します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede2256efabf561be6b3f99543437087cb5c3890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550273"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="89b55-103">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="89b55-103">Connect pilot pool to legacy Edge Servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89b55-104">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="89b55-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="89b55-105">Lync Server 2013 を展開した後、サイトのフェデレーションルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b55-105">After deploying Lync Server 2013, you need to configure a federation route for your site.</span></span> <span data-ttu-id="89b55-106">Lync Server 2010 で使用されているフェデレーションルートを使用するためには、このルートを使用するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b55-106">In order to use the federated route that is being used by Lync Server 2010, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="89b55-107">Lync server 2013 サイトが Lync Server 2010 展開のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="89b55-107">To enable the Lync Server 2013 site to use the Director and Edge Server of the Lync Server 2010 deployment, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="89b55-108">トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="89b55-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="89b55-109">**トポロジ ビルダー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="89b55-109">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="89b55-110">**Lync Server** ノードの直下にあるサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="89b55-110">Select your site, which is directly below the **Lync Server** node.</span></span>

3.  <span data-ttu-id="89b55-111">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b55-111">On the **Actions** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="89b55-112">左ウィンドウで、[**フェデレーション ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b55-112">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="89b55-113">ディレクターが表示されていない場合は、[ **サイトのフェデレーションルートの割り当て**] で [ **SIP フェデレーションの有効化**] を選択し、[lync server 2010 director] または [Lync server 2010 エッジサーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89b55-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Lync Server 2010 Director, or the Lync Server 2010 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="89b55-114">![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="89b55-114">![Edit Properties, Federation route page](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg "Edit Properties, Federation route page")</span></span>  

6.  <span data-ttu-id="89b55-115">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="89b55-115">Click **OK** to close the **Edit Properties** page.</span></span>

7.  <span data-ttu-id="89b55-116">[トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard Edition サーバー** または **Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[ **プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b55-116">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

8.  <span data-ttu-id="89b55-117">[**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="89b55-117">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

9.  <span data-ttu-id="89b55-118">一覧から、レガシ エッジ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="89b55-118">From the list, select the legacy Edge Server.</span></span>
    
    <span data-ttu-id="89b55-119">![従来のエッジを選択する [プロパティの編集] ダイアログ](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "従来のエッジを選択する [プロパティの編集] ダイアログ")</span><span class="sxs-lookup"><span data-stu-id="89b55-119">![Edit Properties dialog, selecting the legacy Edge](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg "Edit Properties dialog, selecting the legacy Edge")</span></span>  

10. <span data-ttu-id="89b55-120">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="89b55-120">Click **OK** to close the **Edit Properties** page.</span></span>

11. <span data-ttu-id="89b55-121">**トポロジ ビルダー**で、最上位ノードの **Lync Server** を選択します。</span><span class="sxs-lookup"><span data-stu-id="89b55-121">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

12. <span data-ttu-id="89b55-122">[**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b55-122">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

13. <span data-ttu-id="89b55-123">**公開ウィザード**の実行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b55-123">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

