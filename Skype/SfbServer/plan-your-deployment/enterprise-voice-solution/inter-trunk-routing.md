---
title: ビジネス サーバーの間のトランクが Skype でルーティング
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。
ms.openlocfilehash: c8c4232bbb4bb2007aa7d01bce1d26a7c5dd6901
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886159"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="7c6b5-103">ビジネス サーバーの間のトランクが Skype でルーティング</span><span class="sxs-lookup"><span data-stu-id="7c6b5-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="7c6b5-104">ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="7c6b5-105">ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="7c6b5-106">これにより、ダウン ストリームのテレフォニー システムへの呼び出しコントロール機能を提供するビジネス サーバーの Skype です。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="7c6b5-107">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="7c6b5-108">同様に、Skype のビジネス サーバーは、呼び出しを配置し、PBX の電話別の IP PBX システムからとの間に受信するように、2 つ以上の IP PBX システムを相互接続できます。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="7c6b5-109">次の図では、PSTN ゲートウェイと IP PBX との間の相互接続性を提供するビジネスのサーバーの Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="7c6b5-111">次の図は、ビジネス サーバーの 2 つの IP PBX システムに接続するため、Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c6b5-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server、IP-PAX システムの相互接続図](../../media/inter_trunk02.jpg)
  

