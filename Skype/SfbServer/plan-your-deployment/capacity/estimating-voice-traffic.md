---
title: Skype for Business Server の音声使用量とトラフィックの見積もり
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 次のメトリックを使用して、各サイトのユーザートラフィックを見積もり、そのトラフィックをサポートするために必要なポートの数を見積もることができます。
ms.openlocfilehash: 09c3e638d25225376b95afd60bdd6d3c311c1f5a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277616"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="29fae-103">Skype for Business Server の音声使用量とトラフィックの見積もり</span><span class="sxs-lookup"><span data-stu-id="29fae-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="29fae-104">次のメトリックを使用して、各サイトのユーザートラフィックを見積もり、そのトラフィックをサポートするために必要なポートの数を見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="29fae-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="29fae-105">**軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="29fae-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="29fae-106">**中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="29fae-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="29fae-107">**重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="29fae-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="29fae-108">ポートの数によって、必要な仲介サーバーとゲートウェイの数が決まります。</span><span class="sxs-lookup"><span data-stu-id="29fae-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="29fae-109">ほとんどの組織が、2つのポートから最大960ポートへの展開を検討している公衆交換電話網 (PSTN) ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="29fae-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="29fae-110">(大規模なゲートウェイもありますが、主にテレフォニーサービスプロバイダーによって使用されます)。</span><span class="sxs-lookup"><span data-stu-id="29fae-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="29fae-p102">たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。</span><span class="sxs-lookup"><span data-stu-id="29fae-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

