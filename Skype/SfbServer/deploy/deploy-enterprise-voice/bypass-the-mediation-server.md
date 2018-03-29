---
title: 常に仲介サーバーをバイパスするサーバー 2015 のビジネス用の Skype でのメディア バイ パスを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。
ms.openlocfilehash: 5a7ca70b6f060c9d6a5399934fb784c9247e95fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="3e003-103">常に仲介サーバーをバイパスするサーバー 2015 のビジネス用の Skype でのメディア バイ パスを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e003-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="3e003-104">常にビジネス サーバーのエンタープライズ VoIP の Skype に仲介サーバーをバイパスするのにはメディア バイ パスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3e003-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="3e003-105">使用する場合は、メディアのグローバル設定を構成するには、このトピックの手順を省略、前提としてビジネス エンドポイントの Skype とトランク接続でメディア バイ パスを構成するすべてのピアとの間の適切な接続があること。</span><span class="sxs-lookup"><span data-stu-id="3e003-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="3e003-106">Skype ビジネス エンドポイントとのメディアのバイパスがそれぞれのトランク接続が有効になっている仲介サーバーへのすべてのピアとの間の適切な接続がない場合は、サイトと地域の情報を使用してグローバル メディア バイ パスの設定を構成する必要があります。用いたメディアをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="3e003-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="3e003-107">これにより、メディアが仲介サーバーをバイパスするときを決定するときに詳細に制御できます。</span><span class="sxs-lookup"><span data-stu-id="3e003-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="3e003-108">これを行うには、[メディアの構成は、サイトと地域の情報を使用してサーバー 2015 のビジネス用の Skype のグローバル設定をバイパス](use-site-and-region-information.md)し、[ネットワーク サイトとサブネットを関連付ける](deploy-network.md#BKMK_AssociateSubnets)手順を代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="3e003-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="3e003-109">仲介サーバーを常にバイパスするよう、メディア バイパスをグローバルに有効化するには</span><span class="sxs-lookup"><span data-stu-id="3e003-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="3e003-110">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e003-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="3e003-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e003-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="3e003-112">リスト内の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e003-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="3e003-113">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3e003-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="3e003-114">[**常にバイパスする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e003-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="3e003-115">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e003-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3e003-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e003-116">See also</span></span>

#### 

[<span data-ttu-id="3e003-117">ビジネス 2015年の Skype でのメディア バイ パスの計画します。</span><span class="sxs-lookup"><span data-stu-id="3e003-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="3e003-118">ビジネス サーバー 2015 に Skype でのメディア バイ パスを展開します。</span><span class="sxs-lookup"><span data-stu-id="3e003-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

