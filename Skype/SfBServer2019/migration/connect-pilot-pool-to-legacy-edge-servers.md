---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。 従来のインストールで使用されているフェデレーションルートを使用するためには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753927"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="62da7-104">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="62da7-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="62da7-105">Skype for Business Server 2019 を展開した後、サイトのフェデレーションルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62da7-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="62da7-106">従来のインストールで使用されているフェデレーションルートを使用するためには、このルートを使用するように Skype for Business Server 2019 を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62da7-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="62da7-107">Skype for Business Server 2019 サイトが従来の展開のディレクターおよびエッジサーバーを使用できるようにするには、トポロジビルダーを使用して、従来のエッジプールを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="62da7-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="62da7-108">トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="62da7-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="62da7-109">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="62da7-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="62da7-110">[ **Skype For Business Server** ] ノードのすぐ下にあるサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="62da7-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="62da7-111">[**操作**] メニューの [**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62da7-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="62da7-112">左ウィンドウで、[**フェデレーション ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62da7-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="62da7-113">[**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] を選択してから、従来のディレクター、またはディレクターが表示されていない場合は従来のエッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="62da7-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="62da7-114">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="62da7-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="62da7-115">[トポロジビルダー] の [Skype for Business Server 2019] ノードで、 **Standard Edition サーバー**または**Enterprise Edition フロントエンドプール**に移動して、プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62da7-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="62da7-116">[**関連付け**] で、[**エッジ プール (メディア コンポーネント用) を関連付ける**] の横のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="62da7-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="62da7-117">一覧から、レガシ エッジ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="62da7-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="62da7-118">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="62da7-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="62da7-119">[**トポロジビルダー**] で、最上位ノードの [ **Skype for business Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="62da7-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="62da7-120">[**操作**] メニューで、[**トポロジの公開**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="62da7-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="62da7-121">**公開ウィザード**の実行が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62da7-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

