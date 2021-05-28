---
title: Microsoft Teams のトラブルシューティングでログ ファイルを使用する
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams によって生成されたデバッグ ログ、メディア ログ、デスクトップ ログ、ログが見つかる場所、および監視とトラブルシューティングに役立つ方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689695"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="64c33-103">ログ ファイルを使用して、ログの監視とトラブルシューティングを行Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64c33-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="64c33-104">クライアントによって自動的に生成される 3 種類のログ ファイルがあります。このファイルは、クライアントの監視とトラブルシューティングに役立Teams。</span><span class="sxs-lookup"><span data-stu-id="64c33-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="64c33-105">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="64c33-106">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="64c33-107">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="64c33-108">この記事では、これらのログとログの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="64c33-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="64c33-109">特定の問題のトラブルシューティングについては、「トラブルシューティング」を参照[Teamsしてください](/MicrosoftTeams/troubleshoot/teams)。</span><span class="sxs-lookup"><span data-stu-id="64c33-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="64c33-110">サポートに連絡する方法については、「サポートを受け取る [」を参照してください](/microsoft-365/business-video/get-help-support)。</span><span class="sxs-lookup"><span data-stu-id="64c33-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="64c33-111">Microsoft サポートでサポート要求を作成する場合、サポート エンジニアはデバッグ ログを必要とします。</span><span class="sxs-lookup"><span data-stu-id="64c33-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="64c33-112">サポート要求を作成する前にデバッグ ログを用意すると、Microsoft が問題のトラブルシューティングをすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="64c33-113">**メディア** ログまたは **デスクトップ ログ** は、Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="64c33-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="64c33-114">この記事では、デバッグ ログ **という用語は** 、トラブルシューティングに使用されるログを指します。</span><span class="sxs-lookup"><span data-stu-id="64c33-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="64c33-115">ただし、これらのログに対して生成されるファイルには、診断ログという用語 **が** 名前に含まれます。</span><span class="sxs-lookup"><span data-stu-id="64c33-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="64c33-116">ログを収集して有効にする</span><span class="sxs-lookup"><span data-stu-id="64c33-116">Collect and enable logging</span></span>

<span data-ttu-id="64c33-117">問題が発生するとすぐにログを収集することが重要です。</span><span class="sxs-lookup"><span data-stu-id="64c33-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="64c33-118">ログは、2 回のクリックだけで収集できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="64c33-119">Windows: システム トレイの [Teams] アイコンを右クリックし、[サポート ファイルの収集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64c33-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="64c33-120">Mac: [ヘルプ] メニューを選択し、[サポート ファイルの収集 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64c33-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="64c33-121">デバッグ ログ、デスクトップ ログ、およびメディア ログは、MSTeams Diagnostics Log という名前の 1 つのフォルダーに収集されます <local data and time> 。</span><span class="sxs-lookup"><span data-stu-id="64c33-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="64c33-122">このフォルダーは、Microsoft サポートでサポート要求を開く際に圧縮および共有できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="64c33-123">フォルダーには、デスクトップ、会議 (メディア)、デバッグ (Web) のフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64c33-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="64c33-124">次のキーボード ショートカットを使用して、ファイルを収集できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="64c33-125">Windows: Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="64c33-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="64c33-126">Mac: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="64c33-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="64c33-127">メディア ログは既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="64c33-127">Media logging is turned off by default.</span></span> <span data-ttu-id="64c33-128">メディア ログを有効にするには、ユーザーはクライアントでオプションを有効Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="64c33-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="64c33-129">[全般]**設定**  >  **に移動** し、[会議の診断のログ記録を有効にする **] を選択します (Teams)。**</span><span class="sxs-lookup"><span data-stu-id="64c33-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="64c33-130">ログTeamsを開始するには、クライアントを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c33-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="64c33-131">メディア のログ記録が有効になっている場合は、オーディオとビデオの問題を調査するために必要な追加のファイルが [会議] フォルダーに含まれます。</span><span class="sxs-lookup"><span data-stu-id="64c33-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="64c33-132">メディア ログが有効になっていない場合、使用できるログの数は限られています。</span><span class="sxs-lookup"><span data-stu-id="64c33-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="64c33-133">次の表は、さまざまなクライアントとその関連ログの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="64c33-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="64c33-134">ログ ファイルは、クライアントとオペレーティング システムに固有の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="64c33-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="64c33-135">クライアント</span><span class="sxs-lookup"><span data-stu-id="64c33-135">Client</span></span> |<span data-ttu-id="64c33-136">デバッグ</span><span class="sxs-lookup"><span data-stu-id="64c33-136">Debug</span></span>|<span data-ttu-id="64c33-137">デスクトップ</span><span class="sxs-lookup"><span data-stu-id="64c33-137">Desktop</span></span>|<span data-ttu-id="64c33-138">メディア</span><span class="sxs-lookup"><span data-stu-id="64c33-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="64c33-139">Web</span><span class="sxs-lookup"><span data-stu-id="64c33-139">Web</span></span>    |<span data-ttu-id="64c33-140">X</span><span class="sxs-lookup"><span data-stu-id="64c33-140">X</span></span>         |-         |-         |
|<span data-ttu-id="64c33-141">Windows</span><span class="sxs-lookup"><span data-stu-id="64c33-141">Windows</span></span>     |<span data-ttu-id="64c33-142">X</span><span class="sxs-lookup"><span data-stu-id="64c33-142">X</span></span>         |<span data-ttu-id="64c33-143">X</span><span class="sxs-lookup"><span data-stu-id="64c33-143">X</span></span>         |<span data-ttu-id="64c33-144">X</span><span class="sxs-lookup"><span data-stu-id="64c33-144">X</span></span>         |
|<span data-ttu-id="64c33-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="64c33-145">Mac OSX</span></span>     |<span data-ttu-id="64c33-146">X</span><span class="sxs-lookup"><span data-stu-id="64c33-146">X</span></span>         |<span data-ttu-id="64c33-147">X</span><span class="sxs-lookup"><span data-stu-id="64c33-147">X</span></span>         |<span data-ttu-id="64c33-148">X</span><span class="sxs-lookup"><span data-stu-id="64c33-148">X</span></span>         |
|<span data-ttu-id="64c33-149">Linux</span><span class="sxs-lookup"><span data-stu-id="64c33-149">Linux</span></span>     |<span data-ttu-id="64c33-150">X</span><span class="sxs-lookup"><span data-stu-id="64c33-150">X</span></span>         |<span data-ttu-id="64c33-151">X</span><span class="sxs-lookup"><span data-stu-id="64c33-151">X</span></span>         |<span data-ttu-id="64c33-152">X</span><span class="sxs-lookup"><span data-stu-id="64c33-152">X</span></span>         |
|<span data-ttu-id="64c33-153">iOS</span><span class="sxs-lookup"><span data-stu-id="64c33-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="64c33-154">Android</span><span class="sxs-lookup"><span data-stu-id="64c33-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="64c33-155">サポートされるオペレーティング システムとブラウザーの完全なリストについては、「[Microsoft Teams のクライアントを取得する](get-clients.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64c33-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="64c33-156">デバッグ ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-156">Debug logs</span></span>

<span data-ttu-id="64c33-157">詳細については _、「ログ記録の収集と有効化_」セクションWindows Mac の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c33-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="64c33-158">デバッグ ログは、Windows Mac デスクトップ クライアントとブラウザー ベースのクライアントによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="64c33-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="64c33-159">ログはテキスト ベースであり、ボトムアップから読み取りされます。</span><span class="sxs-lookup"><span data-stu-id="64c33-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="64c33-160">任意のテキスト ベースのエディターを使用して読み取り、クライアントにログインするときに新しいログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64c33-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="64c33-161">デバッグ ログには次のデータ フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64c33-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="64c33-162">ログイン</span><span class="sxs-lookup"><span data-stu-id="64c33-162">Login</span></span>

-   <span data-ttu-id="64c33-163">中層サービスへの接続要求</span><span class="sxs-lookup"><span data-stu-id="64c33-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="64c33-164">通話/会話</span><span class="sxs-lookup"><span data-stu-id="64c33-164">Call/conversation</span></span>

<span data-ttu-id="64c33-165">Linux のログを収集するには:キーボード ショートカット: Ctrl + Alt + Shift + 1 ファイルは ~/Downloads で使用できます</span><span class="sxs-lookup"><span data-stu-id="64c33-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="64c33-166">ブラウザーのログを収集するには:キーボード ショートカット: Crtl + Alt + Shift + 1 ファイルは %userprofile%\Downloads で使用できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="64c33-167">メディア ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-167">Media logs</span></span>

<span data-ttu-id="64c33-168">詳細については _、「ログ記録の収集と有効化_」セクションWindows Mac の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c33-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="64c33-169">メディア ログには、音声、ビデオ、画面の共有に関する診断データがTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="64c33-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="64c33-170">これらは、通話関連の問題にリンクされているサポート ケースに必要です。</span><span class="sxs-lookup"><span data-stu-id="64c33-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="64c33-171">メディア ログは既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="64c33-171">Media logging is turned off by default.</span></span> <span data-ttu-id="64c33-172">会議の診断データをTeamsするには、ユーザーがクライアントでオプションを有効Teamsがあります。</span><span class="sxs-lookup"><span data-stu-id="64c33-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="64c33-173">[全般 **設定** に移動し、[会議の診断のログ記録を有効にする (Teams を再起動する必要があります) チェック ボックスをオンにし、Teams を再起動して、問題を  >  再現します。</span><span class="sxs-lookup"><span data-stu-id="64c33-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="64c33-174">ログ ファイルを Microsoft サポートに送信する場合は、ログ ファイルのタイムスタンプを確認して、問題を再現した時間をログで確実にカバーしてください。</span><span class="sxs-lookup"><span data-stu-id="64c33-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="64c33-175">Linux のログを収集するには:ファイルは ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog および *~/.config/Microsoft/Microsoft Teams/skylib/*.blog で使用できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="64c33-176">生成されるログ ファイルとログ ファイルに含まれる情報の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="64c33-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="64c33-177">ログ ファイル名</span><span class="sxs-lookup"><span data-stu-id="64c33-177">Log file name</span></span>  |<span data-ttu-id="64c33-178">説明</span><span class="sxs-lookup"><span data-stu-id="64c33-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="64c33-179">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="64c33-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="64c33-180">メディア スタックに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="64c33-180">Contains information related to the media stack.</span></span> <span data-ttu-id="64c33-181">これには、解像度、デコーダーとエンコーダーの使用、送信および受信されたフレーム数、カメラとビデオ ベースの画面共有 (VBSS) セッションの状態などのチャネルの状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64c33-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="64c33-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="64c33-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="64c33-183">コントロールが指定された場合のタイムスタンプ、マウス ポインター情報など、リモート制御アクションに関連する情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="64c33-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="64c33-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="64c33-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="64c33-185">メディア スタック トレース イベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="64c33-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="64c33-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="64c33-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="64c33-187">レンダリング品質など、メディア エージェントに関連する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="64c33-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="64c33-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="64c33-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="64c33-189">ts 呼び出し API のイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="64c33-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="64c33-190">デスクトップ ログ</span><span class="sxs-lookup"><span data-stu-id="64c33-190">Desktop logs</span></span>

<span data-ttu-id="64c33-191">詳細については _、「ログ記録の収集と有効化_」セクションWindows Mac の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c33-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="64c33-192">デスクトップ ログ (ブートストラップ ログとも呼ばれる) には、デスクトップ クライアントとブラウザーの間で発生するログ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64c33-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="64c33-193">メディア ログと同様に、これらのログは Microsoft から要求された場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="64c33-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="64c33-194">ログはテキスト ベースであり、トップダウン形式の任意のテキスト ベースのエディターを使用して読み取り可能です。</span><span class="sxs-lookup"><span data-stu-id="64c33-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="64c33-195">Linux のログを収集するには:システム トレイの [Microsoft Teams] アイコンをクリックし、[ログの取得]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64c33-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="64c33-196">ファイルは ~/.config/Microsoft/Microsoft Teams/logs.txt で使用logs.txt。</span><span class="sxs-lookup"><span data-stu-id="64c33-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="64c33-197">ブラウザートレース</span><span class="sxs-lookup"><span data-stu-id="64c33-197">Browser trace</span></span>

<span data-ttu-id="64c33-198">一部のカテゴリのエラーについては、Microsoft サポートでブラウザー トレースの収集が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64c33-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="64c33-199">この情報は、エラーが発生した場合のクライアントの状態Teams詳細を提供できます。</span><span class="sxs-lookup"><span data-stu-id="64c33-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="64c33-200">ブラウザーのトレースを開始する前に、ブラウザーにサインインTeams。</span><span class="sxs-lookup"><span data-stu-id="64c33-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="64c33-201">トレースに機密性の高いサインイン情報が含まれるので、トレースを開始する前にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c33-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="64c33-202">サインインした後、ブラウザーに応じて次のリンクのいずれかを選択し、提供されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="64c33-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="64c33-203">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="64c33-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="64c33-204">Edge</span><span class="sxs-lookup"><span data-stu-id="64c33-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="64c33-205">Safari</span><span class="sxs-lookup"><span data-stu-id="64c33-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="64c33-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="64c33-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="64c33-207">この手順では、Azure portal へのすべての参照を、新しいクライアントTeamsします。</span><span class="sxs-lookup"><span data-stu-id="64c33-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="64c33-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="64c33-208">Related topics</span></span>

[<span data-ttu-id="64c33-209">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="64c33-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
