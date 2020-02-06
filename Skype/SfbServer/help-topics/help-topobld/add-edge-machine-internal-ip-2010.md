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
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: このページを使用して、内部 IP アドレスとエッジサーバーの内部完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 1847362f93c1d1ff67c09fb9f552641b0e770bbc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821139"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="a4afa-103">エッジ コンピューター内部 IP の追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="a4afa-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="a4afa-104">このページを使用して、内部 IP アドレスとエッジサーバーの内部完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4afa-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="a4afa-105">[**内部 IPv4 アドレス**] に、プールに追加するエッジサーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a4afa-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="a4afa-106">[ **INTERNAL FQDN**] に、プールに追加するエッジサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4afa-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="a4afa-107">指定する FQDN は、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4afa-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="a4afa-108">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="a4afa-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a4afa-109">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="a4afa-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a4afa-110">したがって、ドメインに参加していないエッジサーバーとして展開するコンピューターの名前で、ドメインネームシステム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4afa-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a4afa-111">DNS サフィックスをコンピューター名に追加する方法について詳しくは、「microsoft [Edge サポートのための dns の構成](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a4afa-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


