---
title: ポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション
description: ポートの概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543093"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="815ab-103">Lync Server 2013 でのポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="815ab-103">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="815ab-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="815ab-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="815ab-105">エッジサーバーに展開されている拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシに対して定義されているポートとプロトコルは、XMPP フェデレーションパートナーからエッジサーバーへの通信を許可すると共に、エッジサーバーから XMPP フェデレーションパートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="815ab-105">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="815ab-106">ルールは、フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへの内部接続ファイアウォール上にも定義されています。</span><span class="sxs-lookup"><span data-stu-id="815ab-106">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="815ab-107">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="815ab-107">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="815ab-108">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="815ab-108">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="815ab-109">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="815ab-109">Source (IP address)</span></span></th>
<th><span data-ttu-id="815ab-110">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="815ab-110">Destination (IP address)</span></span></th>
<th><span data-ttu-id="815ab-111">Comments</span><span class="sxs-lookup"><span data-stu-id="815ab-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="815ab-112">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="815ab-112">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="815ab-113">任意</span><span class="sxs-lookup"><span data-stu-id="815ab-113">Any</span></span></p></td>
<td><p><span data-ttu-id="815ab-114">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="815ab-114">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="815ab-115">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="815ab-115">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="815ab-116">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="815ab-116">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="815ab-117">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="815ab-117">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="815ab-118">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="815ab-118">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="815ab-119">任意</span><span class="sxs-lookup"><span data-stu-id="815ab-119">Any</span></span></p></td>
<td><p><span data-ttu-id="815ab-120">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="815ab-120">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="815ab-121">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="815ab-121">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="815ab-122">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="815ab-122">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="815ab-123">任意</span><span class="sxs-lookup"><span data-stu-id="815ab-123">Any</span></span></p></td>
<td><p><span data-ttu-id="815ab-124">内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="815ab-124">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="815ab-125">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="815ab-125">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="815ab-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="815ab-126">See Also</span></span>


[<span data-ttu-id="815ab-127">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="815ab-127">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="815ab-128">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="815ab-128">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

