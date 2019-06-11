---
title: 'Lync Server 2013: 大規模な会議のサポートについてよく寄せられる質問'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="7f14e-102">Lync Server 2013 の大規模な会議のサポートについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7f14e-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f14e-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7f14e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7f14e-104">以下のセクションでは、大規模な会議を作成して実行する場合の一般的な質問に対する回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="7f14e-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="7f14e-105">Q: 大きな会議に参加できるユーザー数はいくつですか。</span><span class="sxs-lookup"><span data-stu-id="7f14e-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="7f14e-106">Lync Server のユーザーモデルでは、共有プール内の250ユーザー、または大規模な会議専用のプール内の1000ユーザーの制限が指定されていますが、これらの番号は、テストで使用した特定のハードウェアのセットに対してのみ、テストしたユーザーの数のみを表します。</span><span class="sxs-lookup"><span data-stu-id="7f14e-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="7f14e-107">今回のテストに基づき、最大サイズの制限をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f14e-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="7f14e-108">ただし、1つ以上の会議ポリシー (Lync Server 管理シェルで Windows PowerShell コマンドレットを使用して構成する) または Lync Server を使用して、組織内の会議に許可されている実際の参加者の数を制御することができます。コントロールパネル) を選びます。</span><span class="sxs-lookup"><span data-stu-id="7f14e-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="7f14e-109">会議ポリシーで指定した数値は、1から4294967295までの任意の32ビットの整数にすることができますが、推奨されるサイズは 2 ~ 250 のどちらかです。既定値は250です。</span><span class="sxs-lookup"><span data-stu-id="7f14e-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="7f14e-110">Q: 大規模な会議専用のプールでは、どのくらいの会議や他のワークロードを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="7f14e-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="7f14e-111">最大で1000の参加者の大規模な会議で最高のユーザーエクスペリエンスを実現するには、大規模な会議専用のプールで一度に1つの大きな会議のみをホスティングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f14e-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="7f14e-112">また、大規模な会議の進行中に、そのプールで他のワークロードを実行できないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f14e-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="7f14e-113">Q: 大規模な会議の開催者が専用のプールをホームにしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f14e-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="7f14e-114">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7f14e-114">No.</span></span> <span data-ttu-id="7f14e-115">専用プールで大規模な会議のスケジュールを管理する専用スタッフ以外のユーザーは、すべてのユーザーを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f14e-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="7f14e-116">これにより、その他のリアルタイム通信トラフィックが、プールでホストされている大規模な会議で問題が発生するのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="7f14e-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="7f14e-117">大規模な会議スケジュールのスタッフのユーザーアカウントを使用して、専用プールで大規模な会議をスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f14e-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="7f14e-118">会議の開催者 (大きな会議を要求するユーザー) のユーザーアカウントを大きな会議の発表者として追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f14e-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="7f14e-119">Q: 大規模な会議では、どのようなメディアモダリティを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="7f14e-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="7f14e-120">最大1000人のユーザーとの大規模な会議には、オーディオ、ビデオ、PowerPoint 共有、ホワイトボード、プレゼンスのポーリングなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f14e-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="7f14e-121">Q: 大規模な会議でグループインスタントメッセージング (IM) を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="7f14e-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="7f14e-122">はい。</span><span class="sxs-lookup"><span data-stu-id="7f14e-122">Yes.</span></span> <span data-ttu-id="7f14e-123">ただし、特に多くの会議参加者によって送信されるインスタントメッセージは大量であるため、IM ウィンドウでのテキストのスクロール速度の問題により、ユーザーエクスペリエンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f14e-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="7f14e-124">最大で1000のユーザーに大量のインスタントメッセージを配信すると、サーバーの負荷が大きくなり、パフォーマンスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f14e-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="7f14e-125">通常、IM は質問と回答にのみ必要です (\&q&a)。</span><span class="sxs-lookup"><span data-stu-id="7f14e-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="7f14e-126">電話からダイヤルインすることで、ユーザーは大きな会議に参加できますか?</span><span class="sxs-lookup"><span data-stu-id="7f14e-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="7f14e-127">はい。</span><span class="sxs-lookup"><span data-stu-id="7f14e-127">Yes.</span></span> <span data-ttu-id="7f14e-128">Lync Server 2013 プールが正しく展開され、ダイヤルイン会議が有効になっている場合、ユーザーはダイヤルインして大人数の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="7f14e-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="7f14e-129">このテストでは、最大 15% の1000ユーザーが、10分間に大きな会議に参加できることが示されています。</span><span class="sxs-lookup"><span data-stu-id="7f14e-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="7f14e-130">Q: 大規模な会議を仮想トポロジでホストすることはできますか?</span><span class="sxs-lookup"><span data-stu-id="7f14e-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="7f14e-131">仮想トポロジで大規模な会議をテストしていないため、仮想マシンを使用して大規模な会議専用のプールをホストすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7f14e-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

