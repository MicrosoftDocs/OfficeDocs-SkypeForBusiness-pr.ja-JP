---
title: エッジ サーバーの IP オプションを追加します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 を使用すると、エッジ サーバーおよびエッジ プールの各インタ フェースの IPv4 と IPv6 のアドレスを構成できます。 これを行うには、次の項目を行います。
ms.openlocfilehash: 8bf379c4ce8d23990cd004e8307b9bd4508bc45b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999570"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="7aad3-104">エッジ サーバーの IP オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="7aad3-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="7aad3-105">Microsoft Lync Server 2013 を使用すると、エッジ サーバーおよびエッジ プールの各インタ フェースの IPv4 と IPv6 のアドレスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7aad3-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="7aad3-106">これを行うには、次の項目を行います。</span><span class="sxs-lookup"><span data-stu-id="7aad3-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="7aad3-107">**内部インターフェイスの IPv4 を有効にする**:] チェック ボックスを選択して、エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv4 アドレスを適用する場合は、</span><span class="sxs-lookup"><span data-stu-id="7aad3-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="7aad3-108">**内部インターフェイスの IPv6 を有効にする**:] チェック ボックスを選択して、エッジ サーバーまたはエッジ プールの内部インターフェイスに IPv6 アドレスを適用する場合は、</span><span class="sxs-lookup"><span data-stu-id="7aad3-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="7aad3-109">**外部インターフェイスの IPv4 を有効にする**:] チェック ボックスを選択して、エッジ サーバーまたはエッジ プールの外部インタ フェースに IPv4 アドレスを適用する場合は、</span><span class="sxs-lookup"><span data-stu-id="7aad3-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="7aad3-110">**外部インターフェイスの IPv6 を有効にする**:] チェック ボックスを選択して、エッジ サーバーまたはエッジ プールの外部インターフェイスに IPv6 アドレスを適用する場合は、</span><span class="sxs-lookup"><span data-stu-id="7aad3-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="7aad3-111">外部の IP アドレスのネットワーク アドレス変換を使用するには、エッジ サーバーまたはエッジ プールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7aad3-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="7aad3-112">これを行う**このエッジ プールの外部 IP アドレスが NAT によって変換**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7aad3-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="7aad3-113">NAT のサポート。</span><span class="sxs-lookup"><span data-stu-id="7aad3-113">NAT support.</span></span> <span data-ttu-id="7aad3-114">ハードウェア負荷分散ハードウェア負荷分散、エッジ サーバー プールを展開する場合は、NAT オプションを選択して、使用している場合は、ネットワーク アドレス変換 (NAT) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7aad3-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

