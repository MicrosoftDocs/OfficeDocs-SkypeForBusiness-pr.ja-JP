---
title: DNS の概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 688438e07416895f5c8070830e4bc0467325de14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="cd558-102">Lync Server 2013 での DNS の概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション</span><span class="sxs-lookup"><span data-stu-id="cd558-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd558-103">_**トピックの最終更新日:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="cd558-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="cd558-104">展開用に拡張メッセージとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーに2つのドメインネームシステム (DNS) レコードを作成します。これにより、エッジサーバーまたはエッジプールのアクセスエッジサービスに対するレコードが解決されます。</span><span class="sxs-lookup"><span data-stu-id="cd558-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cd558-105">XMPP の DNS の概要</span><span class="sxs-lookup"><span data-stu-id="cd558-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd558-106">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="cd558-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="cd558-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="cd558-107">FQDN</span></span></th>
<th><span data-ttu-id="cd558-108">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="cd558-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="cd558-109">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="cd558-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd558-110">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="cd558-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="cd558-111">_xmpp-サーバーの _tcp</span><span class="sxs-lookup"><span data-stu-id="cd558-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cd558-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cd558-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cd558-113">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。すべての内部 SIP ドメインについて必要に応じて、グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーを構成することにより、Lync が有効なユーザー。</span><span class="sxs-lookup"><span data-stu-id="cd558-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="cd558-114">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd558-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="cd558-115">詳細については、 <strong>「</strong>関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd558-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd558-116">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="cd558-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="cd558-117">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="cd558-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="cd558-118">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="cd558-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="cd558-119">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="cd558-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="cd558-120">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="cd558-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd558-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd558-121">See Also</span></span>


[<span data-ttu-id="cd558-122">Lync Server 2013 での XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="cd558-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="cd558-123">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="cd558-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

