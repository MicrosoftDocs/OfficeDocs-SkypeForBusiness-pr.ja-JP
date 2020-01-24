---
title: Microsoft Teams でメモリを使用する方法
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft Teams でシステムメモリを使用する方法と、デスクトップアプリケーションと web アプリケーションの間でメモリ使用が同じになる理由について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6dcbe03851b8dbb31cd0bd6f1b580913d4dc683d
ms.sourcegitcommit: f017e38095098d4d28c71241dddac53538be79d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "41506919"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="04251-103">Microsoft Teams でメモリを使用する方法</span><span class="sxs-lookup"><span data-stu-id="04251-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="04251-104">一部の Microsoft Teams ユーザーは、Teams でのメモリの使い方について質問があります。</span><span class="sxs-lookup"><span data-stu-id="04251-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="04251-105">この記事では、Teams でメモリがどのように使用されるかについて説明します。また、Teams デスクトップアプリケーション (アプリ) と Teams web アプリでは、同じコンピューター上の他のアプリやワークロードが、適切に実行するために十分なメモリを持つことを防ぐことができません。</span><span class="sxs-lookup"><span data-stu-id="04251-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="04251-106">Teams は最新の web テクノロジを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="04251-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="04251-107">これを実現するために、Teams デスクトップクライアントは、Chromium を使ってレンダリングするために、電子に開発されました。</span><span class="sxs-lookup"><span data-stu-id="04251-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="04251-108">これは、Edge や Chrome など、多くの主要なブラウザーの背後にある同じレンダリングエンジンです。</span><span class="sxs-lookup"><span data-stu-id="04251-108">This is the same rendering engine behind many of today’s most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="04251-109">Teams のしくみ</span><span class="sxs-lookup"><span data-stu-id="04251-109">How Teams works</span></span>

<span data-ttu-id="04251-110">電子版のチームでは、より迅速な開発が可能になり、さまざまなオペレーティングシステム (Windows、Mac、Linux) 間で Teams バージョン間のパリティも維持されます。</span><span class="sxs-lookup"><span data-stu-id="04251-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="04251-111">このパリティは、電子と Chromium がすべてのバージョンで同様のコードベースを維持するために可能です。</span><span class="sxs-lookup"><span data-stu-id="04251-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="04251-112">このアーキテクチャのもう1つの利点は、Teams web app とデスクトップバージョンの間に同じメモリ使用量プロファイルがあることです。</span><span class="sxs-lookup"><span data-stu-id="04251-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="04251-113">Web アプリとデスクトップバージョンはどちらも、ブラウザーで使用する場合と同様の方法でメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="04251-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="04251-114">電子情報の詳細については[、お客様の Web サイト](https://electronjs.org/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04251-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="04251-115">詳しくは、「 [Chrome メモリの](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) [Chromium メモリ使用量](https://www.chromium.org/developers/memory-usage-backgrounder)と重要な概念」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04251-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="04251-116">次の画像は、Windows 用 Teams デスクトップアプリと Teams Web アプリ (この例では Google Chrome で実行されています) のメモリ使用量を並べて示しています。</span><span class="sxs-lookup"><span data-stu-id="04251-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams デスクトップアプリと Web アプリメモリ使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="04251-118">Teams でのメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="04251-118">Memory usage in Teams</span></span>

<span data-ttu-id="04251-119">システムメモリに含まれているチームの*予期*される動作を理解し、システムメモリの問題が本当に発生したときの症状を把握することが重要です。</span><span class="sxs-lookup"><span data-stu-id="04251-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="04251-120">Teams によるメモリ使用量の期待値</span><span class="sxs-lookup"><span data-stu-id="04251-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="04251-121">Teams デスクトップアプリと Teams web アプリのどちらを実行していても、Chromium は利用可能なシステムメモリの量を検出し、そのメモリを利用してレンダリングエクスペリエンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="04251-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="04251-122">他のアプリやサービスがシステムメモリを必要とする場合、Chromium はこれらのプロセスにメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="04251-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="04251-123">Chromium は、現在実行されている内容に影響を与えることなくチームのパフォーマンスを最適化するために、チームのメモリ使用量を継続的に調整します。</span><span class="sxs-lookup"><span data-stu-id="04251-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="04251-124">このように、類似した Chromium のワークロードでは、使用可能なシステムメモリの量に応じて、さまざまな量のメモリを利用できます。</span><span class="sxs-lookup"><span data-stu-id="04251-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="04251-125">次の図は、4つの異なるシステム上のチームによるメモリ使用量を示しています。各システムでは、それぞれ異なるメモリ容量が使用されています。</span><span class="sxs-lookup"><span data-stu-id="04251-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="04251-126">各システムは同様のワークロードを処理しています (同じアプリを開いて実行しています)。</span><span class="sxs-lookup"><span data-stu-id="04251-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![異なるシステム間での Teams のメモリ使用量](media/teams-memory-usage.png)

<span data-ttu-id="04251-128">コンピューターにメモリが追加されている場合、チームはそのメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="04251-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="04251-129">メモリが不足しているシステムでは、チームはあまり使用しません。</span><span class="sxs-lookup"><span data-stu-id="04251-129">In systems where memory is scarce, Teams will use less.</span></span> 

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="04251-130">システムメモリの問題の症状</span><span class="sxs-lookup"><span data-stu-id="04251-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="04251-131">コンピューターに次のいずれかの現象が表示される場合は、深刻なシステムメモリの問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04251-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="04251-132">複数の大きなアプリケーションが同時に実行されている場合、メモリの使用量が高くなります。</span><span class="sxs-lookup"><span data-stu-id="04251-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="04251-133">システムのパフォーマンスが低下したり、アプリケーションがハングしたりする。</span><span class="sxs-lookup"><span data-stu-id="04251-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="04251-134">すべてのアプリで、90% 以上の全体的なシステムメモリ使用量が維持されます。</span><span class="sxs-lookup"><span data-stu-id="04251-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="04251-135">この量のメモリ使用量によって、チームは、他のアプリやワークロードにメモリを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="04251-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="04251-136">90% のメモリ使用量が継続すると、チームはメモリをシステムに戻さないということになります。これは、問題を示します。</span><span class="sxs-lookup"><span data-stu-id="04251-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="04251-137">次の図は、システムメモリ使用量が異常に高い場合のタスクマネージャーのビューの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="04251-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![タスクマネージャーの [チームメモリ使用量] ビュー](media/teams-memory-high-mem-process-list.png)

![タスクマネージャーの Teams のメモリ使用量グラフ](media/teams-memory-high-mem-process-list2.png)
