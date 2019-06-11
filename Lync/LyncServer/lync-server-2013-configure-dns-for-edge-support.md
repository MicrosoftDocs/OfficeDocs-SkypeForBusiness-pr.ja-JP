---
title: 'Lync Server 2013: エッジ サポートの DNS の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="13199-102">Lync Server 2013 でのエッジ サポートの DNS の構成</span><span class="sxs-lookup"><span data-stu-id="13199-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13199-103">_**最終更新日:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="13199-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="13199-104">エッジサーバーとリバースプロキシインターフェイスの両方を含む、内部と外部のエッジインターフェイスに対して、ドメインネームシステム (DNS) レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13199-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="13199-105">既定では、エッジサーバーはドメインに参加しておらず、完全修飾ドメイン名 (完全修飾ドメイン名) を持ちません。</span><span class="sxs-lookup"><span data-stu-id="13199-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="13199-106">エッジサーバーは、完全修飾ドメイン名ではなく、短い (マシン) 名でのみ参照されます。</span><span class="sxs-lookup"><span data-stu-id="13199-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="13199-107">ただし、トポロジビルダーでは、短い名前ではなく Fqdn を使用します。</span><span class="sxs-lookup"><span data-stu-id="13199-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="13199-108">エッジサーバーの名前は、トポロジビルダーで使用される FQDN と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13199-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="13199-109">これを行うには、コンピューター名と組み合わせるときに、予期される FQDN が返される DNS サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="13199-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="13199-110">DNS サフィックスをコンピューター名に追加するには、「ドメインに参加していないコンピューター名とエッジサーバーに DNS サフィックスを追加するには」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="13199-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13199-111">既定では、クエリの dns ドメイン名に対して同じ種類の複数のリソースレコードが存在する場合、DNS はラウンドロビンアルゴリズムを使って、クエリの応答で返されるリソースレコードデータの順序を入れ替えます。</span><span class="sxs-lookup"><span data-stu-id="13199-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="13199-112">Lync Server 2013 DNS ロードバランシングは、dns の負荷分散メカニズムの一部として DNS ラウンドロビンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="13199-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="13199-113">ラウンドロビンの設定が無効になっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13199-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="13199-114">Windows オペレーティングシステムを実行していない DNS サーバーを使用している場合は、ラウンドロビンリソースレコードの順序が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13199-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="13199-115">各 DNS SRV レコードを作成して確認するには、「**DNS srv レコードを作成するには**」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="13199-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="13199-116">「**Dns a レコードを作成するに**は」の手順を使用して、外部ユーザーのアクセスに必要な dns a レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="13199-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="13199-117">レコードが正しく構成され、正常に動作していることを確認するには、このトピックの「**DNS レコードを確認するに**は」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13199-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="13199-118">外部ユーザーアクセスをサポートするために必要なレコードの詳細については、「 [Lync Server 2013 の DNS 要件を確認](lync-server-2013-determine-dns-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13199-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="13199-119">ドメインに参加していないエッジサーバー上のコンピューター名に DNS サフィックスを追加するには</span><span class="sxs-lookup"><span data-stu-id="13199-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="13199-120">コンピューターで [**スタート**] をクリックし、[**コンピューター**] を右クリックして、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="13199-121">[**コンピューター名、ドメインおよびワークグループの設定**] で [**設定の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="13199-122">[**コンピューター名**] タブで [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="13199-123">[**コンピューター名/ドメインの変更**] で、[**その他**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="13199-124">[ **DNS サフィックスと NetBIOS コンピューター名**] の [**このコンピューターのプライマリ DNS サフィックス**] に、内部ドメインの名前 (たとえば、corp.contoso.com) を入力し、[ **OK]** を3回クリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="13199-125">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="13199-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="13199-126">DNS SRV レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="13199-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="13199-127">適切な DNS サーバーで [**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**]、[ **DNS**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="13199-128">リモートユーザーおよびフェデレーションパートナーによる外部 DNS 参照に対して、1つの外部 dns エントリがあることを DNS で構成する必要があります。2) 境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) 内のエッジサーバーで使用される DNS 検索のエントリ。 Lync Server 2013 を実行している内部サーバーのレコードを含みます。および 3) 内部のクライアントと、Lync Server 2013 を実行しているサーバーによる参照用の内部 DNS エントリ。</span><span class="sxs-lookup"><span data-stu-id="13199-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="13199-129">SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="13199-130">[**その他の新しいレコード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="13199-131">[**リソースレコードの種類を選択**してください] に「**サービスの場所 (SRV)**」と入力し、[**レコードの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="13199-132">DNS SRV レコードに必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="13199-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="13199-133">DNS A レコードを作成するには</span><span class="sxs-lookup"><span data-stu-id="13199-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="13199-134">DNS サーバーで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**]、[ **dns**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="13199-135">SIP ドメインのコンソールツリーで [**前方参照ゾーン**] を展開し、Lync Server 2013 がインストールされているドメインを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="13199-136">[**新しいホスト (A)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="13199-137">DNS SRV レコードに必要なすべての情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="13199-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="13199-138">DNS レコードを確認するには</span><span class="sxs-lookup"><span data-stu-id="13199-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="13199-139">ドメイン内のクライアントコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13199-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="13199-140">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13199-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="13199-141">コマンドプロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="13199-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="13199-142">FQDN の適切な IP アドレスに解決される返信を受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="13199-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13199-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="13199-143">See Also</span></span>


[<span data-ttu-id="13199-144">Hosted Exchange UM との統合のための DNS SRV レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="13199-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="13199-145">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="13199-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

