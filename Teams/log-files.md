---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a14d6db6c03b540a6495b9028a4f0342ff92636
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716336"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="484e4-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="484e4-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="484e4-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="484e4-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="484e4-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-105">Debug logs</span></span>

-   <span data-ttu-id="484e4-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-106">Media logs</span></span>

-   <span data-ttu-id="484e4-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-107">Desktop logs</span></span>

<span data-ttu-id="484e4-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="484e4-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="484e4-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="484e4-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="484e4-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="484e4-113">Client</span></span> |<span data-ttu-id="484e4-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="484e4-114">Debug</span></span>|<span data-ttu-id="484e4-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="484e4-115">Desktop</span></span>|<span data-ttu-id="484e4-116">メディア</span><span class="sxs-lookup"><span data-stu-id="484e4-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="484e4-117">Web</span><span class="sxs-lookup"><span data-stu-id="484e4-117">Web</span></span>    |<span data-ttu-id="484e4-118">X</span><span class="sxs-lookup"><span data-stu-id="484e4-118">X</span></span>         |-         |-         |
|<span data-ttu-id="484e4-119">Windows</span><span class="sxs-lookup"><span data-stu-id="484e4-119">Windows</span></span>     |<span data-ttu-id="484e4-120">X</span><span class="sxs-lookup"><span data-stu-id="484e4-120">X</span></span>         |<span data-ttu-id="484e4-121">X</span><span class="sxs-lookup"><span data-stu-id="484e4-121">X</span></span>         |<span data-ttu-id="484e4-122">X</span><span class="sxs-lookup"><span data-stu-id="484e4-122">X</span></span>         |
|<span data-ttu-id="484e4-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="484e4-123">Mac OSX</span></span>     |<span data-ttu-id="484e4-124">X</span><span class="sxs-lookup"><span data-stu-id="484e4-124">X</span></span>         |<span data-ttu-id="484e4-125">X</span><span class="sxs-lookup"><span data-stu-id="484e4-125">X</span></span>         |<span data-ttu-id="484e4-126">X</span><span class="sxs-lookup"><span data-stu-id="484e4-126">X</span></span>         |
|<span data-ttu-id="484e4-127">iOS</span><span class="sxs-lookup"><span data-stu-id="484e4-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="484e4-128">Android</span><span class="sxs-lookup"><span data-stu-id="484e4-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="484e4-129">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="484e4-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="484e4-130">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="484e4-131">これらは最も一般的なログであり、すべてのマイクロソフトのサポートの場合に必要な。</span><span class="sxs-lookup"><span data-stu-id="484e4-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="484e4-132">デバッグ ログは、Windows と Mac のデスクトップ クライアントとブラウザー ベースのクライアントによって作成されました。</span><span class="sxs-lookup"><span data-stu-id="484e4-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="484e4-133">ログは、テキスト ベースを下から読み終えています。</span><span class="sxs-lookup"><span data-stu-id="484e4-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="484e4-134">任意のテキスト ベースのエディターを使用して読み取ることができ、クライアントへのログイン時に新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="484e4-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="484e4-135">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="484e4-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="484e4-136">ログイン</span><span class="sxs-lookup"><span data-stu-id="484e4-136">Login</span></span>

-   <span data-ttu-id="484e4-137">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="484e4-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="484e4-138">通話/会話</span><span class="sxs-lookup"><span data-stu-id="484e4-138">Call/conversation</span></span>

<span data-ttu-id="484e4-139">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="484e4-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="484e4-140">Windows:</span><span class="sxs-lookup"><span data-stu-id="484e4-140">Windows:</span></span>

    1.  <span data-ttu-id="484e4-141">アプリケーション トレイの **Microsoft Teams アイコン**をクリックし、[**Get Logs (ログを取得)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="484e4-141">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="484e4-142">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="484e4-142">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="484e4-143">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="484e4-143">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="484e4-144">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="484e4-144">Mac OSX:</span></span>

    1.  <span data-ttu-id="484e4-145">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="484e4-145">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="484e4-146">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="484e4-146">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="484e4-147">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="484e4-147">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="484e4-148">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="484e4-148">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="484e4-149">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="484e4-149">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="484e4-150">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="484e4-150">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="484e4-151">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-151">Media Logs</span></span>
---------------------------

<span data-ttu-id="484e4-p104">メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="484e4-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="484e4-155">クライアント</span><span class="sxs-lookup"><span data-stu-id="484e4-155">Client</span></span> |<span data-ttu-id="484e4-156">場所</span><span class="sxs-lookup"><span data-stu-id="484e4-156">Location</span></span> |
|---------|---------|
|<span data-ttu-id="484e4-157">Windows</span><span class="sxs-lookup"><span data-stu-id="484e4-157">Windows</span></span>     |<span data-ttu-id="484e4-158">%appdata%\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="484e4-158">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="484e4-159">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="484e4-159">Mac OSX</span></span>     |<span data-ttu-id="484e4-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="484e4-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="484e4-161">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="484e4-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="484e4-p105">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="484e4-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="484e4-165">クライアント</span><span class="sxs-lookup"><span data-stu-id="484e4-165">Client</span></span> |<span data-ttu-id="484e4-166">場所</span><span class="sxs-lookup"><span data-stu-id="484e4-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="484e4-167">Windows</span><span class="sxs-lookup"><span data-stu-id="484e4-167">Windows</span></span>     |<span data-ttu-id="484e4-168">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="484e4-168">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="484e4-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="484e4-169">Mac OSX</span></span>     |<span data-ttu-id="484e4-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="484e4-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
