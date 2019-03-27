---
title: パイロット プールのレガシ エッジ サーバーへの接続
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバー 2019 の Skype を展開した後、サイトのフェデレーション ルートを構成する必要があります。 従来のインストールで使用されているフェデレーション ルートを使用するには、このルートを使用するビジネス サーバー 2019 の Skype を構成しなければなりません。
ms.openlocfilehash: 5a3498041b4af762d184cd56e3883a90612b13e0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874746"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="3489e-104">パイロット プールのレガシ エッジ サーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="3489e-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="3489e-105">ビジネス サーバー 2019 の Skype を展開した後、サイトのフェデレーション ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3489e-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="3489e-106">従来のインストールで使用されているフェデレーション ルートを使用するには、このルートを使用するビジネス サーバー 2019 の Skype を構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3489e-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="3489e-107">ダイレクタと従来の配置のエッジ サーバーを使用するのにビジネス サーバー 2019 サイトの Skype を有効にするには、従来のエッジ プールを関連付けるにはトポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="3489e-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="3489e-108">トポロジ ビルダーを使用してレガシ エッジ プールを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="3489e-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="3489e-109">トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="3489e-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="3489e-110">**Skype**ビジネス サーバーのノードの直下にある自分のサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="3489e-111">[**アクション**] メニューで、**プロパティの編集**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="3489e-112">左側のウィンドウでは、**フェデレーション ルート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="3489e-113">[**サイトのフェデレーション ルートの割り当て**は、**フェデレーションの SIP を有効にする**を選択し、ディレクターが表示されない場合は、従来のディレクター、または既存のエッジ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="3489e-114">**プロパティの編集**] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="3489e-115">トポロジ ビルダーでは、ビジネス サーバー 2019 ノードでは、Skype で**Standard Edition サーバー**または**エンタープライズ エディションのフロント エンド プール**に移動、プールを右クリックし、**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="3489e-116">[**関連付け**を**関連付けるエッジ プール**を (メディア コンポーネント) の横のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="3489e-117">リストから既存のエッジ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="3489e-118">**プロパティの編集**] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="3489e-119">**トポロジ ビルダー**では、 **Skype**ビジネス サーバーの最上位のノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3489e-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="3489e-120">**[操作**] メニューから [**トポロジの公開**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="3489e-121">**発行ウィザード**を完了すると、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3489e-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

