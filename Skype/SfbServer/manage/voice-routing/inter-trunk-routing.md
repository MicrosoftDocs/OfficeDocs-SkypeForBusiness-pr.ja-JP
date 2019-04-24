---
title: ビジネス サーバーの間のトランクが Skype でルーティング
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 '
ms.openlocfilehash: 9f73899d59e79d8fc93e768f0e870449baaeb7fb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214803"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="55f02-103">ビジネス サーバーの間のトランクが Skype でルーティング</span><span class="sxs-lookup"><span data-stu-id="55f02-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="55f02-104">ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="55f02-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="55f02-105">この機能により、ダウン ストリームのテレフォニー システムへの呼び出しコントロール機能を提供するビジネス サーバーの Skype です。</span><span class="sxs-lookup"><span data-stu-id="55f02-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="55f02-106">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="55f02-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="55f02-107">同様に、Skype のビジネス サーバーは、呼び出しを配置し、PBX の電話別の IP PBX システムからとの間に受信するように、2 つ以上の IP PBX システムを相互接続できます。</span><span class="sxs-lookup"><span data-stu-id="55f02-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="55f02-108">次の図では、PSTN ゲートウェイと IP PBX との間の相互接続性を提供するビジネスのサーバーの Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="55f02-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN ゲートウェイと IP PBX との間の相互接続](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="55f02-110">次の図は、ビジネス サーバーの 2 つの IP PBX システムに接続するため、Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="55f02-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype ビジネス サーバーの 2 つの IP PGX システムに接続します。](../../media/two-ip-pbx-systems.jpg)

