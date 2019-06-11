---
title: DNS の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="66b49-102">DNS の概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="66b49-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66b49-103">_**最終更新日:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="66b49-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="66b49-104">展開用の拡張メッセージングとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーで、エッジサーバーまたはエッジプールのアクセスエッジサービスへのレコードを解決する2つのドメインネームシステム (DNS) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="66b49-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="66b49-105">拡張メッセージングとプレゼンスプロトコルの DNS 概要</span><span class="sxs-lookup"><span data-stu-id="66b49-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66b49-106">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="66b49-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="66b49-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="66b49-107">FQDN</span></span></th>
<th><span data-ttu-id="66b49-108">IP アドレス/FQDN ホストレコード</span><span class="sxs-lookup"><span data-stu-id="66b49-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="66b49-109">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="66b49-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66b49-110">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="66b49-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="66b49-111">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="66b49-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="66b49-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="66b49-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="66b49-113">アクセスエッジサービスまたはエッジプールの XMPP プロキシ外部インターフェイス。グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、すべての内部 SIP ドメインについて必要に応じてこの手順を繰り返します。Lync 対応ユーザー。</span><span class="sxs-lookup"><span data-stu-id="66b49-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="66b49-114">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66b49-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="66b49-115">詳細については、 <strong>「</strong>関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66b49-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66b49-116">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="66b49-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="66b49-117">xmpp.contoso.com (など)</span><span class="sxs-lookup"><span data-stu-id="66b49-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="66b49-118">エッジサーバーまたは XMPP プロキシをホストしているエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="66b49-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="66b49-119">XMPP プロキシサービスをホストしているアクセスエッジサービスまたはエッジプールへのポイント。</span><span class="sxs-lookup"><span data-stu-id="66b49-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="66b49-120">通常、作成した SRV レコードは、このホスト (A または AAAA) レコードをポイントします。</span><span class="sxs-lookup"><span data-stu-id="66b49-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66b49-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="66b49-121">See Also</span></span>


[<span data-ttu-id="66b49-122">Lync Server 2013 XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="66b49-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="66b49-123">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="66b49-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

