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
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112193"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="fcf44-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="fcf44-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="fcf44-104">クライアントによって自動的に生成される 3 種類のログ ファイルがあります。これは、Microsoft Teams のトラブルシューティングを支援するために利用できます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="fcf44-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-105">Debug logs</span></span>

-   <span data-ttu-id="fcf44-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-106">Media logs</span></span>

-   <span data-ttu-id="fcf44-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-107">Desktop logs</span></span>

<span data-ttu-id="fcf44-108">Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。</span><span class="sxs-lookup"><span data-stu-id="fcf44-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="fcf44-109">サポート要求を作成する前にデバッグ ログを用意すると、Microsoft は問題のトラブルシューティングをすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="fcf44-110">**メディア** ログ **またはデスクトップ** ログは、Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fcf44-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="fcf44-111">この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="fcf44-112">ただし、これらのログに対して生成されるファイルには、名前に診断 **ログという** 用語が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="fcf44-113">次の表は、さまざまなクライアントとその関連ログの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcf44-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="fcf44-114">ログ ファイルは、クライアントとオペレーティング システムに固有の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="fcf44-115">クライアント</span><span class="sxs-lookup"><span data-stu-id="fcf44-115">Client</span></span> |<span data-ttu-id="fcf44-116">デバッグ</span><span class="sxs-lookup"><span data-stu-id="fcf44-116">Debug</span></span>|<span data-ttu-id="fcf44-117">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="fcf44-117">Desktop</span></span>|<span data-ttu-id="fcf44-118">メディア</span><span class="sxs-lookup"><span data-stu-id="fcf44-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="fcf44-119">Web</span><span class="sxs-lookup"><span data-stu-id="fcf44-119">Web</span></span>    |<span data-ttu-id="fcf44-120">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-120">X</span></span>         |-         |-         |
|<span data-ttu-id="fcf44-121">Windows</span><span class="sxs-lookup"><span data-stu-id="fcf44-121">Windows</span></span>     |<span data-ttu-id="fcf44-122">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-122">X</span></span>         |<span data-ttu-id="fcf44-123">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-123">X</span></span>         |<span data-ttu-id="fcf44-124">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-124">X</span></span>         |
|<span data-ttu-id="fcf44-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fcf44-125">Mac OSX</span></span>     |<span data-ttu-id="fcf44-126">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-126">X</span></span>         |<span data-ttu-id="fcf44-127">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-127">X</span></span>         |<span data-ttu-id="fcf44-128">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-128">X</span></span>         |
|<span data-ttu-id="fcf44-129">Linux</span><span class="sxs-lookup"><span data-stu-id="fcf44-129">Linux</span></span>     |<span data-ttu-id="fcf44-130">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-130">X</span></span>         |<span data-ttu-id="fcf44-131">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-131">X</span></span>         |<span data-ttu-id="fcf44-132">X</span><span class="sxs-lookup"><span data-stu-id="fcf44-132">X</span></span>         |
|<span data-ttu-id="fcf44-133">iOS</span><span class="sxs-lookup"><span data-stu-id="fcf44-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="fcf44-134">Android</span><span class="sxs-lookup"><span data-stu-id="fcf44-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="fcf44-135">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fcf44-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="fcf44-136">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="fcf44-137">これらは最も一般的なログであり、すべての Microsoft サポート ケースで必要です。</span><span class="sxs-lookup"><span data-stu-id="fcf44-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="fcf44-138">デバッグ ログは、Windows および Mac のデスクトップ クライアントおよびブラウザー ベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="fcf44-139">ログはテキスト ベースで、下から読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="fcf44-140">任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="fcf44-141">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="fcf44-142">ログイン</span><span class="sxs-lookup"><span data-stu-id="fcf44-142">Login</span></span>

-   <span data-ttu-id="fcf44-143">中層サービスへの接続要求</span><span class="sxs-lookup"><span data-stu-id="fcf44-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="fcf44-144">通話/会話</span><span class="sxs-lookup"><span data-stu-id="fcf44-144">Call/conversation</span></span>

<span data-ttu-id="fcf44-145">デバッグ ログは、次の OS 固有のメソッドを使用して生成されます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="fcf44-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf44-146">Windows:</span></span>

      <span data-ttu-id="fcf44-147">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fcf44-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="fcf44-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="fcf44-148">Mac OSX:</span></span>

      <span data-ttu-id="fcf44-149">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fcf44-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="fcf44-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf44-150">Linux:</span></span>

      <span data-ttu-id="fcf44-151">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="fcf44-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="fcf44-152">デバッグ ログは、次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="fcf44-153">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="fcf44-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="fcf44-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fcf44-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="fcf44-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="fcf44-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="fcf44-156">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="fcf44-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="fcf44-157">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-157">Media logs</span></span>
---------------------------

<span data-ttu-id="fcf44-158">メディア ログには、Teams 会議での音声、ビデオ、画面共有に関する診断データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="fcf44-159">これらは、通話関連の問題にリンクされているサポート ケースに必要です。</span><span class="sxs-lookup"><span data-stu-id="fcf44-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="fcf44-160">メディア ログは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fcf44-160">Media logging is turned off by default.</span></span> <span data-ttu-id="fcf44-161">Teams 会議の診断データをログに記録するには、ユーザーが Teams クライアントでオプションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf44-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="fcf44-162">[設定全般 **]** に移動し、[会議の診断のログを有効にする (Teams の再起動が必要) ] チェック ボックスをオンにし、Teams を再起動して、  >  問題を再現します。 </span><span class="sxs-lookup"><span data-stu-id="fcf44-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="fcf44-163">次の表に、メディア ログの場所の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="fcf44-164">ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現したログの時間枠を確実にカバーしてください。</span><span class="sxs-lookup"><span data-stu-id="fcf44-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="fcf44-165">クライアント</span><span class="sxs-lookup"><span data-stu-id="fcf44-165">Client</span></span> |<span data-ttu-id="fcf44-166">場所</span><span class="sxs-lookup"><span data-stu-id="fcf44-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fcf44-167">Windows</span><span class="sxs-lookup"><span data-stu-id="fcf44-167">Windows</span></span>     |<span data-ttu-id="fcf44-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="fcf44-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="fcf44-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="fcf44-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="fcf44-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fcf44-171">Mac OSX</span></span>     |<span data-ttu-id="fcf44-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fcf44-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="fcf44-174">Linux</span><span class="sxs-lookup"><span data-stu-id="fcf44-174">Linux</span></span>       |<span data-ttu-id="fcf44-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="fcf44-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="fcf44-177">生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="fcf44-178">ログ ファイル名</span><span class="sxs-lookup"><span data-stu-id="fcf44-178">Log file name</span></span>  |<span data-ttu-id="fcf44-179">説明</span><span class="sxs-lookup"><span data-stu-id="fcf44-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fcf44-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="fcf44-181">メディア スタックに関連する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="fcf44-181">Contains information related to the media stack.</span></span> <span data-ttu-id="fcf44-182">これには、解像度、デコーダーとエンコーダー、送信および受信したフレーム数、カメラとビデオベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="fcf44-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="fcf44-184">コントロールを指定した場合のタイム スタンプ、マウス ポインター情報など、リモート コントロールの操作に関連する情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="fcf44-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="fcf44-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="fcf44-186">メディア スタックトレース イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="fcf44-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="fcf44-188">メディア エージェントに関連する情報 (レンダリング品質など) が含まれている。</span><span class="sxs-lookup"><span data-stu-id="fcf44-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="fcf44-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="fcf44-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="fcf44-190">ts 呼び出し API のイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="fcf44-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="fcf44-191">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="fcf44-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="fcf44-192">デスクトップ ログ (bootstrapper ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="fcf44-193">メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fcf44-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="fcf44-194">ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="fcf44-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="fcf44-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="fcf44-195">Windows:</span></span>

 - <span data-ttu-id="fcf44-196">システム トレイの **Microsoft Teams** アイコンを右クリックし、[ログの取得] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcf44-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="fcf44-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="fcf44-197">Mac OsX:</span></span>

 - <span data-ttu-id="fcf44-198">[ヘルプ **] プルダウン メニュー** から **[ログ** の取得] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcf44-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="fcf44-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="fcf44-199">Linux:</span></span>

 - <span data-ttu-id="fcf44-200">システム トレイの **Microsoft Teams** アイコンをクリックし、[ログの取得] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fcf44-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="fcf44-201">クライアント</span><span class="sxs-lookup"><span data-stu-id="fcf44-201">Client</span></span> |<span data-ttu-id="fcf44-202">場所</span><span class="sxs-lookup"><span data-stu-id="fcf44-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="fcf44-203">Windows</span><span class="sxs-lookup"><span data-stu-id="fcf44-203">Windows</span></span>     |<span data-ttu-id="fcf44-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="fcf44-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="fcf44-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="fcf44-205">Mac OSX</span></span>     |<span data-ttu-id="fcf44-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fcf44-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="fcf44-207">Linux</span><span class="sxs-lookup"><span data-stu-id="fcf44-207">Linux</span></span>       |<span data-ttu-id="fcf44-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="fcf44-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="fcf44-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcf44-209">Related topics</span></span>

[<span data-ttu-id="fcf44-210">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fcf44-210">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)