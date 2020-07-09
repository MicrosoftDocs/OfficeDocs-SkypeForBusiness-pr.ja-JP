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
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085753"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="7df67-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="7df67-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="7df67-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="7df67-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="7df67-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-105">Debug logs</span></span>

-   <span data-ttu-id="7df67-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-106">Media logs</span></span>

-   <span data-ttu-id="7df67-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-107">Desktop logs</span></span>

<span data-ttu-id="7df67-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="7df67-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="7df67-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="7df67-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="7df67-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7df67-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="7df67-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="7df67-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="7df67-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="7df67-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="7df67-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="7df67-113">Client</span></span> |<span data-ttu-id="7df67-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="7df67-114">Debug</span></span>|<span data-ttu-id="7df67-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7df67-115">Desktop</span></span>|<span data-ttu-id="7df67-116">メディア</span><span class="sxs-lookup"><span data-stu-id="7df67-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="7df67-117">Web</span><span class="sxs-lookup"><span data-stu-id="7df67-117">Web</span></span>    |<span data-ttu-id="7df67-118">X</span><span class="sxs-lookup"><span data-stu-id="7df67-118">X</span></span>         |-         |-         |
|<span data-ttu-id="7df67-119">Windows</span><span class="sxs-lookup"><span data-stu-id="7df67-119">Windows</span></span>     |<span data-ttu-id="7df67-120">X</span><span class="sxs-lookup"><span data-stu-id="7df67-120">X</span></span>         |<span data-ttu-id="7df67-121">X</span><span class="sxs-lookup"><span data-stu-id="7df67-121">X</span></span>         |<span data-ttu-id="7df67-122">X</span><span class="sxs-lookup"><span data-stu-id="7df67-122">X</span></span>         |
|<span data-ttu-id="7df67-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7df67-123">Mac OSX</span></span>     |<span data-ttu-id="7df67-124">X</span><span class="sxs-lookup"><span data-stu-id="7df67-124">X</span></span>         |<span data-ttu-id="7df67-125">X</span><span class="sxs-lookup"><span data-stu-id="7df67-125">X</span></span>         |<span data-ttu-id="7df67-126">X</span><span class="sxs-lookup"><span data-stu-id="7df67-126">X</span></span>         |
|<span data-ttu-id="7df67-127">Linux</span><span class="sxs-lookup"><span data-stu-id="7df67-127">Linux</span></span>     |<span data-ttu-id="7df67-128">X</span><span class="sxs-lookup"><span data-stu-id="7df67-128">X</span></span>         |<span data-ttu-id="7df67-129">X</span><span class="sxs-lookup"><span data-stu-id="7df67-129">X</span></span>         |<span data-ttu-id="7df67-130">X</span><span class="sxs-lookup"><span data-stu-id="7df67-130">X</span></span>         |
|<span data-ttu-id="7df67-131">iOS</span><span class="sxs-lookup"><span data-stu-id="7df67-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="7df67-132">Android</span><span class="sxs-lookup"><span data-stu-id="7df67-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="7df67-133">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7df67-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="7df67-134">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="7df67-135">これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。</span><span class="sxs-lookup"><span data-stu-id="7df67-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="7df67-136">デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="7df67-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="7df67-137">ログはテキストベースであり、最後から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="7df67-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="7df67-138">テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7df67-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="7df67-139">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7df67-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="7df67-140">ログイン</span><span class="sxs-lookup"><span data-stu-id="7df67-140">Login</span></span>

-   <span data-ttu-id="7df67-141">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="7df67-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="7df67-142">通話/会話</span><span class="sxs-lookup"><span data-stu-id="7df67-142">Call/conversation</span></span>

<span data-ttu-id="7df67-143">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="7df67-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="7df67-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="7df67-144">Windows:</span></span>

      <span data-ttu-id="7df67-145">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7df67-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="7df67-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="7df67-146">Mac OSX:</span></span>

      <span data-ttu-id="7df67-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7df67-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="7df67-148">走ら</span><span class="sxs-lookup"><span data-stu-id="7df67-148">Linux:</span></span>

      <span data-ttu-id="7df67-149">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="7df67-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="7df67-150">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7df67-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="7df67-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="7df67-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="7df67-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="7df67-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="7df67-153">Linux: ~/ダウンロード</span><span class="sxs-lookup"><span data-stu-id="7df67-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="7df67-154">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="7df67-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="7df67-155">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="7df67-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="7df67-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="7df67-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7df67-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="7df67-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="7df67-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="7df67-159">クライアント</span><span class="sxs-lookup"><span data-stu-id="7df67-159">Client</span></span> |<span data-ttu-id="7df67-160">場所</span><span class="sxs-lookup"><span data-stu-id="7df67-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7df67-161">Windows</span><span class="sxs-lookup"><span data-stu-id="7df67-161">Windows</span></span>     |<span data-ttu-id="7df67-162">%appdata%\Microsoft\Teams\media-stack \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="7df67-163">%appdata%\Microsoft\Teams\skylib \\ \*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="7df67-164">%appdata%\Microsoft\Teams\media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="7df67-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="7df67-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7df67-165">Mac OSX</span></span>     |<span data-ttu-id="7df67-166">~/Library/application support Support/Microsoft/Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="7df67-167">~/Library/application support Support/Microsoft/Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="7df67-168">Linux</span><span class="sxs-lookup"><span data-stu-id="7df67-168">Linux</span></span>       |<span data-ttu-id="7df67-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="7df67-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="7df67-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="7df67-171">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="7df67-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="7df67-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="7df67-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="7df67-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7df67-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="7df67-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="7df67-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="7df67-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="7df67-175">Windows:</span></span>

1.  <span data-ttu-id="7df67-176">システムトレイで**Microsoft Teams**アイコンを右クリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7df67-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="7df67-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="7df67-177">Mac OsX:</span></span>

1.  <span data-ttu-id="7df67-178">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="7df67-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="7df67-179">走ら</span><span class="sxs-lookup"><span data-stu-id="7df67-179">Linux:</span></span>

1.  <span data-ttu-id="7df67-180">システムトレイの**Microsoft Teams**アイコンをクリックし、[**ログの取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7df67-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="7df67-181">クライアント</span><span class="sxs-lookup"><span data-stu-id="7df67-181">Client</span></span> |<span data-ttu-id="7df67-182">場所</span><span class="sxs-lookup"><span data-stu-id="7df67-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="7df67-183">Windows</span><span class="sxs-lookup"><span data-stu-id="7df67-183">Windows</span></span>     |<span data-ttu-id="7df67-184">% appdata% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="7df67-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="7df67-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="7df67-185">Mac OSX</span></span>     |<span data-ttu-id="7df67-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7df67-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="7df67-187">Linux</span><span class="sxs-lookup"><span data-stu-id="7df67-187">Linux</span></span>       |<span data-ttu-id="7df67-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="7df67-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="7df67-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="7df67-189">Related topics</span></span>

[<span data-ttu-id="7df67-190">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7df67-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

