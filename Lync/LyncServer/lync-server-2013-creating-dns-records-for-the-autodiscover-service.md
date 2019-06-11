---
title: 'Lync Server 2013: 自動検出サービスの DNS レコードの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5307251e9c3dea202b08b48bf45e109ef19449ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="8510e-102">Lync Server 2013 での自動検出サービスの DNS レコードの作成</span><span class="sxs-lookup"><span data-stu-id="8510e-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8510e-103">_**最終更新日:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="8510e-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="8510e-104">Lync モバイルユーザーは、自動検出を有効にする必要があります。また、の一部では、いくつかのドメインネームシステム (DNS) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="8510e-105">必要に応じて、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="8510e-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="8510e-106">組織のネットワーク内から接続しているモバイルユーザーをサポートする内部 DNS レコード。</span><span class="sxs-lookup"><span data-stu-id="8510e-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="8510e-107">インターネットから接続しているモバイルユーザーをサポートするための、外部またはパブリックの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="8510e-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="8510e-108">その理由</span><span class="sxs-lookup"><span data-stu-id="8510e-108">Why both?</span></span> <span data-ttu-id="8510e-109">内部 DNS レコードと、各 SIP ドメインの外部 DNS レコードの両方を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="8510e-110">作成する DNS レコードは、(host) レコードまたは CNAME レコードのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8510e-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="8510e-111">この記事では、以下の内部および外部の DNS レコードを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8510e-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="8510e-112">モバイルユーザーの DNS 要件の詳細については、「 [Lync Server 2013 でのモビリティの技術要件」](lync-server-2013-technical-requirements-for-mobility.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8510e-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="8510e-113">内部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="8510e-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="8510e-114">内部 DNS レコードを作成するには、ドメイン管理者グループのメンバーであるか、DnsAdmins グループのメンバーであるドメインアカウントを使用して、ネットワーク内の DNS サーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="8510e-115">DNS 管理スナップインを開きます。 [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8510e-116">DNS サーバーのコンソールツリーで、Lync Server 2013 ディレクタープールとフロントエンドプールがインストールされている Active Directory ドメインの [**前方参照ゾーン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="8510e-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="8510e-117">(たとえば、contoso. local)。</span><span class="sxs-lookup"><span data-stu-id="8510e-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="8510e-118">内部 DNS レコードのディレクタープールに対して、ホスト A (AAAA for IPv6) レコードが存在するかどうかを確認します。ホスト a レコードは、ディレクタープールの内部 Web サービス完全修飾ドメイン名 (FQDN) に存在する必要があります (たとえば、lyncwebdir01)。</span><span class="sxs-lookup"><span data-stu-id="8510e-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="8510e-119">この情報が表示されていない場合は、ディレクタープールを使用していない可能性があります。また、セットアップ時には、フロントエンドプールの FQDN、または単一のサーバー FQDN を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="8510e-120">内部の DNS レコードについて、フロントエンドプールにホスト A (AAAA for IPv6) レコードが存在するかどうかを確認して、[ホスト A (または AAAA)] レコードが、フロントエンドプール用の内部 Web サービス FQDN に存在する必要があることを確認します (例を参照してください)。、lyncwebpool01)。</span><span class="sxs-lookup"><span data-stu-id="8510e-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="8510e-121">そうでない場合は、フロントエンドサーバーまたは Standard Edition サーバーの FQDN をメモしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="8510e-122">ホスト A (または AAAA) レコードが存在することを確認したら、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="8510e-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="8510e-123">SIP ドメイン名を右クリックし、[**新しいエイリアス (CNAME)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="8510e-124">[ **Alias name**] に、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8510e-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="8510e-125">**ターゲットホストの完全修飾ドメイン名 (FQDN)** で、ディレクタープールの内部 WEB サービス FQDN (たとえば、lyncwebdir01) を入力または参照して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="8510e-126">Lync Server 2013 環境でサポートしている各 SIP ドメインの前方参照ゾーンに新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="8510e-127">外部 DNS CNAME レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="8510e-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="8510e-128">外部 DNS CNAME レコードを作成するには、パブリック DNS プロバイダーに接続して、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="8510e-129">DNS プロバイダーの環境では、外部 DNS を管理する方法が異なるため、正確な場所を説明することはできませんが、次の手順をお楽しみください。</span><span class="sxs-lookup"><span data-stu-id="8510e-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="8510e-130">その環境で DNS レコードを作成できるアカウントを使用して、外部 DNS プロバイダーにログインします。</span><span class="sxs-lookup"><span data-stu-id="8510e-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="8510e-131">この環境用に SIP ドメインが既に作成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="8510e-132">この SIP ドメインの**前方参照ゾーン**を展開するか、使用されている外部 DNS インターフェイスに応じて選択します。</span><span class="sxs-lookup"><span data-stu-id="8510e-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="8510e-133">ディレクタープール (lyncwebexdir01.contoso.com など) に対して、既にホスト A (AAAA) レコードが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8510e-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="8510e-134">そうでない場合は、ディレクタープールを使用していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="8510e-135">その場合は、フロントエンドプールの FQDN を使用するか、フロントエンドサーバーまたは Standard Edition サーバー用にこの操作を単一のサーバーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="8510e-136">また、フロントエンドプール (lyncwebextpool01.contoso.com など) に対して、外部 Web サービスの完全修飾ドメイン名 (FQDN) に対してホスト A (AAAA) レコードが存在することを確認する必要があります。また、フロントエンドプールを持っていない場合は、単一サーバーの FQDN の FQDN にもなります。</span><span class="sxs-lookup"><span data-stu-id="8510e-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="8510e-137">前の手順で説明したように、ディレクタープールを持っていない場合は、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="8510e-138">次に、外部 DNS プロバイダーに適した形式で、**新しいエイリアス (CNAME)** を作成するためのオプションを選択します (これは、DNS プロバイダーの形式によっては、メニューオプションまたはリンクの場合があります)。</span><span class="sxs-lookup"><span data-stu-id="8510e-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="8510e-139">内部 DNS と同じような形式の**エイリアス名**のテキストボックスがある必要があります。これには、外部自動検出サービス URL のホスト名として lyncdiscover を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="8510e-140">また、[ **target host には完全修飾ドメイン名 (FQDN)** を指定してください] テキストボックスには、ディレクタープールの外部 WEB サービス FQDN を入力する場所 (たとえば、lyncwebexdir01.contoso.com) を入力し、[OK] をクリックするか、[すべて撮影] をクリックします。外部 DNS でこのエントリの作成を許可するアクション。</span><span class="sxs-lookup"><span data-stu-id="8510e-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="8510e-141">上の手順4で説明したように、ディレクタープールを持っていない場合は、必要に応じて、フロントエンドプールの FQDN か、セットアップした単一サーバーの FQDN を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="8510e-142">Lync 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 CNAME レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="8510e-143">内部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="8510e-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="8510e-144">内部 DNS レコードを作成するには、ドメイン管理者グループのメンバーであるか、DnsAdmins グループのメンバーであるドメインアカウントを使って、ネットワーク内の DNS サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8510e-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="8510e-145">DNS 管理スナップインを開きます。 [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="8510e-146">内部の DNS レコードの場合は、DNS サーバーのコンソールツリーで、Lync Server 2013 ディレクタープールとフロントエンドプールがインストールされている Active Directory ドメインの [**前方参照ゾーン**] (たとえば、[contoso. local]) を展開します。</span><span class="sxs-lookup"><span data-stu-id="8510e-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="8510e-147">内部 DNS レコードのディレクタープールに対して、ホスト A (AAAA for IPv6) レコードが存在するかどうかを確認します。ホスト a レコードは、ディレクタープールの内部 Web サービス完全修飾ドメイン名 (FQDN) に存在する必要があります (たとえば、lyncwebdir01)。</span><span class="sxs-lookup"><span data-stu-id="8510e-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="8510e-148">この情報が表示されていない場合は、ディレクタープールを使用していない可能性があります。セットアップ時には、フロントエンドプールの IP アドレスまたは1つのサーバー IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="8510e-149">内部の DNS レコードについて、フロントエンドプールにホスト A (AAAA for IPv6) レコードが存在するかどうかを確認して、[ホスト A (または AAAA)] レコードが、フロントエンドプール用の内部 Web サービス FQDN に存在する必要があることを確認します (例を参照してください)。、lyncwebpool01)。</span><span class="sxs-lookup"><span data-stu-id="8510e-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="8510e-150">そうでない場合は、フロントエンドサーバーまたは Standard Edition サーバーの IP アドレスをメモしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="8510e-151">ホスト A (または AAAA) レコードが存在することを確認したら、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="8510e-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="8510e-152">SIP ドメイン名を右クリックし、[**新しいホスト (A または AAAA)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="8510e-153">[**名前**] に、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8510e-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="8510e-154">[ **IP アドレス**] に、ディレクターの内部 Web サービスの IP アドレスを入力します (または、ロードバランサーを使っている場合は、ディレクターロードバランサーの仮想 IP (VIP) を入力します)。</span><span class="sxs-lookup"><span data-stu-id="8510e-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="8510e-155">上記の手順4で説明したように、ディレクターを使っていない場合は、フロントエンドサーバーまたは Standard Edition サーバーの IP アドレスを入力する必要があります。ロードバランサーを使っている場合は、フロントエンドプールのロードバランサーの VIP を入力します。</span><span class="sxs-lookup"><span data-stu-id="8510e-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="8510e-156">[**ホストの追加**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="8510e-157">追加の A レコードまたは AAAA レコードを作成するには、Lync Server 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで新しい自動検出 A レコードまたは AAAA レコードを作成する必要があることに注意して、手順 8 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8510e-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="8510e-158">(IPv6、AAAA) レコードの作成が完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8510e-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="8510e-159">外部 DNS A レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="8510e-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="8510e-160">外部 DNS レコードを作成するには、パブリック DNS プロバイダーに接続して、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8510e-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="8510e-161">DNS プロバイダーの環境では、外部 DNS を管理する方法が異なるため、正確な場所を説明することはできませんが、次の手順をお楽しみください。</span><span class="sxs-lookup"><span data-stu-id="8510e-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="8510e-162">その環境で DNS レコードを作成できるアカウントとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="8510e-163">外部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="8510e-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="8510e-164">外部 DNS レコードの場合は、DNS サーバーのコンソールツリーで、SIP ドメインの [**前方参照ゾーン**] を展開します (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="8510e-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="8510e-165">ディレクタープール (lyncwebexdir01.contoso.com など) に対して、既にホスト A (AAAA 用の AAAA) レコードが表示されている場合は、そのレコードが存在し、IP アドレスが何であるかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="8510e-166">そうでない場合は、ディレクタープールを使用していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="8510e-167">その場合は、フロントエンドプールの IP アドレスを使用するか、フロントエンドサーバーまたは Standard Edition サーバーに対してこの操作を1台のサーバーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="8510e-168">サーバーはロードバランサーの背後にあるか、またはリバースプロキシを使っている可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8510e-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="8510e-169">以下の手順に従って、IP アドレスをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="8510e-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="8510e-170">また、フロントエンドプール (lyncwebextpool01.contoso.com など) に対して、外部 Web サービスの完全修飾ドメイン名 (FQDN) に対して、またはシングルサーバーの Lync インストール用の IP アドレスに対して、host A (AAAA for IPv6) レコードが存在することも確認する必要があります。フロントエンドプールがありません。</span><span class="sxs-lookup"><span data-stu-id="8510e-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="8510e-171">前の手順で説明したように、ディレクタープールを持っていない場合は、以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="8510e-172">外部 DNS プロバイダーに適した形式で、**新しいホスト a または AAAA**を作成するためのオプションを選択します (これは、DNS プロバイダーの形式によっては、メニューオプションまたはリンクの場合があります)。</span><span class="sxs-lookup"><span data-stu-id="8510e-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="8510e-173">**名前**を入力する場所があります。外部自動検出サービス URL のホスト名として「lyncdiscover」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8510e-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="8510e-174">[ **Ip アドレス**] ボックスもある必要があります。ここでは、ディレクタープールの ip アドレス (たとえば、lyncwebexdir01.contoso.com)、またはプールのロードバランサーの ip アドレス (または同一につながる逆プロキシ IP) を入力して、をクリックします。[OK] をクリックするか、外部 DNS の任意の操作を実行してこのエントリの作成を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="8510e-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="8510e-175">上の手順4で説明したように、ディレクタープールを持っていない場合は、必要に応じて、フロントエンドプールの IP アドレスまたは設定した単一サーバー IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="8510e-176">Lync 2013 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 (A または AAAA) レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8510e-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

