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
ms.openlocfilehash: 95d28bac036476c417ccbe7929a23ab9fb37f3a8
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018901"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="ffeae-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="ffeae-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="ffeae-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="ffeae-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-105">Debug logs</span></span>

-   <span data-ttu-id="ffeae-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-106">Media logs</span></span>

-   <span data-ttu-id="ffeae-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-107">Desktop logs</span></span>

<span data-ttu-id="ffeae-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ffeae-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="ffeae-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ffeae-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="ffeae-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="ffeae-113">Client</span></span> |<span data-ttu-id="ffeae-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ffeae-114">Debug</span></span>|<span data-ttu-id="ffeae-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="ffeae-115">Desktop</span></span>|<span data-ttu-id="ffeae-116">メディア</span><span class="sxs-lookup"><span data-stu-id="ffeae-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="ffeae-117">Web</span><span class="sxs-lookup"><span data-stu-id="ffeae-117">Web</span></span>    |<span data-ttu-id="ffeae-118">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-118">X</span></span>         |-         |-         |
|<span data-ttu-id="ffeae-119">Windows</span><span class="sxs-lookup"><span data-stu-id="ffeae-119">Windows</span></span>     |<span data-ttu-id="ffeae-120">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-120">X</span></span>         |<span data-ttu-id="ffeae-121">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-121">X</span></span>         |<span data-ttu-id="ffeae-122">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-122">X</span></span>         |
|<span data-ttu-id="ffeae-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ffeae-123">Mac OSX</span></span>     |<span data-ttu-id="ffeae-124">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-124">X</span></span>         |<span data-ttu-id="ffeae-125">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-125">X</span></span>         |<span data-ttu-id="ffeae-126">X</span><span class="sxs-lookup"><span data-stu-id="ffeae-126">X</span></span>         |
|<span data-ttu-id="ffeae-127">iOS</span><span class="sxs-lookup"><span data-stu-id="ffeae-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="ffeae-128">Android</span><span class="sxs-lookup"><span data-stu-id="ffeae-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="ffeae-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ffeae-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="ffeae-130">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ffeae-130">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="ffeae-131">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="ffeae-132">これらは最も一般的なログであり、すべてのマイクロソフトのサポートの場合に必要な。</span><span class="sxs-lookup"><span data-stu-id="ffeae-132">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="ffeae-133">デバッグ ログは、Windows と Mac のデスクトップ クライアントとブラウザー ベースのクライアントによって作成されました。</span><span class="sxs-lookup"><span data-stu-id="ffeae-133">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="ffeae-134">ログは、テキスト ベースを下から読み終えています。</span><span class="sxs-lookup"><span data-stu-id="ffeae-134">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="ffeae-135">任意のテキスト ベースのエディターを使用して読み取ることができ、クライアントへのログイン時に新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-135">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="ffeae-136">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="ffeae-137">ログイン</span><span class="sxs-lookup"><span data-stu-id="ffeae-137">Login</span></span>

-   <span data-ttu-id="ffeae-138">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="ffeae-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="ffeae-139">通話/会話</span><span class="sxs-lookup"><span data-stu-id="ffeae-139">Call/conversation</span></span>

<span data-ttu-id="ffeae-140">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="ffeae-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="ffeae-141">Windows:</span></span>

    1.  <span data-ttu-id="ffeae-142">アプリケーション トレイの **Microsoft Teams アイコン**をクリックし、[**Get Logs (ログを取得)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffeae-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="ffeae-143">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="ffeae-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="ffeae-144">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="ffeae-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="ffeae-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="ffeae-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="ffeae-146">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="ffeae-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="ffeae-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="ffeae-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="ffeae-148">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="ffeae-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="ffeae-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="ffeae-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="ffeae-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="ffeae-151">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="ffeae-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="ffeae-152">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="ffeae-p104">メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="ffeae-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="ffeae-156">クライアント</span><span class="sxs-lookup"><span data-stu-id="ffeae-156">Client</span></span> |<span data-ttu-id="ffeae-157">場所</span><span class="sxs-lookup"><span data-stu-id="ffeae-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="ffeae-158">Windows</span><span class="sxs-lookup"><span data-stu-id="ffeae-158">Windows</span></span>     |<span data-ttu-id="ffeae-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="ffeae-159">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="ffeae-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ffeae-160">Mac OSX</span></span>     |<span data-ttu-id="ffeae-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="ffeae-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="ffeae-162">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="ffeae-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="ffeae-p105">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="ffeae-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="ffeae-166">クライアント</span><span class="sxs-lookup"><span data-stu-id="ffeae-166">Client</span></span> |<span data-ttu-id="ffeae-167">場所</span><span class="sxs-lookup"><span data-stu-id="ffeae-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="ffeae-168">Windows</span><span class="sxs-lookup"><span data-stu-id="ffeae-168">Windows</span></span>     |<span data-ttu-id="ffeae-169">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="ffeae-169">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="ffeae-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ffeae-170">Mac OSX</span></span>     |<span data-ttu-id="ffeae-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="ffeae-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
