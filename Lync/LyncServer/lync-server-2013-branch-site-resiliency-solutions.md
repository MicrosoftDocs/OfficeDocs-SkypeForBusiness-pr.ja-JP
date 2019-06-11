---
title: 'Lync Server 2013: ブランチ サイトの復元ソリューション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="94e6f-102">Lync Server 2013 のブランチ サイトの復元ソリューション</span><span class="sxs-lookup"><span data-stu-id="94e6f-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94e6f-103">_**最終更新日:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="94e6f-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="94e6f-104">ブランチ サイトの復元を提供することには明白な利点があります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="94e6f-105">特に、セントラルサイトへの接続が失われた場合、ブランチサイトユーザーは引き続きエンタープライズ Voip サービスとボイスメールを使用できます (詳しくは、「ボイスメールの再ルーティング設定」をご覧ください。詳細については、「 [Lync Server のブランチサイトの回復性要件」を参照してください。2013](lync-server-2013-branch-site-resiliency-requirements.md))。</span><span class="sxs-lookup"><span data-stu-id="94e6f-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="94e6f-106">ただし、ユーザー数が 25 に満たないサイトでは、復元ソリューションによる十分な投資利益が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="94e6f-p102">ブランチ サイトの復元を実現するには、3 つの方法があります。次の表は、組織に最適な方法を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94e6f-109">条件</span><span class="sxs-lookup"><span data-stu-id="94e6f-109">If you…</span></span></th>
<th><span data-ttu-id="94e6f-110">推奨されるオプション</span><span class="sxs-lookup"><span data-stu-id="94e6f-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94e6f-111">ブランチ サイトに 25 から 1,000 ユーザーが所属しており、投資収益率が全面的な展開をサポートしない、またはローカル管理者がいない場合</span><span class="sxs-lookup"><span data-stu-id="94e6f-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="94e6f-112">存続可能ブランチ アプライアンス</span><span class="sxs-lookup"><span data-stu-id="94e6f-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="94e6f-113">Survivable Branch Appliance は、業界標準のブレードサーバーであり、Windows Server 2008 R2 で実行されている Lync Server レジストラーと仲介サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="94e6f-114">Survivable Branch Appliance には、公衆交換電話網 (PSTN) ゲートウェイも含まれています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="94e6f-115">認定されたサードパーティ製のデバイス (Survivable Branch Appliance (SBA) 認定プログラムで Microsoft パートナーによって開発されたもの) は、WAN の障害が発生した場合に、継続的な PSTN 接続を提供しますが、この方法では回復力がありません。これらの機能はセントラルサイトのフロントエンドサーバーに依存しているため、プレゼンスと会議が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="94e6f-116">Survivable Branch アプライアンスの詳細について&quot;は、このトピックの&quot;後半の「Survivable branch Appliance の詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94e6f-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="94e6f-117"><strong>注:</strong>Survivable Branch アプライアンスでも SIP トランクを使用することにした場合は、Survivable Branch Appliance ベンダーにお問い合わせください。組織に最も適したサービスプロバイダーについては、こちらをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94e6f-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94e6f-118">ブランチサイトでの1000と2000ユーザーの間のホスト、回復可能な WAN 接続の不足、Lync Server 管理者のトレーニング</span><span class="sxs-lookup"><span data-stu-id="94e6f-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="94e6f-119">Survivable Branch Server または2つの Survivable Branch アプライアンス。</span><span class="sxs-lookup"><span data-stu-id="94e6f-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="94e6f-120">Survivable Branch Server は、Lync Server レジストラーと仲介サーバーソフトウェアがインストールされている、Windows Server 会議の指定したハードウェア要件です。</span><span class="sxs-lookup"><span data-stu-id="94e6f-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="94e6f-121">これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="94e6f-122">Survivable ブランチサーバーの詳細について&quot;は、このトピックの&quot;後半の「Survivable branch Server の詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94e6f-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94e6f-123">最大5000ユーザー向けの音声機能だけでなく、プレゼンスと会議の機能が必要な場合、Lync Server 管理者のトレーニングを受けることができます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="94e6f-124">ブランチ サイトとしてではなく、Standard Edition サーバーが含まれるセントラル サイトとして展開します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="94e6f-125">フルスケールの Lync Server 展開では、WAN の障害が発生した場合に、継続的な PSTN 接続、回復可能なプレゼンス、会議が提供されます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="94e6f-126">このソリューションの準備について詳しくは、「 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013 向けの組織計画</a>」をご覧ください。 <a href="lync-server-2013-determining-your-system-requirements.md">lync server 2013 のシステム要件の決定</a>、 <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013 のインフラストラクチャ要件の決定</a>、計画ドキュメントのその他の関連するセクション。</span><span class="sxs-lookup"><span data-stu-id="94e6f-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="94e6f-127">復元のトポロジ</span><span class="sxs-lookup"><span data-stu-id="94e6f-127">Resiliency Topologies</span></span>

<span data-ttu-id="94e6f-128">次の図は、ブランチ サイトの復元性を確保するうえで推奨されるトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="94e6f-129">**ブランチ サイトの復元オプション**</span><span class="sxs-lookup"><span data-stu-id="94e6f-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="94e6f-130">![音声分岐の回復性オプション](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "音声分岐の回復性オプション")</span><span class="sxs-lookup"><span data-stu-id="94e6f-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="94e6f-131">存続可能ブランチ アプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="94e6f-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="94e6f-132">Lync Server Survivable Branch Appliance には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="94e6f-133">ユーザー認証、登録、通話ルーティングのためのレジストラー</span><span class="sxs-lookup"><span data-stu-id="94e6f-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="94e6f-134">レジストラーと PSTN ゲートウェイ間の信号を処理する仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="94e6f-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="94e6f-135">WAN の停止時に代替トランスポートとして PSTN に通話をルーティングする PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="94e6f-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="94e6f-136">ローカル ユーザーのデータ記憶域用 SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="94e6f-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="94e6f-137">Survivable Branch Appliance には、PSTN trunks、アナログポート、イーサネットアダプターも含まれています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="94e6f-138">セントラルサイトへのブランチサイトの WAN 接続が利用できなくなった場合、内部ブランチユーザーは引き続き Survivable Branch Appliance レジストラーに登録され、Survivable Branch Appliance 接続を使用して中断した音声サービスを取得しますを選びます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="94e6f-139">自宅またはその他のリモートの場所から接続しているブランチ サイトのユーザーは、ブランチ サイトへの WAN リンクが使用できない場合にセントラル サイトのレジストラー サーバーに登録されることができます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="94e6f-140">これらのユーザーはすべての統合コミュニケーション機能を使用できますが、唯一の例外は、ブランチ サイトへの着信通話がボイス メールに転送されることです。</span><span class="sxs-lookup"><span data-stu-id="94e6f-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="94e6f-141">WAN 接続が使用可能になると、ブランチ サイトのユーザーはすべての機能を再び使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="94e6f-142">Survivable Branch Appliance へのフェールオーバーもサービスの復元でも、IT 管理者が存在している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94e6f-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="94e6f-143">Lync Server は、ブランチサイトで最大2つの Survivable ブランチアプライアンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="94e6f-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94e6f-144">Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="94e6f-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="94e6f-145">存続可能ブランチ アプライアンスの展開の概要</span><span class="sxs-lookup"><span data-stu-id="94e6f-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="94e6f-146">Survivable Branch Appliance は、Microsoft との提携により、元の機器メーカーによって製造され、付加価値の小売店に代わって展開されます。</span><span class="sxs-lookup"><span data-stu-id="94e6f-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="94e6f-147">この展開は、Lync Server がセントラルサイトに展開されている場合、またはブランチサイトへの WAN 接続が行われていて、ブランチサイトユーザーがエンタープライズ Voip を有効にしている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="94e6f-148">これらのフェーズの詳細については、「 [Survivable Branch Appliance または server を Lync Server 2013 に](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94e6f-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94e6f-149">段階</span><span class="sxs-lookup"><span data-stu-id="94e6f-149">Phase</span></span></th>
<th><span data-ttu-id="94e6f-150">ステップ</span><span class="sxs-lookup"><span data-stu-id="94e6f-150">Steps</span></span></th>
<th><span data-ttu-id="94e6f-151">ユーザー権限</span><span class="sxs-lookup"><span data-stu-id="94e6f-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94e6f-152">Survivable Branch Appliance の Active Directory ドメインサービスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="94e6f-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="94e6f-153"><strong>セントラル サイトにおいて:</strong></span><span class="sxs-lookup"><span data-stu-id="94e6f-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="94e6f-154">ブランチサイトに Survivable Branch Appliance をインストールしてアクティブ化する技術者のドメインユーザーアカウント (またはエンタープライズ id) を作成します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-155">Active Directory Domain Services で、Survivable Branch Appliance の完全修飾ドメイン名 (FQDN) が適用されたコンピューターアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-156">Topology Builder で、Survivable Branch Appliance を作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="94e6f-157">技術者のユーザー アカウントは、RTCUniversalSBATechnicians のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="94e6f-158">Survivable Branch アプライアンスは、RTCSBAUniversalServices グループに属している必要があります。これは、Topology Builder を使用すると自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94e6f-159">Survivable Branch アプライアンスをインストールしてアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="94e6f-160"><strong>ブランチ サイトにおいて:</strong></span><span class="sxs-lookup"><span data-stu-id="94e6f-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="94e6f-161">Survivable Branch アプライアンスをイーサネットポートと PSTN ポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-162">Survivable Branch Appliance を起動します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-163">セントラルサイトで Survivable Branch Appliance 用に作成したドメインユーザーアカウントを使用して、Survivable Branch Appliance をドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="94e6f-164">コンピューター アカウントで作成された FQDN に一致する FQDN と IP アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-165">OEM のユーザーインターフェイスを使用して、Survivable Branch Appliance を構成します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="94e6f-166">PSTN 接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="94e6f-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="94e6f-167">技術者のユーザー アカウントは、RTCUniversalSBATechnicians のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e6f-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="94e6f-168">存続可能ブランチ サーバーの詳細</span><span class="sxs-lookup"><span data-stu-id="94e6f-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="94e6f-169">[Topology Builder] で、ブランチサイトを作成し、そのサイトに Survivable Branch Server を追加してから、役割をインストールするコンピューターで Lync Server Deployment ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="94e6f-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94e6f-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="94e6f-170">See Also</span></span>


[<span data-ttu-id="94e6f-171">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="94e6f-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

