---
title: ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype ビジネス 2015年のストレスおよびパフォーマンス ツールについてよく寄せられる質問 (FAQ)、どのようなツールの構成がサポートされているを検索、ツールに関する問題のトラブルシューティング、およびストレスおよびパフォーマンス ツールを実行するときに表示される動作を明確にすることに便利です。.
ms.openlocfilehash: 604644d5aecb12f94304d1c7ce271c68208e1964
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906747"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="64e15-103">ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="64e15-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="64e15-104">Skype ビジネス 2015年のストレスおよびパフォーマンス ツールについてよく寄せられる質問 (FAQ)、どのようなツールの構成がサポートされているを検索、ツールに関する問題のトラブルシューティング、およびストレスおよびパフォーマンス ツールを実行するときに表示される動作を明確にすることに便利です。.</span><span class="sxs-lookup"><span data-stu-id="64e15-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="64e15-105">この FAQ では、ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールでは、Skype に関してよく寄せられる質問について説明し、トラブルシューティングおよびツールの構成の選択に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="64e15-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="64e15-106">実稼働環境で LyncPerfTool.exe を実行することができますか。</span><span class="sxs-lookup"><span data-stu-id="64e15-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="64e15-107">これはお勧め**できません**。</span><span class="sxs-lookup"><span data-stu-id="64e15-107">This is **not** recommended.</span></span> <span data-ttu-id="64e15-108">ツール、本番サーバのパフォーマンス、セキュリティ、およびエンド ユーザー エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="64e15-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="64e15-109">ログオン ユーザーを最初にします。</span><span class="sxs-lookup"><span data-stu-id="64e15-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="64e15-110">高負荷サーバー実行しているでしょうか。</span><span class="sxs-lookup"><span data-stu-id="64e15-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="64e15-111">初めてユーザーがログオンすると、追加の操作は、バック グラウンドで行われます。</span><span class="sxs-lookup"><span data-stu-id="64e15-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="64e15-112">結果として、Microsoft SQL Server バック エンド サーバーにパフォーマンスが低下することができます。</span><span class="sxs-lookup"><span data-stu-id="64e15-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="64e15-113">ユーザーのすべてのログに記録する簡単なテストを実行し、ツールを使用して結果を測定を開始する前にクライアントを再起動し、実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64e15-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="64e15-114">Skype ビジネス サーバーは、1 秒あたり 12 個を超えるの同時ユーザー ログオン セッションをサポートしないですが、サーバーで処理できる実際の数は、ハードウェアの構成によって異なり、サポートされている値よりも小さい場合があります注意してください。</span><span class="sxs-lookup"><span data-stu-id="64e15-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="64e15-115">クライアントでメモリが不足しています!</span><span class="sxs-lookup"><span data-stu-id="64e15-115">My clients are running out of memory!</span></span> <span data-ttu-id="64e15-116">どうしたらいいでしょう。</span><span class="sxs-lookup"><span data-stu-id="64e15-116">What should I do?</span></span>

<span data-ttu-id="64e15-117">クライアントがメモリから実行している場合は、ビジネス サーバーのフロント エンド プールの Skype あたりログオンしたユーザーの数を減らす必要があります。</span><span class="sxs-lookup"><span data-stu-id="64e15-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="64e15-118">問題が永続的な場合は、最後のプール拡張正面にもできます。</span><span class="sxs-lookup"><span data-stu-id="64e15-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="64e15-119">に対して実行できますこのツール ビジネスのサーバーで、Skype 自体ですか。</span><span class="sxs-lookup"><span data-stu-id="64e15-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="64e15-120">するべきではありません。</span><span class="sxs-lookup"><span data-stu-id="64e15-120">You shouldn't do that.</span></span> <span data-ttu-id="64e15-121">バイナリが一致しないのため、エラーが表示するために、このシナリオがサポートされていないと、目標は、サーバー上のリソースの消費量を測定するためです。</span><span class="sxs-lookup"><span data-stu-id="64e15-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="64e15-122">実際には、ツールの実行が、サーバーのパフォーマンスに影響を与えるデータと測定値が無効になります。</span><span class="sxs-lookup"><span data-stu-id="64e15-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="64e15-123">仮想サーバー上または [Microsoft HYPER-V Server 2008/2012 に LyncPerfTool.exe を実行することができますか。</span><span class="sxs-lookup"><span data-stu-id="64e15-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="64e15-124">はいできますよ。</span><span class="sxs-lookup"><span data-stu-id="64e15-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="64e15-125">MPOP は何を意味しますか。</span><span class="sxs-lookup"><span data-stu-id="64e15-125">What does MPOP mean?</span></span>

<span data-ttu-id="64e15-126">MPOP は、「プレゼンスの複数のポイント」言い換えると簡略化された方法です。</span><span class="sxs-lookup"><span data-stu-id="64e15-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="64e15-127">MPOP は、ユーザーがログオンしている Skype をビジネス 2015年クライアントの複数のコンピューターまたはデバイスからのシナリオをシミュレートするものです。</span><span class="sxs-lookup"><span data-stu-id="64e15-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="64e15-128">、LyncPerfTool.exe、の各エンドポイントを使用する既定のプロファイルに注意します。</span><span class="sxs-lookup"><span data-stu-id="64e15-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="64e15-129">つまり、プロファイルは、プレゼンスの 2 つの点の間で分割されていません。</span><span class="sxs-lookup"><span data-stu-id="64e15-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="64e15-130">LyncPerfTool.exe を起動しましたが、何も起こらない。</span><span class="sxs-lookup"><span data-stu-id="64e15-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="64e15-131">どうなっているのですか。</span><span class="sxs-lookup"><span data-stu-id="64e15-131">What's going on?</span></span>

<span data-ttu-id="64e15-132">ユーザーが接続しているかどうかを参照してくださいサーバーのアクティブなエンドポイントの合計カウンターを確認してください。</span><span class="sxs-lookup"><span data-stu-id="64e15-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="64e15-133">ユーザーが接続していない場合、Skype をビジネス サーバー 2015 の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="64e15-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="64e15-134">皆さんは通常この問題は、サーバー名、ユーザーのプレフィックス、またはパスワードのいずれかが間違っているために発生します。</span><span class="sxs-lookup"><span data-stu-id="64e15-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="64e15-135">外部クライアントがアクセス プロキシと対象サーバーの値を指定する必要があります注意してをください。</span><span class="sxs-lookup"><span data-stu-id="64e15-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="64e15-136">構成ファイル内のポート番号を確認します。</span><span class="sxs-lookup"><span data-stu-id="64e15-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="64e15-137">何かが計測されることを確認する方法は?</span><span class="sxs-lookup"><span data-stu-id="64e15-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="64e15-138">ユーザーが接続しているかどうかと、実行するアクションを示すパフォーマンス カウンターは LyncPerfTool ですが、アクションが測定されているかどうかを確認する最も簡単な方法は、Skype ビジネス 2015年クライアント用のアカウントのいずれかにログオンし、これらの操作を行いますアクション自分でします。</span><span class="sxs-lookup"><span data-stu-id="64e15-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="64e15-139">測定値を確認するのには結果が取得されたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="64e15-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="64e15-140">Lync Server 2010 の容量計画ツールと Lync Server 2013 の容量計画ツールのインストールがあるとします。</span><span class="sxs-lookup"><span data-stu-id="64e15-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="64e15-141">いいですか。</span><span class="sxs-lookup"><span data-stu-id="64e15-141">Is that okay?</span></span>

 <span data-ttu-id="64e15-142">これらのツールには、相互運用性の問題があります。</span><span class="sxs-lookup"><span data-stu-id="64e15-142">These tools have interoperability issues!</span></span> <span data-ttu-id="64e15-143">ビジネス サーバー 2015 応力の Skype から有効なデータを取得するのにはこれらのツールとパフォーマンス ツールの以前のバージョンをすべてアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64e15-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="64e15-144">ストレスおよびパフォーマンス ツールが CAA 呼び出し情報のサーバー トポロジを設定するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="64e15-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="64e15-145">残念ですが、ツールは、このことはありません。</span><span class="sxs-lookup"><span data-stu-id="64e15-145">No, the tools won't do this.</span></span> <span data-ttu-id="64e15-146">ツールは、ユーザー、連絡先、および配布リスト、ユーザーの負荷をシミュレートするためにのみ作成します。</span><span class="sxs-lookup"><span data-stu-id="64e15-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="64e15-147">ツールがサポートできるユーザーの最大数とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="64e15-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="64e15-148">テストでは、私たち最大 80,000 ユーザーの作成して合計 30,000 人のユーザーがこれらのツールを実行するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="64e15-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="64e15-149">最大 120,000 のユーザーは、技術的な制限の値を大きくできますが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="64e15-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="64e15-150">これらの値は、サーバーと、環境内のハードウェアに依存していることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="64e15-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

