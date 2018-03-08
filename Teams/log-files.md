---
title: "Microsoft チームがトラブルシューティングのログ ファイルを使用します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "メディアをデバッグして、Microsoft チームは、それらがある、どのように役立つのトラブルシューティングをデスクトップのログが生成されるについて説明します。"
ms.openlocfilehash: 109f23ce188c5046d7aeaef7abc9d952a7780f47
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="82b86-103">Microsoft チームがトラブルシューティングのログ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="82b86-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="82b86-104">Microsoft チームのトラブルシューティングを支援するために利用できるクライアントが自動的に生成されたログ ファイルの 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="82b86-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="82b86-105">ログをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="82b86-105">Debug logs</span></span>

-   <span data-ttu-id="82b86-106">メディアのログ</span><span class="sxs-lookup"><span data-stu-id="82b86-106">Media logs</span></span>

-   <span data-ttu-id="82b86-107">デスクトップのログ</span><span class="sxs-lookup"><span data-stu-id="82b86-107">Desktop logs</span></span>

<span data-ttu-id="82b86-p101">Microsoft のサポートが、サポートの依頼を作成するときにサポート担当者にデバッグ ログが必要です。サポート リクエストを作成する前に、これらのログを用意ができるように、問題のトラブルシューティングをすぐに開始します。メディアまたはデスクトップのログは Microsoft によって要求された場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="82b86-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="82b86-p102">次の表は、さまざまなクライアントと関連付けられているログについて説明します。ログ ファイルは、クライアントとオペレーティング システムに特定の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="82b86-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="82b86-113">クライアント</span><span class="sxs-lookup"><span data-stu-id="82b86-113">Client</span></span> |<span data-ttu-id="82b86-114">デバッグ</span><span class="sxs-lookup"><span data-stu-id="82b86-114">Debug</span></span>|<span data-ttu-id="82b86-115">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="82b86-115">Desktop</span></span>|<span data-ttu-id="82b86-116">メディア</span><span class="sxs-lookup"><span data-stu-id="82b86-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="82b86-117">Web</span><span class="sxs-lookup"><span data-stu-id="82b86-117">Web</span></span>    |<span data-ttu-id="82b86-118">X</span><span class="sxs-lookup"><span data-stu-id="82b86-118">X</span></span>         |-         |-         |
|<span data-ttu-id="82b86-119">Windows</span><span class="sxs-lookup"><span data-stu-id="82b86-119">Windows</span></span>     |<span data-ttu-id="82b86-120">○</span><span class="sxs-lookup"><span data-stu-id="82b86-120">X</span></span>         |<span data-ttu-id="82b86-121">○</span><span class="sxs-lookup"><span data-stu-id="82b86-121">X</span></span>         |<span data-ttu-id="82b86-122">○</span><span class="sxs-lookup"><span data-stu-id="82b86-122">X</span></span>         |
|<span data-ttu-id="82b86-123">Mac os X</span><span class="sxs-lookup"><span data-stu-id="82b86-123">Mac OSX</span></span>     |<span data-ttu-id="82b86-124">○</span><span class="sxs-lookup"><span data-stu-id="82b86-124">X</span></span>         |<span data-ttu-id="82b86-125">○</span><span class="sxs-lookup"><span data-stu-id="82b86-125">X</span></span>         |<span data-ttu-id="82b86-126">○</span><span class="sxs-lookup"><span data-stu-id="82b86-126">X</span></span>         |
|<span data-ttu-id="82b86-127">iOS</span><span class="sxs-lookup"><span data-stu-id="82b86-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="82b86-128">Android</span><span class="sxs-lookup"><span data-stu-id="82b86-128">Android</span></span>     |-         |-         |-         |
|<span data-ttu-id="82b86-129">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="82b86-129">Windows Phone</span></span>     |-         |-         |-         |

<span data-ttu-id="82b86-130">サポートされているオペレーティング システムおよびブラウザーの一覧は、次の[Microsoft チームのよく寄せられる質問](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc)を参照します。</span><span class="sxs-lookup"><span data-stu-id="82b86-130">For a complete list of supported operating systems and browsers, reference the following [Microsoft Teams FAQ](https://support.office.com/en-US/article/Frequently-asked-questions-about-Microsoft-Teams-%E2%80%93-Admin-Help-05cbe533-2181-4e95-a4b0-52cd7695fafc).</span></span>

<a name="debug-logs"></a><span data-ttu-id="82b86-131">ログをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="82b86-131">Debug logs</span></span>
---------------------------

<span data-ttu-id="82b86-p103">最も一般的なログは、これらすべての Microsoft サポートの場合に必要なします。デバッグ ログ ウィンドウと Mac のデスクトップ クライアントとブラウザー ベースのクライアントによって生成します。ログは、テキスト ベース下部から読み取るです。任意のテキスト エディターを使用して読み取ることができ、クライアントにログインしたときに新しいログを作成します。</span><span class="sxs-lookup"><span data-stu-id="82b86-p103">These are the most common logs and are required for all Microsoft support cases. Debug logs are produced by the Window and Mac desktop clients, as well as browser based clients. The logs are text based and are read from the bottom up. They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="82b86-136">デバッグ ログは、次のデータ フローを表示します。</span><span class="sxs-lookup"><span data-stu-id="82b86-136">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="82b86-137">ログイン</span><span class="sxs-lookup"><span data-stu-id="82b86-137">Login</span></span>

-   <span data-ttu-id="82b86-138">中間層サービスへの接続の要求</span><span class="sxs-lookup"><span data-stu-id="82b86-138">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="82b86-139">通話/会話</span><span class="sxs-lookup"><span data-stu-id="82b86-139">Call/conversation</span></span>

<span data-ttu-id="82b86-140">デバッグ ログを作成するには、次の OS 特定方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="82b86-140">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="82b86-141">Windows:</span><span class="sxs-lookup"><span data-stu-id="82b86-141">Windows:</span></span>

    1.  <span data-ttu-id="82b86-142">**Microsoft チーム アイコン**を右クリックして、アプリケーション トレイ、[**ログを取得します。**</span><span class="sxs-lookup"><span data-stu-id="82b86-142">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="82b86-143">**[ヘルプ**] プルダウン メニューから**ログのアクセス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b86-143">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="82b86-144">キーボード ショートカット: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="82b86-144">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="82b86-145">Mac os X:</span><span class="sxs-lookup"><span data-stu-id="82b86-145">Mac OSX:</span></span>

    1.  <span data-ttu-id="82b86-146">**[ヘルプ**] プルダウン メニューから**ログのアクセス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="82b86-146">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="82b86-147">キーボード ショートカット: オプション + コマンド + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="82b86-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="82b86-148">デバッグ ログは、次のフォルダーに自動的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="82b86-148">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="82b86-149">Windows: ユーザー プロファイル %\\ダウンロード</span><span class="sxs-lookup"><span data-stu-id="82b86-149">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="82b86-150">Mac os X: ダウンロード</span><span class="sxs-lookup"><span data-stu-id="82b86-150">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="82b86-151">ブラウザー: するように求められますデバッグ ログを既定の保存場所に保存するには</span><span class="sxs-lookup"><span data-stu-id="82b86-151">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="82b86-152">メディアのログ</span><span class="sxs-lookup"><span data-stu-id="82b86-152">Media Logs</span></span>
---------------------------

<span data-ttu-id="82b86-p104">メディア ログには、音声、ビデオ、画面の共有に関する診断のデータが含まれます。出席依頼にのみサポート場合に必要な Microsoft によってのみ検査することができます。次の表では、ログの場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="82b86-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="82b86-156">クライアント</span><span class="sxs-lookup"><span data-stu-id="82b86-156">Client</span></span> |<span data-ttu-id="82b86-157">場所</span><span class="sxs-lookup"><span data-stu-id="82b86-157">Location</span></span> |
|---------|---------|
|<span data-ttu-id="82b86-158">Windows</span><span class="sxs-lookup"><span data-stu-id="82b86-158">Windows</span></span>     |<span data-ttu-id="82b86-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="82b86-159">%appdata%\Roaming\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="82b86-160">Mac os X</span><span class="sxs-lookup"><span data-stu-id="82b86-160">Mac OSX</span></span>     |<span data-ttu-id="82b86-161">~/Library/Application サポート/Microsoft/チーム/メディア スタック\*.blog</span><span class="sxs-lookup"><span data-stu-id="82b86-161">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="82b86-162">デスクトップのログ</span><span class="sxs-lookup"><span data-stu-id="82b86-162">Desktop logs</span></span>
---------------------

<span data-ttu-id="82b86-p105">デスクトップのログとも呼ばれるブートス トラップ ログ] には、デスクトップ クライアントとブラウザーの間で行われるログ データが含まれています。メディア ログ] のように Microsoft によって要求された場合、これらのログは必要のみです。ログは、テキスト ベースでトップダウンの形式で任意のテキスト エディターを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="82b86-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="82b86-166">クライアント</span><span class="sxs-lookup"><span data-stu-id="82b86-166">Client</span></span> |<span data-ttu-id="82b86-167">場所</span><span class="sxs-lookup"><span data-stu-id="82b86-167">Location</span></span> |
|---------|---------|
|<span data-ttu-id="82b86-168">Windows</span><span class="sxs-lookup"><span data-stu-id="82b86-168">Windows</span></span>     |<span data-ttu-id="82b86-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="82b86-169">%appdata%\Roaming\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="82b86-170">Mac os X</span><span class="sxs-lookup"><span data-stu-id="82b86-170">Mac OSX</span></span>     |<span data-ttu-id="82b86-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="82b86-171">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
