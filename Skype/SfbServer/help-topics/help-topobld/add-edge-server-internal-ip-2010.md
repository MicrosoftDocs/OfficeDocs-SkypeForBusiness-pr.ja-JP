---
title: エッジ サーバーの内部 IP を追加する (2010)
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 2f60eef6392b335461a9e0fc427c19d9f1d7b661
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219198"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="8f001-103">エッジ サーバーの内部 IP を追加する (2010)</span><span class="sxs-lookup"><span data-stu-id="8f001-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="8f001-104">このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f001-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="8f001-105">指定する FQDN が、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f001-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="8f001-106">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="8f001-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="8f001-107">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f001-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8f001-108">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f001-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="8f001-109">コンピューター名に DNS サフィックスを追加する方法の詳細については、「 [エッジサポートの dns の構成](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f001-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span></span>


