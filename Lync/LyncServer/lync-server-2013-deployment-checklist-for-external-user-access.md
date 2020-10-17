---
title: 'Lync Server 2013: 外部ユーザーアクセスの展開チェックリスト'
description: 'Lync Server 2013: 外部ユーザーアクセスの展開チェックリスト。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a31534d1dcf3ba4dd0bb222de682d247c9683f94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568330"
---
# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5dc09-103">Lync Server 2013 での外部ユーザーアクセスの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5dc09-103">Deployment checklist for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dc09-104">_**トピックの最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="5dc09-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="5dc09-105">境界ネットワークを展開し、外部ユーザーのサポートを実装する前に、フロントエンドプールまたは Standard Edition サーバーを含む、Microsoft Lync Server 2013 の内部サーバーを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-105">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="5dc09-106">オプションのディレクターを内部ネットワークに展開することを計画している場合は、エッジサーバーを展開する前にも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-106">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="5dc09-107">ディレクターの展開プロセスの詳細については、「計画」のドキュメントの「 [Lync Server 2013 のディレクターのシナリオ](lync-server-2013-scenarios-for-the-director.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-107">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="5dc09-108">Microsoft Lync Server 2013 には、内部サーバーとエッジサーバーの両方の計画と展開を容易にするためのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5dc09-108">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="5dc09-109">トポロジが完成したら、作成したトポロジ定義を運用環境に公開します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-109">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="5dc09-110">これを行うためには、**Domain Admins** グループと **RTCUniversalServerAdmins** グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-110">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="5dc09-111">**計画ツール**    Office Communications Server 2007 R2 には、計画ツールとエッジ計画ツールが含まれており、これを使用してトポロジ設計をガイドすることができます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-111">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="5dc09-112">Lync Server 2010 では、これら2つのツールは、計画されたユーザー数の収集、音声の要件、外部ユーザーアクセスの種類、フェデレーションオプションなどの追加機能を備えた単一の計画ツールに統合されました。</span><span class="sxs-lookup"><span data-stu-id="5dc09-112">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="5dc09-113">さらに、IP アドレス、ロードバランサーの種類、その他の境界ネットワークに関する考慮事項など、インフラストラクチャのネットワークパラメーターを計画することができます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-113">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="5dc09-114">**トポロジビルダー**    Lync Server 2013 トポロジビルダーを使用して、トポロジとコンポーネントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-114">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="5dc09-115">トポロジビルダーは、Lync Server 2013 を実行しているサーバーを展開するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="5dc09-115">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="5dc09-116">トポロジビルダーは、組織内の Lync Server 2013 を実行しているすべてのサーバーを構成するために使用される中央管理ストアに結果を発行します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-116">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="5dc09-117">トポロジビルダーを使用せずに、サーバーに Lync Server 2013 をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5dc09-117">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="5dc09-118">トポロジビルダーを実行してエッジトポロジを定義するなど、計画プロセス中にエッジトポロジを設計した場合は、その結果を使用してエッジサーバーの展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-118">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="5dc09-119">以前にエッジトポロジの作成を終了していない場合、または以前に指定した情報を変更する場合は、他の展開手順を続行する前に、トポロジビルダーの実行を終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-119">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="5dc09-120">トポロジを構築する方法の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-120">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="5dc09-121">計画ツールとトポロジビルダーの詳細については、「計画」のドキュメントの「 [Lync Server 2013 の計画プロセスの開始](lync-server-2013-beginning-the-planning-process.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-121">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="5dc09-122">次の表に、エッジ サーバーの展開プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-122">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="5dc09-123">外部ユーザーアクセスを展開する前に実行する必要のある計画の決定事項を確認するには、「 [Lync Server 2013 の外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-123">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5dc09-124">次の表には、新規展開に関する情報を掲載しています。</span><span class="sxs-lookup"><span data-stu-id="5dc09-124">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="5dc09-125">エッジサーバーを Lync Server 2010、Office Communications Server 2007 R2 または Office Communications Server の2007環境に展開している場合は、「 <A href="migration.md">Migration</A> The lync server 2013 への移行の詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-125">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="5dc09-126">Office communications server 2007、Live Communications Server 2005、Live Communications Server 2003 を含む、Office Communications Server 2007 R2 より前のバージョンの移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5dc09-126">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="5dc09-127">エッジ サーバーのパフォーマンスとセキュリティを向上させ、展開作業を円滑に行うことができるようにするため、次のベスト プラクティスに従って境界ネットワークとエッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-127">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="5dc09-128">エッジサーバーの展開は、組織内の Lync Server 2013 の動作をテストおよび検証した後にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="5dc09-128">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="5dc09-p108">エッジ サーバーは、ドメインではなく、ワークグループに展開することをお勧めします。これにより、インストールが容易になり、Active Directory ドメイン サービス (AD DS) を境界ネットワークの外側に置くことができます。境界ネットワーク上に AD DS を配置すると、セキュリティ リスクが高くなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="5dc09-p109">全体が境界ネットワーク内にあるドメインへのエッジ サーバーの追加はサポートされていますが、お勧めしません。内部ドメインに属するエッジ サーバーは、インターネットは最も信頼性が低く、境界ネットワークはインターネットよりも信頼性が高く、内部ネットワークは最も信頼性が高いという信頼されたネットワークの境界の規則に違反します。内部ドメインのメンバーであるエッジ サーバーは自動的に最も信頼性の高いネットワークに属しますが、実際にはより信頼性の低いネットワーク (境界ネットワーク) に存在するからです。</span><span class="sxs-lookup"><span data-stu-id="5dc09-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="5dc09-135">エッジ サーバーの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="5dc09-135">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dc09-136">フェーズ</span><span class="sxs-lookup"><span data-stu-id="5dc09-136">Phase</span></span></th>
<th><span data-ttu-id="5dc09-137">手順</span><span class="sxs-lookup"><span data-stu-id="5dc09-137">Steps</span></span></th>
<th><span data-ttu-id="5dc09-138">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="5dc09-138">Permissions</span></span></th>
<th><span data-ttu-id="5dc09-139">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="5dc09-139">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dc09-140">適切なエッジ トポロジの作成および適切なコンポーネントの決定。</span><span class="sxs-lookup"><span data-stu-id="5dc09-140">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5dc09-141">トポロジビルダーを実行して、エッジサーバーの設定を構成し、トポロジを作成および公開した後、Lync Server 管理シェルを使用してトポロジ構成ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-141">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5dc09-142"><strong>Domain admins</strong> グループおよび <strong>RTCUniversalServerAdmins</strong> または <strong>csadmins</strong> グループ</span><span class="sxs-lookup"><span data-stu-id="5dc09-142"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5dc09-143">ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを定義することはできますが、トポロジを公開するには <STRONG>Domain Admins</STRONG> グループおよび <STRONG>RTCUniversalServerAdmins</STRONG> グループのメンバーであるアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5dc09-143">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="5dc09-144">「展開」のドキュメントの「 <a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-144"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dc09-145">セットアップの準備。</span><span class="sxs-lookup"><span data-stu-id="5dc09-145">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5dc09-146">システムの前提条件が適合していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-146">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-147">各エッジ サーバーの、内部とパブリック側の両方のネットワーク インターフェイスの IP アドレス (IPv4 および IPv6 (使用されている場合)) を構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-147">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-148">内部および外部の DNS レコード (IPv4 および IPv6 の場合はホスト A および AAAA) を構成します。これにはエッジ サーバーとして展開されるコンピューターでの DNS サフィックスの構成も含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-148">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-p110">(オプション) パブリック証明書を作成してインストールします。証明書の取得に必要な時間は、証明書を発行する証明機関 (CA) によって異なります。現時点でこのステップを実行しない場合は、エッジ サーバーのインストール時に実行する必要があります。証明書を取得してインストールしないと、エッジ サーバー サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="5dc09-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-p111">展開が Windows Live、AOL、または Yahoo! ユーザーとの通信をサポートする場合は、パブリック IM 接続のサポートをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="5dc09-155">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5dc09-155">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="5dc09-156">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="5dc09-156">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5dc09-157">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="5dc09-157">Messenger until the service shut down date.</span></span> <span data-ttu-id="5dc09-158">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="5dc09-158">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="5dc09-159">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="5dc09-159">has been announced.</span></span> <span data-ttu-id="5dc09-160">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc09-160">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="5dc09-161">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="5dc09-161">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5dc09-162">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5dc09-162">Messenger.</span></span> <span data-ttu-id="5dc09-163">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="5dc09-163">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="5dc09-164">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="5dc09-164">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5dc09-165">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5dc09-165">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5dc09-166">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dc09-166">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="5dc09-167">展開で使用される場合は、Office Communications Server 2007、Office Communications Server 2007 R2、Lync Server 2010 パートナーに対する XMPP およびフェデレーションサポートのサポートを準備します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-167">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="5dc09-168">ファイアウォールの構成。</span><span class="sxs-lookup"><span data-stu-id="5dc09-168">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5dc09-169">組織に合わせて設定</span><span class="sxs-lookup"><span data-stu-id="5dc09-169">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="5dc09-170">「展開」のドキュメントの「 <a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-170"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dc09-171">リバース プロキシの設定。</span><span class="sxs-lookup"><span data-stu-id="5dc09-171">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5dc09-172">境界ネットワークでリバースプロキシ (Microsoft Forefront Threat Management Gateway 2010 または Microsoft インターネットセキュリティとアクセラレータ (ISA) Server Service Pack 1) を設定し、必要なパブリック証明書を取得して、リバースプロキシサーバーで web 公開ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-172">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="5dc09-173">モビリティの計画を行っており、フロントエンド プールまたは Standard Edition サーバーに Mobility Service を展開する場合は、Mobility Service 用のリバース プロキシを準備します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-173">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5dc09-174"><strong>Administrators</strong> グループまたはリバース プロキシの管理者</span><span class="sxs-lookup"><span data-stu-id="5dc09-174"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="5dc09-175">「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 用のリバースプロキシサーバーの</a>セットアップ」</span><span class="sxs-lookup"><span data-stu-id="5dc09-175"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dc09-176">ディレクターのセットアップ (オプション)。</span><span class="sxs-lookup"><span data-stu-id="5dc09-176">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5dc09-177">(オプション) 内部ネットワークにディレクターを 1 つ以上インストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-177">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5dc09-178"><strong>Administrators</strong> グループ</span><span class="sxs-lookup"><span data-stu-id="5dc09-178"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="5dc09-179">「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 でのディレクターのセットアップ</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-179"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dc09-180">エッジ サーバーの設定。</span><span class="sxs-lookup"><span data-stu-id="5dc09-180">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5dc09-181">必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-181">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-182">エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-182">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-183">各エッジサーバーに Lync Server 2013 ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-183">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-184">エッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-184">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-185">各エッジ サーバー用の証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="5dc09-185">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-186">エッジ サーバー サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-186">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5dc09-187"><strong>Administrators</strong> グループ</span><span class="sxs-lookup"><span data-stu-id="5dc09-187"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="5dc09-188">「展開」のドキュメントの「 <a href="lync-server-2013-setting-up-edge-servers.md">Lync Server 2013 でのエッジサーバーのセットアップ</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-188"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dc09-189">外部ユーザー アクセスの展開の構成。</span><span class="sxs-lookup"><span data-stu-id="5dc09-189">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5dc09-190">Lync Server コントロールパネルを使用して、次の各機能のサポートを構成します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="5dc09-190">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="5dc09-191">メディア リレー</span><span class="sxs-lookup"><span data-stu-id="5dc09-191">Media relay</span></span></p></li>
<li><p><span data-ttu-id="5dc09-192">フェデレーション ルート</span><span class="sxs-lookup"><span data-stu-id="5dc09-192">Federation route</span></span></p></li>
<li><p><span data-ttu-id="5dc09-193">リモート ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="5dc09-193">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="5dc09-194">Lync Server、Office Communications Server、Live Communications Server とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="5dc09-194">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="5dc09-195">パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="5dc09-195">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="5dc09-196">XMPP フェデレーション</span><span class="sxs-lookup"><span data-stu-id="5dc09-196">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="5dc09-197">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="5dc09-197">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="5dc09-198">(必要に応じて) リモート ユーザー アクセス、フェデレーション、パブリック IM 接続、XMPP、および匿名ユーザー サポート用のユーザー アカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-198">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5dc09-199"><strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="5dc09-199"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="5dc09-200">「展開」のドキュメントの「 <a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスのサポートの構成</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-200"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dc09-201">エッジ サーバー構成の確認。</span><span class="sxs-lookup"><span data-stu-id="5dc09-201">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5dc09-202">内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-202">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-203">外部ユーザー (リモート ユーザー、フェデレーション ドメイン内のユーザー、パブリック IM ユーザー、および匿名ユーザーなど) が、必要に応じて展開に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc09-203">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="5dc09-204">Lync Server リモート接続アナライザーを使用して構成と通信を確認する <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="5dc09-204">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="5dc09-205">構成および通信の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="5dc09-205">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="5dc09-206">レプリケーションの確認の場合は、<strong>RTCUniversalServerAdmins</strong> グループ、または <strong>CSAdministrator</strong> の役割に割り当てられているユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="5dc09-206">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="5dc09-207">ユーザー接続の確認の場合は、サポートしている外部ユーザー アクセスの各種ユーザー</span><span class="sxs-lookup"><span data-stu-id="5dc09-207">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="5dc09-208">リモート ユーザー</span><span class="sxs-lookup"><span data-stu-id="5dc09-208">Remote users</span></span></p></td>
<td><p><span data-ttu-id="5dc09-209">「展開」のドキュメントの「 <a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジ展開の確認</a>」</span><span class="sxs-lookup"><span data-stu-id="5dc09-209"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

