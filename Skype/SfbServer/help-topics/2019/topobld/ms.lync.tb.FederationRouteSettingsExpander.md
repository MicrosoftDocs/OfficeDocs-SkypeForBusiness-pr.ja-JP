---
title: フェデレーション ルートの設定の拡張
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: サイトのフェデレーション ルートの割り当てを設定するには、エッジ サーバーまたはエッジ サーバー プールで有効にするフェデレーション最初必要があります。 エッジ サーバーまたはプールでフェデレーションが有効でない場合、サイトのフェデレーション ルートの割り当ての設定は変更できません。
ms.openlocfilehash: 201fa7b556cc3a12c422145cf46c844faafb1cb4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371782"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="aff0b-104">フェデレーション ルートの設定の拡張</span><span class="sxs-lookup"><span data-stu-id="aff0b-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="aff0b-105">サイトのフェデレーション ルートの割り当てを設定するには、エッジ サーバーまたはエッジ サーバー プールで有効にするフェデレーション最初必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff0b-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="aff0b-106">エッジ サーバーまたはプールでフェデレーションが有効でない場合、サイトのフェデレーション ルートの割り当ての設定は変更できません。</span><span class="sxs-lookup"><span data-stu-id="aff0b-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="aff0b-107">エッジ サーバーまたはプールでフェデレーション設定を構成すると場合、は、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="aff0b-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="aff0b-108">**すべてのサイトに許可するフェデレーション ルートの割り当て**この設定は、すべてのサイトに影響されます。</span><span class="sxs-lookup"><span data-stu-id="aff0b-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="aff0b-109">このサイトで構成している設定がすべてのサイトに対して適切であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aff0b-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="aff0b-110">**フェデレーションの SIP を有効にします。** SIP フェデレーション ルートを有効にするには、このオプションを選択し、フェデレーション ルートとしてディレクター、またはエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="aff0b-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="aff0b-111">**XMPP を有効にするフェデレーション**XMPP フェデレーション ルートの場合を有効にするには、このオプションを選択し、フェデレーション ルートとしてディレクター、またはエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="aff0b-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="aff0b-112">XMPP ゲートウェイとプロキシ サーバー 2015 のビジネス用の Skype では利用ビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aff0b-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="aff0b-113">詳細については、[移行する XMPP フェデレーション](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aff0b-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

