---
title: Skype for Business Server でメディア バイパスを構成して、常に仲介サーバーをバイパスする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: メディア バイパスを有効にして、Skype for Business Server の仲介サーバーを常にバイパスエンタープライズ VoIP。
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804217"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="b3e98-103">Skype for Business Server でメディア バイパスを構成して、常に仲介サーバーをバイパスする</span><span class="sxs-lookup"><span data-stu-id="b3e98-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="b3e98-104">メディア バイパスを有効にして、Skype for Business Server の仲介サーバーを常にバイパスエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="b3e98-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="b3e98-105">このトピックの手順を使用してメディア バイパスのグローバル設定を構成する場合、Skype for Business エンドポイントとトランク接続でメディア バイパスを構成したピア間の接続が良好な場合が前提です。</span><span class="sxs-lookup"><span data-stu-id="b3e98-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="b3e98-106">Skype for Business エンドポイントと、それぞれのトランク接続でメディア バイパスが有効になっている仲介サーバーへのすべてのピア間の接続が良好ではない場合は、メディア バイパスを使用するときにサイトおよび地域情報を使用するグローバル メディア バイパス設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3e98-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="b3e98-107">これにより、メディアが仲介サーバーをバイパスするか判定する際に、よりよく制御できます。</span><span class="sxs-lookup"><span data-stu-id="b3e98-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="b3e98-108">これを行うには [、「Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and Associate a subnet with a network [site](deploy-network.md#BKMK_AssociateSubnets) instead」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3e98-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="b3e98-109">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="b3e98-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="b3e98-110">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3e98-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b3e98-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e98-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b3e98-112">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e98-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="b3e98-113">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b3e98-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="b3e98-114">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e98-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="b3e98-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3e98-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3e98-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3e98-116">See also</span></span>

[<span data-ttu-id="b3e98-117">Skype for Business でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="b3e98-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="b3e98-118">Skype for Business Server でのメディア バイパスの展開</span><span class="sxs-lookup"><span data-stu-id="b3e98-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

