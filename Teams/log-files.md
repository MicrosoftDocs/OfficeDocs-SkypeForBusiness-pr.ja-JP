---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されたデバッグ ログ、メディア ログ、デスクトップ ログ、ログが見つかる場所、および監視とトラブルシューティングに役立つ方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337744"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="4f2c1-103">ログ ファイルを使用して、ログの監視とトラブルシューティングを行Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f2c1-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="4f2c1-104">クライアントによって自動的に生成される 3 種類のログ ファイルがあります。このファイルは、クライアントの監視とトラブルシューティングに役立Teams。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="4f2c1-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="4f2c1-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="4f2c1-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="4f2c1-108">この記事では、3 つのログと、その使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="4f2c1-109">特定の問題のトラブルシューティングについては、「トラブルシューティング」を参照[Teamsしてください](/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="4f2c1-110">サポートに連絡する方法については、「サポートを受け取る [」を参照してください](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="4f2c1-111">Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="4f2c1-112">サポート要求を作成する前にデバッグ ログを用意すると、Microsoft が問題のトラブルシューティングをすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="4f2c1-113">**メディア** ログまたは **デスクトップ ログ** は、Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="4f2c1-114">この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="4f2c1-115">ただし、これらのログに対して生成されるファイルには、診断ログという用語 **が** 名前に含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="4f2c1-116">次の表は、さまざまなクライアントとその関連ログの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="4f2c1-117">ログ ファイルは、クライアントとオペレーティング システムに固有の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="4f2c1-118">クライアント</span><span class="sxs-lookup"><span data-stu-id="4f2c1-118">Client</span></span> |<span data-ttu-id="4f2c1-119">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-119">Debug</span></span>|<span data-ttu-id="4f2c1-120">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-120">Desktop</span></span>|<span data-ttu-id="4f2c1-121">メディア</span><span class="sxs-lookup"><span data-stu-id="4f2c1-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="4f2c1-122">Web</span><span class="sxs-lookup"><span data-stu-id="4f2c1-122">Web</span></span>    |<span data-ttu-id="4f2c1-123">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-123">X</span></span>         |-         |-         |
|<span data-ttu-id="4f2c1-124">Windows</span><span class="sxs-lookup"><span data-stu-id="4f2c1-124">Windows</span></span>     |<span data-ttu-id="4f2c1-125">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-125">X</span></span>         |<span data-ttu-id="4f2c1-126">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-126">X</span></span>         |<span data-ttu-id="4f2c1-127">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-127">X</span></span>         |
|<span data-ttu-id="4f2c1-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4f2c1-128">Mac OSX</span></span>     |<span data-ttu-id="4f2c1-129">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-129">X</span></span>         |<span data-ttu-id="4f2c1-130">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-130">X</span></span>         |<span data-ttu-id="4f2c1-131">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-131">X</span></span>         |
|<span data-ttu-id="4f2c1-132">Linux</span><span class="sxs-lookup"><span data-stu-id="4f2c1-132">Linux</span></span>     |<span data-ttu-id="4f2c1-133">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-133">X</span></span>         |<span data-ttu-id="4f2c1-134">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-134">X</span></span>         |<span data-ttu-id="4f2c1-135">X</span><span class="sxs-lookup"><span data-stu-id="4f2c1-135">X</span></span>         |
|<span data-ttu-id="4f2c1-136">iOS</span><span class="sxs-lookup"><span data-stu-id="4f2c1-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="4f2c1-137">Android</span><span class="sxs-lookup"><span data-stu-id="4f2c1-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="4f2c1-138">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="4f2c1-139">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-139">Debug logs</span></span>

<span data-ttu-id="4f2c1-140">これらは最も一般的なログであり、すべての Microsoft サポート ケースで必要です。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="4f2c1-141">デバッグ ログは、Windows Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="4f2c1-142">ログはテキスト ベースであり、ボトムアップから読み取されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="4f2c1-143">任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="4f2c1-144">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="4f2c1-145">ログイン</span><span class="sxs-lookup"><span data-stu-id="4f2c1-145">Login</span></span>

-   <span data-ttu-id="4f2c1-146">中層サービスへの接続要求</span><span class="sxs-lookup"><span data-stu-id="4f2c1-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="4f2c1-147">通話/会話</span><span class="sxs-lookup"><span data-stu-id="4f2c1-147">Call/conversation</span></span>

<span data-ttu-id="4f2c1-148">デバッグ ログは、次の OS 固有の方法を使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="4f2c1-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-149">Windows:</span></span>

      <span data-ttu-id="4f2c1-150">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4f2c1-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="4f2c1-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-151">Mac OSX:</span></span>

      <span data-ttu-id="4f2c1-152">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4f2c1-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="4f2c1-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-153">Linux:</span></span>

      <span data-ttu-id="4f2c1-154">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4f2c1-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="4f2c1-155">デバッグ ログは、次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="4f2c1-156">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="4f2c1-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="4f2c1-157">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="4f2c1-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="4f2c1-158">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="4f2c1-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="4f2c1-159">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="4f2c1-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="4f2c1-160">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-160">Media logs</span></span>

<span data-ttu-id="4f2c1-161">メディア ログには、音声、ビデオ、画面の共有に関する診断データがTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="4f2c1-162">これらは、通話関連の問題にリンクされているサポート ケースに必要です。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="4f2c1-163">メディア ログは既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-163">Media logging is turned off by default.</span></span> <span data-ttu-id="4f2c1-164">会議の診断データをTeamsするには、ユーザーがクライアントでオプションを有効Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="4f2c1-165">[全般 **設定** に移動し、[会議の診断のログ記録を有効にする (Teams を再起動する必要があります) チェック ボックスをオンにし、Teams を再起動して、問題を  >  再現します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="4f2c1-166">次の表に、メディア ログの場所の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="4f2c1-167">ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現した時間をログで確実にカバーしてください。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="4f2c1-168">クライアント</span><span class="sxs-lookup"><span data-stu-id="4f2c1-168">Client</span></span> |<span data-ttu-id="4f2c1-169">場所</span><span class="sxs-lookup"><span data-stu-id="4f2c1-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4f2c1-170">Windows</span><span class="sxs-lookup"><span data-stu-id="4f2c1-170">Windows</span></span>     |<span data-ttu-id="4f2c1-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="4f2c1-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="4f2c1-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="4f2c1-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="4f2c1-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4f2c1-174">Mac OSX</span></span>     |<span data-ttu-id="4f2c1-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4f2c1-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="4f2c1-177">Linux</span><span class="sxs-lookup"><span data-stu-id="4f2c1-177">Linux</span></span>       |<span data-ttu-id="4f2c1-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4f2c1-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="4f2c1-180">生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="4f2c1-181">ログ ファイル名</span><span class="sxs-lookup"><span data-stu-id="4f2c1-181">Log file name</span></span>  |<span data-ttu-id="4f2c1-182">説明</span><span class="sxs-lookup"><span data-stu-id="4f2c1-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4f2c1-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="4f2c1-184">メディア スタックに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-184">Contains information related to the media stack.</span></span> <span data-ttu-id="4f2c1-185">これには、解像度、デコーダーとエンコーダーの使用、送信および受信されたフレーム数、カメラとビデオ ベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="4f2c1-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="4f2c1-187">コントロールが指定された場合のタイムスタンプ、マウス ポインター情報など、リモート制御アクションに関連する情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="4f2c1-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="4f2c1-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="4f2c1-189">メディア スタック トレース イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="4f2c1-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="4f2c1-191">レンダリング品質など、メディア エージェントに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="4f2c1-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="4f2c1-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="4f2c1-193">ts 呼び出し API のイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="4f2c1-194">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="4f2c1-194">Desktop logs</span></span>

<span data-ttu-id="4f2c1-195">デスクトップ ログ (ブートストラップ ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="4f2c1-196">メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="4f2c1-197">ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="4f2c1-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-198">Windows:</span></span>

 - <span data-ttu-id="4f2c1-199">システム トレイの **[Microsoft Teams]** アイコンを右クリックし、[ログの取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="4f2c1-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-200">Mac OsX:</span></span>

 - <span data-ttu-id="4f2c1-201">[ヘルプ **] プルダウン メニュー** から **[ログの** 取得] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="4f2c1-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="4f2c1-202">Linux:</span></span>

 - <span data-ttu-id="4f2c1-203">システム トレイの **[Microsoft Teams]** アイコンをクリックし、[ログの取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="4f2c1-204">クライアント</span><span class="sxs-lookup"><span data-stu-id="4f2c1-204">Client</span></span> |<span data-ttu-id="4f2c1-205">場所</span><span class="sxs-lookup"><span data-stu-id="4f2c1-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4f2c1-206">Windows</span><span class="sxs-lookup"><span data-stu-id="4f2c1-206">Windows</span></span>     |<span data-ttu-id="4f2c1-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="4f2c1-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="4f2c1-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4f2c1-208">Mac OSX</span></span>     |<span data-ttu-id="4f2c1-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4f2c1-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="4f2c1-210">Linux</span><span class="sxs-lookup"><span data-stu-id="4f2c1-210">Linux</span></span>       |<span data-ttu-id="4f2c1-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4f2c1-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="4f2c1-212">ブラウザートレース</span><span class="sxs-lookup"><span data-stu-id="4f2c1-212">Browser trace</span></span>

<span data-ttu-id="4f2c1-213">一部のカテゴリのエラーについては、Microsoft サポートでブラウザー トレースの収集が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="4f2c1-214">この情報は、エラーが発生した場合のクライアントの状態Teams詳細を提供できます。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="4f2c1-215">ブラウザーのトレースを開始する前に、ブラウザーにサインインTeams。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="4f2c1-216">トレースに機密性の高いサインイン情報が含まれるので、トレースを開始する前にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="4f2c1-217">サインインした後、ブラウザーに応じて次のリンクのいずれかを選択し、提供されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="4f2c1-218">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="4f2c1-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="4f2c1-219">Edge</span><span class="sxs-lookup"><span data-stu-id="4f2c1-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="4f2c1-220">Safari</span><span class="sxs-lookup"><span data-stu-id="4f2c1-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="4f2c1-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="4f2c1-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="4f2c1-222">この手順では、Azure portal へのすべての参照を、新しいクライアントTeamsします。</span><span class="sxs-lookup"><span data-stu-id="4f2c1-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4f2c1-223">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4f2c1-223">Related topics</span></span>

[<span data-ttu-id="4f2c1-224">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4f2c1-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
