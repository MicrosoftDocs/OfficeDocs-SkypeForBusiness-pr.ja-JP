---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012193"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="9952b-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="9952b-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="9952b-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="9952b-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="9952b-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-105">Debug logs</span></span>

-   <span data-ttu-id="9952b-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-106">Media logs</span></span>

-   <span data-ttu-id="9952b-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-107">Desktop logs</span></span>

<span data-ttu-id="9952b-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="9952b-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="9952b-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="9952b-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="9952b-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9952b-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="9952b-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="9952b-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="9952b-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="9952b-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="9952b-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="9952b-113">Client</span></span> |<span data-ttu-id="9952b-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="9952b-114">Debug</span></span>|<span data-ttu-id="9952b-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="9952b-115">Desktop</span></span>|<span data-ttu-id="9952b-116">メディア</span><span class="sxs-lookup"><span data-stu-id="9952b-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="9952b-117">Web</span><span class="sxs-lookup"><span data-stu-id="9952b-117">Web</span></span>    |<span data-ttu-id="9952b-118">X</span><span class="sxs-lookup"><span data-stu-id="9952b-118">X</span></span>         |-         |-         |
|<span data-ttu-id="9952b-119">Windows</span><span class="sxs-lookup"><span data-stu-id="9952b-119">Windows</span></span>     |<span data-ttu-id="9952b-120">X</span><span class="sxs-lookup"><span data-stu-id="9952b-120">X</span></span>         |<span data-ttu-id="9952b-121">X</span><span class="sxs-lookup"><span data-stu-id="9952b-121">X</span></span>         |<span data-ttu-id="9952b-122">X</span><span class="sxs-lookup"><span data-stu-id="9952b-122">X</span></span>         |
|<span data-ttu-id="9952b-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9952b-123">Mac OSX</span></span>     |<span data-ttu-id="9952b-124">X</span><span class="sxs-lookup"><span data-stu-id="9952b-124">X</span></span>         |<span data-ttu-id="9952b-125">X</span><span class="sxs-lookup"><span data-stu-id="9952b-125">X</span></span>         |<span data-ttu-id="9952b-126">X</span><span class="sxs-lookup"><span data-stu-id="9952b-126">X</span></span>         |
|<span data-ttu-id="9952b-127">Linux</span><span class="sxs-lookup"><span data-stu-id="9952b-127">Linux</span></span>     |<span data-ttu-id="9952b-128">X</span><span class="sxs-lookup"><span data-stu-id="9952b-128">X</span></span>         |<span data-ttu-id="9952b-129">X</span><span class="sxs-lookup"><span data-stu-id="9952b-129">X</span></span>         |<span data-ttu-id="9952b-130">X</span><span class="sxs-lookup"><span data-stu-id="9952b-130">X</span></span>         |
|<span data-ttu-id="9952b-131">iOS</span><span class="sxs-lookup"><span data-stu-id="9952b-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="9952b-132">Android</span><span class="sxs-lookup"><span data-stu-id="9952b-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="9952b-133">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9952b-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="9952b-134">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="9952b-135">これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。</span><span class="sxs-lookup"><span data-stu-id="9952b-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="9952b-136">デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="9952b-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="9952b-137">ログはテキストベースであり、最後から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="9952b-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="9952b-138">テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9952b-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="9952b-139">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9952b-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="9952b-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="9952b-140">Login</span></span>

-   <span data-ttu-id="9952b-141">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="9952b-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="9952b-142">通話/会話</span><span class="sxs-lookup"><span data-stu-id="9952b-142">Call/conversation</span></span>

<span data-ttu-id="9952b-143">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="9952b-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="9952b-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="9952b-144">Windows:</span></span>

      <span data-ttu-id="9952b-145">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="9952b-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="9952b-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="9952b-146">Mac OSX:</span></span>

      <span data-ttu-id="9952b-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="9952b-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="9952b-148">走ら</span><span class="sxs-lookup"><span data-stu-id="9952b-148">Linux:</span></span>

      <span data-ttu-id="9952b-149">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="9952b-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="9952b-150">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="9952b-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="9952b-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="9952b-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="9952b-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="9952b-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="9952b-153">Linux: ~/ダウンロード</span><span class="sxs-lookup"><span data-stu-id="9952b-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="9952b-154">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="9952b-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="9952b-155">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="9952b-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="9952b-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="9952b-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9952b-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="9952b-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="9952b-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="9952b-159">クライアント</span><span class="sxs-lookup"><span data-stu-id="9952b-159">Client</span></span> |<span data-ttu-id="9952b-160">場所</span><span class="sxs-lookup"><span data-stu-id="9952b-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9952b-161">Windows</span><span class="sxs-lookup"><span data-stu-id="9952b-161">Windows</span></span>     |<span data-ttu-id="9952b-162">%appdata%\Microsoft\Teams\media-stack \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="9952b-163">%appdata%\Microsoft\Teams\skylib \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="9952b-164">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="9952b-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="9952b-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9952b-165">Mac OSX</span></span>     |<span data-ttu-id="9952b-166">~/Library/application support Support/Microsoft/Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="9952b-167">~/Library/application support Support/Microsoft/Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="9952b-168">Linux</span><span class="sxs-lookup"><span data-stu-id="9952b-168">Linux</span></span>       |<span data-ttu-id="9952b-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="9952b-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="9952b-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="9952b-171">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="9952b-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="9952b-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="9952b-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="9952b-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9952b-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="9952b-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="9952b-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="9952b-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="9952b-175">Windows:</span></span>

1.  <span data-ttu-id="9952b-176">システムトレイで**Microsoft Teams**アイコンを右クリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9952b-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="9952b-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="9952b-177">Mac OsX:</span></span>

1.  <span data-ttu-id="9952b-178">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="9952b-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="9952b-179">走ら</span><span class="sxs-lookup"><span data-stu-id="9952b-179">Linux:</span></span>

1.  <span data-ttu-id="9952b-180">システムトレイの**Microsoft Teams**アイコンをクリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9952b-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="9952b-181">クライアント</span><span class="sxs-lookup"><span data-stu-id="9952b-181">Client</span></span> |<span data-ttu-id="9952b-182">場所</span><span class="sxs-lookup"><span data-stu-id="9952b-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9952b-183">Windows</span><span class="sxs-lookup"><span data-stu-id="9952b-183">Windows</span></span>     |<span data-ttu-id="9952b-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="9952b-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="9952b-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9952b-185">Mac OSX</span></span>     |<span data-ttu-id="9952b-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="9952b-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="9952b-187">Linux</span><span class="sxs-lookup"><span data-stu-id="9952b-187">Linux</span></span>       |<span data-ttu-id="9952b-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="9952b-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
