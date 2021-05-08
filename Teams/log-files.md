---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264877"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="16222-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="16222-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="16222-104">クライアントによって自動的に生成される 3 種類のログ ファイルがあります。このファイルは、クライアントのトラブルシューティングに役立Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="16222-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="16222-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="16222-105">Debug logs</span></span>

-   <span data-ttu-id="16222-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="16222-106">Media logs</span></span>

-   <span data-ttu-id="16222-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="16222-107">Desktop logs</span></span>

<span data-ttu-id="16222-108">Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。</span><span class="sxs-lookup"><span data-stu-id="16222-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="16222-109">サポート要求を作成する前にデバッグ ログを用意すると、Microsoft が問題のトラブルシューティングをすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="16222-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="16222-110">**メディア** ログまたは **デスクトップ ログ** は、Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="16222-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="16222-111">この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。</span><span class="sxs-lookup"><span data-stu-id="16222-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="16222-112">ただし、これらのログに対して生成されるファイルには、診断ログという用語 **が** 名前に含まれます。</span><span class="sxs-lookup"><span data-stu-id="16222-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="16222-113">次の表は、さまざまなクライアントとその関連ログの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="16222-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="16222-114">ログ ファイルは、クライアントとオペレーティング システムに固有の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="16222-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="16222-115">クライアント</span><span class="sxs-lookup"><span data-stu-id="16222-115">Client</span></span> |<span data-ttu-id="16222-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="16222-116">Debug</span></span>|<span data-ttu-id="16222-117">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="16222-117">Desktop</span></span>|<span data-ttu-id="16222-118">メディア</span><span class="sxs-lookup"><span data-stu-id="16222-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="16222-119">Web</span><span class="sxs-lookup"><span data-stu-id="16222-119">Web</span></span>    |<span data-ttu-id="16222-120">X</span><span class="sxs-lookup"><span data-stu-id="16222-120">X</span></span>         |-         |-         |
|<span data-ttu-id="16222-121">Windows</span><span class="sxs-lookup"><span data-stu-id="16222-121">Windows</span></span>     |<span data-ttu-id="16222-122">X</span><span class="sxs-lookup"><span data-stu-id="16222-122">X</span></span>         |<span data-ttu-id="16222-123">X</span><span class="sxs-lookup"><span data-stu-id="16222-123">X</span></span>         |<span data-ttu-id="16222-124">X</span><span class="sxs-lookup"><span data-stu-id="16222-124">X</span></span>         |
|<span data-ttu-id="16222-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="16222-125">Mac OSX</span></span>     |<span data-ttu-id="16222-126">X</span><span class="sxs-lookup"><span data-stu-id="16222-126">X</span></span>         |<span data-ttu-id="16222-127">X</span><span class="sxs-lookup"><span data-stu-id="16222-127">X</span></span>         |<span data-ttu-id="16222-128">X</span><span class="sxs-lookup"><span data-stu-id="16222-128">X</span></span>         |
|<span data-ttu-id="16222-129">Linux</span><span class="sxs-lookup"><span data-stu-id="16222-129">Linux</span></span>     |<span data-ttu-id="16222-130">X</span><span class="sxs-lookup"><span data-stu-id="16222-130">X</span></span>         |<span data-ttu-id="16222-131">X</span><span class="sxs-lookup"><span data-stu-id="16222-131">X</span></span>         |<span data-ttu-id="16222-132">X</span><span class="sxs-lookup"><span data-stu-id="16222-132">X</span></span>         |
|<span data-ttu-id="16222-133">iOS</span><span class="sxs-lookup"><span data-stu-id="16222-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="16222-134">Android</span><span class="sxs-lookup"><span data-stu-id="16222-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="16222-135">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="16222-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="16222-136">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="16222-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="16222-137">これらは最も一般的なログであり、すべての Microsoft サポート ケースで必要です。</span><span class="sxs-lookup"><span data-stu-id="16222-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="16222-138">デバッグ ログは、Windows Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="16222-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="16222-139">ログはテキスト ベースであり、ボトムアップから読み取されます。</span><span class="sxs-lookup"><span data-stu-id="16222-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="16222-140">任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="16222-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="16222-141">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16222-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="16222-142">ログイン</span><span class="sxs-lookup"><span data-stu-id="16222-142">Login</span></span>

-   <span data-ttu-id="16222-143">中層サービスへの接続要求</span><span class="sxs-lookup"><span data-stu-id="16222-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="16222-144">通話/会話</span><span class="sxs-lookup"><span data-stu-id="16222-144">Call/conversation</span></span>

<span data-ttu-id="16222-145">デバッグ ログは、次の OS 固有の方法を使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="16222-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="16222-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="16222-146">Windows:</span></span>

      <span data-ttu-id="16222-147">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="16222-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="16222-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="16222-148">Mac OSX:</span></span>

      <span data-ttu-id="16222-149">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="16222-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="16222-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="16222-150">Linux:</span></span>

      <span data-ttu-id="16222-151">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="16222-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="16222-152">デバッグ ログは、次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="16222-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="16222-153">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="16222-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="16222-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="16222-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="16222-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="16222-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="16222-156">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="16222-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="16222-157">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="16222-157">Media logs</span></span>
---------------------------

<span data-ttu-id="16222-158">メディア ログには、音声、ビデオ、画面の共有に関する診断データがTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="16222-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="16222-159">これらは、通話関連の問題にリンクされているサポート ケースに必要です。</span><span class="sxs-lookup"><span data-stu-id="16222-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="16222-160">メディア ログは既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="16222-160">Media logging is turned off by default.</span></span> <span data-ttu-id="16222-161">会議の診断データをTeamsするには、ユーザーがクライアントでオプションを有効Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="16222-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="16222-162">[全般 **設定** に移動し、[会議の診断のログ記録を有効にする (Teams を再起動する必要があります) チェック ボックスをオンにし、Teams を再起動して、問題を  >  再現します。</span><span class="sxs-lookup"><span data-stu-id="16222-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="16222-163">次の表に、メディア ログの場所の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="16222-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="16222-164">ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現した時間をログで確実にカバーしてください。</span><span class="sxs-lookup"><span data-stu-id="16222-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="16222-165">クライアント</span><span class="sxs-lookup"><span data-stu-id="16222-165">Client</span></span> |<span data-ttu-id="16222-166">場所</span><span class="sxs-lookup"><span data-stu-id="16222-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="16222-167">Windows</span><span class="sxs-lookup"><span data-stu-id="16222-167">Windows</span></span>     |<span data-ttu-id="16222-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="16222-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="16222-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="16222-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="16222-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="16222-171">Mac OSX</span></span>     |<span data-ttu-id="16222-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="16222-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="16222-174">Linux</span><span class="sxs-lookup"><span data-stu-id="16222-174">Linux</span></span>       |<span data-ttu-id="16222-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="16222-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="16222-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="16222-177">生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16222-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="16222-178">ログ ファイル名</span><span class="sxs-lookup"><span data-stu-id="16222-178">Log file name</span></span>  |<span data-ttu-id="16222-179">説明</span><span class="sxs-lookup"><span data-stu-id="16222-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="16222-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="16222-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="16222-181">メディア スタックに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="16222-181">Contains information related to the media stack.</span></span> <span data-ttu-id="16222-182">これには、解像度、デコーダーとエンコーダーの使用、送信および受信されたフレーム数、カメラとビデオ ベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16222-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="16222-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="16222-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="16222-184">コントロールが指定された場合のタイムスタンプ、マウス ポインター情報など、リモート制御アクションに関連する情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="16222-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="16222-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="16222-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="16222-186">メディア スタック トレース イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="16222-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="16222-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="16222-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="16222-188">レンダリング品質など、メディア エージェントに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="16222-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="16222-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="16222-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="16222-190">ts 呼び出し API のイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="16222-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="16222-191">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="16222-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="16222-192">デスクトップ ログ (ブートストラップ ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16222-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="16222-193">メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="16222-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="16222-194">ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="16222-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="16222-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="16222-195">Windows:</span></span>

 - <span data-ttu-id="16222-196">システム トレイの **[Microsoft Teams]** アイコンを右クリックし、[ログの取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="16222-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="16222-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="16222-197">Mac OsX:</span></span>

 - <span data-ttu-id="16222-198">[ヘルプ **] プルダウン メニュー** から **[ログの** 取得] を選択します。</span><span class="sxs-lookup"><span data-stu-id="16222-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="16222-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="16222-199">Linux:</span></span>

 - <span data-ttu-id="16222-200">システム トレイの **[Microsoft Teams]** アイコンをクリックし、[ログの取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="16222-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="16222-201">クライアント</span><span class="sxs-lookup"><span data-stu-id="16222-201">Client</span></span> |<span data-ttu-id="16222-202">場所</span><span class="sxs-lookup"><span data-stu-id="16222-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="16222-203">Windows</span><span class="sxs-lookup"><span data-stu-id="16222-203">Windows</span></span>     |<span data-ttu-id="16222-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="16222-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="16222-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="16222-205">Mac OSX</span></span>     |<span data-ttu-id="16222-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="16222-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="16222-207">Linux</span><span class="sxs-lookup"><span data-stu-id="16222-207">Linux</span></span>       |<span data-ttu-id="16222-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="16222-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="16222-209">ブラウザートレース</span><span class="sxs-lookup"><span data-stu-id="16222-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="16222-210">一部のカテゴリのエラーについては、Microsoft サポートでブラウザー トレースの収集が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16222-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="16222-211">この情報は、エラーが発生した場合のクライアントの状態Teams詳細を提供できます。</span><span class="sxs-lookup"><span data-stu-id="16222-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="16222-212">ブラウザーのトレースを開始する前に、ブラウザーにサインインTeams。</span><span class="sxs-lookup"><span data-stu-id="16222-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="16222-213">トレースに機密性の高いサインイン情報が含まれるので、トレースを開始する前にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="16222-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="16222-214">サインインした後、ブラウザーに応じて次のリンクのいずれかを選択し、提供されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="16222-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="16222-215">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="16222-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="16222-216">Edge</span><span class="sxs-lookup"><span data-stu-id="16222-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="16222-217">Safari</span><span class="sxs-lookup"><span data-stu-id="16222-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="16222-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="16222-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="16222-219">この手順では、Azure portal へのすべての参照を、新しいクライアントTeamsします。</span><span class="sxs-lookup"><span data-stu-id="16222-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="16222-220">関連トピック</span><span class="sxs-lookup"><span data-stu-id="16222-220">Related topics</span></span>

[<span data-ttu-id="16222-221">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="16222-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
