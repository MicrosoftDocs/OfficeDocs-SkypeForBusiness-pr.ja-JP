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
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="56722-102">Lync Server 2013 での Lync フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="56722-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56722-103">_**最終更新日:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="56722-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="56722-104">エッジサーバーまたはサーバーを既に展開している場合は、フェデレーションシナリオ機能を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="56722-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="56722-105">エッジサーバーをセットアップしていない場合は、最初にこの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="56722-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="56722-106">詳細については、「 [Lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。これには、展開ドキュメントの「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56722-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56722-107">XMPP フェデレーション、Lync フェデレーション、またはパブリックインスタントメッセージング接続の任意の組み合わせを設定する場合は、それらを同時に、または一度に1つずつ展開することができます。</span><span class="sxs-lookup"><span data-stu-id="56722-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="56722-108">トポロジビルダーと Lync Server 管理シェルを使用してオプションを構成する場合は、1つ、2つ、または3つのフェデレーションの種類のオプションを構成した後で、エッジサーバーで展開ウィザードを実行すると、必要な手順の数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="56722-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="56722-109">トポロジビルダーと展開ウィザードでの Lync フェデレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="56722-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="56722-110">フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="56722-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="56722-111">[Edge プール] を展開し、エッジサーバーまたはエッジサーバープールを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="56722-112">[プロパティの編集] を選びます。</span><span class="sxs-lookup"><span data-stu-id="56722-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="56722-113">[プロパティの編集] の [全般] で、[このエッジプールに対してフェデレーションを有効にする (ポート 5061)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56722-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="56722-114">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-114">Click OK.</span></span>

3.  <span data-ttu-id="56722-115">[アクション] をクリックし、[トポロジ] を選択し、[発行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56722-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="56722-116">トポロジの発行を求められたら、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="56722-117">発行が完了したら、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="56722-118">エッジサーバーで、Lync Server 展開ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="56722-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="56722-119">[Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="56722-120">[実行] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-120">Click Run Again.</span></span>

5.  <span data-ttu-id="56722-121">Lync Server コンポーネントのセットアップで、[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56722-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="56722-122">概要画面には、実行中の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56722-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="56722-123">展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="56722-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="56722-124">[完了] をクリックして展開を完了します。</span><span class="sxs-lookup"><span data-stu-id="56722-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56722-125">このオプションは選択できますが、フェデレーション用に組織内のエッジプールまたはエッジサーバーを1つだけにすることができます。</span><span class="sxs-lookup"><span data-stu-id="56722-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="56722-126">パブリックインスタントメッセージング (IM) ユーザーを含むフェデレーションユーザーによるすべてのアクセスは、同じエッジプールまたは単一エッジサーバーを通過します。</span><span class="sxs-lookup"><span data-stu-id="56722-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="56722-127">たとえば、展開に、ニューヨークに展開されたエッジプールまたは1つのエッジサーバーとロンドンに展開された1つのエッジサーバーが含まれており、ニューヨークのプールまたは単一エッジサーバーでフェデレーションサポートを有効にしている場合、フェデレーションユーザーのシグナルトラフィックはニューヨークを通過します。エッジプールまたは単一エッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="56722-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="56722-128">これは、london ユーザーとの通信でも同じですが、london フェデレーションユーザーを呼び出す London の内部ユーザーは、A/V トラフィック用に London プールまたはエッジサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="56722-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="56722-129">パートナーとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="56722-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="56722-130">別の Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2、または Office Communicator 2007 とのフェデレーションを正常に実行するには、次の表からフェデレーションの種類を選択し、DNS SRV レコード、DNS ホスト (A または AAAA) を定義します。IPv6)、およびフェデレーションの種類に適用されるポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="56722-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="56722-131">フェデレーションの種類</span><span class="sxs-lookup"><span data-stu-id="56722-131">Federation type</span></span></th>
    <th><span data-ttu-id="56722-132">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="56722-132">DNS Records</span></span></th>
    <th><span data-ttu-id="56722-133">ポリシー定義</span><span class="sxs-lookup"><span data-stu-id="56722-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="56722-134">メモ</span><span class="sxs-lookup"><span data-stu-id="56722-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="56722-135">検出されたパートナードメイン</span><span class="sxs-lookup"><span data-stu-id="56722-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="56722-136">_Tcp _sipfederationtls 形式の SRV レコードを構成します。&lt;SRV レコードの&gt;ポート値が TCP 5061 であり、<strong>このサービスを提供</strong>しているホストが sip として定義されている外部ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="56722-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="56722-137">&lt;外部ドメイン名&gt; –アクセスエッジサービスの FQDN。</span><span class="sxs-lookup"><span data-stu-id="56722-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="56722-138">SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 での microsoft edge サポートの DNS の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56722-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="56722-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="56722-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="56722-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="56722-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="56722-141">以前のバージョンでは、この種類のフェデレーションを<strong>オープン拡張フェデレーション</strong>として参照しました。</span><span class="sxs-lookup"><span data-stu-id="56722-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="56722-142">SRV レコードの作成は、この種類のフェデレーションに必要であり、他のパートナーがフェデレーションを検出できるようにするために必要です。</span><span class="sxs-lookup"><span data-stu-id="56722-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="56722-143">許可されたパートナードメイン</span><span class="sxs-lookup"><span data-stu-id="56722-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="56722-144">_Tcp _sipfederationtls 形式の SRV レコードを構成します。&lt;SRV レコードの&gt;ポート値が TCP 5061 であり、<strong>このサービスを提供</strong>しているホストが sip として定義されている外部ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="56722-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="56722-145">&lt;外部ドメイン名&gt; –アクセスエッジサービスの FQDN。</span><span class="sxs-lookup"><span data-stu-id="56722-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="56722-146">SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 での microsoft edge サポートの DNS の構成</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56722-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="56722-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="56722-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="56722-148">以前のバージョンでは、この種類のフェデレーションを<strong>拡張フェデレーション</strong>として参照しました。</span><span class="sxs-lookup"><span data-stu-id="56722-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="56722-149">SRV レコードの作成は、この種類のフェデレーションではオプションであり、他のパートナーがフェデレーションを検出できるようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56722-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="56722-150">これは、<strong>オープン拡張フェデレーション</strong>、または検出された<strong>パートナードメイン</strong>の場合です。</span><span class="sxs-lookup"><span data-stu-id="56722-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="56722-151">許可されたパートナーサーバー</span><span class="sxs-lookup"><span data-stu-id="56722-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="56722-152">ポリシーでフェデレーションパートナーとして SIP ドメイン名とパートナーエッジサーバーの FQDN を構成する</span><span class="sxs-lookup"><span data-stu-id="56722-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="56722-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="56722-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="56722-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013 での、許可された外部ドメイン向けサポートの構成</a></span><span class="sxs-lookup"><span data-stu-id="56722-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="56722-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013 での禁止された外部ドメイン向けサポートの構成</a></span><span class="sxs-lookup"><span data-stu-id="56722-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="56722-156">このフェデレーションタイプは、1対1の関係であり、他のフェデレーションパートナーを検出することはできません。</span><span class="sxs-lookup"><span data-stu-id="56722-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="56722-157">各フェデレーションパートナーは、個別に構成されます。</span><span class="sxs-lookup"><span data-stu-id="56722-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="56722-158">以前のバージョンでは、これは<strong>直接フェデレーション</strong>と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="56722-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="56722-159">ホスティングプロバイダーとパブリック IM プロバイダー</span><span class="sxs-lookup"><span data-stu-id="56722-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="56722-160">この種類のフェデレーションには特定の DNS 要件が定義されていません</span><span class="sxs-lookup"><span data-stu-id="56722-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="56722-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></span><span class="sxs-lookup"><span data-stu-id="56722-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="56722-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="56722-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="56722-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></span><span class="sxs-lookup"><span data-stu-id="56722-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="56722-164">このフェデレーションタイプでは、ユーザーに対して構成するサービスとホスティングプロバイダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="56722-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="56722-165">一般的な使用方法 Windows Live Messenger、Yahoo! などのパブリック IM プロバイダーの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56722-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="56722-166">および AOL、Lync Online、Office 365 などのホスティングプロバイダー</span><span class="sxs-lookup"><span data-stu-id="56722-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="56722-167">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="56722-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="56722-168">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="56722-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="56722-169">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="56722-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="56722-170">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="56722-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="56722-171">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="56722-171">has been announced.</span></span> <span data-ttu-id="56722-172">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56722-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="56722-173">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="56722-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="56722-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="56722-174">Messenger.</span></span> <span data-ttu-id="56722-175">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="56722-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="56722-176">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="56722-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="56722-177">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="56722-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="56722-178">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="56722-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="56722-179">必要な DNS ホスト (A または AAAA の場合は AAAA) と DNS SRV レコードを定義して構成する</span><span class="sxs-lookup"><span data-stu-id="56722-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="56722-180">Lync Server コントロールパネルを使用するか、Lync Server 管理シェルと適切なコマンドレットを使用して、ポリシーを定義して構成します。</span><span class="sxs-lookup"><span data-stu-id="56722-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="56722-181">Lync Server 管理シェルコマンドレットの詳細については、「 [Lync server 2013 のフェデレーションと外部アクセスコマンドレット](https://docs.microsoft.com/powershell/module/skype/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56722-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56722-182">Lync Room System (LRS) では、フェデレーションされた Lync パートナーの開催者によって送信された会議の [参加] ボタンは表示されません。</span><span class="sxs-lookup"><span data-stu-id="56722-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="56722-183">LRS に表示される会議の参加リンクの場合、送信側の組織は、次のコマンドレットを使用して TNEF を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56722-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="56722-184">これは LRS 固有のものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="56722-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="56722-185">また、MAPI プロパティは転送されませんが、Outlook の場合は、outlook と Lync では、会議の出席依頼を開き、会議の URL をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="56722-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="56722-186">TNEFEnabled が true に設定されている場合、Exchange 2013 は、OnlineMeetingExternalLink を含む MAPI プロパティを削除しません。また、アラームに [参加] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="56722-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56722-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="56722-187">See Also</span></span>


[<span data-ttu-id="56722-188">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</span><span class="sxs-lookup"><span data-stu-id="56722-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="56722-189">Lync Server 2013 へのフェデレーションおよび外部アクセスの管理</span><span class="sxs-lookup"><span data-stu-id="56722-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

