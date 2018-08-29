---
title: エッジのマシンの内部 ip アドレスを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
description: このページを使用すると、内部の IP アドレスおよびエッジ サーバーの内部の完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: e7a6690ddb928aae0548ff1b61be58976f48666f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251236"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="8f831-103">エッジのマシンの内部 ip アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f831-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="8f831-104">このページを使用すると、内部の IP アドレスおよびエッジ サーバーの内部の完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f831-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="8f831-105">指定した FQDN は、サーバー上で構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f831-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="8f831-106">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="8f831-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="8f831-107">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f831-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="8f831-108">そのため、ドメインに参加していないエッジ サーバーとして展開するコンピューターの名前をドメイン ネーム システム (DNS) サフィックスを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8f831-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="8f831-109">コンピューター名に DNS サフィックスを追加する方法の詳細は、[エッジ サポートの DNS の構成](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f831-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


