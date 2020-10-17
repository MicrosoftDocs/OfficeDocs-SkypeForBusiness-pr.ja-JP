---
title: 'Lync Server 2013: 自動検出のための DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520054"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="d56ce-102">Lync Server 2013 での自動検出用の DNS の構成</span><span class="sxs-lookup"><span data-stu-id="d56ce-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d56ce-103">_**トピックの最終更新日:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="d56ce-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="d56ce-104">Lync クライアントの自動検出をサポートするには、次のドメインネームシステム (DNS) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="d56ce-105">組織のネットワーク内から接続する Lync クライアントをサポートするための内部 DNS レコード</span><span class="sxs-lookup"><span data-stu-id="d56ce-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="d56ce-106">インターネットから接続する Lync クライアントをサポートするための外部 (パブリック) DNS レコード</span><span class="sxs-lookup"><span data-stu-id="d56ce-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="d56ce-107">内部 DNS レコードと外部 DNS レコードは SIP ドメインごとに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="d56ce-108">追加のサブジェクト代替名 (SAN) を使用して新しい証明書を作成する機能に基づいて、DNS レコードを (ホスト) レコードまたは CNAME レコードのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d56ce-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="d56ce-109">Lyncdiscover を使用して新しい外部 (パブリック) 証明書を要求および展開できない場合。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="d56ce-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="d56ce-110">SAN では、HTTP/TCP ポート80を使用するための手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-110">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="d56ce-111">次の手順では、内部および外部 DNS レコードを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-111">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="d56ce-112">DNS CNAME レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="d56ce-112">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="d56ce-113">次のように、DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-113">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="d56ce-114">内部 DNS レコードを作成するには、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-114">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="d56ce-115">外部 DNS レコードを作成するには、パブリック DNS プロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-115">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="d56ce-116">DNS 管理スナップインを開きます。[**スタート**] ボタンをクリックし、[**管理ツール**]、[**DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d56ce-117">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d56ce-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="d56ce-118">内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する Active Directory ドメイン (例: contoso.local) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-118">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d56ce-119">このドメインは、Lync Server 2013 &nbsp; ディレクタープールおよびフロントエンドプールがインストールされている Active Directory ドメインです。</span><span class="sxs-lookup"><span data-stu-id="d56ce-119">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="d56ce-120">外部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-120">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="d56ce-121">ディレクタープールのホスト A レコードが存在することを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-121">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="d56ce-122">内部 DNS レコードの場合、ホスト A レコードは、ディレクタープールの内部 Web サービス完全修飾ドメイン名 (FQDN) (たとえば、lyncwebdir01.contoso.local) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-122">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="d56ce-123">外部 DNS レコードの場合、ホスト A レコードは、ディレクタープールの外部 web サービス FQDN (たとえば、lyncwebextdir.contoso.com) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-123">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="d56ce-124">次のように、フロントエンドプールのホスト A レコードが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-124">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="d56ce-125">内部 DNS レコードの場合、ホスト A レコードはフロントエンドプールの内部 Web サービス FQDN (たとえば、: lyncwebpool01.contoso.local) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-125">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="d56ce-126">外部 DNS レコードの場合、ホスト A レコードはフロントエンドプールの外部 Web サービス FQDN (たとえば、lyncwebextpool01.contoso.com) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-126">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="d56ce-127">内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-127">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d56ce-128">外部 DNS レコードを作成する場合、使用する SIP ドメインの [<STRONG>前方参照ゾーン</STRONG>] は手順 3. で既に展開されています。</span><span class="sxs-lookup"><span data-stu-id="d56ce-128">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="d56ce-129">SIP ドメイン名を右クリックして、[**新しいエイリアス (CNAME)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-129">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="d56ce-130">[**エイリアス名**] に、次のどちらかを入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-130">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="d56ce-131">内部 DNS レコードの場合、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-131">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="d56ce-132">外部 DNS レコードの場合、自動検出サービスの外部 URL のホスト名として、「lyncdiscover」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-132">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="d56ce-133">[**ターゲット ホスト用の完全修飾ドメイン名 (FQDN)**] で、次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d56ce-133">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="d56ce-134">内部 DNS レコードの場合は、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01.contoso.local) を入力または参照し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-134">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="d56ce-135">外部 DNS レコードの場合は、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) を入力または参照し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-135">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d56ce-136">ディレクターを使用しない場合は、フロントエンドプールに内部および外部 Web サービスの FQDN を使用します。または、単一サーバーの場合は、フロントエンドサーバーまたは Standard Edition サーバーの FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-136">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d56ce-137">Lync Server 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-137">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="d56ce-138">DNS A レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="d56ce-138">To create DNS A records</span></span>

1.  <span data-ttu-id="d56ce-139">次のように、DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-139">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="d56ce-140">内部 DNS レコードを作成するには、Domain Admins グループのメンバーまたは DnsAdmins グループのメンバーとして、ネットワーク内の DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-140">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="d56ce-141">外部 DNS レコードを作成するには、パブリック DNS プロバイダーまたは外部 DNS サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-141">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="d56ce-142">DNS 管理スナップインを開きます。[**スタート**] ボタンをクリックし、[**管理ツール**]、[**DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-142">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="d56ce-143">次のどちらかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d56ce-143">Do one of the following:</span></span>
    
      - <span data-ttu-id="d56ce-144">内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する Active Directory ドメイン (例: contoso.local) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-144">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d56ce-145">このドメインは、Lync Server 2013 &nbsp; ディレクタープールおよびフロントエンドプールがインストールされている Active Directory ドメインです。</span><span class="sxs-lookup"><span data-stu-id="d56ce-145">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="d56ce-146">外部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-146">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="d56ce-147">次のように、ディレクタープールのホスト A (IPv6, AAAA) レコードが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-147">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="d56ce-148">内部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、ディレクタープールの内部 Web サービス FQDN (たとえば、lyncwebdir01.contoso.local) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-148">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="d56ce-149">外部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、ディレクタープールの外部 Web サービス FQDN (たとえば、lyncwebextdir.contoso.com) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-149">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="d56ce-150">次のように、フロントエンドプールのホスト A (IPv6, AAAA) レコードが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-150">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="d56ce-151">内部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、フロントエンドプールの内部 Web サービス FQDN (たとえば、: lyncwebpool01.contoso.local) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-151">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="d56ce-152">外部 DNS レコードの場合、ホスト A (IPv6 では AAAA) レコードは、フロントエンドプールの外部 Web サービス FQDN (たとえば、lyncwebextpool01.contoso.com) に対して存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-152">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="d56ce-153">内部 DNS レコードの場合、DNS サーバーのコンソール ツリーで、使用する SIP ドメイン (例: contoso.com) の [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-153">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d56ce-154">外部 DNS レコードを作成する場合、使用する SIP ドメインの [<STRONG>前方参照ゾーン</STRONG>] は手順 3. で既に展開されています。</span><span class="sxs-lookup"><span data-stu-id="d56ce-154">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="d56ce-155">SIP ドメイン名を右クリックして、[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-155">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="d56ce-156">[**名前**] に、ホスト名を次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-156">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="d56ce-157">内部 DNS レコードの場合、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-157">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="d56ce-158">外部 DNS レコードの場合、自動検出サービスの外部 URL のホスト名として、「lyncdiscover」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-158">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d56ce-159">ドメイン名は、レコードが定義されるゾーンから取られるため、A レコードの一部として入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d56ce-159">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="d56ce-160">[**IP アドレス**] に、IP アドレスを次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-160">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="d56ce-161">内部 DNS レコードの場合は、ディレクターの内部 Web サービス IP アドレスを入力します (または、ロードバランサーを使用する場合は、ディレクターロードバランサーの仮想 IP (VIP) を入力します)。</span><span class="sxs-lookup"><span data-stu-id="d56ce-161">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d56ce-162">ディレクターを使用しない場合は、フロントエンドサーバーまたは Standard Edition サーバーの IP アドレスを入力するか、ロードバランサーを使用する場合は、フロントエンドプールのロードバランサーの VIP を入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-162">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="d56ce-163">外部 DNS レコードの場合、リバース プロキシの外部またはパブリック IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-163">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="d56ce-164">[**ホストの追加**] をクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-164">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="d56ce-165">追加の A レコードを作成するには、手順 8. ～ 10. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d56ce-165">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d56ce-166">Lync Server 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい lyncdiscover および lyncdiscoverinternal A レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56ce-166">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="d56ce-167">A (IPv6 では AAAA) レコードの作成が完了した後で、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56ce-167">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

