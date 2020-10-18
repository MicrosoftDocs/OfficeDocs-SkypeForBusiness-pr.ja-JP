---
title: DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
description: DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング。
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
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572763"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="b20f6-103">Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="b20f6-103">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b20f6-104">_**トピックの最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="b20f6-104">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="b20f6-105">Office Communications Server または Lync Server パートナーとのフェデレーションを定義するために必要となるドメインネームシステム (DNS) レコードは、他の組織のドメインの自動 DNS 検出を許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b20f6-105">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="b20f6-106">Sipfederationtls を発行する場合 \_ 。 \_プロトコル.</span><span class="sxs-lookup"><span data-stu-id="b20f6-106">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="b20f6-107">*\<SIP domain name\>* SRV レコード。他の SIP フェデレーションドメインは、フェデレーションを "検出" することができます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-107">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="b20f6-108">Lync server コントロールパネルで [ドメインとブロックされたドメインを許可する] の設定を使用するか、Lync Server 管理シェルと **Get**、 **Set**、 **New**、 **Remove-csalloweddomain** および **-get-csblockeddomain** PowerShell コマンドレットを使用して、許可または禁止ドメイン構成を設定することによって、どのフェデレーションドメインが自分と通信できるかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-108">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="b20f6-109">これらの設定の構成方法および PowerShell コマンドレットの使用の詳細については、このトピックの最後にある**関連トピック**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f6-109">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="b20f6-110">DNS レコードの概要の表には、開いている、つまり検出可能なフェデレーションに必要なエントリが示されています。</span><span class="sxs-lookup"><span data-stu-id="b20f6-110">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="b20f6-111">フェデレーション検出を実装しない場合は、sipfederationtls を構成しないことを決定でき \_ ます。 \_プロトコル.</span><span class="sxs-lookup"><span data-stu-id="b20f6-111">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="b20f6-112">*\<SIP domain name\>* レコード.</span><span class="sxs-lookup"><span data-stu-id="b20f6-112">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b20f6-113">_Sipfederationtls を使用する必要がある特定のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-113">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="b20f6-114"><EM> &lt; SIP ドメイン名 &gt; </EM> SRV レコードですが、検出可能なフェデレーションを使用したくありません。</span><span class="sxs-lookup"><span data-stu-id="b20f6-114"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="b20f6-115">このようなインスタンスの1つとして、ユーザーのモビリティを展開した場所があります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-115">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="b20f6-116">モビリティープッシュ通知クリアリングハウス (PNCH) は特別な種類のフェデレーションで、lync 2010 モバイルクライアントまたは lync 2013 モバイルクライアント2010を使用して、Lync モバイルクライアントまたは Windows Phone を使用している Apple iPhone または iPad の Microsoft Lync Mobile クライアントに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-116">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="b20f6-117">_Sipfederationtls。 _tcp。</span><span class="sxs-lookup"><span data-stu-id="b20f6-117">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="b20f6-118"><EM> &lt; SIP ドメイン名 &gt; </EM> SRV レコードは、モビリティおよびプッシュ通知の場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-118"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="b20f6-119">この問題を軽減して、発見性を制御するには、[ <STRONG>パートナードメインの検出を有効</STRONG> にする] の設定をクリアして、検出をオフにします。</span><span class="sxs-lookup"><span data-stu-id="b20f6-119">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="b20f6-120">展開用に拡張メッセージとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーに2つのドメインネームシステム (DNS) レコードを作成します。これにより、エッジサーバーまたはエッジプールのアクセスエッジサービスに対するレコードが解決されます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-120">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="b20f6-121">パブリックインスタントメッセージング接続用にドメインネームシステム (DNS) を構成すると、外部ユーザーをサポートする構成がパブリック IM 接続をサポートすることがわかります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-121">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="b20f6-122">エッジサーバーまたはエッジプールを既に構成している場合は、パブリック IM 接続をサポートするために必要な DNS レコードを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-122">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="b20f6-123">DNS の概要-パブリックインスタントメッセージング接続を含む SIP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="b20f6-123">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b20f6-124">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="b20f6-124">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b20f6-125">FQDN</span><span class="sxs-lookup"><span data-stu-id="b20f6-125">FQDN</span></span></th>
<th><span data-ttu-id="b20f6-126">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="b20f6-126">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b20f6-127">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="b20f6-127">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b20f6-128">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="b20f6-128">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="b20f6-129">_sipfederationtls _sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="b20f6-129">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b20f6-130">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b20f6-130">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b20f6-131">他の潜在的フェデレーションパートナーへのフェデレーションの自動 DNS 検出に必要なアクセスエッジサービスの外部インターフェイス (以前のリリースでは拡張フェデレーションと呼ばれます) と呼ばれる、"許可された SIP ドメイン" と呼ばれるものです。Lync が有効なユーザーを持つすべての SIP ドメインについて必要に応じて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b20f6-131">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="b20f6-132">この SRV レコードは、モビリティおよび Push Notification Clearing House (PNCH) で必要です。</span><span class="sxs-lookup"><span data-stu-id="b20f6-132">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="b20f6-133">複数の SIP ドメインがある場合は、Lync Mobile クライアントを持つ各ドメインの SRV レコードを作成して発行します。</span><span class="sxs-lookup"><span data-stu-id="b20f6-133">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="b20f6-134">展開でサポートされている各 SIP ドメインに対して明示的な SRV レコードが存在しない場合、プッシュ通知サービスと Apple プッシュ通知サービスが期待どおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-134">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="b20f6-135">DNS の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)</span><span class="sxs-lookup"><span data-stu-id="b20f6-135">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b20f6-136">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="b20f6-136">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b20f6-137">FQDN</span><span class="sxs-lookup"><span data-stu-id="b20f6-137">FQDN</span></span></th>
<th><span data-ttu-id="b20f6-138">IP アドレス/FQDN ホスト レコード</span><span class="sxs-lookup"><span data-stu-id="b20f6-138">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="b20f6-139">マッピング先/コメント</span><span class="sxs-lookup"><span data-stu-id="b20f6-139">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b20f6-140">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="b20f6-140">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="b20f6-141">_xmpp-server._tcp</span><span class="sxs-lookup"><span data-stu-id="b20f6-141">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b20f6-142">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b20f6-142">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b20f6-143">アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。</span><span class="sxs-lookup"><span data-stu-id="b20f6-143">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="b20f6-144">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b20f6-144">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="b20f6-145">詳細については、 <strong>「</strong> 関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b20f6-145">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b20f6-146">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b20f6-146">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b20f6-147">xmpp.contoso.com (例)</span><span class="sxs-lookup"><span data-stu-id="b20f6-147">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="b20f6-148">XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="b20f6-148">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="b20f6-149">XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。</span><span class="sxs-lookup"><span data-stu-id="b20f6-149">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="b20f6-150">通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</span><span class="sxs-lookup"><span data-stu-id="b20f6-150">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b20f6-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="b20f6-151">See Also</span></span>


[<span data-ttu-id="b20f6-152">Lync Server 2013 での XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b20f6-152">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="b20f6-153">Lync Server 2013 でのプッシュ通知の構成</span><span class="sxs-lookup"><span data-stu-id="b20f6-153">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="b20f6-154">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b20f6-154">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="b20f6-155">Lync Server 2013 での外部ユーザーアクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="b20f6-155">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="b20f6-156">Lync Server 2013 の DNS 要件を決定する</span><span class="sxs-lookup"><span data-stu-id="b20f6-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="b20f6-157">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</span><span class="sxs-lookup"><span data-stu-id="b20f6-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

