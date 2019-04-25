---
title: Skype ビジネス サーバーを常に仲介サーバーをバイパスするためのメディア バイ パスを構成します。
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。
ms.openlocfilehash: 31ecb80df342ac68ba6bb28b20248648bd5808c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223776"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d9023-103">Skype ビジネス サーバーを常に仲介サーバーをバイパスするためのメディア バイ パスを構成します。</span><span class="sxs-lookup"><span data-stu-id="d9023-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="d9023-104">常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d9023-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="d9023-105">使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略、前提としてビジネス エンドポイントの Skype とトランク接続でメディア バイ パスを構成するすべてのピアとの間の適切な接続があること。</span><span class="sxs-lookup"><span data-stu-id="d9023-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="d9023-106">Skype ビジネス エンドポイントとのメディアのバイパスがそれぞれのトランク接続が有効になっている仲介サーバーへのすべてのピアとの間の適切な接続がない場合は、サイトと地域の情報を使用してグローバル メディア バイ パスの設定を構成する必要があります。用いたメディアをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="d9023-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="d9023-107">これにより、メディアが仲介サーバーをバイパスするときを決定するときに詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="d9023-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="d9023-108">これを行うには、[構成メディア ビジネス サーバーは、サイトと地域の情報を使用するの Skype のグローバル設定を使用しない](use-site-and-region-information.md)と、[ネットワーク サイトとサブネットを関連付ける](deploy-network.md#BKMK_AssociateSubnets)手順を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="d9023-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="d9023-109">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="d9023-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="d9023-110">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9023-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="d9023-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9023-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="d9023-112">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9023-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="d9023-113">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9023-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="d9023-114">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9023-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="d9023-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9023-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9023-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9023-116">See also</span></span>

[<span data-ttu-id="d9023-117">ビジネス用の Skype でメディアをバイパスするための計画します。</span><span class="sxs-lookup"><span data-stu-id="d9023-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="d9023-118">ビジネス サーバーの Skype でのメディア バイ パスを展開します。</span><span class="sxs-lookup"><span data-stu-id="d9023-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

