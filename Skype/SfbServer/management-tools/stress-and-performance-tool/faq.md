---
title: Skype for Business Server 2015 Stress and Performance Tool の FAQ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 Stress and Performance Tool についてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、Stress and Performance ツールの実行中に発生する可能性がある動作の明確化に役立ちます。
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814967"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="12f82-103">Skype for Business Server 2015 Stress and Performance Tool の FAQ</span><span class="sxs-lookup"><span data-stu-id="12f82-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="12f82-104">Skype for Business 2015 Stress and Performance Tool についてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、Stress and Performance ツールの実行中に発生する可能性がある動作の明確化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12f82-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="12f82-105">この FAQ では、Skype for Business Server 2015 Stress and Performance ツールに関してよく寄せられる質問について説明し、トラブルシューティングやツール構成の選択に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="12f82-106">実稼働環境でLyncPerfTool.exe実行できますか。</span><span class="sxs-lookup"><span data-stu-id="12f82-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="12f82-107">これはお **勧め** しません。</span><span class="sxs-lookup"><span data-stu-id="12f82-107">This is **not** recommended.</span></span> <span data-ttu-id="12f82-108">このツールは、実稼働サーバーのパフォーマンス、セキュリティ、およびエンド ユーザー エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="12f82-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="12f82-109">ユーザーを初めてログオンします。</span><span class="sxs-lookup"><span data-stu-id="12f82-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="12f82-110">サーバーで高負荷が実行されている理由</span><span class="sxs-lookup"><span data-stu-id="12f82-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="12f82-111">ユーザーが初めてログオンすると、バックグラウンドで追加の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="12f82-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="12f82-112">その結果、バック エンド サーバー Microsoft SQL Serverパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="12f82-113">すべてのユーザーにログオンする短いテストを実行してから、ツールで結果の測定を開始する前にクライアントを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="12f82-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="12f82-114">Skype for Business Server は、1 秒あたり 12 を超える同時ユーザー ログオン セッションをサポートしませんが、サーバーで処理できる実際の数はハードウェア構成によって異なり、サポートされる値よりも小さい場合があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="12f82-115">クライアントのメモリが使い切っています。</span><span class="sxs-lookup"><span data-stu-id="12f82-115">My clients are running out of memory!</span></span> <span data-ttu-id="12f82-116">どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="12f82-116">What should I do?</span></span>

<span data-ttu-id="12f82-117">クライアントのメモリが使い切っている場合は、Skype for Business Server フロント エンド プールごとにログオンしているユーザーの数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="12f82-118">問題が解決しない場合は、フロントエンド プールをスケール アウトする方法も選択できます。</span><span class="sxs-lookup"><span data-stu-id="12f82-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="12f82-119">このツールを Skype for Business サーバー上で実行できますか。</span><span class="sxs-lookup"><span data-stu-id="12f82-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="12f82-120">この操作は行わない方が良い。</span><span class="sxs-lookup"><span data-stu-id="12f82-120">You shouldn't do that.</span></span> <span data-ttu-id="12f82-121">このシナリオは、バイナリの不一致が原因で失敗する可能性があります。また、サーバー上のリソース消費を測定する目的のため、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12f82-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="12f82-122">実際にツールを実行すると、サーバーのパフォーマンスに影響を与え、データと測定値が無効になります。</span><span class="sxs-lookup"><span data-stu-id="12f82-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="12f82-123">仮想サーバー上LyncPerfTool.exe Microsoft Hyper-V Server 2008/2012で実行できますか。</span><span class="sxs-lookup"><span data-stu-id="12f82-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="12f82-124">はいできますよ。</span><span class="sxs-lookup"><span data-stu-id="12f82-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="12f82-125">MPOP の意味</span><span class="sxs-lookup"><span data-stu-id="12f82-125">What does MPOP mean?</span></span>

<span data-ttu-id="12f82-126">MPOP は、"複数のプレゼンス ポイント" を示す短縮された方法です。</span><span class="sxs-lookup"><span data-stu-id="12f82-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="12f82-127">MPOP は、ユーザーが複数のコンピューターまたはデバイスから Skype for Business 2015 クライアントにログオンするシナリオをシミュレートすることを意図しています。</span><span class="sxs-lookup"><span data-stu-id="12f82-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="12f82-128">この場合、各エンドポイントLyncPerfTool.exe既定のプロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="12f82-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="12f82-129">つまり、プロファイルは 2 つのプレゼンス ポイント間で分割されるのではないのです。</span><span class="sxs-lookup"><span data-stu-id="12f82-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="12f82-130">私はLyncPerfTool.exe開始しましたが、何も起こっていません。</span><span class="sxs-lookup"><span data-stu-id="12f82-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="12f82-131">何が起こっているのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="12f82-131">What's going on?</span></span>

<span data-ttu-id="12f82-132">ユーザーが接続している場合は、サーバーの [アクティブなエンドポイントの合計] カウンターを確認します。</span><span class="sxs-lookup"><span data-stu-id="12f82-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="12f82-133">ユーザーが接続していない場合は、Skype for Business Server 2015 の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="12f82-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="12f82-134">通常、表示される問題は、サーバー名、ユーザー プレフィックス、またはパスワードの 1 つが正しくないので発生します。</span><span class="sxs-lookup"><span data-stu-id="12f82-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="12f82-135">外部クライアントでは、アクセス プロキシと TargetServer の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="12f82-136">構成ファイルのポート番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="12f82-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="12f82-137">何かが測定されているのを確認する方法</span><span class="sxs-lookup"><span data-stu-id="12f82-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="12f82-138">LyncPerfTool パフォーマンス カウンターは、ユーザーが接続してアクションを実行するかどうかを示しますが、アクションが測定されているかどうかを確認する最も簡単な方法は、Skype for Business 2015 クライアントを使用してアカウントの 1 つにログオンし、それらのアクションを自分で実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="12f82-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="12f82-139">結果を確認して測定値が取られたか確認します。</span><span class="sxs-lookup"><span data-stu-id="12f82-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="12f82-140">Lync Server 2010 Capacity Planning Tools または Lync Server 2013 Capacity Planning ツールがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="12f82-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="12f82-141">問題ありませんか?</span><span class="sxs-lookup"><span data-stu-id="12f82-141">Is that okay?</span></span>

 <span data-ttu-id="12f82-142">これらのツールには相互運用性の問題があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-142">These tools have interoperability issues!</span></span> <span data-ttu-id="12f82-143">Skype for Business Server 2015 Stress and Performance ツールから有効なデータを取得するには、これらのツールのすべての以前のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12f82-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="12f82-144">Stress and Performance ツールは CAA 通話情報サーバー トポロジをセットアップしますか?</span><span class="sxs-lookup"><span data-stu-id="12f82-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="12f82-145">いいえ、ツールではこれを行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="12f82-145">No, the tools won't do this.</span></span> <span data-ttu-id="12f82-146">ツールは、ユーザー負荷をシミュレートするために、ユーザー、連絡先、および配布リストのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="12f82-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="12f82-147">ツールがサポートするユーザーの最大数は何ですか?</span><span class="sxs-lookup"><span data-stu-id="12f82-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="12f82-148">テストでは、最大 80,000 ユーザーを作成し、これらのツールを実行する合計 30,000 ユーザーのテストを実行しました。</span><span class="sxs-lookup"><span data-stu-id="12f82-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="12f82-149">最大 120,000 ユーザーをお勧めしますが、技術的な制限により高い値が可能です。</span><span class="sxs-lookup"><span data-stu-id="12f82-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="12f82-150">これらの値は環境内のサーバーとハードウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="12f82-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

