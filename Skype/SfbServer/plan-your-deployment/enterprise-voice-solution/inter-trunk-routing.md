---
title: Skype for Business Server でのインタートランクルーティング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Skype for Business Server Enterprise Voice がトランク間ルーティングをサポートする方法について説明します。
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802857"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="6980b-103">Skype for Business Server でのインタートランクルーティング</span><span class="sxs-lookup"><span data-stu-id="6980b-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="6980b-104">Skype for Business Server Enterprise Voice がトランク間ルーティングをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6980b-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="6980b-105">Skype for Business Server は、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="6980b-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="6980b-106">これにより、Skype for Business Server は、下流のテレフォニーシステムへの通話コントロール機能を提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6980b-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="6980b-107">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="6980b-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="6980b-108">同様に、Skype for Business Server は2つ以上の IP PBX システムを相互に接続して、さまざまな IP PBX システムから PBX 電話間で通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="6980b-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="6980b-109">次の図は、PSTN ゲートウェイと ip-pbx の間の相互活用を実現する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="6980b-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="6980b-111">次の図は、2つの IP PBX システムを接続する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="6980b-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server、IP-PAX システムの相互接続図](../../media/inter_trunk02.jpg)
  

