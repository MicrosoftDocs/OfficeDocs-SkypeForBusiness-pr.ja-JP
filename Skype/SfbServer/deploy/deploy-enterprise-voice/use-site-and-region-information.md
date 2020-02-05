---
title: サイトと地域の情報を使用するために、Skype for Business Server でメディアを無視するグローバル設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Skype for Business Server Enterprise Voice で特定のサイトと地域に対してのみ使用するようにメディアバイパスを構成します。
ms.openlocfilehash: 7a424e6737c1165eb037ca1130e3b87c4d0436e0
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766940"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="6deaa-103">サイトと地域の情報を使用するために、Skype for Business Server でメディアを無視するグローバル設定を構成する</span><span class="sxs-lookup"><span data-stu-id="6deaa-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="6deaa-104">Skype for Business Server Enterprise Voice で特定のサイトと地域に対してのみ使用するようにメディアバイパスを構成します。</span><span class="sxs-lookup"><span data-stu-id="6deaa-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="6deaa-105">このトピックの手順を使用してメディアのバイパスのグローバル設定を構成する場合、すべての Skype for Business エンドポイントと、トランク接続でメディアをバイパスするように構成したピアとの間の接続が良好でないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6deaa-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6deaa-p101">ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="6deaa-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="6deaa-109">メディアのバイパスが正常に動作するためには、トポロジビルダーで定義されているサイトと、ネットワーク領域とネットワークサイトを構成するときに定義されているサイトの間で一貫性が保たれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6deaa-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="6deaa-110">たとえば、PSTN ゲートウェイのみが展開されていることを示すために、トポロジビルダーで定義したブランチサイトがある場合、そのブランチサイトは、ブランチサイトユーザーが pstn 経由でルーティングする PSTN 通話を使用できるようにするエンタープライズ Voip ポリシーを使って構成する必要があります。ブランチサイトのゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="6deaa-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="6deaa-111">メディア バイパスのサイトおよび地域情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="6deaa-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="6deaa-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6deaa-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="6deaa-113">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6deaa-114">表の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="6deaa-115">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="6deaa-116">[**サイトと地域の構成を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="6deaa-117">必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6deaa-p103">このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="6deaa-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6deaa-121">Click **Commit**.</span></span>
    
<span data-ttu-id="6deaa-p104">次に、「[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)」の説明に従ってネットワーク サイトにサブネットを追加します。すべてのサブネットをネットワーク サイトに関連付けたら、メディア バイパスの展開は完了です。</span><span class="sxs-lookup"><span data-stu-id="6deaa-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6deaa-124">ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6deaa-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="6deaa-125">詳細については、「 [Skype For business でネットワークのリージョン、サイト、サブネットを展開](deploy-network.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6deaa-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6deaa-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6deaa-126">See also</span></span>

[<span data-ttu-id="6deaa-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="6deaa-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

