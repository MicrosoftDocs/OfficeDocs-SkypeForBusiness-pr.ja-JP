---
title: Skype for Business Server でのインタートランクルーティング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server は、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。 '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816967"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="a73da-103">Skype for Business Server でのインタートランクルーティング</span><span class="sxs-lookup"><span data-stu-id="a73da-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="a73da-104">Skype for Business Server は、intertrunk ルーティングのサポートを通じて、基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="a73da-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="a73da-105">この機能により、Skype for Business Server は、下流のテレフォニーシステムへの通話コントロール機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="a73da-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="a73da-106">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="a73da-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="a73da-107">同様に、Skype for Business Server は2つ以上の IP PBX システムを相互に接続して、さまざまな IP PBX システムから PBX 電話間で通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="a73da-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="a73da-108">次の図は、PSTN ゲートウェイと ip-pbx の間の相互活用を実現する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="a73da-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![PSTN ゲートウェイと ip-pbx の相互通信](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="a73da-110">次の図は、2つの IP PBX システムを接続する Skype for Business Server を示しています。</span><span class="sxs-lookup"><span data-stu-id="a73da-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![2つの TCP/IP を接続する Skype for Business Server-PGX システム](../../media/two-ip-pbx-systems.jpg)

