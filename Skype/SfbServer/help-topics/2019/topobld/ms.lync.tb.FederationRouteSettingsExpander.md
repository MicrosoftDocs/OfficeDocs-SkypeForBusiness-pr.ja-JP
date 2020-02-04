---
title: フェデレーション ルート設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: サイトフェデレーションルートの割り当てを設定するには、最初にエッジサーバープールまたはエッジサーバープールでフェデレーションを有効にする必要があります。 エッジサーバーまたはプールでフェデレーションが有効になっていない場合は、サイトのフェデレーションルートの割り当て設定を変更できません。
ms.openlocfilehash: a9679d5ddfe4652a79f58596940af7f450e4b470
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688563"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="cafe3-104">フェデレーション ルート設定の展開</span><span class="sxs-lookup"><span data-stu-id="cafe3-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="cafe3-105">サイトフェデレーションルートの割り当てを設定するには、最初にエッジサーバープールまたはエッジサーバープールでフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cafe3-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="cafe3-106">エッジサーバーまたはプールでフェデレーションが有効になっていない場合は、サイトのフェデレーションルートの割り当て設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="cafe3-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="cafe3-107">エッジサーバーまたはプールでフェデレーション設定が構成されている場合は、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cafe3-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="cafe3-108">**すべてのサイトにフェデレーションルートの割り当てを許可**するこの設定は、すべてのサイトに影響します。</span><span class="sxs-lookup"><span data-stu-id="cafe3-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="cafe3-109">このサイトで構成する設定は、すべてのサイトに対して適切であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cafe3-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="cafe3-110">**SIP フェデレーションを有効にする**SIP フェデレーションルートを有効にして、フェデレーションルートとしてディレクターまたはエッジプールを選択するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cafe3-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="cafe3-111">**XMPP フェデレーションを有効にする**XMPP フェデレーションルートを有効にし、フェデレーションルートとしてディレクターまたはエッジプールを選択するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cafe3-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="cafe3-112">XMPP ゲートウェイとプロキシは、Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cafe3-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cafe3-113">詳細については、「 [XMPP フェデレーションを移行](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cafe3-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

