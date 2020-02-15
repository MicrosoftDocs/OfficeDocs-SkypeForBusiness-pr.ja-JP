---
title: 'Lync Server 2013: ポートの概要-リバースプロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 203acca41c3e759bb05787c2bc23fd0ac773355f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="11f6f-102">ポートの概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="11f6f-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11f6f-103">_**トピックの最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="11f6f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="11f6f-104">リバース プロキシには、ファイアウォールとポート/プロトコルに関して最小限の要件があります。</span><span class="sxs-lookup"><span data-stu-id="11f6f-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="11f6f-105">外部ファイアウォールの要件は、HTTPS/TCP/443 とオプションの HTTP/TCP/80 です。</span><span class="sxs-lookup"><span data-stu-id="11f6f-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="11f6f-106">HTTPS は、SSL と、リバースプロキシを介してセキュリティで保護された TLS 通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="11f6f-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="11f6f-107">証明書を変更するときに自動検出サービスへのアクセスを許可することを選択すると、HTTP が使用されます。コストを正当化できないかどうかがわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="11f6f-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="11f6f-108">クライアントは、HTTPS 上の Office Web Apps サーバーに接続することを予期しています。</span><span class="sxs-lookup"><span data-stu-id="11f6f-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="11f6f-109">Office Web Apps サーバーは、HTTPS/TCP/443 上の内部クライアントから通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11f6f-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="11f6f-110">推奨される構成は、リバースプロキシから Office Web Apps サーバーへの HTTPS/TCP/443 を許可することです。</span><span class="sxs-lookup"><span data-stu-id="11f6f-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="11f6f-111">ポート8080は、リバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP にトラフィックをルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="11f6f-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="11f6f-112">ポート TCP 8080 は、外部 web サービス公開ルールの証明書の変更が望ましくない状況 (たとえば、多数の SIP ドメインがある場合) で、Lync を実行しているモバイルデバイスで自動検出サービスを検索するために必要です。</span><span class="sxs-lookup"><span data-stu-id="11f6f-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="11f6f-113">必要な SAN エントリを含む新しい証明書を取得する場合は、TCP ポート 8080 は不要であるため、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="11f6f-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="11f6f-114">ポート4443はリバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプールの仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープールの VIP へのトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="11f6f-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="11f6f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="11f6f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="11f6f-116">標準 Edition サーバーまたは中央管理ストアの役割を管理するフロントエンドプールからの tcp トラフィックをポート4443の内部展開に、リバースプロキシからの4443と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="11f6f-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="11f6f-117">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="11f6f-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="11f6f-118">リバース プロキシ サーバーのファイアウォールの詳細: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f6f-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11f6f-119">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="11f6f-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11f6f-120">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="11f6f-120">Source IP Address</span></span></th>
<th><span data-ttu-id="11f6f-121">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="11f6f-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="11f6f-122">メモ</span><span class="sxs-lookup"><span data-stu-id="11f6f-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11f6f-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="11f6f-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="11f6f-124">任意</span><span class="sxs-lookup"><span data-stu-id="11f6f-124">Any</span></span></p></td>
<td><p><span data-ttu-id="11f6f-125">リバース プロキシのリスナー</span><span class="sxs-lookup"><span data-stu-id="11f6f-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="11f6f-126">オプションユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合は、HTTPS にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="11f6f-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="11f6f-127">また、組織で外部 web サービス公開ルール証明書を変更しない場合に、Lync を実行しているモバイルデバイス用の Office Web Apps および自動検出サービスを使用する場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="11f6f-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11f6f-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11f6f-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11f6f-129">任意</span><span class="sxs-lookup"><span data-stu-id="11f6f-129">Any</span></span></p></td>
<td><p><span data-ttu-id="11f6f-130">リバース プロキシのリスナー</span><span class="sxs-lookup"><span data-stu-id="11f6f-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="11f6f-131">アドレス帳のダウンロード、アドレス帳の Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新、グループ拡張、会議用 Office Web アプリ、ダイヤルイン会議、および会議。</span><span class="sxs-lookup"><span data-stu-id="11f6f-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="11f6f-132">リバース プロキシ サーバーのファイアウォールの詳細: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f6f-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11f6f-133">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="11f6f-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="11f6f-134">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="11f6f-134">Source IP Address</span></span></th>
<th><span data-ttu-id="11f6f-135">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="11f6f-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="11f6f-136">メモ</span><span class="sxs-lookup"><span data-stu-id="11f6f-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11f6f-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="11f6f-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="11f6f-138">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f6f-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="11f6f-139">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="11f6f-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="11f6f-140">組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスに対して自動検出サービスを使用する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="11f6f-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="11f6f-141">リバース プロキシの外部インターフェイスのポート 80 に送信されるトラフィックは、そのトラフィックと内部 Web トラフィックをプールの Web サービスが区別できるように、リバース プロキシの内部インターフェイスからポート 8080 のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="11f6f-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11f6f-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="11f6f-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="11f6f-143">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f6f-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="11f6f-144">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="11f6f-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="11f6f-145">リバース プロキシの外部インターフェイスのポート 443 に送信されるトラフィックは、リバース プロキシの内部インターフェイスからポート 4443 のプールにリダイレクトされるため、プールの Web サービスはこのトラフィックを内部の Web トラフィックと区別できます。</span><span class="sxs-lookup"><span data-stu-id="11f6f-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11f6f-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="11f6f-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="11f6f-147">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11f6f-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="11f6f-148">会議用の Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="11f6f-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

