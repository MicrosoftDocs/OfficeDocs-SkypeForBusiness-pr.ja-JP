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
ms.openlocfilehash: f13acc1a401a6753b335c17fe0cd8a7984849216
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582114"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="7d766-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="7d766-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="7d766-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="7d766-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="7d766-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-105">Debug logs</span></span>

-   <span data-ttu-id="7d766-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-106">Media logs</span></span>

-   <span data-ttu-id="7d766-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-107">Desktop logs</span></span>

<span data-ttu-id="7d766-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="7d766-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="7d766-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7d766-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="7d766-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="7d766-113">Client</span></span> |<span data-ttu-id="7d766-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7d766-114">Debug</span></span>|<span data-ttu-id="7d766-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7d766-115">Desktop</span></span>|<span data-ttu-id="7d766-116">メディア</span><span class="sxs-lookup"><span data-stu-id="7d766-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="7d766-117">Web</span><span class="sxs-lookup"><span data-stu-id="7d766-117">Web</span></span>    |<span data-ttu-id="7d766-118">X</span><span class="sxs-lookup"><span data-stu-id="7d766-118">X</span></span>         |-         |-         |
|<span data-ttu-id="7d766-119">Windows</span><span class="sxs-lookup"><span data-stu-id="7d766-119">Windows</span></span>     |<span data-ttu-id="7d766-120">X</span><span class="sxs-lookup"><span data-stu-id="7d766-120">X</span></span>         |<span data-ttu-id="7d766-121">X</span><span class="sxs-lookup"><span data-stu-id="7d766-121">X</span></span>         |<span data-ttu-id="7d766-122">X</span><span class="sxs-lookup"><span data-stu-id="7d766-122">X</span></span>         |
|<span data-ttu-id="7d766-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7d766-123">Mac OSX</span></span>     |<span data-ttu-id="7d766-124">X</span><span class="sxs-lookup"><span data-stu-id="7d766-124">X</span></span>         |<span data-ttu-id="7d766-125">X</span><span class="sxs-lookup"><span data-stu-id="7d766-125">X</span></span>         |<span data-ttu-id="7d766-126">X</span><span class="sxs-lookup"><span data-stu-id="7d766-126">X</span></span>         |
|<span data-ttu-id="7d766-127">Linux</span><span class="sxs-lookup"><span data-stu-id="7d766-127">Linux</span></span>     |<span data-ttu-id="7d766-128">X</span><span class="sxs-lookup"><span data-stu-id="7d766-128">X</span></span>         |<span data-ttu-id="7d766-129">X</span><span class="sxs-lookup"><span data-stu-id="7d766-129">X</span></span>         |<span data-ttu-id="7d766-130">X</span><span class="sxs-lookup"><span data-stu-id="7d766-130">X</span></span>         |
|<span data-ttu-id="7d766-131">iOS</span><span class="sxs-lookup"><span data-stu-id="7d766-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="7d766-132">Android</span><span class="sxs-lookup"><span data-stu-id="7d766-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="7d766-133">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7d766-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="7d766-134">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="7d766-135">これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。</span><span class="sxs-lookup"><span data-stu-id="7d766-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="7d766-136">デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="7d766-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="7d766-137">ログはテキストベースであり、最後から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="7d766-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="7d766-138">テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d766-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="7d766-139">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d766-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="7d766-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="7d766-140">Login</span></span>

-   <span data-ttu-id="7d766-141">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="7d766-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="7d766-142">通話/会話</span><span class="sxs-lookup"><span data-stu-id="7d766-142">Call/conversation</span></span>

<span data-ttu-id="7d766-143">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="7d766-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="7d766-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="7d766-144">Windows:</span></span>

      <span data-ttu-id="7d766-145">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7d766-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="7d766-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="7d766-146">Mac OSX:</span></span>

      <span data-ttu-id="7d766-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7d766-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="7d766-148">走ら</span><span class="sxs-lookup"><span data-stu-id="7d766-148">Linux:</span></span>

      <span data-ttu-id="7d766-149">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7d766-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="7d766-150">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7d766-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="7d766-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="7d766-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="7d766-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="7d766-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="7d766-153">Linux: ~/ダウンロード</span><span class="sxs-lookup"><span data-stu-id="7d766-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="7d766-154">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="7d766-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="7d766-155">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="7d766-p104">メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="7d766-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="7d766-159">クライアント</span><span class="sxs-lookup"><span data-stu-id="7d766-159">Client</span></span> |<span data-ttu-id="7d766-160">場所</span><span class="sxs-lookup"><span data-stu-id="7d766-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7d766-161">Windows</span><span class="sxs-lookup"><span data-stu-id="7d766-161">Windows</span></span>     |<span data-ttu-id="7d766-162">%appdata%\Microsoft\Teams\media-stack \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="7d766-163">%appdata%\Microsoft\Teams\skylib \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="7d766-164">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="7d766-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="7d766-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7d766-165">Mac OSX</span></span>     |<span data-ttu-id="7d766-166">~/Library/application support Support/Microsoft/Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="7d766-167">~/Library/application support Support/Microsoft/Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="7d766-168">Linux</span><span class="sxs-lookup"><span data-stu-id="7d766-168">Linux</span></span>       |<span data-ttu-id="7d766-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="7d766-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7d766-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="7d766-171">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="7d766-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="7d766-p105">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="7d766-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="7d766-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="7d766-175">Windows:</span></span>

1.  <span data-ttu-id="7d766-176">システムトレイで**Microsoft Teams**アイコンを右クリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d766-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="7d766-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="7d766-177">Mac OsX:</span></span>

1.  <span data-ttu-id="7d766-178">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="7d766-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="7d766-179">走ら</span><span class="sxs-lookup"><span data-stu-id="7d766-179">Linux:</span></span>

1.  <span data-ttu-id="7d766-180">システムトレイの**Microsoft Teams**アイコンをクリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7d766-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="7d766-181">クライアント</span><span class="sxs-lookup"><span data-stu-id="7d766-181">Client</span></span> |<span data-ttu-id="7d766-182">場所</span><span class="sxs-lookup"><span data-stu-id="7d766-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7d766-183">Windows</span><span class="sxs-lookup"><span data-stu-id="7d766-183">Windows</span></span>     |<span data-ttu-id="7d766-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="7d766-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="7d766-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7d766-185">Mac OSX</span></span>     |<span data-ttu-id="7d766-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7d766-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="7d766-187">Linux</span><span class="sxs-lookup"><span data-stu-id="7d766-187">Linux</span></span>       |<span data-ttu-id="7d766-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7d766-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="7d766-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7d766-189">Related topics</span></span>

[<span data-ttu-id="7d766-190">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7d766-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

