---
title: エッジ コンピューター内部 IP の追加 (2010)
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219380"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="6f437-103">エッジ コンピューター内部 IP の追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="6f437-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="6f437-104">このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f437-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="6f437-105">[ **内部 IPv4 アドレス**] に、プールに追加するエッジサーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f437-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="6f437-106">[ **内部 FQDN**] に、プールに追加するエッジサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f437-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="6f437-107">指定する FQDN が、サーバーに構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f437-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="6f437-108">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="6f437-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="6f437-109">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f437-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6f437-110">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f437-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="6f437-111">コンピューター名への DNS サフィックスの追加の詳細については、「[Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f437-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


