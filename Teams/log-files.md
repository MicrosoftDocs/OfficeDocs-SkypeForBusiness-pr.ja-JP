---
title: "Microsoft Teams のトラブルシューティングでログ ファイルを使用する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams によって生成されるデバッグ ログ、メディア ログ、デスクトップ ログ、これらのログの場所、トラブルシューティングでのログの活用について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 4c6ebf84a117aaa4fa3dd37fa7bee593054324d3
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="28bdd-103">Microsoft Teams のトラブルシューティングでログ ファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="28bdd-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="28bdd-104">クライアントによって自動的に生成されるログは 3 種類あり、これらのログを使用して Microsoft Teams のトラブルシューティングに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="28bdd-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-105">Debug logs</span></span>

-   <span data-ttu-id="28bdd-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-106">Media logs</span></span>

-   <span data-ttu-id="28bdd-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-107">Desktop logs</span></span>

<span data-ttu-id="28bdd-p101">Microsoft サポートでサポート リクエストを作成する際、サポート エンジニアによってデバッグ ログが要求されます。サポート リクエストを作成する前にこのログを手元に用意しておくと、Microsoft はすばやく問題解決を開始することができます。メディア ログやデスクトップ ログは Microsoft によって要求された場合のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="28bdd-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="28bdd-p102">次の表にクライアントとそれに関連付けられたログの概要を示します。ログ ファイルの格納場所は、クライアントとオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="28bdd-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="28bdd-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="28bdd-113">Client</span></span> |<span data-ttu-id="28bdd-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="28bdd-114">Debug</span></span>|<span data-ttu-id="28bdd-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="28bdd-115">Desktop</span></span>|<span data-ttu-id="28bdd-116">メディア</span><span class="sxs-lookup"><span data-stu-id="28bdd-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="28bdd-117">Web</span><span class="sxs-lookup"><span data-stu-id="28bdd-117">Web</span></span>    |<span data-ttu-id="28bdd-118">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-118">X</span></span>         |-         |-         |
|<span data-ttu-id="28bdd-119">Windows</span><span class="sxs-lookup"><span data-stu-id="28bdd-119">Windows</span></span>     |<span data-ttu-id="28bdd-120">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-120">X</span></span>         |<span data-ttu-id="28bdd-121">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-121">X</span></span>         |<span data-ttu-id="28bdd-122">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-122">X</span></span>         |
|<span data-ttu-id="28bdd-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="28bdd-123">Mac OSX</span></span>     |<span data-ttu-id="28bdd-124">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-124">X</span></span>         |<span data-ttu-id="28bdd-125">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-125">X</span></span>         |<span data-ttu-id="28bdd-126">X</span><span class="sxs-lookup"><span data-stu-id="28bdd-126">X</span></span>         |
|<span data-ttu-id="28bdd-127">iOS</span><span class="sxs-lookup"><span data-stu-id="28bdd-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="28bdd-128">Android</span><span class="sxs-lookup"><span data-stu-id="28bdd-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="28bdd-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="28bdd-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="28bdd-130">サポートされるオペレーティング システムとブラウザーの完全なリストについては、次の「[Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="28bdd-130">For a complete list of supported operating systems and browsers, reference the following [Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span></span>

<a name="debug-logs"></a><span data-ttu-id="28bdd-131">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="28bdd-p103">デバッグ ログは最も一般的なログで、すべての Microsoft サポート ケースで必要とされます。このログは Window と Mac デスクトップ クライアント、ブラウザー ベースのクライアントで生成されます。ログはテキストベースで、下から上に読み取られます。ログは任意のテキストベースのエディタで読み取ることができます。クライアントにログインすると、新規のログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-p103">These are the most common logs and are required for all Microsoft support cases. Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients. The logs are text based and are read from the bottom up. They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="28bdd-136">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="28bdd-137">ログイン</span><span class="sxs-lookup"><span data-stu-id="28bdd-137">Login</span></span>

-   <span data-ttu-id="28bdd-138">中間層サーバーへの接続要求</span><span class="sxs-lookup"><span data-stu-id="28bdd-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="28bdd-139">通話/会話</span><span class="sxs-lookup"><span data-stu-id="28bdd-139">Call/conversation</span></span>

<span data-ttu-id="28bdd-140">デバッグ ログは OS 依存の方法により生成できます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="28bdd-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="28bdd-141">Windows:</span></span>

    1.  <span data-ttu-id="28bdd-142">アプリケーション トレイの **Microsoft Teams アイコン**をクリックし、[**Get Logs (ログを取得)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="28bdd-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="28bdd-143">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="28bdd-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="28bdd-144">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="28bdd-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="28bdd-145">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="28bdd-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="28bdd-146">[**ヘルプ**] プルダウン メニューで [**Get Logs (ログを取得)**] を選択する</span><span class="sxs-lookup"><span data-stu-id="28bdd-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="28bdd-147">キーボード ショートカット: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="28bdd-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="28bdd-148">デバッグ ログは次のフォルダーに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="28bdd-149">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="28bdd-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="28bdd-150">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="28bdd-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="28bdd-151">ブラウザー: 既定の保存場所にデバッグ ログを保存するように求められます</span><span class="sxs-lookup"><span data-stu-id="28bdd-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="28bdd-152">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="28bdd-p104">メディア ログには、音声、ビデオ、画面共有に関する診断データが含まれます。このログは要求があった場合にのみサポート ケースで必要とされ、Microsoft のみが検査できます。次の表にログの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="28bdd-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="28bdd-156">クライアント</span><span class="sxs-lookup"><span data-stu-id="28bdd-156">Client</span></span> |<span data-ttu-id="28bdd-157">場所</span><span class="sxs-lookup"><span data-stu-id="28bdd-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="28bdd-158">Windows</span><span class="sxs-lookup"><span data-stu-id="28bdd-158">Windows</span></span>     |<span data-ttu-id="28bdd-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="28bdd-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="28bdd-160">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="28bdd-160">Mac OSX</span></span>     |<span data-ttu-id="28bdd-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="28bdd-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="28bdd-162">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="28bdd-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="28bdd-p105">bootstrapper ログとも呼ばれるデスクトップ ログには、デスクトップ クライアントとブラウザー間で発生するログ データが含まれます。メディア ログと同様に、このログは Microsoft から要求された場合にのみ必要です。テキスト ベースのログで、任意のテキストベース エディタを使用して上から下の形式で読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="28bdd-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="28bdd-166">クライアント</span><span class="sxs-lookup"><span data-stu-id="28bdd-166">Client</span></span> |<span data-ttu-id="28bdd-167">場所</span><span class="sxs-lookup"><span data-stu-id="28bdd-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="28bdd-168">Windows</span><span class="sxs-lookup"><span data-stu-id="28bdd-168">Windows</span></span>     |<span data-ttu-id="28bdd-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="28bdd-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="28bdd-170">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="28bdd-170">Mac OSX</span></span>     |<span data-ttu-id="28bdd-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="28bdd-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
