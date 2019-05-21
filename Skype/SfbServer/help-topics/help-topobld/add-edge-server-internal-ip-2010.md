---
title: エッジ サーバーの内部 IP の追加 (2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: このページを使用して、エッジサーバーの内部 IP アドレスと内部の完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: dfe5d082b14d5480061f7262c481e455b7eb8a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302445"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="9b63c-103">エッジ サーバーの内部 IP の追加 (2010)</span><span class="sxs-lookup"><span data-stu-id="9b63c-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="9b63c-104">このページを使用して、エッジサーバーの内部 IP アドレスと内部の完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b63c-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="9b63c-105">指定する FQDN は、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b63c-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="9b63c-106">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="9b63c-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="9b63c-107">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b63c-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="9b63c-108">したがって、ドメインに参加していないエッジサーバーとして展開するコンピューターの名前で、ドメインネームシステム (DNS) サフィックスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b63c-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="9b63c-109">DNS サフィックスをコンピューター名に追加する方法について詳しくは、「microsoft [Edge サポートのための dns の構成](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b63c-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span></span>


