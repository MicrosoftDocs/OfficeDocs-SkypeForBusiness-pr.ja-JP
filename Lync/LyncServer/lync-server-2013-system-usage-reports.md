---
title: 'Lync Server 2013: システム使用状況レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b020217863dd4adf04a8e91041dcae8fa078ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="4d912-102">Lync Server 2013 のシステム使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d912-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4d912-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4d912-104">システム使用状況レポートは、Lync Server によって収集された通話詳細記録 (CDR) データに基づいて、システム使用状況の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d912-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d912-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4d912-105">In This Section</span></span>

  - [<span data-ttu-id="4d912-106">Lync Server 2013 のユーザー登録レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="4d912-107">ユーザーログオンなどの登録イベントに基づいて、Lync Server 2013 の展開へのユーザー接続の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4d912-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="4d912-108">レポートでは、内部ログオンと外部ログオンの両方を表示することができます。また、Lync Server 2013 にログオンしたユーザーの数と、ログオン時に実際にサービスを使用したユーザーの数を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d912-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="4d912-109">Lync Server 2013 のピアツーピアアクティビティ概要レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="4d912-p102">インスタント メッセージング (IM)、音声、ビデオ、ファイル送信、およびアプリケーション共有のピアツーピア セッションに関する概要が示されます。ピアツーピア セッションは、関係するユーザーが 2 人だけのセッションです。</span><span class="sxs-lookup"><span data-stu-id="4d912-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="4d912-112">Lync Server 2013 の電話会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="4d912-113">すべての会議アクティビティに関する概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="4d912-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="4d912-114">会議は 3 人以上のユーザーが関係するセッションです。</span><span class="sxs-lookup"><span data-stu-id="4d912-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="4d912-115">Lync Server 2013 の PSTN 電話会議の概要レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="4d912-p104">すべての PSTN 会議に関する概要が示されます。PSTN 会議とは、少なくとも 1 人のユーザーが公衆交換電話網 (PSTN) を使用してダイヤルインする会議です。\*\* ダイヤルイン会議とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4d912-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="4d912-118">Lync Server 2013 の応答グループの使用レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="4d912-119">応答グループの使用状況の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d912-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="4d912-120">応答グループアプリケーションを使用すると、ヘルプデスクやカスタマーサポート回線などのエンティティに電話を自動的にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d912-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="4d912-121">Lync Server 2013 の IP 電話インベントリレポート</span><span class="sxs-lookup"><span data-stu-id="4d912-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="4d912-122">組織で現在使用されている IP 電話に関する情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="4d912-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="4d912-123">レポートは電話の登録とログオンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="4d912-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="4d912-124">完全な在庫とは考えないでください。</span><span class="sxs-lookup"><span data-stu-id="4d912-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="4d912-125">たとえば、少なくとも 1 回はログオンしたため、レポートにまだ含まれている電話が廃棄されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4d912-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="4d912-126">同様に、ユーザーが新しい電話で Lync Server にログオンしていないために、レポートに表示されない新しい電話がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4d912-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="4d912-127">Lync Server 2013 での通話受付管理レポート</span><span class="sxs-lookup"><span data-stu-id="4d912-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="4d912-p107">通話受付管理を使用するピアツーピア アクティビティおよび会議アクティビティの一覧が示されます。通話受付管理 (CAC) を利用すると、帯域幅の制約に基づいて、音声通話、ビデオ通話などのリアルタイム通信セッションを許可する必要があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4d912-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

