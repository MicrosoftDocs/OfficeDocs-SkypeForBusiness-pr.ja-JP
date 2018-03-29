---
title: エッジのマシンの内部 IP 2010 を追加します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: このページを使用すると、内部の IP アドレスおよびエッジ サーバーの内部の完全修飾ドメイン名 (FQDN) を指定します。
ms.openlocfilehash: 2fedde361e252d400f4362add4757df3f0c40057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="7210e-103">エッジのマシンの内部 IP 2010 を追加します。</span><span class="sxs-lookup"><span data-stu-id="7210e-103">Add Edge Machine Internal IP 2010</span></span>
 
<span data-ttu-id="7210e-104">このページを使用すると、内部の IP アドレスおよびエッジ サーバーの内部の完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7210e-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
- <span data-ttu-id="7210e-105">**内部の IPv4 アドレス**のプールに追加するエッジ サーバーの IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7210e-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>
    
- <span data-ttu-id="7210e-106">**内部 FQDN**をプールに追加するエッジ サーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7210e-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>
    
<span data-ttu-id="7210e-107">指定した FQDN は、サーバー上で構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7210e-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="7210e-108">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="7210e-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7210e-109">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="7210e-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7210e-110">そのため、ドメインに参加していないエッジ サーバーとして展開するコンピューターの名前をドメイン ネーム システム (DNS) サフィックスを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7210e-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7210e-111">コンピューター名に DNS サフィックスを追加する方法の詳細は、[エッジ サポートの DNS の構成](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7210e-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

