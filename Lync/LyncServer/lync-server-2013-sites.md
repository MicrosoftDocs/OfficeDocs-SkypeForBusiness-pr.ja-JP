---
title: Lync Server 2013 サイト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="f70cb-102">Lync Server 2013 の Lync Server サイト</span><span class="sxs-lookup"><span data-stu-id="f70cb-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f70cb-103">_**最終更新日:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f70cb-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f70cb-104">Lync server では、Lync Server コンポーネントが含まれているネットワーク上の*サイト*を定義します。</span><span class="sxs-lookup"><span data-stu-id="f70cb-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="f70cb-105">サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。</span><span class="sxs-lookup"><span data-stu-id="f70cb-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="f70cb-106">Lync Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f70cb-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="f70cb-107">Lync Server サイトは、Active Directory サイトに対応している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f70cb-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="f70cb-108">サイトの種類</span><span class="sxs-lookup"><span data-stu-id="f70cb-108">Site Types</span></span>

<span data-ttu-id="f70cb-109">各サイトは、少なくとも1つのフロントエンドプールまたは Standard Edition サーバー、または*ブランチサイト*を含む*セントラルサイト*です。</span><span class="sxs-lookup"><span data-stu-id="f70cb-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="f70cb-110">各ブランチサイトは1つのセントラルサイトと関連付けられ、ブランチサイトのユーザーは、関連付けられたセントラルサイトのサーバーからほとんどの Lync Server 機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="f70cb-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="f70cb-111">各分岐サイトには、次のいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="f70cb-112">*Survivable Branch Appliance (SBA)*。これは、Lync server レジストラーと Windows server で実行されている仲介サーバーを備えた業界標準のブレードサーバーです。</span><span class="sxs-lookup"><span data-stu-id="f70cb-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="f70cb-113">Survivable Branch Appliance には、公衆交換電話網 (PSTN) ゲートウェイも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f70cb-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f70cb-114">Survivable Branch アプライアンスは、25 ~ 1000 ユーザーの支店向けサイト向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="f70cb-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="f70cb-115">*Survivable Branch server (SBS)*: 指定されたハードウェア要件を満たし、Lync server レジストラーと仲介サーバーソフトウェアがインストールされているサーバーです。</span><span class="sxs-lookup"><span data-stu-id="f70cb-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="f70cb-116">これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f70cb-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="f70cb-117">Survivable Branch Server は、1000と5000のユーザーを含むブランチサイト向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="f70cb-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="f70cb-118">PSTN ゲートウェイ、および必要に応じて*仲介サーバー*。</span><span class="sxs-lookup"><span data-stu-id="f70cb-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="f70cb-119">このようなサーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70cb-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="f70cb-120">セントラルサイトへの弾力性のあるワイドエリアネットワーク (WAN) リンクを備えたブランチオフィスでは、3番目のオプション (PSTN ゲートウェイ) と、必要に応じて仲介サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="f70cb-121">回復性の低いリンクを使用する支店のサイトでは、Survivable Branch Appliance または Survivable Branch Server を使用する必要があります。これにより、広域ネットワーク障害の時間の回復性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="f70cb-122">たとえば、Survivable Branch Appliance または Survivable Branch Server が展開されているサイトでは、ブランチサイトをセントラルサイトに接続している WAN が停止している場合でも、ユーザーはエンタープライズ音声通話の発信と受信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="f70cb-123">Survivable Branch Appliance、Survivable Branch Server、復元性の詳細については、計画ドキュメントの「 [Lync server 2013 でのエンタープライズボイスの回復性の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70cb-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="f70cb-124">サイトトポロジ</span><span class="sxs-lookup"><span data-stu-id="f70cb-124">Site Topologies</span></span>

<span data-ttu-id="f70cb-125">展開には、少なくとも1つのセントラルサイトを含める必要があります。また、0を複数のブランチサイトに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="f70cb-126">各ブランチサイトは、1つのセントラルサイトと関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f70cb-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="f70cb-127">セントラルサイトは、プレゼンスや会議など、ブランチサイトでローカルにホストされていない支社サイトへの Lync Server サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f70cb-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="f70cb-128">複数のサイトがある場合は、さまざまなサイトでフロントエンドプールを組み合わせて、障害回復機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f70cb-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="f70cb-129">詳細については、「 [Lync Server 2013 での高可用性と障害回復のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70cb-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f70cb-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="f70cb-130">See Also</span></span>


[<span data-ttu-id="f70cb-131">Lync Server 2013 のサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="f70cb-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="f70cb-132">Lync Server 2013 での高可用性および障害復旧のサポート</span><span class="sxs-lookup"><span data-stu-id="f70cb-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="f70cb-133">Lync Server 2013 でのエンタープライズ VoIP の復旧の計画</span><span class="sxs-lookup"><span data-stu-id="f70cb-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

