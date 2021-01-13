---
title: エッジ サーバー IP 追加オプション
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Microsoft Lync Server 2013 では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。 これを行うには、次の操作を行います。
ms.openlocfilehash: d8bfed4d7318133d33d733953cfcf472aa0e88ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815207"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="8d888-104">エッジ サーバー IP のオプション</span><span class="sxs-lookup"><span data-stu-id="8d888-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="8d888-105">Microsoft Lync Server 2013 では、エッジ サーバーとエッジ プールのインターフェイスごとに IPv4 アドレスと IPv6 アドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8d888-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="8d888-106">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8d888-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="8d888-107">**内部インターフェイスで IPv4** を有効にする : エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv4 アドレスを適用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d888-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="8d888-108">**内部インターフェイスで IPv6** を有効にする : エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv6 アドレスを適用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d888-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="8d888-109">**外部インターフェイスで IPv4** を有効にする : エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv4 アドレスを適用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d888-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="8d888-110">**外部インターフェイスで IPv6** を有効にする : エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv6 アドレスを適用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d888-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="8d888-111">外部 IP アドレスにネットワーク アドレス変換アドレスを使用するエッジ サーバーまたはエッジ プールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d888-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="8d888-112">これを行うには、[**このエッジ プールの外部 IP アドレスは NAT を使用して変換されます**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8d888-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="8d888-p104">NAT のサポート。ロード バランサー機器を使用している場合、ネットワーク アドレス変換 (NAT) はサポートされないため、ロード バランサー機器を使用するエッジ サーバー プールを展開している場合は、NAT オプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="8d888-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

