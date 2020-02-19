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
ms.openlocfilehash: c7d45183b3dac5d96d65d771bf1425546f861c38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="7c0fe-102">証明書の概要-Lync Server 2013 での自動検出</span><span class="sxs-lookup"><span data-stu-id="7c0fe-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c0fe-103">_**トピックの最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="7c0fe-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="7c0fe-104">Lync Server 2013 自動検出サービスは、ディレクターおよびフロントエンドプールサーバー上で実行され、DNS で公開されると、Lync クライアントがサーバーとユーザーサービスを検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="7c0fe-105">Lync Server 2010 からアップグレードし、モビリティを展開しない場合は、クライアントで自動検出を使用する前に、自動検出サービスを実行しているすべてのディレクターおよびフロントエンドサーバーで、証明書のサブジェクトの別名の一覧を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="7c0fe-106">さらに、リバースプロキシの外部 web サービス公開ルールに使用される証明書のサブジェクトの別名の一覧を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="7c0fe-107">リバースプロキシでサブジェクトの別名の一覧を使用するかどうかは、自動検出サービスをポート80またはポート443に公開するかどうかに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="7c0fe-108">**ポート 80**   で公開された自動検出サービスへの最初のクエリがポート80経由で行われる場合、証明書の変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="7c0fe-109">これは、Lync を実行しているモバイルデバイスがポート80のリバースプロキシに外部でアクセスし、内部でポート8080のディレクターまたはフロントエンドサーバーにブリッジされるためです。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="7c0fe-110">詳細については、「 [Lync Server 2013 でのモビリティの技術的な要件](lync-server-2013-technical-requirements-for-mobility.md)」セクションの「ポート80を使用した初期の自動検出プロセス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="7c0fe-111">**ポート 443**   で公開されました。外部 web サービス公開ルールで使用される証明書のサブジェクトの別名リストには、lyncdiscover が含まれている必要があり\*ます。\<組織\> \*内の各 SIP ドメインの microsoft.rtc.management.xds.sipdomain エントリ。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7c0fe-112">HTTPS over HTTP を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="7c0fe-113">HTTPS は、証明書を使用してトラフィックを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="7c0fe-114">HTTP では暗号化が提供されず、送信されるデータはプレーンテキストになります。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="7c0fe-115">内部証明機関を使用した証明書の再発行は、通常、単純なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="7c0fe-116">しかし、web サービス公開ルールで使用されるパブリック証明書の場合、複数のサブジェクトの別名エントリを追加すると、コストがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="7c0fe-117">この問題を回避するために、ポート80経由の最初の自動検出接続をサポートします。その後、ディレクターまたはフロントエンドサーバーのポート8080にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c0fe-118">Lync Server 2013 インフラストラクチャが内部証明機関 (CA) から発行された内部証明書を使用し、ワイヤレス接続をサポートすることを計画している場合は、内部 CA からのルート証明書チェーンをインストールする必要があります。モバイルデバイスでは、または Lync Server 2013 インフラストラクチャ上のパブリック証明書に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="7c0fe-119">このトピックでは、ディレクター、フロントエンドサーバー、およびリバースプロキシに必要な追加のサブジェクトの別名について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="7c0fe-120">追加されたサブジェクトの別名 (SAN) のみが参照されます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="7c0fe-121">証明書の他のエントリに関するガイダンスについては、「計画」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="7c0fe-122">詳細については、「 [lync server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md)」、「 [lync server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」、および「 [lync server 2013 のリバースプロキシの](lync-server-2013-scenarios-for-reverse-proxy.md)シナリオ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="7c0fe-123">次の表は、ディレクタープール、フロントエンドプール、リバースプロキシの自動検出 SAN エントリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="7c0fe-124">ディレクター プールの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7c0fe-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0fe-125">説明</span><span class="sxs-lookup"><span data-stu-id="7c0fe-125">Description</span></span></th>
<th><span data-ttu-id="7c0fe-126">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7c0fe-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0fe-127">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7c0fe-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7c0fe-128">SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0fe-129">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7c0fe-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7c0fe-130">SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7c0fe-131">新しく更新された証明書を新しい SAN エントリと共に既定の証明書に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="7c0fe-132">または、SAN = \* を使用することもできます。&lt;microsoft.rtc.management.xds.sipdomain&gt;。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="7c0fe-133">フロント エンド プールの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7c0fe-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0fe-134">説明</span><span class="sxs-lookup"><span data-stu-id="7c0fe-134">Description</span></span></th>
<th><span data-ttu-id="7c0fe-135">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7c0fe-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0fe-136">内部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7c0fe-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7c0fe-137">SAN = lyncdiscoverinternal。&lt;内部ドメイン名&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c0fe-138">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7c0fe-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7c0fe-139">SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7c0fe-140">新しく更新された証明書を新しい SAN エントリと共に既定の証明書に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="7c0fe-141">または、SAN = \* を使用することもできます。&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="7c0fe-142">リバース プロキシ (パブリック CA) の証明書の要件</span><span class="sxs-lookup"><span data-stu-id="7c0fe-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c0fe-143">説明</span><span class="sxs-lookup"><span data-stu-id="7c0fe-143">Description</span></span></th>
<th><span data-ttu-id="7c0fe-144">サブジェクト名の別名エントリ</span><span class="sxs-lookup"><span data-stu-id="7c0fe-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c0fe-145">外部自動検出サービス URL</span><span class="sxs-lookup"><span data-stu-id="7c0fe-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="7c0fe-146">SAN = lyncdiscover。&lt;microsoft.rtc.management.xds.sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="7c0fe-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7c0fe-147">新しく更新された証明書を、リバースプロキシ上の SSL リスナーに新しい SAN エントリで割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7c0fe-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

