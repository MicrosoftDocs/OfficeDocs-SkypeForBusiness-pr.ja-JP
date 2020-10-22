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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650830"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="4bc8f-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="4bc8f-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="4bc8f-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="4bc8f-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-105">Debug logs</span></span>

-   <span data-ttu-id="4bc8f-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-106">Media logs</span></span>

-   <span data-ttu-id="4bc8f-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-107">Desktop logs</span></span>

<span data-ttu-id="4bc8f-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="4bc8f-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="4bc8f-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="4bc8f-113">Client</span></span> |<span data-ttu-id="4bc8f-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-114">Debug</span></span>|<span data-ttu-id="4bc8f-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-115">Desktop</span></span>|<span data-ttu-id="4bc8f-116">メディア</span><span class="sxs-lookup"><span data-stu-id="4bc8f-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="4bc8f-117">Web</span><span class="sxs-lookup"><span data-stu-id="4bc8f-117">Web</span></span>    |<span data-ttu-id="4bc8f-118">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-118">X</span></span>         |-         |-         |
|<span data-ttu-id="4bc8f-119">Windows</span><span class="sxs-lookup"><span data-stu-id="4bc8f-119">Windows</span></span>     |<span data-ttu-id="4bc8f-120">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-120">X</span></span>         |<span data-ttu-id="4bc8f-121">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-121">X</span></span>         |<span data-ttu-id="4bc8f-122">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-122">X</span></span>         |
|<span data-ttu-id="4bc8f-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4bc8f-123">Mac OSX</span></span>     |<span data-ttu-id="4bc8f-124">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-124">X</span></span>         |<span data-ttu-id="4bc8f-125">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-125">X</span></span>         |<span data-ttu-id="4bc8f-126">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-126">X</span></span>         |
|<span data-ttu-id="4bc8f-127">Linux</span><span class="sxs-lookup"><span data-stu-id="4bc8f-127">Linux</span></span>     |<span data-ttu-id="4bc8f-128">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-128">X</span></span>         |<span data-ttu-id="4bc8f-129">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-129">X</span></span>         |<span data-ttu-id="4bc8f-130">X</span><span class="sxs-lookup"><span data-stu-id="4bc8f-130">X</span></span>         |
|<span data-ttu-id="4bc8f-131">iOS</span><span class="sxs-lookup"><span data-stu-id="4bc8f-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="4bc8f-132">Android</span><span class="sxs-lookup"><span data-stu-id="4bc8f-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="4bc8f-133">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="4bc8f-134">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="4bc8f-135">これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="4bc8f-136">デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="4bc8f-137">ログはテキストベースであり、最後から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="4bc8f-138">テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="4bc8f-139">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="4bc8f-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="4bc8f-140">Login</span></span>

-   <span data-ttu-id="4bc8f-141">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="4bc8f-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="4bc8f-142">通話/会話</span><span class="sxs-lookup"><span data-stu-id="4bc8f-142">Call/conversation</span></span>

<span data-ttu-id="4bc8f-143">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="4bc8f-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="4bc8f-144">Windows:</span></span>

      <span data-ttu-id="4bc8f-145">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4bc8f-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="4bc8f-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="4bc8f-146">Mac OSX:</span></span>

      <span data-ttu-id="4bc8f-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4bc8f-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="4bc8f-148">走ら</span><span class="sxs-lookup"><span data-stu-id="4bc8f-148">Linux:</span></span>

      <span data-ttu-id="4bc8f-149">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4bc8f-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="4bc8f-150">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="4bc8f-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="4bc8f-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="4bc8f-152">Mac OSX: ~/ダウンロード</span><span class="sxs-lookup"><span data-stu-id="4bc8f-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="4bc8f-153">Linux: ~/ダウンロード</span><span class="sxs-lookup"><span data-stu-id="4bc8f-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="4bc8f-154">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="4bc8f-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="4bc8f-155">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-155">Media logs</span></span>
---------------------------

<span data-ttu-id="4bc8f-156">メディアログには、Teams 会議でのオーディオ、ビデオ、画面共有に関する診断データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="4bc8f-157">これは、通話関連の問題にリンクされているサポートケースに必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="4bc8f-158">メディアログは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-158">Media logging is turned off by default.</span></span> <span data-ttu-id="4bc8f-159">Teams 会議の診断データをログに記録するには、ユーザーは Teams クライアントでオプションをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="4bc8f-160">[**設定**全般] に移動し、[  >  **General\*\*\*\*会議の診断のためのログを有効にする (チームの再起動が必要**)] チェックボックスをオンにして、チームを再起動し、問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="4bc8f-161">次の表に、メディアログの場所の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="4bc8f-162">ログファイルを Microsoft サポートに送信する場合は、ログファイルのタイムスタンプを確認して、問題を再現したときにログがその期間に対応していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="4bc8f-163">クライアント</span><span class="sxs-lookup"><span data-stu-id="4bc8f-163">Client</span></span> |<span data-ttu-id="4bc8f-164">場所</span><span class="sxs-lookup"><span data-stu-id="4bc8f-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4bc8f-165">Windows</span><span class="sxs-lookup"><span data-stu-id="4bc8f-165">Windows</span></span>     |<span data-ttu-id="4bc8f-166">%appdata%\Microsoft\Teams\media-stack \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="4bc8f-167">%appdata%\Microsoft\Teams\skylib \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="4bc8f-168">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="4bc8f-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="4bc8f-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4bc8f-169">Mac OSX</span></span>     |<span data-ttu-id="4bc8f-170">~/Library/application support Support/Microsoft/Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4bc8f-171">~/Library/application support Support/Microsoft/Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="4bc8f-172">Linux</span><span class="sxs-lookup"><span data-stu-id="4bc8f-172">Linux</span></span>       |<span data-ttu-id="4bc8f-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4bc8f-174">~/.config/Microsoft/Microsoft Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="4bc8f-175">生成されるログファイルとそれらに含まれる情報の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="4bc8f-176">ログファイル名</span><span class="sxs-lookup"><span data-stu-id="4bc8f-176">Log file name</span></span>  |<span data-ttu-id="4bc8f-177">説明</span><span class="sxs-lookup"><span data-stu-id="4bc8f-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4bc8f-178">Teams. msrtc-0-s1039525249</span><span class="sxs-lookup"><span data-stu-id="4bc8f-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="4bc8f-179">メディアスタックに関連する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-179">Contains information related to the media stack.</span></span> <span data-ttu-id="4bc8f-180">これには、解像度、デコーダー、使用されるエンコーダー、送受信されたフレーム数、カメラおよびビデオベースの画面共有 (VBSS) セッション状態などのチャネル状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="4bc8f-181">rtmcontrol. msrtc-0-2415069487</span><span class="sxs-lookup"><span data-stu-id="4bc8f-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="4bc8f-182">コントロールが指定されているときのタイムスタンプやマウスポインター情報など、リモートコントロールの操作に関連する情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="4bc8f-183">-2-U-xr-U の Teams_MediaStackETW</span><span class="sxs-lookup"><span data-stu-id="4bc8f-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="4bc8f-184">メディアスタックトレースイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="4bc8f-185">Debug-0-s2790420889</span><span class="sxs-lookup"><span data-stu-id="4bc8f-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="4bc8f-186">レンダリング品質など、メディアエージェントに関連する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="4bc8f-187">tscalling-0-2061129496</span><span class="sxs-lookup"><span data-stu-id="4bc8f-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="4bc8f-188">Ts API のイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="4bc8f-189">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="4bc8f-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="4bc8f-p108">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-p108">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="4bc8f-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="4bc8f-193">Windows:</span></span>

1.  <span data-ttu-id="4bc8f-194">システムトレイで**Microsoft Teams**アイコンを右クリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="4bc8f-195">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="4bc8f-195">Mac OsX:</span></span>

1.  <span data-ttu-id="4bc8f-196">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="4bc8f-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="4bc8f-197">走ら</span><span class="sxs-lookup"><span data-stu-id="4bc8f-197">Linux:</span></span>

1.  <span data-ttu-id="4bc8f-198">システムトレイの**Microsoft Teams**アイコンをクリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bc8f-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="4bc8f-199">クライアント</span><span class="sxs-lookup"><span data-stu-id="4bc8f-199">Client</span></span> |<span data-ttu-id="4bc8f-200">場所</span><span class="sxs-lookup"><span data-stu-id="4bc8f-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4bc8f-201">Windows</span><span class="sxs-lookup"><span data-stu-id="4bc8f-201">Windows</span></span>     |<span data-ttu-id="4bc8f-202">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="4bc8f-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="4bc8f-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4bc8f-203">Mac OSX</span></span>     |<span data-ttu-id="4bc8f-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4bc8f-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="4bc8f-205">Linux</span><span class="sxs-lookup"><span data-stu-id="4bc8f-205">Linux</span></span>       |<span data-ttu-id="4bc8f-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4bc8f-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="4bc8f-207">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4bc8f-207">Related topics</span></span>

[<span data-ttu-id="4bc8f-208">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4bc8f-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
