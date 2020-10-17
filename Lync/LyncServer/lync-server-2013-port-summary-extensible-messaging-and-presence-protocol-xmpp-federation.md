---
title: ポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション
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
ms.openlocfilehash: 5c8d7f99b4a7c72b9eb039fb7447397e711caa36
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527924"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="6135c-102">Lync Server 2013 でのポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="6135c-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6135c-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6135c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6135c-104">エッジサーバーに展開されている拡張メッセージングおよびプレゼンスプロトコル (XMPP) プロキシに対して定義されているポートとプロトコルは、XMPP フェデレーションパートナーからエッジサーバーへの通信を許可すると共に、エッジサーバーから XMPP フェデレーションパートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="6135c-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="6135c-105">ルールは、フロントエンドサーバーまたはフロントエンドプールからエッジサーバーまたはエッジプールへの内部接続ファイアウォール上にも定義されています。</span><span class="sxs-lookup"><span data-stu-id="6135c-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6135c-106">XMPP のファイアウォールの概要</span><span class="sxs-lookup"><span data-stu-id="6135c-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6135c-107">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="6135c-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6135c-108">送信元 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6135c-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="6135c-109">宛先 (IP アドレス)</span><span class="sxs-lookup"><span data-stu-id="6135c-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="6135c-110">Comments</span><span class="sxs-lookup"><span data-stu-id="6135c-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6135c-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6135c-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6135c-112">任意</span><span class="sxs-lookup"><span data-stu-id="6135c-112">Any</span></span></p></td>
<td><p><span data-ttu-id="6135c-113">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6135c-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6135c-114">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="6135c-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6135c-115">フェデレーションされた XMPP パートナーからのエッジサーバー XMPP プロキシへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="6135c-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6135c-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6135c-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6135c-117">アクセスエッジサービスインターフェイスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6135c-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6135c-118">任意</span><span class="sxs-lookup"><span data-stu-id="6135c-118">Any</span></span></p></td>
<td><p><span data-ttu-id="6135c-119">XMPP 用の標準的なサーバー間通信。</span><span class="sxs-lookup"><span data-stu-id="6135c-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6135c-120">エッジサーバー XMPP プロキシからフェデレーションされた XMPP パートナーへの通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="6135c-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6135c-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="6135c-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="6135c-122">任意</span><span class="sxs-lookup"><span data-stu-id="6135c-122">Any</span></span></p></td>
<td><p><span data-ttu-id="6135c-123">内部エッジサーバーインターフェイス IP</span><span class="sxs-lookup"><span data-stu-id="6135c-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="6135c-124">フロントエンドサーバーまたはフロントエンドプールの XMPP ゲートウェイからエッジサーバーへの内部 XMPP トラフィック</span><span class="sxs-lookup"><span data-stu-id="6135c-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6135c-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6135c-125">See Also</span></span>


[<span data-ttu-id="6135c-126">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="6135c-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="6135c-127">Lync Server 2013 での XMPP フェデレーションパートナーの管理</span><span class="sxs-lookup"><span data-stu-id="6135c-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

