---
title: DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2ccaab6d1d3bcb1cf597bef076601544f47aad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="c3c75-102">Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="c3c75-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3c75-103">_**トピックの最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="c3c75-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="c3c75-104">Office Communications Server または Lync Server パートナーとのフェデレーションを定義するために必要となるドメインネームシステム (DNS) レコードは、他の組織のドメインの自動 DNS 検出を許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="c3c75-105">Sipfederationtls を\_発行する場合。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="c3c75-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="c3c75-106">*SIP ドメイン名\> \<* SRV レコード。他の SIP フェデレーションドメインは、フェデレーションを "検出" することができます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="c3c75-107">Lync server コントロールパネルで [ドメインとブロックされたドメインを許可する] の設定を使用するか、Lync Server 管理シェルと**Get**、 **Set**、 **New**、 **Remove-csalloweddomain**および **-get-csblockeddomain** PowerShell コマンドレットを使用して、許可または禁止ドメイン構成を設定することによって、どのフェデレーションドメインが自分と通信できるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="c3c75-108">これらの設定の構成方法および PowerShell コマンドレットの使用の詳細については、このトピックの最後にある**関連トピック**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3c75-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="c3c75-109">DNS レコードの概要の表には、開いている、つまり検出可能なフェデレーションに必要なエントリが示されています。</span><span class="sxs-lookup"><span data-stu-id="c3c75-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="c3c75-110">フェデレーション検出を実装しない場合は、 \_sipfederationtls を構成しないことを決定できます。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="c3c75-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="c3c75-111">*SIP ドメイン名\>レコード。 \<*</span><span class="sxs-lookup"><span data-stu-id="c3c75-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c3c75-112">_Sipfederationtls を使用する必要がある特定のシナリオがあります。 _tcp。</span><span class="sxs-lookup"><span data-stu-id="c3c75-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="c3c75-113"><EM>SIP ドメイン名&gt; &lt;</EM>SRV レコード。ただし、検出可能なフェデレーションを使用したくありません。</span><span class="sxs-lookup"><span data-stu-id="c3c75-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="c3c75-114">このようなインスタンスの1つとして、ユーザーのモビリティを展開した場所があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="c3c75-115">モビリティープッシュ通知クリアリングハウス (PNCH) は特別な種類のフェデレーションで、lync 2010 モバイルクライアントまたは lync 2013 モバイルクライアント2010を使用して、Lync モバイルクライアントまたは Windows Phone を使用している Apple iPhone または iPad の Microsoft Lync Mobile クライアントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="c3c75-116">_Sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="c3c75-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="c3c75-117"><EM>SIP ドメイン名&gt; &lt;</EM>SRV レコードは、モビリティおよびプッシュ通知の場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="c3c75-118">この問題を軽減して、発見性を制御するには、[<STRONG>パートナードメインの検出を有効</STRONG>にする] の設定をクリアして、検出をオフにします。</span><span class="sxs-lookup"><span data-stu-id="c3c75-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="c3c75-119">展開用に拡張メッセージとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーに2つのドメインネームシステム (DNS) レコードを作成します。これにより、エッジサーバーまたはエッジプールのアクセスエッジサービスに対するレコードが解決されます。</span><span class="sxs-lookup"><span data-stu-id="c3c75-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="c3c75-120">パブリックインスタントメッセージング接続用にドメインネームシステム (DNS) を構成すると、外部ユーザーをサポートする構成がパブリック IM 接続をサポートすることがわかります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="c3c75-121">エッジサーバーまたはエッジプールを既に構成している場合は、パブリック IM 接続をサポートするために必要な DNS レコードを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="c3c75-122">DNS の概要-パブリックインスタントメッセージング接続を含む SIP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="c3c75-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3c75-123">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="c3c75-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c3c75-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="c3c75-124">FQDN</span></span></th>
<th><span data-ttu-id="c3c75-125">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="c3c75-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="c3c75-126">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="c3c75-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3c75-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="c3c75-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="c3c75-128">_sipfederationtls の _tcp</span><span class="sxs-lookup"><span data-stu-id="c3c75-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3c75-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3c75-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3c75-130">他の潜在的フェデレーションパートナーへのフェデレーションの自動 DNS 検出に必要なアクセスエッジサービスの外部インターフェイス (以前のリリースでは拡張フェデレーションと呼ばれます) と呼ばれる、"許可された SIP ドメイン" と呼ばれるものです。Lync が有効なユーザーを持つすべての SIP ドメインについて必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="c3c75-131">この SRV レコードは、モビリティおよび Push Notification Clearing House (PNCH) で必要です。</span><span class="sxs-lookup"><span data-stu-id="c3c75-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="c3c75-132">複数の SIP ドメインがある場合は、Lync Mobile クライアントを持つ各ドメインの SRV レコードを作成して発行します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="c3c75-133">展開でサポートされている各 SIP ドメインに対して明示的な SRV レコードが存在しない場合、プッシュ通知サービスと Apple プッシュ通知サービスが期待どおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="c3c75-134">DNS の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)</span><span class="sxs-lookup"><span data-stu-id="c3c75-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3c75-135">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="c3c75-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c3c75-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="c3c75-136">FQDN</span></span></th>
<th><span data-ttu-id="c3c75-137">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="c3c75-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="c3c75-138">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="c3c75-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3c75-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="c3c75-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="c3c75-140">_xmpp-サーバーの _tcp</span><span class="sxs-lookup"><span data-stu-id="c3c75-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3c75-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3c75-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3c75-142">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。すべての内部 SIP ドメインについて必要に応じて、グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーを構成することにより、Lync が有効なユーザー。</span><span class="sxs-lookup"><span data-stu-id="c3c75-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="c3c75-143">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3c75-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="c3c75-144">詳細については、 <strong>「</strong>関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3c75-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3c75-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3c75-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3c75-146">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="c3c75-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="c3c75-147">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c3c75-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="c3c75-148">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="c3c75-149">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="c3c75-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3c75-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3c75-150">See Also</span></span>


[<span data-ttu-id="c3c75-151">Lync Server 2013 での XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c3c75-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="c3c75-152">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="c3c75-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="c3c75-153">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c3c75-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="c3c75-154">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c3c75-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="c3c75-155">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="c3c75-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="c3c75-156">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="c3c75-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

