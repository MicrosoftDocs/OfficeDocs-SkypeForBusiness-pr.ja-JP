---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813705"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="2ca05-104">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="2ca05-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="2ca05-105">Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ca05-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="2ca05-106">従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ca05-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="2ca05-107">Skype for Business Server 2019 サイトで従来の展開のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="2ca05-108">トポロジビルダーを使用して従来のエッジプールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="2ca05-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="2ca05-109">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="2ca05-110">**Skype For Business Server**ノードのすぐ下にあるサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="2ca05-111">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ca05-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="2ca05-112">左側のウィンドウで、[**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="2ca05-113">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選択し、[レガシディレクター]、またはディレクターが表示されていない場合は従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ca05-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="2ca05-114">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="2ca05-115">[トポロジビルダー] の [Skype for Business Server 2019] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ca05-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="2ca05-116">[**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2ca05-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="2ca05-117">リストから、従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2ca05-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="2ca05-118">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="2ca05-119">[**トポロジビルダー**] で、最上位のノードである [ **Skype for business Server**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2ca05-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="2ca05-120">[**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ca05-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="2ca05-121">**発行ウィザード**が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ca05-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

