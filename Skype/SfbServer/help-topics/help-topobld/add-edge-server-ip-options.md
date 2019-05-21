---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成することができます。 この操作を行うには、次の操作を行います。
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293974"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="933b4-104">エッジ サーバー IP 追加オプション</span><span class="sxs-lookup"><span data-stu-id="933b4-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="933b4-105">Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="933b4-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="933b4-106">この操作を行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="933b4-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="933b4-107">**[内部インターフェイスで Ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="933b4-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="933b4-108">**[内部インターフェイスで Ipv6 を有効**にする]: ipv6 アドレスをエッジサーバーまたはエッジプールの内部インターフェイスに適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="933b4-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="933b4-109">**[外部インターフェイスで Ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="933b4-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="933b4-110">**[外部インターフェイスで Ipv6 を有効**にする]: ipv6 アドレスをエッジサーバーまたはエッジプールの外部インターフェイスに適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="933b4-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="933b4-111">また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="933b4-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="933b4-112">この操作を行うには、チェックボックスをオンにします。**このエッジプールの外部 IP アドレスは NAT によって変換され**ます。</span><span class="sxs-lookup"><span data-stu-id="933b4-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="933b4-113">NAT サポート。</span><span class="sxs-lookup"><span data-stu-id="933b4-113">NAT support.</span></span> <span data-ttu-id="933b4-114">ハードウェア負荷分散を使用している場合、ネットワークアドレス変換 (NAT) はサポートされていません。そのため、ハードウェア負荷分散でエッジサーバープールを展開している場合は、[NAT] オプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="933b4-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

