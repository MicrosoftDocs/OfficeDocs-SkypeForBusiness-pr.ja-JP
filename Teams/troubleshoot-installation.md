---
title: Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Windows の Teams デスクトップ クライアント アプリのインストールと更新に関する問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: 7b8d4984a8ee40f9a013155ad28b682e000260ba
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086143"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="90f62-103">Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="90f62-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="90f62-104">この記事では、Windows で実行されている Teams デスクトップ クライアント アプリのインストールと更新に関する問題を診断し、トラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90f62-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="90f62-105">Teams が正常に更新されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="90f62-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="90f62-106">以下の手順に従って、Teams の更新が正常にインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="90f62-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="90f62-107">Teams で、プロファイルの画像を選択してから、**[概要] \*\* > \*\* [バージョン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f62-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="90f62-108">同じメニューで、[**更新プログラムのチェック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f62-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="90f62-109">アプリの上部にあるバナーが、Teams の「更新」が必要であることを示すのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="90f62-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="90f62-110">このプロセスにより、新しいバージョンの Teams がダウンロードされると、リンクは約 1 分後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="90f62-111">また、既に最新バージョンを実行しているかどうかをバナーで確認することもできます。その場合、更新は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="90f62-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="90f62-112">バナーの [更新] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f62-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="90f62-113">Teams が再起動するまで待ってから、手順 1 を繰り返して、アプリが更新されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="90f62-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="90f62-114">失敗メッセージが表示される場合、または、バージョン番号が手順 4 と同じである場合は、更新プロセスに失敗しています。</span><span class="sxs-lookup"><span data-stu-id="90f62-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="90f62-115">インストールと更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="90f62-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="90f62-116">インストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="90f62-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="90f62-117">Teams がインストールされている場合、Teams インストーラーは一連のイベントを %LocalAppData%\SquirrelTemp\SquirrelSetup.log に記録します。</span><span class="sxs-lookup"><span data-stu-id="90f62-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="90f62-118">最初に調べる必要があるのは、ログの最後にあるエラー メッセージまたはコール スタックです。</span><span class="sxs-lookup"><span data-stu-id="90f62-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="90f62-119">ログの先頭にあるコール スタックは、インストールの問題が存在することを意味しない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="90f62-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="90f62-120">必要なものを確認するために、(別のコンピューターであっても) 正常なインストールのログとログを比較する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="90f62-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="90f62-121">SquirrelSetup.log に原因が示されていない場合、または問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステム ログを収集して分析する](#collect-and-analyze-application-and-system-logs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f62-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="90f62-122">更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="90f62-122">Troubleshoot update issues</span></span>

<span data-ttu-id="90f62-123">Teams が正常にインストールされると、ログの場所が %LocalAppData%\SquirrelTemp から %AppData%\Microsoft\Teams に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="90f62-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="90f62-124">この場所には、SquirrelSetup.log と logs.txt の 2 つのログ ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="90f62-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="90f62-125">この場所にある SquirrelSetup.log ファイルは、Teams アプリにサービスを提供する実行可能ファイルである Update.exe によって書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="90f62-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="90f62-126">Logs.txt ファイルは、重要なアプリケーション イベントを記録するために Teams アプリ (具体的には Teams.exe) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="90f62-127">失敗情報が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-127">It will likely contain failure information.</span></span>

<span data-ttu-id="90f62-128">これらのログ ファイルには、個人を特定できる情報 (PII) が含まれているため、Microsoft には送信されません。</span><span class="sxs-lookup"><span data-stu-id="90f62-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="90f62-129">Teams は、(ポリシーに応じて) 更新プロセスを自動的に開始することができます。または、ユーザーのプロファイル画像 > **[更新プログラムのチェック]** に移動して、手動で更新を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90f62-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="90f62-130">いずれの方法でも、次のイベント シーケンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="90f62-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="90f62-131">**更新プログラムのチェック**。</span><span class="sxs-lookup"><span data-stu-id="90f62-131">**Check for updates**.</span></span> <span data-ttu-id="90f62-132">Teams は Web 要求を行い、現在のアプリのバージョンと展開リング情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="90f62-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="90f62-133">この手順の目標は、ダウンロード リンクを取得することです。</span><span class="sxs-lookup"><span data-stu-id="90f62-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="90f62-134">この手順での失敗は、Logs.txt に記録されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="90f62-135">**更新プログラムのダウンロード**。</span><span class="sxs-lookup"><span data-stu-id="90f62-135">**Download update**.</span></span> <span data-ttu-id="90f62-136">Teams は、手順 1 で取得したダウンロード リンクを使用して、更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="90f62-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="90f62-137">ダウンロードが完了すると、Teams は Update.exe を呼び出してダウンロードをステージングします。</span><span class="sxs-lookup"><span data-stu-id="90f62-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="90f62-138">また、ダウンロード失敗は、Logs.txt に記録されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="90f62-139">**更新プログラムをステージングする**。</span><span class="sxs-lookup"><span data-stu-id="90f62-139">**Stage the update**.</span></span> <span data-ttu-id="90f62-140">ダウンロードされたコンテンツは検証され、中間フォルダー %LocalAppData%\Microsoft\Teams\stage) に解凍され、Update.exe によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="90f62-141">この段階での失敗は SquirrelTemp.log に記録されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="90f62-142">**更新プログラムのインストール**。</span><span class="sxs-lookup"><span data-stu-id="90f62-142">**Install the update**.</span></span> <span data-ttu-id="90f62-143">Teams を開始する方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="90f62-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="90f62-144">ユーザーがログインすると、システムが自動的に Teams を開始します。または、ショートカットを使用して Teams を開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="90f62-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="90f62-145">この手順では、Update.exe がステージング フォルダーの存在を確認し、コンテンツを再度検証し、ファイル操作を実行してアプリのステージングを解除します。</span><span class="sxs-lookup"><span data-stu-id="90f62-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="90f62-146">%LocalAppData%\Microsoft\Teams\current の古いアプリケーション フォルダーは %LocalAppData%\Microsoft\Teams\previous にバックアップされ、ステージ フォルダーの名前は "current" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="90f62-147">この段階での失敗は SquirrelTemp.log に記録されます。</span><span class="sxs-lookup"><span data-stu-id="90f62-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="90f62-148">SquirrelTemp.log または Logs.txt には、根本的な原因を特定するのに十分な情報が含まれていないため、問題のトラブルシューティングを行うための詳細情報が必要な場合は、[アプリケーションおよびシステム ログの収集と分析](#collect-and-analyze-application-and-system-logs)に進みます。</span><span class="sxs-lookup"><span data-stu-id="90f62-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="90f62-149">アプリケーションおよびシステム ログの収集と分析</span><span class="sxs-lookup"><span data-stu-id="90f62-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="90f62-150">このセクションでは、アプリケーションとシステムのログを収集して分析し、問題のトラブルシューティングを行うためのより包括的な情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90f62-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="90f62-151">Sysinternals ツールを使用して、これらの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="90f62-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="90f62-152">詳細については、「[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f62-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="90f62-153">ログを収集する</span><span class="sxs-lookup"><span data-stu-id="90f62-153">Collect logs</span></span>

1. <span data-ttu-id="90f62-154">[Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="90f62-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="90f62-155">ローカルドライブの %TEMP% フォルダーに zip ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="90f62-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="90f62-156">管理者特権でのコマンド プロンプトを開き、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="90f62-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="90f62-157">次のコマンドを実行して、TEMP フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="90f62-157">Run the following to go to your TEMP folder:</span></span>

        ```console
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="90f62-158">設定とアプリケーション ログをコピーします。</span><span class="sxs-lookup"><span data-stu-id="90f62-158">Copy the setup and application logs.</span></span> <span data-ttu-id="90f62-159">障害点によっては、これらのログの一部が存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="90f62-160">次のコマンドを実行して、開いているハンドルをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="90f62-160">Run the following to capture the open handles.</span></span>

        ```console
        handle > handles.txt
        ```

    4. <span data-ttu-id="90f62-161">次のコマンドを実行して、開いている DLL をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="90f62-161">Run the following to capture the opened DLLs.</span></span>

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="90f62-162">次のコマンドを実行して、実行中のドライバーをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="90f62-162">Run the following to capture the drivers that are running.</span></span>

        ```console
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="90f62-163">次のコマンドを実行して、Teams フォルダーのアクセス制御リスト (ACL) をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="90f62-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="90f62-164">ログの分析 (上級ユーザー向け)</span><span class="sxs-lookup"><span data-stu-id="90f62-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="90f62-165">更新に失敗すると、アプリが予期しない動作をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="90f62-166">たとえば、Teams を終了できない、古いバージョンの Teams を使用している、または Teams を開始できないなどです。</span><span class="sxs-lookup"><span data-stu-id="90f62-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="90f62-167">更新中に問題が発生した場合は、原因を見つけるために最初に探す場所は SquirrelTemp.log です。</span><span class="sxs-lookup"><span data-stu-id="90f62-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="90f62-168">ここでは、最も一般的なものから最も一般的でないものまで、さまざまな種類の更新の失敗と、ログを使用してそれらを分析およびトラブルシューティングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="90f62-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="90f62-169">Teams を終了できません</span><span class="sxs-lookup"><span data-stu-id="90f62-169">Unable to exit Teams</span></span>

<span data-ttu-id="90f62-170">Teams は自身を新しいバージョンに更新する必要があると判断すると、新しいアプリをダウンロードしてステージングし、次にコンピューターがアイドル状態になったときに自動的に再起動する機会を待ちます。</span><span class="sxs-lookup"><span data-stu-id="90f62-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="90f62-171">このプロセス中の一般的な問題は、別のプロセスやファイル システム ドライバーが Teams.exe プロセスをロックして、Teams.exe が終了しない場合です。</span><span class="sxs-lookup"><span data-stu-id="90f62-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="90f62-172">その結果、Teams アプリは、新しくダウンロードされてステージングされたアプリに置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="90f62-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="90f62-173">トラブルシューティングのヒント:</span><span class="sxs-lookup"><span data-stu-id="90f62-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="90f62-174">これが発生している問題であることを確認するために、Teams を終了します (タスクバーの [Teams] を右クリックし、[**終了**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="90f62-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="90f62-175">次に、Windows のタスク マネージャーを開いて、Teams インスタンスがまだ実行中であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="90f62-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="90f62-176">この問題が発生しているコンピューターを使用していない場合は、この問題が発生しているコンピューターから収集された SquirrelTemp.log を調べ、"Program: Unable to terminate the process in the log" というエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="90f62-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="90f62-177">Teams.exe の終了を妨げている原因を特定するには、Dlls.txt および Handles.txt ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="90f62-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="90f62-178">これらは、Teams の終了を妨げたプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="90f62-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="90f62-179">Teams の終了を妨げる可能性のあるもう 1 つの原因は、カーネル モードのファイル システム フィルター ドライバーです。</span><span class="sxs-lookup"><span data-stu-id="90f62-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="90f62-180">SysInternals ツールの [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump) を使用して、```procdump -mk <pid>``` を実行して、カーネル モード プロセス ダンプを収集します。ここで、<pid> はタスク マネージャーから取得したプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="90f62-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="90f62-181">Driverquery.txt ログファイルを調べて、Teams に干渉する可能性のあるアクティブなフィルター ドライバーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="90f62-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="90f62-182">この状態から回復するには、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="90f62-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="90f62-183">ファイルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="90f62-183">File permissions</span></span>

<span data-ttu-id="90f62-184">Teams は、インストールおよび更新プロセスを通して、ユーザーのプロファイルに多くのサブフォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="90f62-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="90f62-185">アプリとアップデーターは昇格されていないユーザーとして実行されるので、次のフォルダーに対する読み取りアクセス許可と書き込みアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="90f62-186">フォルダー</span><span class="sxs-lookup"><span data-stu-id="90f62-186">Folder</span></span>  |<span data-ttu-id="90f62-187">使用元</span><span class="sxs-lookup"><span data-stu-id="90f62-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="90f62-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="90f62-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="90f62-189">インストール段階での Teams (たとえば、Teams_Windows_x64.exe)</span><span class="sxs-lookup"><span data-stu-id="90f62-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="90f62-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="90f62-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="90f62-191">更新プロセス中にアプリ パッケージを抽出してステージングする Teams アップデーター (Update.exe)</span><span class="sxs-lookup"><span data-stu-id="90f62-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="90f62-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="90f62-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="90f62-193">Teams アプリ (Teams.exe) は、設定、アプリの状態、(事前にステージングされた) ダウンロードした更新パッケージを保存します</span><span class="sxs-lookup"><span data-stu-id="90f62-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="90f62-194">Teams がファイルに書き込めないため、アクセスが拒否された場合、別のソフトウェア アプリケーションが干渉しているか、セキュリティ記述子のエントリがフォルダーへの書き込みアクセスを制限している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="90f62-195">トラブルシューティングのヒント:</span><span class="sxs-lookup"><span data-stu-id="90f62-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="90f62-196">SquirrelTemp.log または Logs.txt で「アクセスが拒否されました」の証拠を探します。</span><span class="sxs-lookup"><span data-stu-id="90f62-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="90f62-197">これらのファイルを確認して、失敗したファイルへの書き込みが試みられているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="90f62-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="90f62-198">Icacls.txt を開き、管理者以外のユーザーによる書き込み操作をブロックする効果的なアクセス制御エントリ (ACE) を探します。通常は、DACL エントリのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="90f62-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="90f62-199">詳細については、[icacls のドキュメント](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90f62-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="90f62-200">ファイルの破損</span><span class="sxs-lookup"><span data-stu-id="90f62-200">File corrupted</span></span>

<span data-ttu-id="90f62-201">場合によっては、暗号化ソフトウェアが %LocalAppData%\Microsoft\Teams フォルダー内のファイルを変更する可能性があり、これにより Teams が起動できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="90f62-202">アプリが更新されていないときでも、いつでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90f62-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="90f62-203">残念ながら、ファイルが破損している場合、この状態から回復する唯一の方法は、Teams をアンインストールして再インストールすることです。</span><span class="sxs-lookup"><span data-stu-id="90f62-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="90f62-204">これらの手順のいずれかを使用しても問題の根本的な原因を特定できない場合は、[プロセス モニター](https://docs.microsoft.com/sysinternals/downloads/procmon) セッションを試すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90f62-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="90f62-205">プロセス モニターは、レジストリやファイルシステムへのアクセスを記録する Sysinternals ツールです。</span><span class="sxs-lookup"><span data-stu-id="90f62-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="90f62-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="90f62-206">Related topics</span></span>

- [<span data-ttu-id="90f62-207">Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="90f62-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="90f62-208">Teams クライアントの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="90f62-208">Teams client updates</span></span>](teams-client-update.md)
- [<span data-ttu-id="90f62-209">チームのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="90f62-209">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)