---
title: 'Lync Server 2013: DNS SRV レコードの作成と確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="4ada7-102">Lync Server 2013 での DNS SRV レコードの作成と確認</span><span class="sxs-lookup"><span data-stu-id="4ada7-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ada7-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4ada7-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4ada7-104">この手順を完了するには、ドメイン管理者グループのメンバー、または DnsAdmins グループのメンバーとして、サーバーまたはドメインに最低でもログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ada7-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4ada7-105">このトピックでは、Lync Server 2013 の展開で作成する必要があるドメインネームシステム (DNS) レコードを構成する方法と、自動クライアントサインインに必要なものを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="4ada7-106">フロントエンドプールを作成すると、セットアップによってプールの Active Directory オブジェクトと設定が作成されます。これには、プールの完全修飾ドメイン名 (FQDN) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4ada7-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="4ada7-107">同様のオブジェクトと設定が、Standard Edition サーバー用に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4ada7-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="4ada7-108">クライアントがプールまたは Standard Edition サーバーに接続できるようにするには、プールまたは Standard Edition サーバーの FQDN が DNS に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ada7-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="4ada7-109">SIP ドメインごとに、内部 DNS で DNS SRV レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ada7-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="4ada7-110">この手順では、内部 DNS に SIP ユーザードメイン用のゾーンが含まれていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4ada7-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="4ada7-111">DNS SRV レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="4ada7-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="4ada7-112">DNS サーバーで [**スタート**] をクリックし、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4ada7-113">SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされる SIP ドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="4ada7-114">[**その他の新しいレコード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="4ada7-115">[**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="4ada7-116">[**サービス**] をクリックして、「 \*\* \_sipinternaltls\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="4ada7-117">[**プロトコル**] をクリックして、「 \*\* \_tcp\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="4ada7-118">[**ポート番号**] をクリックし、「**5061**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="4ada7-119">[**このサービスを提供しているホスト**] をクリックして、プールまたは Standard Edition サーバーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="4ada7-120">[**OK**] をクリックしてから、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="4ada7-121">DNS SRV レコードの作成を確認するには</span><span class="sxs-lookup"><span data-stu-id="4ada7-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="4ada7-122">Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="4ada7-123">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4ada7-124">[**開く**] ボックスに**cmd**と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4ada7-125">コマンドプロンプトで「 **nslookup**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="4ada7-126">「 **Set type = srv**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="4ada7-127">「 \*\* \_Sipinternaltls」\_と入力します。tcp.contoso.com\*\*を選び、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="4ada7-128">トランスポート層セキュリティ (TLS) レコードに対して表示される出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4ada7-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="4ada7-129">サーバー: \<\>contoso.com</span><span class="sxs-lookup"><span data-stu-id="4ada7-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="4ada7-130">Address: \<DNS サーバーの IP アドレス\></span><span class="sxs-lookup"><span data-stu-id="4ada7-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="4ada7-131">権限のない回答:</span><span class="sxs-lookup"><span data-stu-id="4ada7-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="4ada7-132">\_sipinternaltls.\_tcp.contoso.com SRV サービスの場所:</span><span class="sxs-lookup"><span data-stu-id="4ada7-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="4ada7-133">priority = 0</span><span class="sxs-lookup"><span data-stu-id="4ada7-133">priority = 0</span></span>
    
    <span data-ttu-id="4ada7-134">weight = 0</span><span class="sxs-lookup"><span data-stu-id="4ada7-134">weight = 0</span></span>
    
    <span data-ttu-id="4ada7-135">ポート = 5061</span><span class="sxs-lookup"><span data-stu-id="4ada7-135">port = 5061</span></span>
    
    <span data-ttu-id="4ada7-136">svr hostname = poolname.contoso.com (または Standard Edition server A レコード)</span><span class="sxs-lookup"><span data-stu-id="4ada7-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="4ada7-137">poolname.contoso.com internet address = \<1 つの enterprise edition サーバーの\>仮想\<IP アドレス、または Standard Edition サーバーの1つの enterprise edition サーバー\>または\<ip アドレスのみを持つプール。\></span><span class="sxs-lookup"><span data-stu-id="4ada7-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="4ada7-138">完了したら、コマンドプロンプトで「 **exit**」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="4ada7-139">フロントエンドプールまたは Standard Edition サーバーの FQDN が解決できることを確認するには</span><span class="sxs-lookup"><span data-stu-id="4ada7-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="4ada7-140">ドメイン内のクライアントコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="4ada7-141">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="4ada7-142">[**開く**] ボックスに**cmd**と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ada7-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="4ada7-143">コマンドプロンプトに、標準エディションサーバー \<\>のフロントエンドプール\>または fqdn の**nslookup** \<FQDN と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="4ada7-144">FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ada7-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

