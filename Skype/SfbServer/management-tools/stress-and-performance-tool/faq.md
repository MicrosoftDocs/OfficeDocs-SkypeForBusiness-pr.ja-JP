---
title: Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 応力とパフォーマンスツールについてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスツールとパフォーマンスツールの実行時に表示される可能性がある behaviours の明確化に役立ちます。.
ms.openlocfilehash: 36bb3e05751bd69b747d84fa563347b29362ddd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299710"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="11aed-103">Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="11aed-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="11aed-104">Skype for Business 2015 応力とパフォーマンスツールについてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスツールとパフォーマンスツールの実行時に表示される可能性がある behaviours の明確化に役立ちます。.</span><span class="sxs-lookup"><span data-stu-id="11aed-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="11aed-105">この FAQ では、Skype for Business Server 2015 のストレスとパフォーマンスツールについてよく寄せられる質問の一部について説明し、トラブルシューティングやツール構成の選択肢について説明します。</span><span class="sxs-lookup"><span data-stu-id="11aed-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="11aed-106">LyncPerfTool を運用環境で実行できますか?</span><span class="sxs-lookup"><span data-stu-id="11aed-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="11aed-107">この方法はお勧めでき**ません**。</span><span class="sxs-lookup"><span data-stu-id="11aed-107">This is **not** recommended.</span></span> <span data-ttu-id="11aed-108">このツールは、プロダクションサーバーのパフォーマンス、セキュリティ、およびエンドユーザーエクスペリエンスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="11aed-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="11aed-109">ユーザーを初めてログインします。</span><span class="sxs-lookup"><span data-stu-id="11aed-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="11aed-110">サーバーで高負荷が発生しているのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="11aed-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="11aed-111">ユーザーが初めてログオンしたときは、バックグラウンドで追加の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="11aed-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="11aed-112">その結果、Microsoft SQL Server バックエンドサーバーのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11aed-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="11aed-113">すべてのユーザーに対してログを記録する短いテストを実行してから、ツールを使用して結果の測定を開始する前に、クライアントを再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="11aed-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="11aed-114">Skype for Business Server は1秒あたり12回の同時ユーザーログオンセッションをサポートしていませんが、サーバーで処理できる実際の番号はハードウェア構成によって異なり、サポートされている値よりも低い場合があります。</span><span class="sxs-lookup"><span data-stu-id="11aed-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="11aed-115">クライアントでメモリが不足しています。</span><span class="sxs-lookup"><span data-stu-id="11aed-115">My clients are running out of memory!</span></span> <span data-ttu-id="11aed-116">どうしたらいいでしょう。</span><span class="sxs-lookup"><span data-stu-id="11aed-116">What should I do?</span></span>

<span data-ttu-id="11aed-117">クライアントでメモリが不足している場合は、Skype for Business Server フロントエンドプールごとにログオンしているユーザー数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="11aed-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="11aed-118">問題が永続的である場合は、フロントエンドプールのスケールを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="11aed-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="11aed-119">Skype for Business サーバー自体でこのツールを実行することはできますか?</span><span class="sxs-lookup"><span data-stu-id="11aed-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="11aed-120">この操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="11aed-120">You shouldn't do that.</span></span> <span data-ttu-id="11aed-121">このシナリオは、バイナリの不一致が原因で失敗する可能性があります。また、目標がサーバー上のリソース消費量を測定するためであるため、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="11aed-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="11aed-122">実際にツールを実行していると、サーバーのパフォーマンスに影響し、データと測定値が無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="11aed-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="11aed-123">仮想サーバーまたは Microsoft Hyper-v Server 2008/2012 で LyncPerfTool を実行できますか?</span><span class="sxs-lookup"><span data-stu-id="11aed-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="11aed-124">はいできますよ。</span><span class="sxs-lookup"><span data-stu-id="11aed-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="11aed-125">MPOP は何を意味していますか?</span><span class="sxs-lookup"><span data-stu-id="11aed-125">What does MPOP mean?</span></span>

<span data-ttu-id="11aed-126">MPOP は、"複数のポイントを持つ" と言う短い方法です。</span><span class="sxs-lookup"><span data-stu-id="11aed-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="11aed-127">MPOP は、ユーザーが複数のコンピューターまたはデバイスから Skype for Business 2015 クライアントにログオンしているシナリオをシミュレートすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="11aed-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="11aed-128">LyncPerfTool では、各エンドポイントで既定のプロファイルが使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11aed-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="11aed-129">つまり、プロファイルが2つのプレゼンス間で分割されることはありません。</span><span class="sxs-lookup"><span data-stu-id="11aed-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="11aed-130">LyncPerfTool を開始しましたが、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="11aed-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="11aed-131">どうなっているのですか。</span><span class="sxs-lookup"><span data-stu-id="11aed-131">What's going on?</span></span>

<span data-ttu-id="11aed-132">サーバー上のアクティブなエンドポイントの合計カウンターを確認して、ユーザーが接続しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="11aed-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="11aed-133">ユーザーが接続していない場合は、Skype for Business Server 2015 の構成を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11aed-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="11aed-134">通常発生する問題は、サーバー名、ユーザーのプレフィックス、またはパスワードが間違っていることが原因です。</span><span class="sxs-lookup"><span data-stu-id="11aed-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="11aed-135">外部クライアントでは、アクセスプロキシと TargetServer の値を指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11aed-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="11aed-136">構成ファイルでポート番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="11aed-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="11aed-137">何らかの測定が行われているかどうかを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="11aed-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="11aed-138">ユーザーが接続して操作を実行しているかどうかを示す LyncPerfTool のパフォーマンスカウンターはありますが、操作が測定されているかどうかを確認するには、Skype for Business 2015 クライアントを使用しているアカウントにログオンして実行する方法が最も簡単です。操作を自分で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="11aed-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="11aed-139">結果を確認して、測定値が取得されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="11aed-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="11aed-140">Lync Server 2010 キャパシティプランニングツールと Lync Server 2013 キャパシティプランニングツールがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="11aed-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="11aed-141">どうしたらいいですか?</span><span class="sxs-lookup"><span data-stu-id="11aed-141">Is that okay?</span></span>

 <span data-ttu-id="11aed-142">これらのツールには相互運用性の問題があります。</span><span class="sxs-lookup"><span data-stu-id="11aed-142">These tools have interoperability issues!</span></span> <span data-ttu-id="11aed-143">Skype for Business Server 2015 のストレスとパフォーマンスのツールから有効なデータを取得するには、これらのツールの以前のバージョンをすべてアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11aed-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="11aed-144">ストレスとパフォーマンスのツールで CAA を Call Information server topology をセットアップしますか?</span><span class="sxs-lookup"><span data-stu-id="11aed-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="11aed-145">いいえ、ツールでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="11aed-145">No, the tools won't do this.</span></span> <span data-ttu-id="11aed-146">このツールでは、ユーザー、連絡先、配布リストのみを作成して、ユーザーロードをシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="11aed-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="11aed-147">ツールでサポートされるユーザーの最大数は何人ですか?</span><span class="sxs-lookup"><span data-stu-id="11aed-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="11aed-148">テストでは、最大8万ユーザーを作成し、これらのツールを実行する合計3万ユーザーを実行しました。</span><span class="sxs-lookup"><span data-stu-id="11aed-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="11aed-149">最大で12万のユーザーを対象としていますが、技術的な制限により高い値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="11aed-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="11aed-150">これらの値は、環境内のサーバーとハードウェアに依存していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="11aed-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

