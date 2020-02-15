---
title: Lync Server 2013 ストレスおよびパフォーマンスツールの FAQ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9de9555f9f009558b700a32ca6e58059eb5ea990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="d9cfe-102">Lync Server 2013 ストレスおよびパフォーマンスツールの FAQ</span><span class="sxs-lookup"><span data-stu-id="d9cfe-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9cfe-103">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d9cfe-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d9cfe-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d9cfe-104">Frequently Asked Questions</span></span>

<span data-ttu-id="d9cfe-105">ここでは、Lync Server 2013 ストレスおよびパフォーマンスツールに関してよく寄せられる質問をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="d9cfe-106">LyncPerfTool を運用環境で実行できますか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="d9cfe-107">この方法はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-107">We do not recommend this.</span></span> <span data-ttu-id="d9cfe-108">このツールは、サーバーのパフォーマンス、セキュリティ、およびユーザーの操作に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="d9cfe-109">ユーザーが初めてログオンしたとき。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="d9cfe-110">サーバーがこのような高負荷で実行されている理由</span><span class="sxs-lookup"><span data-stu-id="d9cfe-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="d9cfe-111">ユーザーが初めてログオンしたときに、追加の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="d9cfe-112">その結果、Microsoft SQL Server バックエンドサーバーのパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="d9cfe-113">結果を測定する前に、すべてのユーザーにログを記録する短時間のテストを実行してから、クライアントを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="d9cfe-114">1秒あたり12人を超える同時ユーザーログオンセッションはサポートしていませんが、ハードウェア構成によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="d9cfe-115">クライアントのメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-115">My clients are running out of memory.</span></span> <span data-ttu-id="d9cfe-116">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-116">What should I do?</span></span>

<span data-ttu-id="d9cfe-117">クライアントのメモリが不足している場合は、コンピューターごとのユーザー数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="d9cfe-118">クライアントは、常に100% の CPU を消費します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="d9cfe-119">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-119">What should I do?</span></span>

<span data-ttu-id="d9cfe-120">すべてのユーザーがログオンした後、クライアントが非常に高い CPU を使用して実行されている場合は、コンピューターごとのユーザー数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="d9cfe-121">高 CPU スパイクを使用できますが、維持されている場合は負荷を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="d9cfe-122">サーバー自体でツールを実行することはできますか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="d9cfe-123">いいえ。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-123">No.</span></span> <span data-ttu-id="d9cfe-124">このシナリオはサポートされておらず、バイナリの不一致が原因で失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="d9cfe-125">また、ポイントはサーバー上のリソース消費を測定することなので、ツールを実行すると、測定値は無意味になります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="d9cfe-126">仮想サーバー上または Microsoft Hyper-v Server 2008/2012 上で LyncPerfTool を実行できますか。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="d9cfe-127">はい。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="d9cfe-128">MPOP の意味</span><span class="sxs-lookup"><span data-stu-id="d9cfe-128">What does MPOP mean?</span></span>

<span data-ttu-id="d9cfe-129">MPOP は、複数のプレゼンスポイントを表します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="d9cfe-130">これは、ユーザーが複数のコンピューターから Lync 2013 にログオンしているシナリオをシミュレートすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="d9cfe-131">LyncPerfTool では、各エンドポイントが既定のプロファイルを使用しています (つまり、プロファイルが2つのプレゼンス間で分割されていないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="d9cfe-132">LyncPerfTool を開始しましたが、何も起きていません。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="d9cfe-133">どうなっているのですか。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-133">What’s going on?</span></span>

<span data-ttu-id="d9cfe-134">ユーザーが接続しているかどうかを確認するには、クライアントの [アクティブなエンドポイントの合計数」カウンターを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="d9cfe-135">ユーザーが接続していない場合は、Lync Server 2013 の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="d9cfe-136">通常、この問題は、サーバー名、ユーザーのプレフィックス、またはパスワードが正しくないことが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="d9cfe-137">外部クライアントでは、TargetServer 値としてアクセスプロキシを指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="d9cfe-138">構成ファイルのポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="d9cfe-139">問題が発生していることをどのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-139">How do I know something is happening?</span></span>

<span data-ttu-id="d9cfe-140">さまざまな LyncPerfTool パフォーマンスカウンターは、ユーザーが接続し、アクションを実行しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="d9cfe-141">ただし、Lync 2013 を使用して目的のアクションを実行することによって、アカウントの1つにログオンすることが簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="d9cfe-142">Live Communications Server 2007 R2 容量計画ツールまたは Lync Server 2010 がインストールされている。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="d9cfe-143">これでよろしいですか。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-143">Is that OK?</span></span>

<span data-ttu-id="d9cfe-144">いいえ。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-144">No.</span></span> <span data-ttu-id="d9cfe-145">相互運用性の問題があるため、この製品の以前のバージョンをすべてアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="d9cfe-146">ストレスとパフォーマンスのツールによって、CAA 呼び出し情報サーバーのトポロジはセットアップされますか。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="d9cfe-147">いいえ。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-147">No.</span></span> <span data-ttu-id="d9cfe-148">このツールは、ユーザー、連絡先、および配布リストを作成し、ユーザーの負荷をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="d9cfe-149">ツールがサポートする最大ユーザー数はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="d9cfe-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="d9cfe-150">これらのツールを使用して、合計8万のユーザーと実行される、3万ユーザーを合計してテストしました。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="d9cfe-151">使用可能なクライアントとサーバーのハードウェアに応じて、技術上の制限により、より高い価値を実現できるということは、最大で12万のユーザーを推奨します。</span><span class="sxs-lookup"><span data-stu-id="d9cfe-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

