---
title: 'Lync Server 2013: ポートの概要-自動検出'
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
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="c683f-102">ポートの概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="c683f-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c683f-103">_**最終更新日:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="c683f-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="c683f-104">Lync Server 2013 自動検出サービスは、監督およびフロントエンドプールサーバー上で実行され、 `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host レコードを使って DNS で公開されると、クライアントで使用して lync server の機能を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c683f-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="c683f-105">Lync Mobile を実行しているモバイルデバイスで自動検出を使用するには、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの代替名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c683f-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="c683f-106">さらに、リバースプロキシの外部 web サービス公開ルールに使用されている証明書のサブジェクト代替名の一覧を変更することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c683f-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="c683f-107">リバースプロキシでサブジェクト代替名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443のどちらに発行するかに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="c683f-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="c683f-108">**ポート 80**   でのモバイルデバイス向けに公開された、自動検出サービスへの初期クエリがポート80経由で行われる場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c683f-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="c683f-109">これは、Lync を実行しているモバイルデバイスは、ポート80の逆プロキシに外部からアクセスして、ポート8080の内部でディレクターまたはフロントエンドサーバーにリダイレクトされるためです。</span><span class="sxs-lookup"><span data-stu-id="c683f-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="c683f-110">**ポート 443**   で公開外部 web サービス公開ルールによって使用される証明書のサブジェクト代替名の`lyncdiscover.<sipdomain>`一覧には、組織内の各 SIP ドメインのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c683f-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c683f-111">モビリティを展開した Lync Server 2010 からの新規インストールまたはアップグレードの場合は、モビリティサービスの自動検出にポート80を使用するか、適切なサブジェクト名とサブジェクトの代替名を指定して再発行された証明書を使います。</span><span class="sxs-lookup"><span data-stu-id="c683f-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="c683f-112">監督とフロントエンドサーバー上の証明書を確認して、選択したパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="c683f-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="c683f-113">リバースプロキシサーバーのファイアウォールの詳細: 外部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c683f-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c683f-114">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c683f-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c683f-115">ソース IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c683f-115">Source IP Address</span></span></th>
<th><span data-ttu-id="c683f-116">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c683f-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="c683f-117">メモ</span><span class="sxs-lookup"><span data-stu-id="c683f-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c683f-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c683f-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c683f-119">任意</span><span class="sxs-lookup"><span data-stu-id="c683f-119">Any</span></span></p></td>
<td><p><span data-ttu-id="c683f-120">リバースプロキシリスナー</span><span class="sxs-lookup"><span data-stu-id="c683f-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c683f-121">省略ユーザーが http://&lt;publishedsitefqdn&gt;を入力した場合に HTTPS にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="c683f-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="c683f-122">また、会議用の Office Web Apps および Lync を実行しているモバイルデバイスで、組織が外部 Web サービス公開ルールの証明書を変更しない場合には、自動検出サービスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c683f-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c683f-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c683f-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c683f-124">任意</span><span class="sxs-lookup"><span data-stu-id="c683f-124">Any</span></span></p></td>
<td><p><span data-ttu-id="c683f-125">リバースプロキシリスナー</span><span class="sxs-lookup"><span data-stu-id="c683f-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c683f-126">アドレス帳のダウンロード、アドレス帳 Web クエリサービス、自動検出、クライアント更新、会議コンテンツ、デバイス更新プログラム、グループ拡張、会議用の Office Web アプリ、ダイヤルイン会議、会議。</span><span class="sxs-lookup"><span data-stu-id="c683f-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="c683f-127">リバースプロキシサーバーのファイアウォールの詳細: 内部インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c683f-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c683f-128">Protocol/TCP または UDP/ポート</span><span class="sxs-lookup"><span data-stu-id="c683f-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c683f-129">ソース IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c683f-129">Source IP Address</span></span></th>
<th><span data-ttu-id="c683f-130">宛先 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c683f-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="c683f-131">メモ</span><span class="sxs-lookup"><span data-stu-id="c683f-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c683f-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="c683f-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="c683f-133">内部のリバースプロキシインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c683f-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c683f-134">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c683f-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c683f-135">組織で外部 web サービス公開ルールの証明書を変更しない場合に、Lync を実行しているモバイルデバイスで自動検出サービスを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="c683f-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="c683f-136">リバースプロキシの外部インターフェイスでポート80に送信されるトラフィックは、プール Web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート8080上のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c683f-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c683f-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c683f-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c683f-138">内部のリバースプロキシインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c683f-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c683f-139">フロントエンドサーバー、フロントエンドプール、ディレクター、ディレクタープール、会議用 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c683f-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c683f-140">リバースプロキシの外部インターフェイスでポート443に送信されるトラフィックは、プール web サービスが内部の web トラフィックと区別できるように、リバースプロキシの内部インターフェイスからポート4443上のプールにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c683f-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

