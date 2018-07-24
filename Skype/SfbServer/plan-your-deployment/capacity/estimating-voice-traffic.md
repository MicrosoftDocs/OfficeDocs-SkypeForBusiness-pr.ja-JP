---
title: Skype のビジネス サーバーの音声の使用率とトラフィックを見積もる
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 次のメトリックを使用すると、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数にユーザーのトラフィックを見積もる。
ms.openlocfilehash: ec4079608bedc19e9cba2e6c1e872d770e6bce46
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20980465"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="db944-103">Skype のビジネス サーバーの音声の使用率とトラフィックを見積もる</span><span class="sxs-lookup"><span data-stu-id="db944-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="db944-104">次のメトリックを使用すると、各サイトおよびそのトラフィックをサポートするのにために必要なポートの数にユーザーのトラフィックを見積もる。</span><span class="sxs-lookup"><span data-stu-id="db944-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="db944-105">**軽度のトラフィック** (1 人あたり 1 時間に 1 PSTN 通話) の場合、1 ポートに対して 15 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="db944-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="db944-106">**中度のトラフィック** (1 人あたり 1 時間に 2 PSTN 通話) の場合、1 ポートに対して 10 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="db944-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="db944-107">**重度のトラフィック** (1 人あたり 1 時間に 3 以上の PSTN 通話) の場合、1 ポートに対して 5 ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="db944-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="db944-108">ポートの数には、仲介サーバーとゲートウェイが必要になることの順番を決定します。</span><span class="sxs-lookup"><span data-stu-id="db944-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="db944-109">960 個のポートに 2 つのポートからのサイズの範囲を展開するほとんどの組織を検討している公衆交換電話網 (PSTN) ゲートウェイです。</span><span class="sxs-lookup"><span data-stu-id="db944-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="db944-110">(がさらに大きくゲートウェイがこれらの主にテレフォニー サービス プロバイダーによって使用されます)。</span><span class="sxs-lookup"><span data-stu-id="db944-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="db944-p102">たとえば、10,000 名のユーザーを擁する中度のトラフィックの組織の場合、1000 ポートが必要となります。必要となるゲートウェイ数は、ゲートウェイの総合した処理能力によって決まる、必要とされるポート数の合計と同じになります。</span><span class="sxs-lookup"><span data-stu-id="db944-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

