---
title: 'Lync Server 2013: フロントエンドプールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="6c299-102">Lync Server 2013 のフロントエンドプールの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="6c299-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c299-103">_**トピックの最終更新日:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="6c299-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="6c299-104">この手順を正常に完了するには、最低限でも Domain Admins グループまたは DnsAdmins グループのメンバーとしてサーバーまたはドメインにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c299-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="6c299-105">トポロジビルダーでトポロジを公開する前に、必要なドメインネームシステム (DNS) レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c299-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="6c299-106">さらに、Lync Server 2013 の展開の構成で使用されている完全修飾ドメイン名 (Fqdn) の一部は論理的で、物理サーバーの Fqdn ではないため、公開する前に追加の DNS 構成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6c299-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6c299-107">Lync Server 2013 は、単一ラベルのドメインをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6c299-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="6c299-108">たとえば、ルート ドメイン名が <STRONG>contoso.local</STRONG> であるフォレストはサポートされますが、<STRONG>local</STRONG> という名前のルート ドメインはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="6c299-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="6c299-109">詳細については、「Microsoft サポート技術情報の記事300684」を参照してください。「単一ラベル DNS 名を使用してドメインに Windows を構成する」の「at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c299-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c299-110">指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c299-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="6c299-111">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。</span><span class="sxs-lookup"><span data-stu-id="6c299-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="6c299-112">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c299-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="6c299-113">Lync Server、エッジサーバー、およびプールを実行しているサーバーの Fqdn を割り当てるときは、標準文字 (A ~ Z、a ~ z、0 ~ 9、およびハイフン)<STRONG>のみを使用</STRONG>します。</span><span class="sxs-lookup"><span data-stu-id="6c299-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="6c299-114">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6c299-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="6c299-115">一般に、外部 DNS および公的証明機関 (CA) では、FQDN に非標準文字はサポートされていません (証明書で FQDN を SN に割り当てる必要がある場合)。</span><span class="sxs-lookup"><span data-stu-id="6c299-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="6c299-116">トポロジを展開した後でトポロジを運用する前に、次の Active Directory と DNS レコードが作成されていることを確認してください (特定の機能の決定に必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="6c299-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="6c299-117">トポロジ内に存在する各サーバーの役割は、Active Directory オブジェクトとして公開されます (コンピューターをドメインに参加させることでこれを実現できます)。</span><span class="sxs-lookup"><span data-stu-id="6c299-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="6c299-118">DNS A レコードはサーバーごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="6c299-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="6c299-119">Sipinternaltls \_\_tcp の形式でクライアントの自動ログオンを使用する場合は、各 SIP ドメインに対して DNS SRV レコードが存在します。\<SIP ドメイン\>。</span><span class="sxs-lookup"><span data-stu-id="6c299-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="6c299-120">クライアントに手動構成を使用する場合、このレコードは不要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="6c299-121">構成済みの簡易 URL のそれぞれの DNS A レコードには、通常 meet、dialin、lwa、scheduler の 4 つがあります。</span><span class="sxs-lookup"><span data-stu-id="6c299-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="6c299-122">さらに、管理者の簡易 URL は、Lync Server 2013 コントロールパネルにアクセスするための特別な URL です。</span><span class="sxs-lookup"><span data-stu-id="6c299-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="6c299-123">SQL Server を実行しているサーバーは、ドメインに参加している必要があります。また、トポロジビルダーが公開しているコンピューターから到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c299-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="6c299-124">表は、「計画」セクションの参照アーキテクチャに従っています。</span><span class="sxs-lookup"><span data-stu-id="6c299-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="6c299-125">詳細については、「計画」のドキュメントの「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c299-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="6c299-126">フロントエンドプールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="6c299-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c299-127">場所</span><span class="sxs-lookup"><span data-stu-id="6c299-127">Location</span></span></th>
<th><span data-ttu-id="6c299-128">型</span><span class="sxs-lookup"><span data-stu-id="6c299-128">Type</span></span></th>
<th><span data-ttu-id="6c299-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="6c299-129">FQDN</span></span></th>
<th><span data-ttu-id="6c299-130">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="6c299-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c299-131">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-132">A</span><span class="sxs-lookup"><span data-stu-id="6c299-132">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6c299-134">Pool01 (DNS 負荷分散)。</span><span class="sxs-lookup"><span data-stu-id="6c299-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="6c299-135">プールの FQDN へのマッピングで、プール内の各フロントエンドサーバーの IP アドレスの DNS A レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-136">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-137">A</span><span class="sxs-lookup"><span data-stu-id="6c299-137">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6c299-139">Pool01 (ロード バランサー機器の仮想 IP (VIP))。</span><span class="sxs-lookup"><span data-stu-id="6c299-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-140">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-141">A</span><span class="sxs-lookup"><span data-stu-id="6c299-141">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="6c299-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="6c299-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="6c299-145">…</span><span class="sxs-lookup"><span data-stu-id="6c299-145">…</span></span></p></td>
<td><p><span data-ttu-id="6c299-146">Pool01 フロントエンドサーバー (ノード 1)。</span><span class="sxs-lookup"><span data-stu-id="6c299-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="6c299-147">Pool01 フロントエンドサーバー (ノード 2)。</span><span class="sxs-lookup"><span data-stu-id="6c299-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="6c299-148">Pool01 フロントエンドサーバー (ノード 3)。</span><span class="sxs-lookup"><span data-stu-id="6c299-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="6c299-149">…</span><span class="sxs-lookup"><span data-stu-id="6c299-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-150">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-151">A</span><span class="sxs-lookup"><span data-stu-id="6c299-151">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6c299-153">Pool01 フロントエンドサーバー (ノード 2)。</span><span class="sxs-lookup"><span data-stu-id="6c299-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-154">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-155">A</span><span class="sxs-lookup"><span data-stu-id="6c299-155">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6c299-157">クライアントとサーバー間の Web トラフィック用の Pool01 (VIP)。</span><span class="sxs-lookup"><span data-stu-id="6c299-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-158">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-159">A</span><span class="sxs-lookup"><span data-stu-id="6c299-159">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="6c299-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="6c299-161">SQL Server 2008 R2 を実行している Pool01 バックエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="6c299-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-162">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-163">A</span><span class="sxs-lookup"><span data-stu-id="6c299-163">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-165">Lync Phone Edition の場合、または DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合の場合に必須です。</span><span class="sxs-lookup"><span data-stu-id="6c299-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="6c299-166">すべての場合に必要なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="6c299-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-167">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-168">A</span><span class="sxs-lookup"><span data-stu-id="6c299-168">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c299-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-170">2 番目の SIP ドメインを前提とします。</span><span class="sxs-lookup"><span data-stu-id="6c299-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="6c299-171">Lync Phone Edition、DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合に必要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="6c299-172">すべての場合に必要なわけではありません。</span><span class="sxs-lookup"><span data-stu-id="6c299-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-173">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-174">A</span><span class="sxs-lookup"><span data-stu-id="6c299-174">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-176">内部で公開されたダイヤルイン会議の簡単な URL-フロントエンドサーバー (またはディレクターがインストールされている場合はディレクター) が簡単な URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="6c299-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-177">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-178">A</span><span class="sxs-lookup"><span data-stu-id="6c299-178">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-180">内部で公開された電話会議の簡単な URL-フロントエンドサーバー (またはディレクターがインストールされている場合はディレクター) が簡単な URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="6c299-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-181">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-182">A</span><span class="sxs-lookup"><span data-stu-id="6c299-182">A</span></span></p></td>
<td><p><span data-ttu-id="6c299-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="6c299-184">同期</span><span class="sxs-lookup"><span data-stu-id="6c299-184">admin</span></span></p></td>
<td><p><span data-ttu-id="6c299-185">(省略可能) Lync Server 2013 コントロールパネルの内部公開-フロントエンドサーバー (またはディレクターがインストールされている場合) は、簡易 URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="6c299-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="6c299-186">ホスト名のみ (ドメイン名なし) にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c299-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6c299-187">VIP = ロード バランサー機器の仮想 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6c299-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="6c299-188">フロントエンドプールの DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="6c299-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6c299-189">場所</span><span class="sxs-lookup"><span data-stu-id="6c299-189">Location</span></span></th>
<th><span data-ttu-id="6c299-190">型</span><span class="sxs-lookup"><span data-stu-id="6c299-190">Type</span></span></th>
<th><span data-ttu-id="6c299-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="6c299-191">FQDN</span></span></th>
<th><span data-ttu-id="6c299-192">対象 FQDN</span><span class="sxs-lookup"><span data-stu-id="6c299-192">Target FQDN</span></span></th>
<th><span data-ttu-id="6c299-193">ポート</span><span class="sxs-lookup"><span data-stu-id="6c299-193">Port</span></span></th>
<th><span data-ttu-id="6c299-194">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="6c299-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c299-195">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-196">SRV</span><span class="sxs-lookup"><span data-stu-id="6c299-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="6c299-197">_sipinternaltls の _tcp</span><span class="sxs-lookup"><span data-stu-id="6c299-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-199">5061</span><span class="sxs-lookup"><span data-stu-id="6c299-199">5061</span></span></p></td>
<td><p><span data-ttu-id="6c299-200">Lync 2013 クライアントを内部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c299-201">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-202">SRV</span><span class="sxs-lookup"><span data-stu-id="6c299-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="6c299-203">_sipinternaltls の _tcp</span><span class="sxs-lookup"><span data-stu-id="6c299-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6c299-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-205">5061</span><span class="sxs-lookup"><span data-stu-id="6c299-205">5061</span></span></p></td>
<td><p><span data-ttu-id="6c299-206">Lync 2013 クライアントを内部で動作するように自動構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c299-207">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="6c299-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="6c299-208">SRV</span><span class="sxs-lookup"><span data-stu-id="6c299-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="6c299-209">_ntp の _udp</span><span class="sxs-lookup"><span data-stu-id="6c299-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6c299-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="6c299-211">123</span><span class="sxs-lookup"><span data-stu-id="6c299-211">123</span></span></p></td>
<td><p><span data-ttu-id="6c299-212">Lync Phone Edition を実行しているデバイスには、ネットワークタイムプロトコル (NTP) ソースが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c299-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="6c299-213">内部では、ドメイン コントローラーを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c299-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="6c299-214">ドメイン コントローラーが定義されていない場合は、NTP サーバー time.windows.com の使用を試みます。</span><span class="sxs-lookup"><span data-stu-id="6c299-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

