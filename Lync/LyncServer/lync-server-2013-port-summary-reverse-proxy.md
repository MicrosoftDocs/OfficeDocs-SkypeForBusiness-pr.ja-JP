---
title: 'Lync Server 2013: ポートの概要 - リバース プロキシ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="84276-102">ポートの概要 - Lync Server 2013 のリバース プロキシ</span><span class="sxs-lookup"><span data-stu-id="84276-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84276-103">_**最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="84276-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="84276-104">リバースプロキシには、ファイアウォールとポート/プロトコルの最小要件があります。</span><span class="sxs-lookup"><span data-stu-id="84276-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="84276-105">外部ファイアウォールの要件として、HTTPS/TCP/443 と、オプションの HTTP/TCP/80 が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="84276-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="84276-106">HTTPS は、SSL と TLS のセキュリティ保護された通信に、リバースプロキシ経由で使用されます。</span><span class="sxs-lookup"><span data-stu-id="84276-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="84276-107">証明書を変更するときに、自動検出サービスへのアクセスを許可することを選んだ場合、HTTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="84276-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="84276-108">クライアントは、HTTPS で Office Web Apps サーバーに連絡することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="84276-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="84276-109">Office Web Apps サーバーは、HTTPS/TCP/443 上の内部クライアントからの通信を想定しています。</span><span class="sxs-lookup"><span data-stu-id="84276-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="84276-110">推奨される構成では、リバースプロキシから Office Web Apps サーバーへの HTTPS/TCP/443 の使用を許可します。</span><span class="sxs-lookup"><span data-stu-id="84276-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="84276-111">ポート8080は、リバースプロキシの内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP にトラフィックをルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="84276-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="84276-112">ポート TCP 8080 は、Lync を実行しているモバイルデバイスで、自動検出サービスを検索するために必要です (たとえば、多数の SIP ドメインがある場合など)。</span><span class="sxs-lookup"><span data-stu-id="84276-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="84276-113">必要な SAN エントリを使用して新しい証明書を取得する場合、ポート TCP 8080 は不要であり、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="84276-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="84276-114">ポート4443は、リバースプロキシ内部インターフェイスからフロントエンドサーバー、フロントエンドプール仮想 IP (VIP)、またはオプションのディレクターまたはディレクタープール VIP へのトラフィックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="84276-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="84276-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="84276-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="84276-116">4443とリバースプロキシの間の TCP トラフィックを、標準エディションサーバーまたは全体管理ストアの役割を管理するフロントエンドプールの内部4443展開に混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="84276-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="84276-117">ポートとプロトコルの詳細</span><span class="sxs-lookup"><span data-stu-id="84276-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="84276-118">リバースプロキシサーバーのファイアウォールの詳細: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84276-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84276-119">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="84276-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="84276-120">ソース IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84276-120">Source IP Address</span></span></th>
<th><span data-ttu-id="84276-121">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84276-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="84276-122">ノート</span><span class="sxs-lookup"><span data-stu-id="84276-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84276-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="84276-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="84276-124">任意</span><span class="sxs-lookup"><span data-stu-id="84276-124">Any</span></span></p></td>
<td><p><span data-ttu-id="84276-125">リバースプロキシリスナー</span><span class="sxs-lookup"><span data-stu-id="84276-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="84276-126">省略ユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合に HTTPS にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="84276-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="84276-127">また、会議用の Office Web Apps および Lync を実行しているモバイルデバイスで、組織が外部 Web サービス公開ルールの証明書を変更しない場合には、自動検出サービスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84276-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84276-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="84276-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="84276-129">任意</span><span class="sxs-lookup"><span data-stu-id="84276-129">Any</span></span></p></td>
<td><p><span data-ttu-id="84276-130">リバースプロキシリスナー</span><span class="sxs-lookup"><span data-stu-id="84276-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="84276-131">アドレス帳のダウンロード、アドレス帳 Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新プログラム、グループ拡張、会議用の Office Web アプリ、ダイヤルイン会議、会議。</span><span class="sxs-lookup"><span data-stu-id="84276-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="84276-132">リバースプロキシサーバーのファイアウォールの詳細: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="84276-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84276-133">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="84276-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="84276-134">ソース IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84276-134">Source IP Address</span></span></th>
<th><span data-ttu-id="84276-135">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84276-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="84276-136">ノート</span><span class="sxs-lookup"><span data-stu-id="84276-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84276-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="84276-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="84276-138">内部のリバースプロキシインターフェイス</span><span class="sxs-lookup"><span data-stu-id="84276-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="84276-139">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="84276-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="84276-140">組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスで自動検出サービスを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="84276-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="84276-141">リバースプロキシの外部インターフェイスでポート80に送信されるトラフィックは、プール Web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート8080上のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="84276-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84276-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="84276-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="84276-143">内部のリバースプロキシインターフェイス</span><span class="sxs-lookup"><span data-stu-id="84276-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="84276-144">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール</span><span class="sxs-lookup"><span data-stu-id="84276-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="84276-145">リバースプロキシの外部インターフェイスでポート443に送信されるトラフィックは、プール web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート4443上のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="84276-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84276-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="84276-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="84276-147">内部のリバースプロキシインターフェイス</span><span class="sxs-lookup"><span data-stu-id="84276-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="84276-148">会議用の Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="84276-148">Office Web Apps for conferencing</span></span></p></td>
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

