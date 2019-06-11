---
title: 小規模組織向けの Lync Server 2013 リファレンストポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="82415-102">小規模組織の Lync Server 2013 のリファレンストポロジ</span><span class="sxs-lookup"><span data-stu-id="82415-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82415-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="82415-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="82415-104">小規模組織向けのリファレンストポロジは、Lync Server を実行している3台のサーバーのみを展開することで、堅牢で可用性の高いソリューションを展開する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="82415-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="82415-105">**小規模な組織向けの関連トポロジ**</span><span class="sxs-lookup"><span data-stu-id="82415-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="82415-106">![3 つのサーバーダイアグラムを展開]している参照トポロジ(images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3 つのサーバーダイアグラムを展開")している参照トポロジ</span><span class="sxs-lookup"><span data-stu-id="82415-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="82415-107">\*\*\*\*   この組織に展開されている標準エディションのサーバーのペア (中央サイトに4000ユーザーが含まれています)。</span><span class="sxs-lookup"><span data-stu-id="82415-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="82415-108">組織では、2つの標準エディションのサーバーを展開し、それらを組み合わせて、高可用性と障害回復を実現しています。</span><span class="sxs-lookup"><span data-stu-id="82415-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="82415-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span><span class="sxs-lookup"><span data-stu-id="82415-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="82415-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span><span class="sxs-lookup"><span data-stu-id="82415-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="82415-111">Lync Server 2013 の高可用性機能と障害回復機能の詳細については、「 [Lync server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82415-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="82415-112">**エッジサーバーの展開をお勧めします。**   エッジサーバーの展開は、内部の IM、プレゼンス、会議には必要ありませんが、小規模展開でもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82415-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="82415-113">組織のファイアウォールの外側にいるユーザーにサービスを提供するために、エッジサーバーを展開することで、Lync Server への投資を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="82415-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="82415-114">その利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82415-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="82415-115">組織の独自のユーザーは、自宅で作業しているか、外出先にいる場合でも、Lync Server 機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="82415-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="82415-116">ユーザーは、外部ユーザーを会議に参加するように招待できます。</span><span class="sxs-lookup"><span data-stu-id="82415-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="82415-117">Lync Server も使用しているパートナー、ベンダー、または顧客の組織がある場合は、その組織と*フェデレーション関係*を形成することができます。</span><span class="sxs-lookup"><span data-stu-id="82415-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="82415-118">Lync Server の展開では、フェデレーションされた組織のユーザーが認識され、より効果的なコラボレーションが実現されます。</span><span class="sxs-lookup"><span data-stu-id="82415-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="82415-119">ユーザーは、次のいずれか、またはすべて、Windows Live、AOL、Yahoo\!、Google Talk などのパブリック IM サービスのユーザーとインスタントメッセージをやり取りできます。</span><span class="sxs-lookup"><span data-stu-id="82415-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="82415-120">これらのサービスとのパブリック IM 接続には、個別のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="82415-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="82415-121">2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="82415-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="82415-122">アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="82415-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="82415-123">サービスが終了するまでの Messenger。</span><span class="sxs-lookup"><span data-stu-id="82415-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="82415-124">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="82415-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="82415-125">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="82415-125">has been announced.</span></span> <span data-ttu-id="82415-126">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82415-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="82415-127">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="82415-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="82415-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="82415-128">Messenger.</span></span> <span data-ttu-id="82415-129">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</span><span class="sxs-lookup"><span data-stu-id="82415-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="82415-130">Lync は、組織間、および世界各地の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="82415-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="82415-131">Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="82415-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="82415-132">Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</span><span class="sxs-lookup"><span data-stu-id="82415-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="82415-133">**ブランチサイト survivability。**   この組織は、Lync Server のエンタープライズ voip 機能のパイロットプログラムを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82415-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="82415-134">一部のユーザーは、単独の音声ソリューションとして Lync Server を使用しています。</span><span class="sxs-lookup"><span data-stu-id="82415-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="82415-135">一部のボイスパイロットユーザーは、ブランチサイトに配置されています。</span><span class="sxs-lookup"><span data-stu-id="82415-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="82415-136">ブランチサイトには、セントラルサイトへの信頼性の高い広域ネットワーク (WAN) リンクがありません。したがって、Survivable Branch Appliance がそこに展開されます。</span><span class="sxs-lookup"><span data-stu-id="82415-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="82415-137">これが展開されていると、WAN リンクがダウンした場合でも、ブランチ サイトのユーザーは通話 (組織内の通話と PSTN 通話の両方) を発信および受信でき、ボイス メール機能は維持され、2 者間のインスタント メッセージング (IM) で通信できます。</span><span class="sxs-lookup"><span data-stu-id="82415-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="82415-138">また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="82415-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="82415-139">**Exchange UM の展開。**</span><span class="sxs-lookup"><span data-stu-id="82415-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="82415-140">このリファレンストポロジには、Lync Server ではなく Microsoft Exchange Server を実行する Exchange ユニファイドメッセージング (UM) サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82415-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="82415-141">Exchange UM の詳細については、計画ドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージングの統合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)と[lync server 2013 でのホストされた Exchange ユニファイドメッセージングの統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)の計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82415-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="82415-142">**Office Web Apps サーバー。**</span><span class="sxs-lookup"><span data-stu-id="82415-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="82415-143">Web 会議を使用するすべての組織に Office Web Apps サーバーまたは Office Web Apps サーバー ファームを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="82415-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="82415-144">Office Web Apps サーバーを使用すると、PowerPoint スライドを Web 会議に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="82415-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="82415-145">詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82415-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

