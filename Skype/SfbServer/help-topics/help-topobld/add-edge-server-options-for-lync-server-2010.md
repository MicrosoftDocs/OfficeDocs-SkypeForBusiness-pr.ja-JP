---
title: Lync Server 2010 のエッジ サーバー オプションの追加
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義することが表示されます。 選択できるオプションは次のとおりです。
ms.openlocfilehash: 57c3916b1a43812c1f647f425fc9df65f99cff35
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897459"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="08bb6-104">Lync Server 2010 のエッジ サーバー オプションの追加</span><span class="sxs-lookup"><span data-stu-id="08bb6-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="08bb6-105">新しいエッジ サーバーまたはエッジ プールを定義し、新しいサーバーまたはプールの機能を定義することが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08bb6-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="08bb6-106">選択できるオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08bb6-106">The options that you can choose are:</span></span>

- <span data-ttu-id="08bb6-107">**単一の FQDN と IP アドレスを使用**: (選択した場合に IPv4 と IPv6 の両方を使用して、各 IP アドレスの種類のいずれかを定義する必要がありますが)、1 つの IPv4 または IPv6 を使用する] チェック ボックスをオンにアドレスと完全修飾ドメイン名 (FQDN) の外部エッジ インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="08bb6-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="08bb6-108">このオプションを選択した場合のみ 1 つの IP アドレス、または 1 つの IPv4 と、1 つの IPv6 を使用するが、エッジ インターフェイスごとに異なるポート番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="08bb6-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="08bb6-109">**フェデレーション (ポート 5061) を有効にする**: その他の SIP フェデレーション、プロバイダー、またはセッション開始プロトコル (SIP) を使用するホストされたサービスとフェデレーションを行うが場合、このチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="08bb6-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="08bb6-110">**このエッジ プールの外部 IP アドレスが NAT によって変換されます**: エッジの外部インターフェイスにプライベート IP アドレスを使用してエッジ サーバーを配置またはエッジ プールの論理的なネットワーク アドレス変換 (NAT) デバイスは、このチェック ボックスをオン分離します。</span><span class="sxs-lookup"><span data-stu-id="08bb6-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="08bb6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="08bb6-111">See also</span></span>

[<span data-ttu-id="08bb6-112">外部ユーザー アクセスの計画</span><span class="sxs-lookup"><span data-stu-id="08bb6-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="08bb6-113">外部ユーザー アクセスを展開します。</span><span class="sxs-lookup"><span data-stu-id="08bb6-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
