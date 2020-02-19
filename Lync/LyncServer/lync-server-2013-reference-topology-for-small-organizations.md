---
title: 小規模組織の Lync Server 2013 リファレンストポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9947fe1657551b901b6b68cc3efbbf811b261b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="15912-102">小規模な組織での Lync Server 2013 の参照トポロジ</span><span class="sxs-lookup"><span data-stu-id="15912-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15912-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="15912-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="15912-104">小規模な組織のための参照トポロジは、Lync Server を実行している3台のサーバーのみを展開することによって、堅牢で可用性の高いソリューションを展開する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="15912-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="15912-105">**小規模な組織のための参照トポロジ**</span><span class="sxs-lookup"><span data-stu-id="15912-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="15912-106">![3つのサーバーダイアグラムを展開する参照トポロジ](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "3つのサーバーダイアグラムを展開する参照トポロジ")</span><span class="sxs-lookup"><span data-stu-id="15912-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="15912-107">\*\*\*\*   この組織に展開された Standard Edition サーバーのペアは、中央サイトに4000ユーザーを持っています。</span><span class="sxs-lookup"><span data-stu-id="15912-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="15912-108">組織は2つの Standard Edition サーバーを展開し、それらを組み合わせて高可用性と障害復旧を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="15912-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="15912-109">各サーバーは2000ユーザーをホームにしていますが、すべてのユーザーに関する情報は2台のサーバー間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="15912-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="15912-110">1つもダウンした場合、管理者はこれらのユーザーをフェールオーバーして、他のサーバーによって提供されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="15912-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="15912-111">Lync Server 2013 の高可用性および障害復旧機能の詳細については、「 [Lync server 2013 の高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15912-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="15912-112">**エッジサーバーの展開をお勧めします。**   内部 IM、プレゼンス、会議にエッジサーバーを展開する必要はありませんが、小規模な展開でも使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15912-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="15912-113">組織のファイアウォールの外側にいるユーザーにサービスを提供するためにエッジサーバーを展開することで、Lync Server への投資を最大化できます。</span><span class="sxs-lookup"><span data-stu-id="15912-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="15912-114">これによって次のような利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="15912-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="15912-115">組織の独自のユーザーは、自宅で作業したり、外出中であったりする場合に、Lync Server の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="15912-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="15912-116">ユーザーは、外部ユーザーを会議に参加するように招待できます。</span><span class="sxs-lookup"><span data-stu-id="15912-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="15912-117">Lync Server も使用するパートナー、ベンダー、または顧客の組織がある場合は、その組織との*フェデレーション関係*を形成できます。</span><span class="sxs-lookup"><span data-stu-id="15912-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="15912-118">その後、Lync Server の展開によって、そのフェデレーション組織のユーザーが認識され、コラボレーションが向上します。</span><span class="sxs-lookup"><span data-stu-id="15912-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="15912-119">ユーザーは、次のいずれかまたはすべてを含むパブリック IM サービスのユーザーとインスタントメッセージを交換できます。 Windows Live\!、AOL、Yahoo、Google Talk。</span><span class="sxs-lookup"><span data-stu-id="15912-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="15912-120">これらのサービスとのパブリック IM 接続には、個別のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="15912-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="15912-121">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="15912-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="15912-122">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="15912-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="15912-123">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="15912-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="15912-124">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="15912-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="15912-125">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="15912-125">has been announced.</span></span> <span data-ttu-id="15912-126">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15912-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="15912-127">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="15912-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="15912-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="15912-128">Messenger.</span></span> <span data-ttu-id="15912-129">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="15912-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="15912-130">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="15912-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="15912-131">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="15912-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="15912-132">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="15912-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="15912-133">**ブランチサイト存続性。**   この組織では、Lync Server のエンタープライズ voip 機能のパイロットプログラムを実行しています。</span><span class="sxs-lookup"><span data-stu-id="15912-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="15912-134">一部のユーザーは、単独の音声ソリューションとして Lync Server を使用しています。</span><span class="sxs-lookup"><span data-stu-id="15912-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="15912-135">これらの音声パイロットユーザーの一部は、ブランチサイトにあります。</span><span class="sxs-lookup"><span data-stu-id="15912-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="15912-136">ブランチサイトには、中央サイトへの信頼できるワイドエリアネットワーク (WAN) リンクがありません。したがって、存続可能 Branch Appliance がそこに展開されます。</span><span class="sxs-lookup"><span data-stu-id="15912-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="15912-137">この展開により、WAN リンクがダウンした場合でも、ブランチサイトのユーザーは通話を発信および受信でき、ボイスメール機能があり、2者間のインスタントメッセージング (IM) と通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15912-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="15912-138">また、WAN リンクが使用不可能なときでも、ユーザーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="15912-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="15912-139">**Exchange UM の展開。**</span><span class="sxs-lookup"><span data-stu-id="15912-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="15912-140">この参照トポロジには、Exchange ユニファイドメッセージング (UM) サーバーが含まれています。このサーバーは、Lync Server ではなく Microsoft Exchange Server を実行します。</span><span class="sxs-lookup"><span data-stu-id="15912-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="15912-141">Exchange UM の詳細については、「計画」のドキュメントの「 [Lync server 2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「 [lync Server 2013 のホスト型 Exchange ユニファイドメッセージング統合](lync-server-2013-hosted-exchange-unified-messaging-integration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15912-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="15912-142">**Office Web Apps Server。**</span><span class="sxs-lookup"><span data-stu-id="15912-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="15912-143">Web 会議を使用するすべての組織で Office Web Apps Server または Office Web Apps Server ファームを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15912-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="15912-144">Office Web Apps サーバーを使用すると、web 会議で PowerPoint スライドを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="15912-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="15912-145">詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15912-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

