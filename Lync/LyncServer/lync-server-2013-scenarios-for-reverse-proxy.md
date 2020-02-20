---
title: 'Lync Server 2013: リバースプロキシのシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="109fe-102">Lync Server 2013 のリバースプロキシのシナリオ</span><span class="sxs-lookup"><span data-stu-id="109fe-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="109fe-103">_**トピックの最終更新日:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="109fe-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="109fe-104">会議およびダイヤルインの簡易 Url、アドレス帳、会議コンテンツ、配布リストの拡張、モビリティサービスなどのサービスやリソースへのアクセスを提供するには、Lync Server 2013 でリバースプロキシが必要です。</span><span class="sxs-lookup"><span data-stu-id="109fe-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="109fe-105">Lync Server 2013 の一般的なリバースプロキシシナリオは、外部クライアント (たとえば、デスクトップクライアントや Lync Web App クライアント) がディレクターまたはフロントエンドサーバーの外部 Web サービスにアクセスできるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="109fe-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="109fe-106">**リバースプロキシと外部 web サービス**</span><span class="sxs-lookup"><span data-stu-id="109fe-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="109fe-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="109fe-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="109fe-108">計画フェーズでは、Lync Server 2013 の展開でリバースプロキシの要件を定義します。</span><span class="sxs-lookup"><span data-stu-id="109fe-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="109fe-109">リバースプロキシは、以下の外部クライアントの機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="109fe-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="109fe-110">Microsoft Lync 2013 デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="109fe-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="109fe-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="109fe-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="109fe-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="109fe-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="109fe-113">Lync Windows ストアアプリ</span><span class="sxs-lookup"><span data-stu-id="109fe-113">Lync Windows Store app</span></span>

<span data-ttu-id="109fe-114">Lync Server 2013 の展開を計画する場合は、Lync Server 2013 の実際の要件をリバースプロキシ機能にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="109fe-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="109fe-115">外部クライアントはポート TCP 443 上のリバースプロキシに接続し、secure socket layer (SSL) またはトランスポート層セキュリティ (TLS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="109fe-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="109fe-116">Microsoft Lync Mobile クライアントは、ポート TCP 80 で接続できますが、Lync discovery services への最初の接続を実行し、管理者が正しいドメインネームシステム (DNS) の CNAME (またはエイリアス) レコードを構成している場合に限り、この通信は暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="109fe-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="109fe-117">Lync Server 2013 (フロントエンドサーバーまたはディレクターに展開された) 外部 web サービスは、ポート TCP 4443 上のリバースプロキシからの接続を想定しており、接続が SSL/TLS であると想定しています。</span><span class="sxs-lookup"><span data-stu-id="109fe-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="109fe-118">外部 web サービスに対して推奨される既定のリスニングポートは、HTTP トラフィックの場合は TCP 8080、HTTPS トラフィックの場合は TCP 4443 です。</span><span class="sxs-lookup"><span data-stu-id="109fe-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="109fe-119">トポロジビルダーでは、既定値を上書きし、外部 web サービス用に独自のリスニングポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="109fe-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="109fe-120">リバースプロキシが外部 web サービスと通信し、外部クライアントがリバースプロキシと通信することに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="109fe-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="109fe-121">外部クライアントはポート TCP 443 でリバースプロキシと通信しますが、リバースプロキシがの外部 web サービスと通信するポートを再定義することができます。</span><span class="sxs-lookup"><span data-stu-id="109fe-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="109fe-122">トポロジビルダーのオプションを使用して web サービスの既定のリスニングポートを上書きすると、インフラストラクチャで発生する可能性があるリスニングポートの競合を解決できます。</span><span class="sxs-lookup"><span data-stu-id="109fe-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="109fe-123">Lync Server 2013 外部 web サービスは、クライアントが使用しようとしているサービスと web サーバーディレクトリを識別するために、クライアントからの変更されていないホストヘッダーを要求します。</span><span class="sxs-lookup"><span data-stu-id="109fe-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="109fe-124">要求はリバースプロキシから送信されたものとして表示される必要がある</span><span class="sxs-lookup"><span data-stu-id="109fe-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="109fe-125">外部 web サービスは、クライアントに提供されるサービスを提供する定義済みの web サーバー仮想ディレクトリ (vDir) を使用します。</span><span class="sxs-lookup"><span data-stu-id="109fe-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="109fe-126">特定の外部的に識別可能な web サービスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="109fe-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="109fe-127">Web 会議会議の "会議" という vDir</span><span class="sxs-lookup"><span data-stu-id="109fe-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="109fe-128">電話によるアクセスと電話会議のための "ダイヤルイン" vDir</span><span class="sxs-lookup"><span data-stu-id="109fe-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="109fe-129">Lync Windows ストアアプリ、Lync Mobile、およびデスクトップクライアント Lync 2013 の "自動検出" vDir。</span><span class="sxs-lookup"><span data-stu-id="109fe-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="109fe-130">Lync Server 2013 の自動検出は、DNS 名 "lyncdiscover" によって認識されます。</span><span class="sxs-lookup"><span data-stu-id="109fe-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="109fe-131">定義されていないサービスは、外部の web サービスへの直接の呼び出しによって外部クライアントによってアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="109fe-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="109fe-132">たとえば、配布グループの展開 (DLX) とアドレス帳サービス (ABS) は、外部 web サービスへの直接呼び出しまたは関連付けられた vDirs によってアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="109fe-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="109fe-133">クライアントは、vDir への実際のパスを知っており、この情報に基づいて uniform record locator (URL) を構築します。</span><span class="sxs-lookup"><span data-stu-id="109fe-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="109fe-134">クライアントは、のような URL を使用してアドレス帳サービスにアクセスします。`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="109fe-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="109fe-135">会議が Lync Server トポロジの一部として定義および構成されている場合の Office Web Apps サーバー</span><span class="sxs-lookup"><span data-stu-id="109fe-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="109fe-136">Office Web Apps サーバーは個別の役割サーバーであり、外部 Web サービスの一部として構成されていません。</span><span class="sxs-lookup"><span data-stu-id="109fe-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="109fe-137">このサーバーは、クライアントアクセスに対して個別に公開されています。</span><span class="sxs-lookup"><span data-stu-id="109fe-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="109fe-138">各サービスの SSL ブリッジを定義します。</span><span class="sxs-lookup"><span data-stu-id="109fe-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="109fe-139">外部ポートの TCP 443 は、TCP 4443 の外部 web サービスポートにマップされます。</span><span class="sxs-lookup"><span data-stu-id="109fe-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="109fe-140">暗号化されていない HTTP の場合、ポート TCP 80 が外部 web サービスポート TCP 8080 にマップされます。</span><span class="sxs-lookup"><span data-stu-id="109fe-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="109fe-141">Web サーバーリソースを発行するためのリバースプロキシリスナーを計画する</span><span class="sxs-lookup"><span data-stu-id="109fe-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="109fe-142">提供されるサービスに基づいて、リバースプロキシの証明書を要求して構成します。</span><span class="sxs-lookup"><span data-stu-id="109fe-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="109fe-143">正しいサブジェクトの別名を使用して構成されている場合、この証明書はリバースプロキシサーバー上の構成されたすべてのリスナーで共有できます。</span><span class="sxs-lookup"><span data-stu-id="109fe-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="109fe-144">リバース プロキシの展開を計画するために使用できるリソースを次に示します。</span><span class="sxs-lookup"><span data-stu-id="109fe-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="109fe-145">Lync Server 2013 のデータ収集</span><span class="sxs-lookup"><span data-stu-id="109fe-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="109fe-146">証明書の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="109fe-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="109fe-147">ポートの概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="109fe-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="109fe-148">DNS の概要-Lync Server 2013 のリバースプロキシ</span><span class="sxs-lookup"><span data-stu-id="109fe-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

