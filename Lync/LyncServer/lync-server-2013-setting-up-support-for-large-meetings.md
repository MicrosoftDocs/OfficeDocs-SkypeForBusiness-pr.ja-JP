---
title: 'Lync Server 2013: 大規模会議のサポートの設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8970d616d78cbfdafa591b58f123918cd20e0040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="9037e-102">Lync Server 2013 での大規模会議のサポートの設定</span><span class="sxs-lookup"><span data-stu-id="9037e-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9037e-103">_**トピックの最終更新日:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="9037e-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="9037e-104">最大 1000 ユーザーの大規模な会議をサポートするには、適切なトポロジの作成、会議のハードウェアおよびソフトウェア前提条件、および環境の適切な構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="9037e-105">トポロジ要件</span><span class="sxs-lookup"><span data-stu-id="9037e-105">Topology Requirements</span></span>

<span data-ttu-id="9037e-106">1つの大規模な会議には、少なくとも1台のフロントエンドサーバーと1台のバックエンドサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="9037e-107">ただし、高可用性を実現するには、バックエンドサーバーがミラー化された2台のフロントエンドサーバープールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9037e-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="9037e-108">大規模な会議を主催するユーザーには、このプールに所属するユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="9037e-109">ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="9037e-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="9037e-110">代わりに、大規模な会議にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="9037e-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="9037e-111">ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。</span><span class="sxs-lookup"><span data-stu-id="9037e-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="9037e-112">大規模な会議の設定はパフォーマンスのために最適化されているため、通常のユーザーとして使用すると、PSTN エンドポイントが関与しているときに、P2P セッションを会議に昇格できないなどの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="9037e-113">2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="9037e-114">詳細については、「 [Lync Server 2013 でのフロントエンドサーバー、インスタントメッセージング、およびプレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="9037e-115">さらに、大規模な会議に使用されているプールに対して、必要に応じて障害回復のバックアップとフェールオーバーを提供する場合は、別のデータセンターに専用プールを設定するのと同じように組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="9037e-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="9037e-116">詳細については、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="9037e-117">![大規模な会議プールの構成](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大規模な会議プールの構成")</span><span class="sxs-lookup"><span data-stu-id="9037e-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="9037e-118">トポロジについて次のような追加の注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="9037e-119">アーカイブファイルを保存するために、アーカイブサーバーが展開されて有効になっている場合は、会議コンテンツを格納するためにファイル共有が必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="9037e-120">ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9037e-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="9037e-121">ファイル共有の構成の詳細については、「 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="9037e-122">大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="9037e-123">Office Web Apps サーバーは、大規模な会議プール専用にすることも、専用プールを展開するサイトの他のプールで使用する Office Web Apps サーバーと同じにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9037e-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="9037e-124">フロントエンドサーバーの負荷分散では、HTTP トラフィック (会議コンテンツのダウンロードなど) にハードウェア負荷分散が必要になります。</span><span class="sxs-lookup"><span data-stu-id="9037e-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="9037e-125">SIP トラフィックには DNS 負荷分散をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9037e-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="9037e-126">詳細については、「 [Lync Server 2013 の負荷分散の要件」を](lync-server-2013-load-balancing-requirements.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="9037e-127">専用の大規模会議プールに対して監視サーバーを使用する場合は、Lync Server 展開のすべてのフロントエンドサーバープール間で共有されている監視サーバーとデータベースを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9037e-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="9037e-128">ハードウェアとソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="9037e-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="9037e-129">専用の大規模会議プールのサーバーのハードウェア要件は、他の Lync Server 2013 サーバーの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="9037e-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="9037e-130">ハードウェア要件の詳細については、「[Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="9037e-131">専用の大規模会議プール内のサーバーは、すべての Lync Server 2013 ソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="9037e-132">ソフトウェア要件の詳細については、次のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9037e-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="9037e-133">Lync Server 2013 でのサーバーおよびツールのオペレーティングシステムのサポート</span><span class="sxs-lookup"><span data-stu-id="9037e-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="9037e-134">Lync Server 2013 でのデータベースソフトウェアのサポート</span><span class="sxs-lookup"><span data-stu-id="9037e-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="9037e-135">Lync Server 2013 の追加ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="9037e-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="9037e-136">さらに、Lync Server 2013 と Lync Server 2013 クライアントの両方に最新の更新プログラムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="9037e-137">構成要件</span><span class="sxs-lookup"><span data-stu-id="9037e-137">Configuration Requirements</span></span>

<span data-ttu-id="9037e-p110">大規模な会議専用に新しい電話会議ポリシーを作成し、専用の大規模会議プールに所属するユーザーに電話会議ポリシーを割り当てることをお勧めします。電話会議ポリシーは次の設定を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="9037e-p110">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="9037e-p111">**MaxMeetingSize** オプションを **1000** に設定します (既定は **250** です)。</span><span class="sxs-lookup"><span data-stu-id="9037e-p111">Set the **MaxMeetingSize** option to **1000**. (The default is **250**.)</span></span>

  - <span data-ttu-id="9037e-142">**AllowLargeMeetings** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="9037e-143">**EnableAppDesktopSharing** オプションを **None** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="9037e-144">**AllowUserToScheduleMeetingsWithAppSharing** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="9037e-145">**AllowSharedNotes** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="9037e-146">**AllowAnnotations** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="9037e-147">**DisablePowerPointAnnotations** オプションを **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="9037e-148">**AllowMultiview** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="9037e-149">**EnableMultiviewJoin** オプションを **False** に設定します。</span><span class="sxs-lookup"><span data-stu-id="9037e-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9037e-150">Lync Server 2013 で1000ユーザーの大規模な会議をサポートするには、会議ポリシーの<STRONG>AllowLargeMeetings</STRONG>設定で、会議スケジューラを true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="9037e-151">この設定を true に設定すると、ユーザーが会議に参加するときに、Lync の使用状況が特大の会議に最適化されます。</span><span class="sxs-lookup"><span data-stu-id="9037e-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="9037e-152">特に、大規模な会議では、Lync は完全な会議参加者リストの初期または更新を表示しません。これは、クライアントと Lync Server 2013 の両方のパフォーマンスのボトルネックになります。</span><span class="sxs-lookup"><span data-stu-id="9037e-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="9037e-153">代わりに Lync では、ユーザーに関する情報と、会議の発表者の一覧のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9037e-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="9037e-154">Lync は、大規模会議で利用可能な参加者の総数を適切に表示します。</span><span class="sxs-lookup"><span data-stu-id="9037e-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="9037e-155">大規模な会議で不要な会議機能を無効にするには、**[最大会議サイズ]** 設定を除き、ここで指定する他のすべての電話会議ポリシー設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="9037e-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="9037e-156">さらに、専用の大規模会議プールを構成して、そのプールに所属し、会議スケジュールの管理を担当する各 Lync Server 2013 ユーザーが適切なアクセス許可を持つようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="9037e-157">これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9037e-157">To do this, do the following:</span></span>

  - <span data-ttu-id="9037e-p114">**[発表者として指定]** オプションを **[なし]** に設定します。通常は、大規模な会議のすべての参加者のうち 1 名または数名のユーザーが発表者であるため、参加者は大規模な会議で発表者として自動的には許可されないようにする必要があります。代わりに、発表者は会議のスケジュール時に明示的に指定するか、大規模な会議中に明示的に昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9037e-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="9037e-161">[**割り当てられた電話会議の種類 (既定**)] チェックボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9037e-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="9037e-162">この設定では、Lync 2013 用のオンライン会議アドインが常に開催者が割り当てた会議を使用して会議をスケジュールするかどうかを制御します。つまり、予約された会議の参加 URL とオーディオ情報は同じになります。</span><span class="sxs-lookup"><span data-stu-id="9037e-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="9037e-163">小規模グループのグループ作業のシナリオでは、すべてのユーザーが自分の会議を割り当てられているため、そのような会議の種類が適切に機能します。定数参加 URL とオーディオ情報を使用すると、会議の参加が容易になります。</span><span class="sxs-lookup"><span data-stu-id="9037e-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="9037e-164">ただし、大規模な会議のシナリオでは、大規模会議サポートスタッフが1つのユーザー資格情報セットを使用して大規模な会議をスケジュールし、会議の出席者に対して参加 Url とオーディオ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9037e-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="9037e-165">この場合、各会議への参加に異なる URL を使用する方が適しています。</span><span class="sxs-lookup"><span data-stu-id="9037e-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="9037e-166">必要でない限り **[匿名ユーザーを既定で承認する]** チェック ボックスがオンになっていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9037e-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="9037e-167">この設定は、割り当てられた会議を使用しない場合に、Lync 2013 用オンラインミーティングアドインによってスケジュールされる既定の会議アクセスの種類に影響します。</span><span class="sxs-lookup"><span data-stu-id="9037e-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="9037e-168">この設定の適切なオプションは、組織のニーズによって決まります。</span><span class="sxs-lookup"><span data-stu-id="9037e-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="9037e-169">組織のほとんどの大規模な会議が社内会議の場合は、このオプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="9037e-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="9037e-170">ほとんどの大規模な会議に外部ユーザーが参加できるようにする必要がある場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9037e-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

