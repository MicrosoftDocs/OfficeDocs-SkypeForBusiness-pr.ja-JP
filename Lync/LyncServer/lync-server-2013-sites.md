---
title: Lync Server 2013 サイト
description: Lync Server 2013 サイト。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59739c5a81fca1f1f3ab5c1b83a23f0be0a5ee2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558963"
---
# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="085c0-103">Lync server 2013 の lync Server サイト</span><span class="sxs-lookup"><span data-stu-id="085c0-103">Lync Server sites for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="085c0-104">_**トピックの最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="085c0-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="085c0-105">Lync Server では、Lync Server コンポーネントを含むネットワーク上の *サイト* を定義します。</span><span class="sxs-lookup"><span data-stu-id="085c0-105">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="085c0-106">サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="085c0-106">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="085c0-107">Lync Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="085c0-107">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="085c0-108">Lync Server サイトは、Active Directory サイトに対応する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="085c0-108">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="085c0-109">サイトの種類</span><span class="sxs-lookup"><span data-stu-id="085c0-109">Site Types</span></span>

<span data-ttu-id="085c0-110">各サイトは、少なくとも1つのフロントエンドプールまたは Standard Edition サーバー、または*ブランチサイト*を含む*セントラルサイト*です。</span><span class="sxs-lookup"><span data-stu-id="085c0-110">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="085c0-111">各ブランチサイトは1つの中央サイトに関連付けられ、ブランチサイトのユーザーは、関連付けられた中央サイトのサーバーからほとんどの Lync Server 機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="085c0-111">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="085c0-112">各ブランチ サイトは、次のいずれかを含みます。</span><span class="sxs-lookup"><span data-stu-id="085c0-112">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="085c0-113">*存続可能 Branch Appliance (SBA)*。これは、Lync server レジストラーと、Windows server を実行している仲介サーバーを備えた業界標準のブレードサーバーです。</span><span class="sxs-lookup"><span data-stu-id="085c0-113">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="085c0-114">存続可能ブランチアプライアンスには、公衆交換電話網 (PSTN) ゲートウェイも搭載されています。</span><span class="sxs-lookup"><span data-stu-id="085c0-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="085c0-115">存続可能 Branch アプライアンスは、ユーザーが 25 ~ 1000 のブランチサイト向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="085c0-115">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="085c0-116">*存続可能ブランチサーバー (SBS)*。これは、指定されたハードウェア要件を満たし、Lync server レジストラーおよび仲介サーバーソフトウェアがインストールされている、Windows server を実行しているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="085c0-116">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="085c0-117">これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="085c0-117">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="085c0-118">存続可能ブランチサーバーは、1000と5000のユーザーが関係するブランチサイト用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="085c0-118">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="085c0-119">PSTN ゲートウェイ、およびオプションの仲介サーバー\*\*。</span><span class="sxs-lookup"><span data-stu-id="085c0-119">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="085c0-120">このおよびその他のサーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="085c0-120">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="085c0-121">セントラル サイトへの復元力のあるワイド エリア ネットワーク (WAN) リンクを備えるブランチ オフィスでは、3 番目のオプションである PSTN ゲートウェイを (必要に応じて仲介サーバーも) 使用できます。</span><span class="sxs-lookup"><span data-stu-id="085c0-121">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="085c0-122">あまり回復不能なリンクを持つ支社のサイトでは、存続可能 Branch Appliance または存続可能ブランチサーバーを使用する必要があります。これにより、広域ネットワーク障害の時間内で復元性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="085c0-122">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="085c0-123">たとえば、存続可能 Branch Appliance または存続可能 Branch Server が展開されているサイトでは、ブランチサイトを中央サイトに接続している WAN がダウンしている場合でも、ユーザーはエンタープライズ Voip 通話を確立したり、受信したりできます。</span><span class="sxs-lookup"><span data-stu-id="085c0-123">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="085c0-124">存続可能 Branch Appliance、存続可能 Branch Server、および復元の詳細については、「計画」のドキュメントの「 [planning For Enterprise Voice 弾力性 In Lync server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="085c0-124">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="085c0-125">サイト トポロジ</span><span class="sxs-lookup"><span data-stu-id="085c0-125">Site Topologies</span></span>

<span data-ttu-id="085c0-126">展開には、少なくとも1つの中央サイトが含まれている必要があります。また、ゼロには多数のブランチサイトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="085c0-126">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="085c0-127">各ブランチサイトは、1つの中央サイトに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="085c0-127">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="085c0-128">中央サイトは、プレゼンスや会議など、ブランチサイトでローカルにホストされていないブランチサイトに Lync Server サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="085c0-128">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="085c0-129">複数のサイトがある場合は、異なるサイトのフロントエンド プールどうしをペアリングして、障害復旧の機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="085c0-129">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="085c0-130">詳細については、「 [Lync Server 2013 の高可用性と障害復旧のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="085c0-130">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="085c0-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="085c0-131">See Also</span></span>


[<span data-ttu-id="085c0-132">Lync Server 2013 のサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="085c0-132">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="085c0-133">Lync Server 2013 での高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="085c0-133">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="085c0-134">Lync Server 2013 でのエンタープライズ Voip の復元の計画</span><span class="sxs-lookup"><span data-stu-id="085c0-134">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

