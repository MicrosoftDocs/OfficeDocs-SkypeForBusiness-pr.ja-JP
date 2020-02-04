---
title: 'Lync Server 2013: 証明書の概要-自動検出'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="c9dd2-102">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="c9dd2-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9dd2-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="c9dd2-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="c9dd2-104">Lync Server 2013 自動検出サービスは、監督およびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync クライアントがサーバーおよびユーザーサービスを見つけるために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="c9dd2-105">Lync Server 2010 からアップグレードしていて、モビリティを展開していない場合は、クライアントで自動検出を使用できるようにする前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの代替名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="c9dd2-106">さらに、リバースプロキシの外部 web サービス公開ルールに使用されている証明書のサブジェクト代替名の一覧を変更することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="c9dd2-107">リバースプロキシでサブジェクト代替名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443のどちらに発行するかに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="c9dd2-108">**ポート 80**   で公開自動検出サービスへの最初のクエリがポート80経由で発生した場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="c9dd2-109">これは、Lync を実行しているモバイルデバイスは、ポート80の逆プロキシに外部からアクセスして、ポート8080の内部でディレクターまたはフロントエンドサーバーにブリッジするためです。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="c9dd2-110">詳細については、「 [Lync Server 2013 でのモビリティの技術要件](lync-server-2013-technical-requirements-for-mobility.md)」を参照してください。「ポート80を使った最初の自動検出プロセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="c9dd2-111">**ポート 443**   で公開される外部 web サービス公開ルールで使われる証明書のサブジェクトの別名リストは、lyncdiscover を含む必要があり\*ます。\<組織\> \*内の各 SIP ドメインの sipdomain エントリ。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c9dd2-112">HTTP 経由で HTTPS を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="c9dd2-113">HTTPS は、証明書を使ってトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="c9dd2-114">HTTP では暗号化は提供されず、送信されたデータはすべてプレーンテキストになります。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="c9dd2-115">内部証明機関を使った証明書の再発行は、通常、単純なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="c9dd2-116">ただし、web サービスの公開ルールで使用されているパブリック証明書の場合、複数のサブジェクト代替名エントリを追加すると、負荷が高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="c9dd2-117">この問題を回避するには、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバー上のポート8080にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9dd2-118">Lync Server 2013 インフラストラクチャで内部証明機関 (CA) から発行された内部証明書を使用していて、ワイヤレス接続のモバイルデバイスをサポートする予定の場合は、内部 CA からのルート証明書チェーンをインストールする必要があります。モバイルデバイスの場合、または Lync Server 2013 インフラストラクチャの公開証明書に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="c9dd2-119">このトピックでは、監督、フロントエンドサーバー、リバースプロキシに必要な追加サブジェクトの代替名について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="c9dd2-120">追加されたサブジェクト代替名 (SAN) のみが参照されます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="c9dd2-121">証明書の他のエントリに関するガイダンスについては、計画セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="c9dd2-122">詳細については、「lync [server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」、「 [lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」、「 [lync server 2013 でのリバースプロキシの](lync-server-2013-scenarios-for-reverse-proxy.md)シナリオ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="c9dd2-123">次の表では、ディレクタープール、フロントエンドプール、リバースプロキシの自動検出 SAN エントリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="c9dd2-124">ディレクタープール証明書の要件</span><span class="sxs-lookup"><span data-stu-id="c9dd2-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9dd2-125">説明</span><span class="sxs-lookup"><span data-stu-id="c9dd2-125">Description</span></span></th>
<th><span data-ttu-id="c9dd2-126">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="c9dd2-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9dd2-127">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="c9dd2-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c9dd2-128">SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9dd2-129">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="c9dd2-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c9dd2-130">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c9dd2-131">新しい SAN エントリを使って、新しく更新された証明書を既定の証明書に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="c9dd2-132">または、SAN = \* を使用することもできます。&lt;sipdomain&gt;。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="c9dd2-133">フロントエンドプール証明書の要件</span><span class="sxs-lookup"><span data-stu-id="c9dd2-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9dd2-134">説明</span><span class="sxs-lookup"><span data-stu-id="c9dd2-134">Description</span></span></th>
<th><span data-ttu-id="c9dd2-135">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="c9dd2-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9dd2-136">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="c9dd2-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c9dd2-137">SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9dd2-138">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="c9dd2-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c9dd2-139">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c9dd2-140">新しい SAN エントリを使って、新しく更新された証明書を既定の証明書に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="c9dd2-141">または、SAN = \* を使用することもできます。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="c9dd2-142">リバースプロキシ (パブリック CA) 証明書の要件</span><span class="sxs-lookup"><span data-stu-id="c9dd2-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9dd2-143">説明</span><span class="sxs-lookup"><span data-stu-id="c9dd2-143">Description</span></span></th>
<th><span data-ttu-id="c9dd2-144">サブジェクトの代替名エントリ</span><span class="sxs-lookup"><span data-stu-id="c9dd2-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9dd2-145">外部自動検出サービスの URL</span><span class="sxs-lookup"><span data-stu-id="c9dd2-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="c9dd2-146">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="c9dd2-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c9dd2-147">新しい SAN エントリを使って、新しく更新された証明書をリバースプロキシの SSL リスナーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c9dd2-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

