---
title: Lync Server 2010 のエッジ サーバー オプションを追加する
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジ サーバーまたはエッジ プールを定義すると、新しいサーバーまたはプールの機能を定義できます。 選択できるオプションは、次のとおりです。
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835517"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="f9b0a-104">Lync Server 2010 のエッジ サーバー オプションの追加</span><span class="sxs-lookup"><span data-stu-id="f9b0a-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="f9b0a-105">新しいエッジ サーバーまたはエッジ プールを定義すると、新しいサーバーまたはプールの機能を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="f9b0a-106">選択できるオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-106">The options that you can choose are:</span></span>

- <span data-ttu-id="f9b0a-107">[**単一の FQDN と IP アドレスを使います**]: 単一の IPv4 アドレスまたは IPv6 アドレス (IPv4 と IPv6 の両方を使用する場合は、それぞれの IP アドレスの種類で 1 つずつ定義する必要があります) と外部エッジ インターフェイスの完全修飾ドメイン名を使用する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9b0a-108">このオプションを選択した場合は、IP アドレスを 1 つだけ使用するか、IPv4 と IPv6 を 1 つずつ使用することになりますが、各エッジ インターフェイスには別々のポート番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="f9b0a-109">[**フェデレーションを有効にします (ポート 5061)**]: セッション開始プロトコル (SIP) を使用している他の SIP フェデレーション、プロバイダー、またはホストされているオファリングとのフェデレーションを行う場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="f9b0a-110">このエッジ プールの外部 IP アドレスは NAT によって変換されます。エッジ外部インターフェイスにプライベート **IP** アドレスを使用し、エッジ サーバーまたはエッジ プールを論理的に背後に配置するネットワーク アドレス変換 (NAT) デバイスを提供する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f9b0a-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b0a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9b0a-111">See also</span></span>

[<span data-ttu-id="f9b0a-112">外部ユーザー アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="f9b0a-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="f9b0a-113">エッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="f9b0a-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
