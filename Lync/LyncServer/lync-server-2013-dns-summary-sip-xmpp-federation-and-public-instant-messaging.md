---
title: DNS 概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
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
ms.openlocfilehash: c927836377a0c7c14054073a9cf17ce638662450
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="01b41-102">DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="01b41-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01b41-103">_**最終更新日:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="01b41-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="01b41-104">Office Communications Server または Lync Server パートナーとのフェデレーションを定義するために必要なドメインネームシステム (DNS) レコードは、他のパースペクティブパートナーによるドメインの自動 DNS 検出を許可するかどうかを決定することによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="01b41-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="01b41-105">\_Sipfederationtls を発行する場合。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="01b41-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="01b41-106">*SIP ドメイン名\> \<* SRV レコードでは、他の SIP フェデレーションドメインでフェデレーションを「検出」できます。</span><span class="sxs-lookup"><span data-stu-id="01b41-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="01b41-107">Lync Server コントロールパネルで [ドメインとブロックされたドメインを許可する] 設定を使用するか、Lync Server 管理シェルと、[**取得**]、[**設定**]、[**新規作成** **]、** [ **CsBlockedDomain** PowerShell コマンドレット] を使用して、許可または禁止されたドメインの構成を設定することで、どのフェデレーションドメインを制御できますか。</span><span class="sxs-lookup"><span data-stu-id="01b41-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="01b41-108">これらの設定を構成する方法と PowerShell コマンドレットの使用方法の詳細については、このトピックの最後にある**関連トピック**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b41-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="01b41-109">[DNS records summary] テーブルには、オープン、または検出可能なフェデレーションに必要なエントリが示されています。</span><span class="sxs-lookup"><span data-stu-id="01b41-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="01b41-110">フェデレーション検出を実装しない場合は、 \_sipfederationtls を構成しないことを選択できます。\_tcp。</span><span class="sxs-lookup"><span data-stu-id="01b41-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="01b41-111">*SIP ドメイン名\>レコード。 \<*</span><span class="sxs-lookup"><span data-stu-id="01b41-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="01b41-112">_Sipfederationtls は、_tcp が必要な特定のシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="01b41-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="01b41-113"><EM>SIP ドメイン名&gt; &lt;</EM>SRV レコードですが、検出可能なフェデレーションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="01b41-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="01b41-114">このようなインスタンスの1つは、ユーザーのモバイル機能を展開した場合です。</span><span class="sxs-lookup"><span data-stu-id="01b41-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="01b41-115">モビリティープッシュ通知 (PNCH) は、lync 2010 モバイルクライアントまたは Lync 2013 モバイルクライアントを使用して、Lync 2010 モバイルクライアントまたは Windows Phone を使用している、Apple iPhone または iPad 上の Microsoft Lync モバイルクライアントで使用される特殊な種類のフェデレーションです。</span><span class="sxs-lookup"><span data-stu-id="01b41-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="01b41-116">_Tcp _sipfederationtls ます。</span><span class="sxs-lookup"><span data-stu-id="01b41-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="01b41-117"><EM>SIP ドメイン名&gt; &lt;</EM>SRV レコードは、モビリティーとプッシュ通知の場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="01b41-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="01b41-118">この問題を軽減して発見性を制御するには、[<STRONG>パートナードメイン探索を有効</STRONG>にする] 設定をオフにして検出をオフにします。</span><span class="sxs-lookup"><span data-stu-id="01b41-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="01b41-119">展開用の拡張メッセージングとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーで、エッジサーバーまたはエッジプールのアクセスエッジサービスへのレコードを解決する2つのドメインネームシステム (DNS) レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="01b41-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="01b41-120">パブリックインスタントメッセージング接続用にドメインネームシステム (DNS) を構成すると、外部ユーザーをサポートする構成はパブリック IM 接続をサポートすることになります。</span><span class="sxs-lookup"><span data-stu-id="01b41-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="01b41-121">エッジサーバーまたはエッジプールを既に構成している場合は、パブリック IM 接続をサポートするために必要な DNS レコードを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b41-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="01b41-122">DNS 概要-パブリックインスタントメッセージング接続を含む SIP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="01b41-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01b41-123">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="01b41-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01b41-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="01b41-124">FQDN</span></span></th>
<th><span data-ttu-id="01b41-125">IP アドレス/FQDN ホストレコード</span><span class="sxs-lookup"><span data-stu-id="01b41-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01b41-126">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="01b41-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01b41-127">外部 DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="01b41-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="01b41-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01b41-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01b41-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01b41-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01b41-130">他の潜在的なフェデレーションパートナーとのフェデレーションを自動的に検出するには、アクセスエッジサービスの外部インターフェイスが必要です。また、"許可された SIP ドメイン" と呼ばれます (以前のリリースでは拡張フェデレーションと呼ばれます)。Lync を有効にしたユーザーがいるすべての SIP ドメインで、必要に応じて繰り返す</span><span class="sxs-lookup"><span data-stu-id="01b41-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="01b41-131">この SRV レコードは、モビリティとプッシュ通知のクリアリングハウスで必要です。</span><span class="sxs-lookup"><span data-stu-id="01b41-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="01b41-132">SIP ドメインが複数ある場合は、Lync モバイルクライアントを含むドメインごとに SRV レコードを作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="01b41-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="01b41-133">展開でサポートされている SIP ドメインごとに、明示的な SRV レコードがない場合、プッシュ通知サービスと Apple プッシュ通知サービスが予期したとおりに動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="01b41-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="01b41-134">DNS の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)</span><span class="sxs-lookup"><span data-stu-id="01b41-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01b41-135">場所/種類/ポート</span><span class="sxs-lookup"><span data-stu-id="01b41-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01b41-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="01b41-136">FQDN</span></span></th>
<th><span data-ttu-id="01b41-137">IP アドレス/FQDN ホストレコード</span><span class="sxs-lookup"><span data-stu-id="01b41-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01b41-138">マップ先/コメント</span><span class="sxs-lookup"><span data-stu-id="01b41-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01b41-139">外部 DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="01b41-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="01b41-140">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01b41-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01b41-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01b41-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01b41-142">アクセスエッジサービスまたはエッジプールの XMPP プロキシ外部インターフェイス。グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、すべての内部 SIP ドメインについて必要に応じてこの手順を繰り返します。Lync 対応ユーザー。</span><span class="sxs-lookup"><span data-stu-id="01b41-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="01b41-143">許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b41-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="01b41-144">詳細については、 <strong>「</strong>関連項目」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01b41-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01b41-145">外部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="01b41-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01b41-146">xmpp.contoso.com (など)</span><span class="sxs-lookup"><span data-stu-id="01b41-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="01b41-147">エッジサーバーまたは XMPP プロキシをホストしているエッジプールのアクセスエッジサービスの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="01b41-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="01b41-148">XMPP プロキシサービスをホストしているアクセスエッジサービスまたはエッジプールへのポイント。</span><span class="sxs-lookup"><span data-stu-id="01b41-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="01b41-149">通常、作成した SRV レコードは、このホスト (A または AAAA) レコードをポイントします。</span><span class="sxs-lookup"><span data-stu-id="01b41-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01b41-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="01b41-150">See Also</span></span>


[<span data-ttu-id="01b41-151">Lync Server 2013 XMPP フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="01b41-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="01b41-152">Lync Server 2013 でプッシュ通知を構成する</span><span class="sxs-lookup"><span data-stu-id="01b41-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="01b41-153">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="01b41-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="01b41-154">Lync Server 2013 の外部ユーザー アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="01b41-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="01b41-155">Lync Server 2013 の DNS の要件を確認する</span><span class="sxs-lookup"><span data-stu-id="01b41-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="01b41-156">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="01b41-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

