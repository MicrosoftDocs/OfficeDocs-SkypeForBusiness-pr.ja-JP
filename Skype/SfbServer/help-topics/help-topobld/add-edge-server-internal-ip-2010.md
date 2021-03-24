---
title: エッジ サーバーの内部 IP を追加する (2010)
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: c8e6c7fb4722d7d6e8b9b01057dc38d64cfe557e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103343"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="ea2c9-103">エッジ サーバー内部 IP の追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="ea2c9-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="ea2c9-104">このページを使用して、エッジ サーバーの内部 IP アドレスと完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="ea2c9-105">指定する FQDN が、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="ea2c9-106">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="ea2c9-107">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="ea2c9-108">そのため、エッジ サーバーとして展開する、ドメインに参加していないコンピューターの名前で、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="ea2c9-109">コンピューター名に DNS サフィックスを追加する方法の詳細については [、「Configure DNS for Edge Support」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)。</span><span class="sxs-lookup"><span data-stu-id="ea2c9-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span></span>