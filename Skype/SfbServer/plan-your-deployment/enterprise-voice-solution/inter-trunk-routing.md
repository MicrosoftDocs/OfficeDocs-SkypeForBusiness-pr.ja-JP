---
title: Skype for Business Server 2015 のトランク間ルーティング
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="7a0ab-103">Skype for Business Server 2015 のトランク間ルーティング</span><span class="sxs-lookup"><span data-stu-id="7a0ab-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7a0ab-104">ビジネス サーバーのエンタープライズ VoIP の Skype がトランクの間のルーティングをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="7a0ab-105">ビジネス サーバーの Skype では、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="7a0ab-106">これにより、ダウン ストリームのテレフォニー システムへの呼び出しコントロール機能を提供するビジネス サーバーの Skype です。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="7a0ab-107">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="7a0ab-108">同様に、Skype のビジネス サーバーは、呼び出しを配置し、PBX の電話別の IP PBX システムからとの間に受信するように、2 つ以上の IP PBX システムを相互接続できます。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="7a0ab-109">次の図では、PSTN ゲートウェイと IP PBX との間の相互接続性を提供するビジネスのサーバーの Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="7a0ab-111">次の図は、ビジネス サーバーの 2 つの IP PBX システムに接続するため、Skype を示しています。</span><span class="sxs-lookup"><span data-stu-id="7a0ab-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server、IP-PAX システムの相互接続図](../../media/inter_trunk02.jpg)
  

