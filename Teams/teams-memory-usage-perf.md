---
title: Microsoft Teams のメモリ使用方法
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft Teams によるシステム メモリの使用方法、およびデスクトップ アプリケーションと Web アプリケーションでメモリ使用量が同じ理由について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033401"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="de9f8-103">Microsoft Teams のメモリ使用方法</span><span class="sxs-lookup"><span data-stu-id="de9f8-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="de9f8-104">一部の Microsoft Teams ユーザーから、Teams によるメモリ使用方法について質問を受けています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="de9f8-105">この記事では、Teams がメモリを使用する方法を説明します。また、Teams デスクトップ アプリケーション (アプリ) と Teams Web アプリによって、同じコンピューター上の別のアプリとワークロードに最適な実行のための十分なメモリが渡されることが阻害されない理由を説明します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="de9f8-106">Teams は先進の Web テクノロジを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="de9f8-107">これを実現するために、Teams のデスクトップ クライアントは Electron で開発されました。Electron はレンダリングに Chromium を使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="de9f8-108">これは、Microsoft Edge や Chrome など、現在人気のある多くのブラウザーで採用されているレンダリング エンジンと同じです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="de9f8-109">Teams のしくみ</span><span class="sxs-lookup"><span data-stu-id="de9f8-109">How Teams works</span></span>

<span data-ttu-id="de9f8-110">Electron で設計されている Teams を使用すると、迅速な展開が可能になります。また、異なるオペレーティング システム (Windows、Mac、Linux) 間の各種 Teams バージョン間で同一性を維持できます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="de9f8-111">この同一性は、Electron と Chromium によってすべてのバージョンで同じコード ベースが維持されるので可能になります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="de9f8-112">このアーキテクチャのもう 1 つの利点は、Teams Web アプリとデスクトップのバージョンにおけるメモリ使用プロファイルが類似することです。</span><span class="sxs-lookup"><span data-stu-id="de9f8-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="de9f8-113">Web アプリとデスクトップのどちらのバージョンでも、ブラウザーで使用する場合と同じようにメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="de9f8-114">Electron について詳しくは、[こちらの Web サイト](https://electronjs.org/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de9f8-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="de9f8-115">詳しくは、「[Chromium のメモリ使用](https://www.chromium.org/developers/memory-usage-backgrounder)」および「[Chrome メモリにおける主要概念](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="de9f8-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="de9f8-116">次の画像では、Windows 用の Teams デスクトップ アプリと Teams Web アプリ (この例では Google Chrome で実行されています) のメモリ使用量を並べて示しています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams デスクトップ アプリと Web アプリのメモリ使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="de9f8-118">Teams でのメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="de9f8-118">Memory usage in Teams</span></span>

<span data-ttu-id="de9f8-119">Teams がシステム メモリを使用する際に *予期される* 動作と、システム メモリの問題が実際に生じたときの症状について理解するのは重要です。</span><span class="sxs-lookup"><span data-stu-id="de9f8-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="de9f8-120">Teams による予期されるメモリ使用量</span><span class="sxs-lookup"><span data-stu-id="de9f8-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="de9f8-121">Teams デスクトップ アプリと Teams Web アプリのどちらを実行しているとしても、使用可能なシステム メモリ量がChromium によって検出され、その中の十分な量のメモリを使用してレンダリング エクスペリエンスが最適化されます。</span><span class="sxs-lookup"><span data-stu-id="de9f8-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="de9f8-122">他のアプリやサービスによってシステム メモリを必要とする場合、Chromium はそれらのプロセスにメモリを渡します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="de9f8-123">Chromium は、現在実行中の他のものに影響を与えることなく Teams のパフォーマンスを最適化するために、Teams のメモリ使用量を継続的に調整します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="de9f8-124">このようにして、Chromium ワークロードは、使用可能なシステム メモリ量に応じて変化するメモリ量を利用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="de9f8-125">次のグラフは、4 つの独立したシステムにおける Teams でのメモリ使用量を示しています。システムごとに使用できるメモリ量が異なります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="de9f8-126">各システムは同様のワークロードを処理しています (同じアプリを開いて実行しています)。</span><span class="sxs-lookup"><span data-stu-id="de9f8-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![異なるシステム間の Teams メモリ使用量](media/teams-memory-usage.png)

<span data-ttu-id="de9f8-128">コンピューターに搭載されているメモリが多い場合、Teams はそのメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="de9f8-129">メモリが十分にないシステムでは、Teams が使用するメモリは少なくなります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="de9f8-130">システム メモリの問題の症状</span><span class="sxs-lookup"><span data-stu-id="de9f8-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="de9f8-131">使用しているコンピューターで、次の 1 つ以上の問題が発生する場合は、システム メモリに重大な問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="de9f8-132">複数の大規模なアプリケーションを同時に実行しているときに、メモリ使用量が高くなります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="de9f8-133">システムのパフォーマンスが低下する、またはアプリケーションがハングします。</span><span class="sxs-lookup"><span data-stu-id="de9f8-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="de9f8-134">すべてのアプリのシステム メモリ使用量全体が継続的に 90% 以上になります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="de9f8-135">このメモリ使用量の場合、Teams は他のアプリおよびワークロードにメモリを戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="de9f8-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="de9f8-136">メモリ使用量が継続的に 90% になるということは、Teams がシステムにメモリを戻しておらず、問題が生じていることを示します。</span><span class="sxs-lookup"><span data-stu-id="de9f8-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="de9f8-137">次の画像は、システム メモリ使用率が異常に高い場合のタスク マネージャーのビューの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="de9f8-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![タスク マネージャーにおける Teams メモリ使用量ビュー](media/teams-memory-high-mem-process-list.png)

![タスク マネージャーにおける Teams メモリ使用量グラフ](media/teams-memory-high-mem-process-list2.png)
