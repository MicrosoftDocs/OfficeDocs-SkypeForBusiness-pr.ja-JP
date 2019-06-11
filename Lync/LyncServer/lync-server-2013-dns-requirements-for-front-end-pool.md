---
title: 'Lync Server 2013: フロントエンド プールの DNS 要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="04f9d-102">Lync Server 2013 のフロントエンド プールの DNS 要件</span><span class="sxs-lookup"><span data-stu-id="04f9d-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04f9d-103">_**最終更新日:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="04f9d-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="04f9d-104">この手順を完了するには、ドメイン管理者グループのメンバー、または DnsAdmins グループのメンバーとして、サーバーまたはドメインに最低でもログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="04f9d-105">トポロジビルダーでトポロジを公開する前に、必要なドメインネームシステム (DNS) レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="04f9d-106">さらに、Lync Server 2013 の展開の構成で使用される完全修飾ドメイン名 (Fqdn) の一部は論理的であり、物理サーバーの Fqdn ではないため、公開前に追加の DNS 構成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="04f9d-107">Lync Server 2013 では、単一ラベルのドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="04f9d-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="04f9d-108">たとえば、 <STRONG>local</STRONG>という名前のルートドメインを持つフォレストはサポートされていますが、 <STRONG>local</STRONG>という名前のルートドメインはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="04f9d-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="04f9d-109">詳細については、「Microsoft サポート技術情報の記事300684」「単一ラベルの DNS 名を使用してドメイン用の Windows を構成する方法について」を参照してください。 "at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>。</span><span class="sxs-lookup"><span data-stu-id="04f9d-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="04f9d-110">指定する名前が、サーバーで構成されているコンピューター名と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="04f9d-111">既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく、短い名前です。</span><span class="sxs-lookup"><span data-stu-id="04f9d-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="04f9d-112">トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="04f9d-113"><STRONG>標準文字のみを使用する</STRONG>Lync Server、エッジサーバー、およびプールを実行しているサーバーの Fqdn を割り当てる場合は、– Z、a ~ z、0 ~ 9、ハイフンを含みます。</span><span class="sxs-lookup"><span data-stu-id="04f9d-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="04f9d-114">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="04f9d-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="04f9d-115">FQDN の非標準文字は、多くの場合、外部 DNS と公共の証明機関 (Ca) でサポートされていません (証明書の SN に FQDN を割り当てる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="04f9d-116">トポロジが展開された後にトポロジを操作する前に、次の Active Directory と DNS レコードが作成されていることを確認してください (具体的な機能の設定が必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="04f9d-117">トポロジに存在する各サーバーの役割は、Active Directory オブジェクトとして公開されます (コンピューターをドメインに参加させることによって、この操作を実行します)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="04f9d-118">DNS A レコードが各サーバーに存在します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="04f9d-119">Sipinternaltls \_\_tcp の形式でクライアントに自動ログオンを使用することを計画している場合は、各 SIP ドメインに対して DNS SRV レコードが存在します。\<SIP ドメイン\>。</span><span class="sxs-lookup"><span data-stu-id="04f9d-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="04f9d-120">クライアントに手動構成を使用する場合は、このレコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="04f9d-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="04f9d-121">構成された簡易 URL ごとに1つの DNS A レコード。通常は、会議、ダイヤルイン、lwa、スケジューラの4種類があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="04f9d-122">さらに、管理者の簡単な URL は、Lync Server 2013 コントロールパネルへのアクセスに使用する特別な URL です。</span><span class="sxs-lookup"><span data-stu-id="04f9d-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="04f9d-123">SQL Server が実行されているサーバーは、ドメインに参加し、トポロジビルダーが発行元のコンピューターからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="04f9d-124">この表は、計画セクションに示されているリファレンスアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="04f9d-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="04f9d-125">詳細については、計画ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04f9d-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="04f9d-126">フロントエンドプールに必要な DNS レコード</span><span class="sxs-lookup"><span data-stu-id="04f9d-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04f9d-127">場所</span><span class="sxs-lookup"><span data-stu-id="04f9d-127">Location</span></span></th>
<th><span data-ttu-id="04f9d-128">型</span><span class="sxs-lookup"><span data-stu-id="04f9d-128">Type</span></span></th>
<th><span data-ttu-id="04f9d-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="04f9d-129">FQDN</span></span></th>
<th><span data-ttu-id="04f9d-130">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="04f9d-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-131">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-132">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-132">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04f9d-134">Pool01 (DNS ロードバランシング)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="04f9d-135">プール内の各フロントエンドサーバーの IP アドレスに対して DNS A レコードが必要です。プールの FQDN にマッピングします。</span><span class="sxs-lookup"><span data-stu-id="04f9d-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-136">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-137">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-137">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04f9d-139">Pool01 (仮想 IP (VIP) (ハードウェアロードバランサー)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-140">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-141">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-141">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="04f9d-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="04f9d-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="04f9d-145">…</span><span class="sxs-lookup"><span data-stu-id="04f9d-145"></span></span></p></td>
<td><p><span data-ttu-id="04f9d-146">Pool01 フロントエンドサーバー (ノード 1)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="04f9d-147">Pool01 フロントエンドサーバー (ノード 2)</span><span class="sxs-lookup"><span data-stu-id="04f9d-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="04f9d-148">Pool01 フロントエンドサーバー (ノード 3)</span><span class="sxs-lookup"><span data-stu-id="04f9d-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="04f9d-149">…</span><span class="sxs-lookup"><span data-stu-id="04f9d-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-150">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-151">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-151">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04f9d-153">Pool01 フロントエンドサーバー (ノード 2)</span><span class="sxs-lookup"><span data-stu-id="04f9d-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-154">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-155">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-155">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04f9d-157">クライアントとサーバーの web トラフィックの Pool01 (VIP)。</span><span class="sxs-lookup"><span data-stu-id="04f9d-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-158">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-159">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-159">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="04f9d-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="04f9d-161">SQL Server 2008 R2 を実行している Pool01 バックエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="04f9d-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-162">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-163">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-163">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-165">Lync Phone Edition の場合、または DNS SRV レコードのないクライアントの自動ログオン、および厳密なドメイン照合の場合に必須です。</span><span class="sxs-lookup"><span data-stu-id="04f9d-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="04f9d-166">すべてのケースで必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="04f9d-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-167">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-168">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-168">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-170">第2の SIP ドメインを仮定します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="04f9d-171">Lync Phone Edition の場合は必須。 DNS SRV レコードがないクライアントの自動ログオン、および厳密なドメインの一致の場合。</span><span class="sxs-lookup"><span data-stu-id="04f9d-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="04f9d-172">すべてのケースで必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="04f9d-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-173">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-174">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-174">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-176">内部で公開されたダイヤルイン会議の単純な URL –フロントエンドサーバー (またはインストールされている場合はディレクター) が単純な URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-177">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-178">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-178">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-180">内部で公開された会議の単純な URL –フロントエンドサーバー (またはインストールされている場合はディレクター) が単純な URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-181">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-182">A</span><span class="sxs-lookup"><span data-stu-id="04f9d-182">A</span></span></p></td>
<td><p><span data-ttu-id="04f9d-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="04f9d-184">同期</span><span class="sxs-lookup"><span data-stu-id="04f9d-184">admin</span></span></p></td>
<td><p><span data-ttu-id="04f9d-185">省略可能なレコード。 Lync Server 2013 コントロールパネルが内部的に公開されている場合は、フロントエンドサーバー (またはディレクター (インストールされている場合はディレクター)) で簡単な URL クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="04f9d-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="04f9d-186">ホスト名のみ (ドメイン名は不要) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04f9d-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="04f9d-187">VIP = ハードウェアロードバランサーの仮想 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="04f9d-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="04f9d-188">フロントエンドプールの DNS SRV レコード</span><span class="sxs-lookup"><span data-stu-id="04f9d-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="04f9d-189">場所</span><span class="sxs-lookup"><span data-stu-id="04f9d-189">Location</span></span></th>
<th><span data-ttu-id="04f9d-190">型</span><span class="sxs-lookup"><span data-stu-id="04f9d-190">Type</span></span></th>
<th><span data-ttu-id="04f9d-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="04f9d-191">FQDN</span></span></th>
<th><span data-ttu-id="04f9d-192">ターゲット FQDN</span><span class="sxs-lookup"><span data-stu-id="04f9d-192">Target FQDN</span></span></th>
<th><span data-ttu-id="04f9d-193">ポート</span><span class="sxs-lookup"><span data-stu-id="04f9d-193">Port</span></span></th>
<th><span data-ttu-id="04f9d-194">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="04f9d-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-195">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-196">SRV</span><span class="sxs-lookup"><span data-stu-id="04f9d-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="04f9d-197">_sipinternaltls の _tcp</span><span class="sxs-lookup"><span data-stu-id="04f9d-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-199">5061</span><span class="sxs-lookup"><span data-stu-id="04f9d-199">5061</span></span></p></td>
<td><p><span data-ttu-id="04f9d-200">Lync 2013 クライアントを内部で動作するように自動構成する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04f9d-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04f9d-201">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-202">SRV</span><span class="sxs-lookup"><span data-stu-id="04f9d-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="04f9d-203">_sipinternaltls の _tcp</span><span class="sxs-lookup"><span data-stu-id="04f9d-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-205">5061</span><span class="sxs-lookup"><span data-stu-id="04f9d-205">5061</span></span></p></td>
<td><p><span data-ttu-id="04f9d-206">Lync 2013 クライアントを内部で動作するように自動構成する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="04f9d-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04f9d-207">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="04f9d-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="04f9d-208">SRV</span><span class="sxs-lookup"><span data-stu-id="04f9d-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="04f9d-209">_ntp._udp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="04f9d-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="04f9d-211">123</span><span class="sxs-lookup"><span data-stu-id="04f9d-211">123</span></span></p></td>
<td><p><span data-ttu-id="04f9d-212">Lync Phone Edition を実行しているデバイスに必要なネットワークタイムプロトコル (NTP) ソース。</span><span class="sxs-lookup"><span data-stu-id="04f9d-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="04f9d-213">内部では、これはドメインコントローラーを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="04f9d-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="04f9d-214">ドメインコントローラーが定義されていない場合は、NTP サーバー time.windows.com を使います。</span><span class="sxs-lookup"><span data-stu-id="04f9d-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

