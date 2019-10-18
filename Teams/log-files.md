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
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba40d1d3694666f8fd0b4612ffe53c49808f7297
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37564925"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="b5d21-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="b5d21-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="b5d21-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="b5d21-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-105">Debug logs</span></span>

-   <span data-ttu-id="b5d21-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-106">Media logs</span></span>

-   <span data-ttu-id="b5d21-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-107">Desktop logs</span></span>

<span data-ttu-id="b5d21-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="b5d21-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="b5d21-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b5d21-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b5d21-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="b5d21-113">Client</span></span> |<span data-ttu-id="b5d21-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="b5d21-114">Debug</span></span>|<span data-ttu-id="b5d21-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="b5d21-115">Desktop</span></span>|<span data-ttu-id="b5d21-116">メディア</span><span class="sxs-lookup"><span data-stu-id="b5d21-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b5d21-117">Web</span><span class="sxs-lookup"><span data-stu-id="b5d21-117">Web</span></span>    |<span data-ttu-id="b5d21-118">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-118">X</span></span>         |-         |-         |
|<span data-ttu-id="b5d21-119">Windows</span><span class="sxs-lookup"><span data-stu-id="b5d21-119">Windows</span></span>     |<span data-ttu-id="b5d21-120">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-120">X</span></span>         |<span data-ttu-id="b5d21-121">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-121">X</span></span>         |<span data-ttu-id="b5d21-122">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-122">X</span></span>         |
|<span data-ttu-id="b5d21-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5d21-123">Mac OSX</span></span>     |<span data-ttu-id="b5d21-124">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-124">X</span></span>         |<span data-ttu-id="b5d21-125">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-125">X</span></span>         |<span data-ttu-id="b5d21-126">X</span><span class="sxs-lookup"><span data-stu-id="b5d21-126">X</span></span>         |
|<span data-ttu-id="b5d21-127">iOS</span><span class="sxs-lookup"><span data-stu-id="b5d21-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b5d21-128">Android</span><span class="sxs-lookup"><span data-stu-id="b5d21-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b5d21-129">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5d21-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="b5d21-130">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="b5d21-131">これらは最も一般的なログであり、Microsoft のすべてのサポート案件に必要です。</span><span class="sxs-lookup"><span data-stu-id="b5d21-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="b5d21-132">デバッグログは、Windows と Mac のデスクトップクライアントだけでなく、ブラウザーベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="b5d21-133">ログはテキストベースであり、最後から読み取られます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="b5d21-134">テキストベースのエディターを使って読むことができます。また、クライアントにログインすると、新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b5d21-135">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b5d21-136">ログイン</span><span class="sxs-lookup"><span data-stu-id="b5d21-136">Login</span></span>

-   <span data-ttu-id="b5d21-137">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="b5d21-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="b5d21-138">通話/会話</span><span class="sxs-lookup"><span data-stu-id="b5d21-138">Call/conversation</span></span>

<span data-ttu-id="b5d21-139">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="b5d21-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5d21-140">Windows:</span></span>

      <span data-ttu-id="b5d21-141">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="b5d21-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="b5d21-142">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="b5d21-142">Mac OSX:</span></span>

      <span data-ttu-id="b5d21-143">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="b5d21-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="b5d21-144">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="b5d21-145">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="b5d21-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="b5d21-146">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="b5d21-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="b5d21-147">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="b5d21-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="b5d21-148">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="b5d21-p104">メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="b5d21-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="b5d21-152">クライアント</span><span class="sxs-lookup"><span data-stu-id="b5d21-152">Client</span></span> |<span data-ttu-id="b5d21-153">場所</span><span class="sxs-lookup"><span data-stu-id="b5d21-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5d21-154">Windows</span><span class="sxs-lookup"><span data-stu-id="b5d21-154">Windows</span></span>     |<span data-ttu-id="b5d21-155">%appdata%\Microsoft\Teams\media-stack\\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-155">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="b5d21-156">%appdata%\Microsoft\Teams\skylib\\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-156">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="b5d21-157">%appdata%\Microsoft\Teams\media-stack\\* .etl</span><span class="sxs-lookup"><span data-stu-id="b5d21-157">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="b5d21-158">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5d21-158">Mac OSX</span></span>     |<span data-ttu-id="b5d21-159">~/Library/application support Support/Microsoft/Teams/media-stack/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-159">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b5d21-160">~/Library/application support Support/Microsoft/Teams/skylib/\*. ブログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-160">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="b5d21-161">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="b5d21-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="b5d21-p105">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d21-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="b5d21-165">Windows:</span><span class="sxs-lookup"><span data-stu-id="b5d21-165">Windows:</span></span>

1.  <span data-ttu-id="b5d21-166">アプリケーション トレイの **Microsoft Teams アイコン**をクリックし、[**Get Logs (ログを取得)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5d21-166">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

<span data-ttu-id="b5d21-167">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="b5d21-167">Mac OsX:</span></span>

1.  <span data-ttu-id="b5d21-168">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="b5d21-168">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="b5d21-169">クライアント</span><span class="sxs-lookup"><span data-stu-id="b5d21-169">Client</span></span> |<span data-ttu-id="b5d21-170">場所</span><span class="sxs-lookup"><span data-stu-id="b5d21-170">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b5d21-171">Windows</span><span class="sxs-lookup"><span data-stu-id="b5d21-171">Windows</span></span>     |<span data-ttu-id="b5d21-172">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5d21-172">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="b5d21-173">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b5d21-173">Mac OSX</span></span>     |<span data-ttu-id="b5d21-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b5d21-174">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
