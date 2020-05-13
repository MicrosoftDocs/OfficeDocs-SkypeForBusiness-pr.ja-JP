---
title: 'Lync Server 2013: Lync フェデレーションのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b955def7b7648f274125353673d6973afb59b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="42261-102">Lync Server 2013 での Lync フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="42261-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42261-103">_**トピックの最終更新日:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="42261-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="42261-104">エッジ サーバーが既に展開されている場合、フェデレーション シナリオ機能は簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="42261-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="42261-105">エッジ サーバーがまだセットアップされていない場合は、これを最初に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="42261-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="42261-106">詳細については、「展開」のドキュメントの「計画」のドキュメントの「planning [for external user](lync-server-2013-planning-for-external-user-access.md) Access in lync server [2013 in lync server](lync-server-2013-deploying-external-user-access.md) 2013」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42261-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42261-p102">XMPP フェデレーション、Lync フェデレーション、またはパブリック インスタント メッセージング接続を組み合わせてセットアップする場合、これらを同時に展開することもできれば、1 つずつ展開することもできます。トポロジ ビルダーと Lync Server 管理シェルを通じてオプションを構成し、1 つ、2 つ、または 3 つすべてのフェデレーションの種類のオプションを構成した後でエッジ サーバーで展開ウィザードを実行すると、必要な手順の数が少なくてすみます。</span><span class="sxs-lookup"><span data-stu-id="42261-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="42261-109">トポロジ ビルダーと展開ウィザードで Lync フェデレーションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="42261-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="42261-p103">フロントエンド サーバーでトポロジ ビルダーを開きます。エッジ プールを展開し、エッジ サーバーまたはエッジ サーバー プールを右クリックします。[プロパティの編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42261-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="42261-p104">[全般] の下の [プロパティの編集] で、[このエッジ プールのフェデレーションの有効化 (ポート 5061)] を選択します。[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42261-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="42261-p105">[アクション] をクリックし、[トポロジ]、[公開] の順にクリックします。トポロジの公開を確認するプロンプトが表示されたら、[次へ] をクリックします。公開が完了したら、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42261-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="42261-p106">エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="42261-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="42261-p107">[Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="42261-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="42261-p108">このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="42261-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="42261-129">パートナーとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="42261-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="42261-130">別の Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2、または Office Communicator 2007 との正常なフェデレーションをセットアップするには、次の表からフェデレーションの種類を選択し、DNS SRV レコード、DNS ホスト (A または IPv6 用の AAAA) を定義して、フェデレーションの種類に適用されるポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="42261-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="42261-131">フェデレーションの種類</span><span class="sxs-lookup"><span data-stu-id="42261-131">Federation type</span></span></th>
    <th><span data-ttu-id="42261-132">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="42261-132">DNS Records</span></span></th>
    <th><span data-ttu-id="42261-133">ポリシー定義</span><span class="sxs-lookup"><span data-stu-id="42261-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="42261-134">メモ</span><span class="sxs-lookup"><span data-stu-id="42261-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="42261-135">検出済みのパートナー ドメイン</span><span class="sxs-lookup"><span data-stu-id="42261-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="42261-136">_Sipfederationtls _tcp &lt; 形式の SRV レコードを構成します。&gt;SRV レコードのポート値が TCP 5061 で、<strong>このサービスを提供するホスト</strong>が sip として定義されている外部ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="42261-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="42261-137">&lt;外部ドメイン名 &gt; –アクセスエッジサービスの FQDN。</span><span class="sxs-lookup"><span data-stu-id="42261-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="42261-138">SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための DNS の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42261-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="42261-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="42261-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="42261-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="42261-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="42261-p110">以前のバージョンでは、このフェデレーションの種類は、<strong>オープン拡張フェデレーション</strong>と呼ばれていました。この種類のフェデレーションでは、SRV レコードの作成が必要です。その他のパートナーがフェデレーションを検出できるようにします。</span><span class="sxs-lookup"><span data-stu-id="42261-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="42261-143">許可されたパートナー ドメイン</span><span class="sxs-lookup"><span data-stu-id="42261-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="42261-144">_Sipfederationtls _tcp &lt; 形式の SRV レコードを構成します。&gt;SRV レコードのポート値が TCP 5061 で、<strong>このサービスを提供するホスト</strong>が sip として定義されている外部ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="42261-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="42261-145">&lt;外部ドメイン名 &gt; –アクセスエッジサービスの FQDN。</span><span class="sxs-lookup"><span data-stu-id="42261-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="42261-146">SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための DNS の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42261-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="42261-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="42261-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="42261-148">以前のバージョンでは、この種類のフェデレーションは<strong>拡張フェデレーション</strong>と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="42261-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="42261-149">SRV レコードの作成は、この種類のフェデレーションではオプションであり、他のパートナーがフェデレーションを検出できるようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="42261-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="42261-150">もちろん、これは<strong>オープン拡張フェデレーション</strong>、または検出された<strong>パートナードメイン</strong></span><span class="sxs-lookup"><span data-stu-id="42261-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="42261-151">許可されたパートナー サーバー</span><span class="sxs-lookup"><span data-stu-id="42261-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="42261-152">ポリシーでフェデレーションパートナーとして SIP ドメイン名とパートナーエッジサーバーの FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="42261-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="42261-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="42261-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="42261-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013 で許可された外部ドメインのサポートを構成する</a></span><span class="sxs-lookup"><span data-stu-id="42261-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="42261-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013 で禁止された外部ドメインのサポートを構成する</a></span><span class="sxs-lookup"><span data-stu-id="42261-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="42261-p113">このフェデレーションの種類は 1 対 1 の関係の定義です。その他のフェデレーション パートナーの検出は許可されません。各フェデレーション パートナーは明示的に構成されます。以前のバージョンでは、これは<strong>直接フェデレーション</strong>と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="42261-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="42261-159">ホスティング プロバイダーとパブリック IM プロバイダー</span><span class="sxs-lookup"><span data-stu-id="42261-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="42261-160">このフェデレーションの種類では、特定の DNS 要件は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="42261-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="42261-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></span><span class="sxs-lookup"><span data-stu-id="42261-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="42261-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="42261-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="42261-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</a></span><span class="sxs-lookup"><span data-stu-id="42261-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="42261-164">このフェデレーションの種類では、ユーザーに対して構成するサービスとホスティングプロバイダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="42261-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="42261-165">一般的には、Windows Live Messenger、Yahoo! などのパブリック IM プロバイダーの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="42261-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="42261-166">および AOL に加えて、Lync Online や Microsoft 365 などのホスティングプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="42261-166">and AOL, as well as hosting providers such as Lync Online and Microsoft 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="42261-167">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="42261-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="42261-168">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="42261-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="42261-169">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="42261-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="42261-170">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="42261-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="42261-171">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="42261-171">has been announced.</span></span> <span data-ttu-id="42261-172">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42261-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="42261-173">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="42261-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="42261-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="42261-174">Messenger.</span></span> <span data-ttu-id="42261-175">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="42261-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="42261-176">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="42261-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="42261-177">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42261-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="42261-178">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="42261-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="42261-179">すべての必要な DNS ホスト (A、または IPv6 では AAAA) と DNS SRV レコードを定義して、構成します。</span><span class="sxs-lookup"><span data-stu-id="42261-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="42261-180">Lync Server コントロールパネルを使用するか、Lync Server 管理シェルと適切なコマンドレットを使用して、ポリシーを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="42261-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="42261-181">Lync Server 管理シェルのコマンドレットの詳細については、「 [Lync server 2013 のフェデレーションと外部アクセスのコマンドレット](https://docs.microsoft.com/powershell/module/skype/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42261-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="42261-182">Lync Room System (LRS) は、フェデレーションされた Lync パートナーの開催者から送信された会議の [参加] ボタンを表示しません。</span><span class="sxs-lookup"><span data-stu-id="42261-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="42261-183">会議参加リンクが LRS に表示されるようにするには、送信側の組織は次のコマンドレットを使用して TNEF を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42261-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="42261-184">これは LRS 固有ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42261-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="42261-185">MAPI プロパティは転送されませんが、Outlook の場合は、会議の招待状を開き、会議の URL をクリックすることで、outlook および Lync は Join リンクを表示しません。</span><span class="sxs-lookup"><span data-stu-id="42261-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="42261-186">TNEFEnabled が true に設定されている場合、Exchange 2013 は OnlineMeetingExternalLink を含む MAPI プロパティを削除しません。アラームに [参加] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="42261-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42261-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="42261-187">See Also</span></span>


[<span data-ttu-id="42261-188">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</span><span class="sxs-lookup"><span data-stu-id="42261-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="42261-189">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="42261-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

