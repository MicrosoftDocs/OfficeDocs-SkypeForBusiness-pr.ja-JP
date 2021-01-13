---
title: Skype for Business Server でのトランク間ルーティング
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server エンタープライズ VoIPがトランク間ルーティングをサポートする方法について説明します。
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825602"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="c263a-103">Skype for Business Server でのトランク間ルーティング</span><span class="sxs-lookup"><span data-stu-id="c263a-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="c263a-104">Skype for Business Server エンタープライズ VoIPがトランク間ルーティングをサポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c263a-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="c263a-105">Skype for Business Server は、Trunk ルーティングのサポートを通じて基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c263a-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="c263a-106">これにより、Skype for Business Server は、ダウンストリームのテレフォニー システムに通話制御機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="c263a-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="c263a-107">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="c263a-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="c263a-108">同様に、Skype for Business Server は 2 つ以上の IP-PBX システムを相互接続して、異なる IP-PBX システムからの PBX 電話間で通話を受信できます。</span><span class="sxs-lookup"><span data-stu-id="c263a-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="c263a-109">次の図は、PSTN ゲートウェイと IP-PBX 間の相互接続を提供する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="c263a-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![PSTN ゲートウェイ/IP-PBX を接続する Lync Server の図](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="c263a-111">次の図は、2 つの IP-PBX システムを接続する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="c263a-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![LYNC Server 相互接続 IP-DIAGRAM システムの図](../../media/inter_trunk02.jpg)
  

