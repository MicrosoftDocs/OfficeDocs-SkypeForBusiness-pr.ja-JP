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
ms.openlocfilehash: 4a3cb794ac34f473311919bd466af5ae33bb7ad1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997896"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="e47fb-103">エッジのマシンの内部 ip アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="e47fb-103">Add Edge Machine Internal IP</span></span>
 
<span data-ttu-id="e47fb-104">このページを使用すると、内部の IP アドレスおよびエッジ サーバーの内部の完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e47fb-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
<span data-ttu-id="e47fb-105">指定した FQDN は、サーバー上で構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e47fb-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="e47fb-106">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="e47fb-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="e47fb-107">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="e47fb-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="e47fb-108">そのため、ドメインに参加していないエッジ サーバーとして展開するコンピューターの名前をドメイン ネーム システム (DNS) サフィックスを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e47fb-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="e47fb-109">コンピューター名に DNS サフィックスを追加する方法の詳細は、[エッジ サポートの DNS の構成](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e47fb-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

