---
title: ビジネス サーバーは、サイトと地域の情報を使用するの Skype でメディア バイ パスのグローバル設定を構成します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: ビジネス サーバーのエンタープライズ VoIP の特定のサイトと Skype 内の領域のみに使用するメディア バイ パスを構成します。
ms.openlocfilehash: 93cc6bea9a4f130bd4b2c0e455b979b477888eeb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222570"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="a56be-103">ビジネス サーバーは、サイトと地域の情報を使用するの Skype でメディア バイ パスのグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a56be-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="a56be-104">ビジネス サーバーのエンタープライズ VoIP の特定のサイトと Skype 内の領域のみに使用するメディア バイ パスを構成します。</span><span class="sxs-lookup"><span data-stu-id="a56be-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="a56be-105">使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略が前提とする必要はありませんビジネス エンドポイントのすべての Skype とトランク接続でメディア バイ パスを構成するすべてのピア間の接続が良好です。</span><span class="sxs-lookup"><span data-stu-id="a56be-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a56be-p101">ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="a56be-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="a56be-109">メディアを使用するバイパスの正しく必要があります一貫性、サイト間トポロジ ビルダーで定義されていると、ネットワーク地域およびネットワーク サイトを構成すると定義されています。</span><span class="sxs-lookup"><span data-stu-id="a56be-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="a56be-110">などがあると、トポロジ ビルダーで定義したブランチ サイトがある場合、PSTN ゲートウェイのみを展開し、ブランチ サイトのユーザー、PSTN 通話を PSTN 経由でルーティングを有効にするエンタープライズ VoIP ポリシーを使用してそのブランチ サイトを構成する必要があります。ブランチ サイトのゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="a56be-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="a56be-111">メディア バイパスのサイトおよび地域情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="a56be-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="a56be-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a56be-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="a56be-113">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a56be-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="a56be-114">表の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a56be-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="a56be-115">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a56be-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="a56be-116">[**サイトと地域の構成を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a56be-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="a56be-117">必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a56be-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a56be-p103">このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a56be-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="a56be-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a56be-121">Click **Commit**.</span></span>
    
<span data-ttu-id="a56be-p104">次に、「[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)」の説明に従ってネットワーク サイトにサブネットを追加します。すべてのサブネットをネットワーク サイトに関連付けたら、メディア バイパスの展開は完了です。</span><span class="sxs-lookup"><span data-stu-id="a56be-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a56be-124">ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a56be-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="a56be-125">詳細については、[ネットワークの領域を展開、サイトとサブネットでビジネス用の Skype](deploy-network.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56be-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a56be-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a56be-126">See also</span></span>

[<span data-ttu-id="a56be-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="a56be-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

