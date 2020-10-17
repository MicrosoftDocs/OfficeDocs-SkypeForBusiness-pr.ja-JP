---
title: 'Lync Server 2013: ポートの概要-自動検出'
description: 'Lync Server 2013: ポートの概要-自動検出。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543143"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="926ec-103">ポートの概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="926ec-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926ec-104">_**トピックの最終更新日:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="926ec-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="926ec-105">Lync Server 2013 の自動検出サービスは、ディレクターおよびフロントエンドプールのサーバー上で実行され、およびホストレコードを使用して DNS で公開されると `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 、クライアントが lync server の機能を検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="926ec-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="926ec-106">Lync Mobile を実行しているモバイルデバイスで自動検出を使用するには、まず、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの別名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="926ec-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="926ec-107">さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="926ec-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="926ec-108">リバースプロキシでサブジェクトの別名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443に公開するかどうかに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="926ec-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="926ec-109">**ポート 80**     で公開モバイルデバイスでは、自動検出サービスへの初期クエリがポート80で行われる場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="926ec-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="926ec-110">これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにリダイレクトされるためです。</span><span class="sxs-lookup"><span data-stu-id="926ec-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="926ec-111">**ポート 443**     で公開外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、 `lyncdiscover.<sipdomain>` 組織内の各 SIP ドメインのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="926ec-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="926ec-112">モビリティを展開した Lync Server 2010 からの新規インストールまたはアップグレードの場合は、Mobility service の自動検出にポート80を使用するか、適切なサブジェクト名とサブジェクトの別名を使用して証明書を再発行します。</span><span class="sxs-lookup"><span data-stu-id="926ec-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="926ec-113">ディレクターおよびフロントエンドサーバーの証明書を確認し、選択したパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="926ec-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="926ec-114">リバース プロキシ サーバーのファイアウォールの詳細: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="926ec-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="926ec-115">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="926ec-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="926ec-116">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="926ec-116">Source IP Address</span></span></th>
<th><span data-ttu-id="926ec-117">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="926ec-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="926ec-118">Notes</span><span class="sxs-lookup"><span data-stu-id="926ec-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="926ec-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="926ec-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="926ec-120">任意</span><span class="sxs-lookup"><span data-stu-id="926ec-120">Any</span></span></p></td>
<td><p><span data-ttu-id="926ec-121">リバース プロキシのリスナー</span><span class="sxs-lookup"><span data-stu-id="926ec-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="926ec-122">オプションユーザーが http://publishedsitefqdn を入力した場合は、HTTPS にリダイレクト &lt; &gt; します。</span><span class="sxs-lookup"><span data-stu-id="926ec-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="926ec-123">また、組織で外部 web サービス公開ルール証明書を変更しない場合に、Lync を実行しているモバイルデバイス用の Office Web Apps および自動検出サービスを使用する場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="926ec-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926ec-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="926ec-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="926ec-125">任意</span><span class="sxs-lookup"><span data-stu-id="926ec-125">Any</span></span></p></td>
<td><p><span data-ttu-id="926ec-126">リバース プロキシのリスナー</span><span class="sxs-lookup"><span data-stu-id="926ec-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="926ec-127">アドレス帳のダウンロード、アドレス帳の Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新、グループ拡張、会議用 Office Web アプリ、ダイヤルイン会議、および会議。</span><span class="sxs-lookup"><span data-stu-id="926ec-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="926ec-128">リバース プロキシ サーバーのファイアウォールの詳細: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="926ec-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="926ec-129">プロトコル/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="926ec-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="926ec-130">送信元 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="926ec-130">Source IP Address</span></span></th>
<th><span data-ttu-id="926ec-131">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="926ec-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="926ec-132">Notes</span><span class="sxs-lookup"><span data-stu-id="926ec-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="926ec-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="926ec-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="926ec-134">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="926ec-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="926ec-135">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="926ec-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="926ec-136">組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスに対して自動検出サービスを使用する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="926ec-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="926ec-137">リバース プロキシの外部インターフェイスのポート 80 に送信されるトラフィックは、そのトラフィックと内部 Web トラフィックをプールの Web サービスが区別できるように、リバース プロキシの内部インターフェイスからポート 8080 のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="926ec-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="926ec-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="926ec-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="926ec-139">リバース プロキシの内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="926ec-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="926ec-140">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="926ec-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="926ec-141">リバース プロキシの外部インターフェイスのポート 443 に送信されるトラフィックは、リバース プロキシの内部インターフェイスからポート 4443 のプールにリダイレクトされるため、プールの Web サービスはこのトラフィックを内部の Web トラフィックと区別できます。</span><span class="sxs-lookup"><span data-stu-id="926ec-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

