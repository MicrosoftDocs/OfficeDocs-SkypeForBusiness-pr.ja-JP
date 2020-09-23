---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219792"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="3f2b9-104">エッジ サーバー IP 追加オプション</span><span class="sxs-lookup"><span data-stu-id="3f2b9-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="3f2b9-105">Microsoft Lync Server 2013 では、エッジサーバーとエッジプールの各インターフェイスに対して IPv4 アドレスと IPv6 アドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="3f2b9-106">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="3f2b9-107">**[内部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="3f2b9-108">**[内部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの内部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="3f2b9-109">**[外部インターフェイスで ipv4 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv4 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="3f2b9-110">**[外部インターフェイスで Ipv6 を有効**にする]: エッジサーバーまたはエッジプールの外部インターフェイスに ipv6 アドレスを適用する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="3f2b9-111">また、外部 IP アドレスにネットワークアドレス変換アドレスを使用するようにエッジサーバーまたはエッジプールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="3f2b9-112">これを行うには、[**このエッジ プールの外部 IP アドレスは NAT を使用して変換されます**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="3f2b9-p104">NAT のサポート。ロード バランサー機器を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされないため、ロード バランサー機器を使用するエッジ サーバー プールを展開している場合は、NAT オプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="3f2b9-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

