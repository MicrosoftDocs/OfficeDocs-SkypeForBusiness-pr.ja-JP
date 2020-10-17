---
title: 'Lync Server 2013: DNS SRV レコードの作成と確認'
description: 'Lync Server 2013: DNS SRV レコードの作成と確認。'
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
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562383"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="059c5-103">Lync Server 2013 で DNS SRV レコードを作成および確認する</span><span class="sxs-lookup"><span data-stu-id="059c5-103">Create and verify DNS SRV records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="059c5-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="059c5-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="059c5-105">この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="059c5-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="059c5-106">このトピックでは、Lync Server 2013 の展開で作成する必要があるドメインネームシステム (DNS) レコード、および自動クライアントサインインに必要なドメインネームシステム (DNS) レコードを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="059c5-106">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="059c5-107">フロントエンドプールを作成すると、プールの完全修飾ドメイン名 (FQDN) を含む、プールの Active Directory オブジェクトと設定がセットアップによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="059c5-107">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="059c5-108">Standard Edition サーバー用に、同様のオブジェクトと設定が作成されます。</span><span class="sxs-lookup"><span data-stu-id="059c5-108">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="059c5-109">クライアントがプールまたは Standard Edition サーバーに接続できるようにするには、プールまたは Standard Edition サーバーの FQDN を DNS に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059c5-109">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="059c5-110">すべての SIP ドメインについて、内部 DNS に DNS SRV レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059c5-110">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="059c5-111">この手順では、内部 DNS に SIP ユーザードメインのゾーンがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="059c5-111">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="059c5-112">DNS SRV レコードを構成するには</span><span class="sxs-lookup"><span data-stu-id="059c5-112">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="059c5-113">DNS サーバー上で、[**スタート**] をクリックし、[**管理ツール**] をクリックします。次に、[**DNS**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-113">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="059c5-114">SIP ドメインのコンソールツリーで、[ **前方参照ゾーン**] を展開し、Lync Server 2013 をインストールする SIP ドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-114">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="059c5-115">[**その他の新しいレコード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-115">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="059c5-116">[**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-116">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="059c5-117">[**サービス**] をクリックし、「 \*\* \_ sipinternaltls\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="059c5-117">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="059c5-118">[**プロトコル**] をクリックし、「 \*\* \_ tcp\*\*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="059c5-118">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="059c5-119">"**ポート番号**" フィールドをクリックし、「**5061**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="059c5-119">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="059c5-120">[ **このサービスを提供**しているホスト] をクリックし、プールまたは Standard Edition サーバーの FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="059c5-120">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="059c5-121">[**OK**] をクリックしてから、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="059c5-122">DNS SRV レコードの作成を確認するには</span><span class="sxs-lookup"><span data-stu-id="059c5-122">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="059c5-123">Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="059c5-123">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="059c5-124">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="059c5-125">[**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-125">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="059c5-126">コマンド プロンプトに「**nslookup**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="059c5-126">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="059c5-127">「**set type=srv**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="059c5-127">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="059c5-128">「Sipinternaltls」と入力\*\* \_ します。 \_tcp.contoso.com\*\*と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="059c5-128">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="059c5-129">トランスポート層セキュリティ (TLS) レコードに対して表示される出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="059c5-129">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="059c5-130">サーバー: \<dns server\> . contoso.com</span><span class="sxs-lookup"><span data-stu-id="059c5-130">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="059c5-131">連絡先 \<IP address of DNS server\></span><span class="sxs-lookup"><span data-stu-id="059c5-131">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="059c5-132">Non-authoritative answer:</span><span class="sxs-lookup"><span data-stu-id="059c5-132">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="059c5-133">\_sipinternaltls。 \_tcp.contoso.com SRV サービスの場所:</span><span class="sxs-lookup"><span data-stu-id="059c5-133">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="059c5-134">priority = 0</span><span class="sxs-lookup"><span data-stu-id="059c5-134">priority = 0</span></span>
    
    <span data-ttu-id="059c5-135">ウエイト = 0</span><span class="sxs-lookup"><span data-stu-id="059c5-135">weight = 0</span></span>
    
    <span data-ttu-id="059c5-136">ポート = 5061</span><span class="sxs-lookup"><span data-stu-id="059c5-136">port = 5061</span></span>
    
    <span data-ttu-id="059c5-137">svr hostname = poolname.contoso.com (または Standard Edition サーバー A レコード)</span><span class="sxs-lookup"><span data-stu-id="059c5-137">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="059c5-138">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> また \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> は \<IP address of the Standard Edition server\></span><span class="sxs-lookup"><span data-stu-id="059c5-138">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="059c5-139">終了したら、コマンド プロンプトに「**exit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="059c5-139">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="059c5-140">フロントエンド プールまたは Standard Edition サーバーの FQDN が解決できることを確認するには</span><span class="sxs-lookup"><span data-stu-id="059c5-140">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="059c5-141">ドメイン内のクライアント コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="059c5-141">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="059c5-142">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-142">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="059c5-143">[**名前**] ボックスに「**cmd**」と入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059c5-143">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="059c5-144">コマンドプロンプトで「 **nslookup** \<FQDN of the Front End pool\> または \<FQDN of the Standard Edition server\> 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="059c5-144">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="059c5-145">受け取る応答が、FQDN の適切な IP アドレスに解決しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="059c5-145">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

