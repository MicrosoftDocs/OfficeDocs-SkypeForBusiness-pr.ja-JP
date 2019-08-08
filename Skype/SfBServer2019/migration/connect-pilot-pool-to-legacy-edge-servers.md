---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。
ms.openlocfilehash: 7a5a65e1488d5a119e3d11affbbaa9995a06626e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239225"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="442e0-104">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="442e0-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="442e0-105">Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="442e0-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="442e0-106">従来のインストールで使用されているフェデレーションルートを使用するには、Skype for Business Server 2019 がこのルートを使用するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="442e0-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="442e0-107">Skype for Business Server 2019 サイトで従来の展開のディレクターとエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="442e0-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="442e0-108">トポロジビルダーを使用して従来のエッジプールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="442e0-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="442e0-109">トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="442e0-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="442e0-110">**Skype For Business Server**ノードのすぐ下にあるサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="442e0-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="442e0-111">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="442e0-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="442e0-112">左側のウィンドウで、[**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="442e0-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="442e0-113">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選択し、[レガシディレクター]、またはディレクターが表示されていない場合は従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="442e0-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="442e0-114">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="442e0-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="442e0-115">[トポロジビルダー] の [Skype for Business Server 2019] ノードで、 **Standard edition Server**または**Enterprise Edition のフロントエンドプール**に移動し、プールを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="442e0-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="442e0-116">[**関連付け**] で [ **Edge プールを関連付ける (メディアコンポーネント)**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="442e0-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="442e0-117">リストから、従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="442e0-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="442e0-118">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="442e0-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="442e0-119">[**トポロジビルダー**] で、最上位のノードである [ **Skype for business Server**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="442e0-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="442e0-120">[**操作**] メニューの [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="442e0-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="442e0-121">**発行ウィザード**が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="442e0-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

