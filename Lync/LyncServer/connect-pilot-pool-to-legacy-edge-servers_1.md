---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="16989-102">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="16989-102">Connect pilot pool to legacy Edge Servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16989-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="16989-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="16989-104">Lync Server 2013 を展開した後、このサイトのフェデレーションルートは構成されていません。</span><span class="sxs-lookup"><span data-stu-id="16989-104">After deploying Lync Server 2013, a federation route for this site is not configured.</span></span> <span data-ttu-id="16989-105">Office Communications Server 2007 R2 で使用されているフェデレーションルートを使用するには、Lync Server 2013 がこのルートを使用するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16989-105">In order to use the federated route that is being used by Office Communications Server 2007 R2, Lync Server 2013 must be configured to use this route.</span></span>

<span data-ttu-id="16989-106">Lync Server 2013 サイトで BackCompatSite のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="16989-106">To enable the Lync Server 2013 site to use the Director and Edge Server of the BackCompatSite, use Topology Builder to associate the legacy Edge pool.</span></span>

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="16989-107">トポロジビルダーを使用して従来のエッジプールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="16989-107">To associate the legacy Edge pool by using Topology Builder</span></span>

1.  <span data-ttu-id="16989-108">トポロジビルダーでパイロットプールトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="16989-108">Open the pilot pool topology in Topology Builder.</span></span>

2.  <span data-ttu-id="16989-109">Lync Server 2013 サイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="16989-109">Select your Lync Server 2013 site.</span></span>

3.  <span data-ttu-id="16989-110">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16989-110">On the **Action** menu, click **Edit Properties**.</span></span>

4.  <span data-ttu-id="16989-111">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選択し、ディレクターが表示されていない場合は、Office Communications server 2007 R2 ディレクターか、Office Communications Server 2007 r2 エッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="16989-111">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the Office Communications Server 2007 R2 Director, or the Office Communications Server 2007 R2 Edge Server if no Director is listed.</span></span>
    
    <span data-ttu-id="16989-112">![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="16989-112">![Edit Properties dialog, Federation route page](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>  

5.  <span data-ttu-id="16989-113">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="16989-113">Click **OK** to close the **Edit Properties** page.</span></span>

6.  <span data-ttu-id="16989-114">[トポロジビルダー] の [Lync Server 2013] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16989-114">In Topology Builder, under the Lync Server 2013 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="16989-115">[**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="16989-115">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span>

8.  <span data-ttu-id="16989-116">リストから、BackCompatSite のエッジサーバーインターフェイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="16989-116">From the list, select the Edge Server interface for the BackCompatSite.</span></span>
    
    <span data-ttu-id="16989-117">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="16989-117">![Edit Properties dialog, General page](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "Edit Properties dialog, General page")</span></span>  

9.  <span data-ttu-id="16989-118">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="16989-118">Click **OK** to close the **Edit Properties** page.</span></span>

10. <span data-ttu-id="16989-119">[**トポロジビルダー**] で、最上位のノードである**Lync Server**を選択します。</span><span class="sxs-lookup"><span data-stu-id="16989-119">In **Topology Builder**, select the top-most node, **Lync Server**.</span></span>

11. <span data-ttu-id="16989-120">[**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16989-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

12. <span data-ttu-id="16989-121">**発行ウィザード**が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16989-121">When the **Publishing wizard** completes, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

