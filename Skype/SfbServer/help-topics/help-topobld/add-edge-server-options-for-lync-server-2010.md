---
title: Lync Server 2010 のエッジ サーバー オプションの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジサーバーまたはエッジプールを定義し、新しいサーバーまたはプールの機能を定義する機会を提供します。 次のオプションを選ぶことができます。
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289995"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="35fc2-104">Lync Server 2010 のエッジ サーバー オプションの追加</span><span class="sxs-lookup"><span data-stu-id="35fc2-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="35fc2-105">新しいエッジサーバーまたはエッジプールを定義し、新しいサーバーまたはプールの機能を定義する機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="35fc2-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="35fc2-106">次のオプションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="35fc2-106">The options that you can choose are:</span></span>

- <span data-ttu-id="35fc2-107">**単一の FQDN と IP アドレスを使用**する: 1 つの ipv4 または ipv6 を使用する場合は、このチェックボックスをオンにします (Ipv4 と ipv6 の両方を使用する場合は、それぞれの IP アドレスの種類) アドレスと、外部エッジインターフェイスの完全修飾ドメイン名 (FQDN) を定義する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="35fc2-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35fc2-108">このオプションを選択した場合は、1つの IP アドレス、または1つの IPv4 と1つの IPv6 のみを使用しますが、各エッジインターフェイスに異なるポート番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35fc2-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="35fc2-109">**フェデレーションを有効にする (ポート 5061)**: セッション開始プロトコル (SIP) を使用する他の SIP フェデレーション、プロバイダー、またはホストされるサービスとフェデレーションを行う場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="35fc2-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="35fc2-110">**このエッジプールの外部 ip アドレスは、NAT によって変換され**ます。 edge 外部インターフェイスにプライベート IP アドレスを使用し、エッジサーバーまたはエッジプールを論理的に配置するためにネットワークアドレス変換 (NAT) デバイスを提供する場合は、このチェックボックスをオンにします。動機.</span><span class="sxs-lookup"><span data-stu-id="35fc2-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="35fc2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="35fc2-111">See also</span></span>

[<span data-ttu-id="35fc2-112">外部ユーザーアクセスの計画</span><span class="sxs-lookup"><span data-stu-id="35fc2-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="35fc2-113">外部ユーザーアクセスの展開</span><span class="sxs-lookup"><span data-stu-id="35fc2-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
