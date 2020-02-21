---
title: パイロットプールを従来のエッジサーバーに接続する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48d2450d468ae6a28faef4c1fcacf577262c42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="dad4a-102">パイロットプールを従来のエッジサーバーに接続する</span><span class="sxs-lookup"><span data-stu-id="dad4a-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dad4a-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dad4a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dad4a-104">Lync Server 2013 を展開した後に、このサイトのフェデレーションルートが構成されていません。</span><span class="sxs-lookup"><span data-stu-id="dad4a-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="dad4a-105">Office Communications Server 2007 R2 で使用されているフェデレーションルートを使用するためには、このルートを使用するように Lync Server 2013 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad4a-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="dad4a-106">Lync Server 2013 サイトが BackCompatSite のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="dad4a-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="dad4a-107">トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="dad4a-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="dad4a-108">トポロジビルダーでパイロットプールトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="dad4a-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="dad4a-109">Lync Server 2013 サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="dad4a-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="dad4a-110">[**アクション**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dad4a-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="dad4a-111">ディレクターが表示されていない場合は、[**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] を選択してから、Office Communications server 2007 R2 Director または Office Communications Server 2007 r2 エッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dad4a-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="dad4a-112">![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="dad4a-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="dad4a-113">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dad4a-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="dad4a-114">[トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard Edition サーバー**または**Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dad4a-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="dad4a-115">[**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="dad4a-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="dad4a-116">リストから、BackCompatSite のエッジサーバーインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="dad4a-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="dad4a-117">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="dad4a-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="dad4a-118">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="dad4a-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="dad4a-119">**トポロジ ビルダー**で、最上位ノードの **Lync Server** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dad4a-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="dad4a-120">[**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dad4a-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="dad4a-121">**公開ウィザード**の実行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dad4a-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

