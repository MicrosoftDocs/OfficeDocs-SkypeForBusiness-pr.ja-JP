---
title: Skype for Business Server でメディアバイパスを構成して、常に仲介サーバーをバイパスする
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: メディアバイパスを有効にして、Skype for Business Server Enterprise Voice の仲介サーバーを常にバイパスします。
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768270"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="23146-103">Skype for Business Server でメディアバイパスを構成して、常に仲介サーバーをバイパスする</span><span class="sxs-lookup"><span data-stu-id="23146-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="23146-104">メディアバイパスを有効にして、Skype for Business Server Enterprise Voice の仲介サーバーを常にバイパスします。</span><span class="sxs-lookup"><span data-stu-id="23146-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="23146-105">このトピックの手順を使用してメディアバイパスのグローバル設定を構成する場合は、Skype for Business エンドポイントと、トランク接続でメディアをバイパスするように構成したすべてのピアとの間に接続性が良好であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="23146-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="23146-106">Skype for Business エンドポイントと、各トランク接続がメディアバイパスに対応している仲介サーバーへのすべてのピアとの接続が適切でない場合は、サイトと地域の情報を使用するようにグローバルメディアバイパス設定を構成する必要があります。メディアのバイパスを採用している場合。</span><span class="sxs-lookup"><span data-stu-id="23146-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="23146-107">これにより、メディアが仲介サーバーをバイパスするタイミングをより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="23146-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="23146-108">これを行うには、「 [Skype For Business Server でのグローバル設定のメディアを無視する](use-site-and-region-information.md)」の手順に従って、サイトと地域の情報を使用し、[サブネットをネットワークサイトに関連付け](deploy-network.md#BKMK_AssociateSubnets)ます。</span><span class="sxs-lookup"><span data-stu-id="23146-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="23146-109">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="23146-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="23146-110">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23146-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="23146-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23146-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="23146-112">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="23146-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="23146-113">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="23146-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="23146-114">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23146-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="23146-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23146-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="23146-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23146-116">See also</span></span>

[<span data-ttu-id="23146-117">Skype for Business でのメディアのバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="23146-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="23146-118">Skype for Business Server でメディアバイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="23146-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

