---
title: 'Lync Server 2013: 大規模会議のサポートに関する FAQ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="167e5-102">Lync Server 2013 の大規模会議のサポートに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="167e5-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="167e5-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="167e5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="167e5-104">以下のセクションは、大規模な会議の作成と実行について、よく尋ねられる質問とその回答です。</span><span class="sxs-lookup"><span data-stu-id="167e5-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="167e5-105">Q: 大規模な会議には、最大何名のユーザーが参加できますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="167e5-106">Lync Server ユーザーモデルでは、共有プールのユーザー数が250の場合、または大規模な会議専用のプールでは1000ユーザーの制限が指定されていますが、これらの番号は、テストで使用した特定のハードウェアセットに対してのみ、テストしたユーザーの数のみを表します。</span><span class="sxs-lookup"><span data-stu-id="167e5-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="167e5-107">テストに基づいて、これらの制限を最大サイズにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="167e5-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="167e5-108">ただし、Lync Server 管理シェルで Windows PowerShell コマンドレットを使用して構成するか、Lync Server を使用して構成する会議ポリシーを構成することによって、組織内の会議に許可される実際の参加者数を制御します。コントロールパネル)。</span><span class="sxs-lookup"><span data-stu-id="167e5-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="167e5-109">電話会議ポリシーで指定する番号は、1から4294967295までの任意の32ビットの整数にすることができますが、推奨サイズは 2 ~ 250 の参加者を含みます。既定値は250です。</span><span class="sxs-lookup"><span data-stu-id="167e5-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="167e5-110">Q: 大規模な会議専用のプールで持つことができる会議またはその他のワークロードの最大数はいくつですか?</span><span class="sxs-lookup"><span data-stu-id="167e5-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="167e5-p102">最大 1000 名の参加者がいる大規模な会議では、最良のユーザー エクスペリエンスを保証できるよう、大規模な会議専用のプールで、一度に 1 つの大規模な会議ホスティングのみを推奨します。また大規模な会議の進行中、そのプールで、その他すべてのワークロードを実行しないことを推奨します。</span><span class="sxs-lookup"><span data-stu-id="167e5-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="167e5-113">Q: 大規模な会議の開催者は、その大規模な会議専用のプールに所属する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="167e5-p103">いいえ。その専用プールで大規模な会議のスケジュール設定を管理する専任スタッフ以外のすべてのユーザーを所属させないことを推奨します。これにより、その他のリアルタイム通信トラフィックが、プールでホストされる大規模な会議に問題を起こすことを防げます。専用プールで大規模な会議をスケジュール設定する場合は、大規模な会議スケジュール設定スタッフのユーザー アカウントを使用する必要があります。会議の開催者 (大規模な会議を要求するユーザー) のユーザー アカウントを、大規模な会議の発表者として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="167e5-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="167e5-119">Q:大規模な会議ではどのようなメディア モダリティを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="167e5-120">最大 1000 ユーザーの大規模な会議では、オーディオ、ビデオ、PowerPoint 共有、ホワイトボード、およびプレゼンス ポーリングを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="167e5-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="167e5-121">Q: 大規模な会議でグループインスタント メッセージング (IM) を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="167e5-122">はい。</span><span class="sxs-lookup"><span data-stu-id="167e5-122">Yes.</span></span> <span data-ttu-id="167e5-123">しかし、多数のインスタント メッセージが (特に、多数の会議の参加者によって) 送信されたとき、IM ウィンドウですばやくテキストをスクロールする際に問題が発生し、ユーザー エクスペリエンスに悪影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="167e5-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="167e5-124">また、最大 1000 ユーザーが大量のインスタント メッセージを送信すると、サーバーに大きな負荷がかかり、パフォーマンスに悪影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="167e5-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="167e5-125">一般的に、IM は質問と回答にのみ必要です\&(Q As)。</span><span class="sxs-lookup"><span data-stu-id="167e5-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="167e5-126">ユーザーは、電話からダイヤルインすることにより、大規模な会議に参加できますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="167e5-127">はい。</span><span class="sxs-lookup"><span data-stu-id="167e5-127">Yes.</span></span> <span data-ttu-id="167e5-128">Lync Server 2013 プールが適切に展開され、ダイヤルイン会議が有効になっている場合、ユーザーはダイヤルインすることにより大規模な会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="167e5-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="167e5-129">当社のテストでは、1000 ユーザーのうち 15% が 10 分間にわたって大規模な会議に参加できることが示されています。</span><span class="sxs-lookup"><span data-stu-id="167e5-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="167e5-130">Q: 仮想トポロジで大規模な会議をホストできますか?</span><span class="sxs-lookup"><span data-stu-id="167e5-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="167e5-131">当社は、仮想トポロジでの大規模な会議はテストしていません。このことから、当社は大規模な会議の専用プールをホストする目的で仮想マシンを使用することはサポートしません。</span><span class="sxs-lookup"><span data-stu-id="167e5-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

