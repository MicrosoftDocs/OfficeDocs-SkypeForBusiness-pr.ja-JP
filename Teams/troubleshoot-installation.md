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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Windows の Teams デスクトップクライアントアプリのインストールと更新に関する問題のトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920154"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a><span data-ttu-id="25400-103">Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25400-103">Troubleshoot Microsoft Teams installation and update issues on Windows</span></span>

<span data-ttu-id="25400-104">この記事では、Windows で実行されている Teams デスクトップクライアントアプリのインストールおよび更新に関する問題の診断とトラブルシューティングを行う方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="25400-104">This article provides guidance for how to diagnose and troubleshoot installation and update issues for the Teams desktop client app running on Windows.</span></span>

## <a name="check-whether-teams-is-updated-successfully"></a><span data-ttu-id="25400-105">チームが正常に更新されたかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="25400-105">Check whether Teams is updated successfully</span></span>

<span data-ttu-id="25400-106">チームの更新プログラムが正常にインストールされたかどうかを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="25400-106">Follow these steps to check whether a Teams update is successfully installed.</span></span>

1. <span data-ttu-id="25400-107">Teams で、プロフィール画像を選択し、[バージョン**情報** > \*\*\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25400-107">In Teams, select your profile picture, and then click **About** > **Version**.</span></span>
2. <span data-ttu-id="25400-108">同じメニューで、[**更新プログラムのチェック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="25400-108">On the same menu, click **Check for updates**.</span></span>
3. <span data-ttu-id="25400-109">アプリの上部にあるバナーで、チームの "更新" が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="25400-109">Wait for the banner at the top of the app to indicate that a “refresh” of Teams is needed.</span></span> <span data-ttu-id="25400-110">このプロセスでは、新しいバージョンの Teams がダウンロードされるので、後で1分ほどリンクを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25400-110">The link should be shown about a minute later as this process downloads the new version of Teams.</span></span> <span data-ttu-id="25400-111">また、バナーでは、既に最新バージョンを実行しているかどうかを確認することができます。この場合、更新プログラムは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="25400-111">The banner also lets you know if you’re already running the latest version in which case, no update is necessary.</span></span>
4. <span data-ttu-id="25400-112">バナーで [更新] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="25400-112">Click the refresh link in the banner.</span></span>
5. <span data-ttu-id="25400-113">Teams が再起動するまで待ってから、手順1を繰り返して、アプリが更新されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25400-113">Wait until Teams restarts, and then repeat step 1 to see whether the app is updated.</span></span>

<span data-ttu-id="25400-114">エラーメッセージが表示された場合、または手順4と同じバージョン番号がある場合は、更新処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="25400-114">If you see a failure message or if the version number is the same as in step 4, the update process failed.</span></span>

## <a name="troubleshoot-installation-and-update-issues"></a><span data-ttu-id="25400-115">インストールと更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25400-115">Troubleshoot installation and update issues</span></span>

### <a name="troubleshoot-installation-issues"></a><span data-ttu-id="25400-116">インストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25400-116">Troubleshoot installation issues</span></span>

<span data-ttu-id="25400-117">Teams がインストールされると、Teams installer は%LocalAppData%\SquirrelTemp\SquirrelSetup.log. への一連のイベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="25400-117">When Teams is installed, the Teams installer logs the sequence of events to %LocalAppData%\SquirrelTemp\SquirrelSetup.log.</span></span> <span data-ttu-id="25400-118">最初に確認するべきことは、ログの最後にあるエラーメッセージまたはコールスタックです。</span><span class="sxs-lookup"><span data-stu-id="25400-118">The first thing to look for is an error message or a call stack near the end of the log.</span></span> <span data-ttu-id="25400-119">ログの最初の呼び出し履歴は、インストールの問題が存在するというわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="25400-119">Note that call stacks at the beginning of the log may not mean that an installation issue exists.</span></span> <span data-ttu-id="25400-120">必要なものを確認するために、(別のコンピューターでも) インストールが正常に完了した場合でも、ログとログの比較を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="25400-120">It can be easier to compare your log against the log from a successful installation (even on another machine) to see what's expected.</span></span>

<span data-ttu-id="25400-121">SquirrelSetup で原因が示されない場合、または問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステムログを収集して分析](#collect-and-analyze-application-and-system-logs)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25400-121">If SquirrelSetup.log doesn't indicate the cause or if you need more information to troubleshoot the issue, see [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

### <a name="troubleshoot-update-issues"></a><span data-ttu-id="25400-122">更新に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25400-122">Troubleshoot update issues</span></span>

<span data-ttu-id="25400-123">Teams が正常にインストールされると、ログの場所が%LocalAppData%\SquirrelTemp から%AppData%\Microsoft\Teams. に切り替わります。</span><span class="sxs-lookup"><span data-stu-id="25400-123">When Teams is successfully installed, the log location switches from %LocalAppData%\SquirrelTemp to %AppData%\Microsoft\Teams.</span></span> <span data-ttu-id="25400-124">この場所には、SquirrelSetup と .log という2つのログファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="25400-124">At this location, there are two log files of interest, SquirrelSetup.log and logs.txt.</span></span>

- <span data-ttu-id="25400-125">この場所に SquirrelSetup ファイルが書き込まれます。 update.exe は、Teams アプリをサービスする実行可能ファイルです。</span><span class="sxs-lookup"><span data-stu-id="25400-125">The SquirrelSetup.log file at this location is written by Update.exe, which is an executable that services the Teams app.</span></span>
- <span data-ttu-id="25400-126">ログの .txt ファイルは、Teams アプリ (具体的には Teams) によって、重要なアプリケーションイベントを記録するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="25400-126">The Logs.txt file is used by the Teams app (specifically Teams.exe) to record significant application events.</span></span> <span data-ttu-id="25400-127">エラー情報が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25400-127">It will likely contain failure information.</span></span>

<span data-ttu-id="25400-128">これらのログファイルには、個人を特定できる情報 (PII) が含まれているため、Microsoft に送信されることはありません。</span><span class="sxs-lookup"><span data-stu-id="25400-128">These log files contain personally identifiable information (PII) and so they're not sent to Microsoft.</span></span>

<span data-ttu-id="25400-129">チームは、自動的に更新プロセスを開始するか (ポリシーによって異なります)、ユーザーはプロファイルの写真 > 更新プログラムを**確認**することで、更新プログラムを手動で確認できます。</span><span class="sxs-lookup"><span data-stu-id="25400-129">Teams can automatically start the update process (depending on the policy) or users can manually check for updates by going to their profile picture > **Check for updates**.</span></span> <span data-ttu-id="25400-130">どちらの方法でも、次のイベントシーケンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="25400-130">Both methods use the following sequence of events.</span></span>

1. <span data-ttu-id="25400-131">**更新プログラムを確認**します。</span><span class="sxs-lookup"><span data-stu-id="25400-131">**Check for updates**.</span></span> <span data-ttu-id="25400-132">チームが web 要求を行い、現在のアプリのバージョンと展開リングの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="25400-132">Teams makes a web request and includes the current app version and deployment ring information.</span></span> <span data-ttu-id="25400-133">この手順の目標は、ダウンロードリンクを取得することです。</span><span class="sxs-lookup"><span data-stu-id="25400-133">The goal of this step is to get the download link.</span></span> <span data-ttu-id="25400-134">この手順で失敗すると、ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="25400-134">A failure at this step is logged in Logs.txt.</span></span>
2. <span data-ttu-id="25400-135">**更新プログラムをダウンロード**します。</span><span class="sxs-lookup"><span data-stu-id="25400-135">**Download update**.</span></span> <span data-ttu-id="25400-136">チームは、手順1で取得したダウンロードリンクを使用して、更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="25400-136">Teams downloads the update by using the download link obtained from step 1.</span></span> <span data-ttu-id="25400-137">ダウンロードが完了すると、Teams によって update.exe が呼び出され、ダウンロードがステージされます。</span><span class="sxs-lookup"><span data-stu-id="25400-137">When the download is complete, Teams calls Update.exe to stage the download.</span></span> <span data-ttu-id="25400-138">ダウンロードに失敗した場合も、output.txt にログが記録されます。</span><span class="sxs-lookup"><span data-stu-id="25400-138">A download failure is also logged in Logs.txt.</span></span>
3. <span data-ttu-id="25400-139">**更新をステージ**します。</span><span class="sxs-lookup"><span data-stu-id="25400-139">**Stage the update**.</span></span> <span data-ttu-id="25400-140">ダウンロードしたコンテンツは検証され、%LocalAppData%\Microsoft\Teams\stage の中間フォルダーに展開されます。これは、update.exe によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="25400-140">The downloaded content is verified and unpacked into an intermediate folder, %LocalAppData%\Microsoft\Teams\stage), which is done by Update.exe.</span></span> <span data-ttu-id="25400-141">この手順でのエラーは、SquirrelTemp に記録されます。</span><span class="sxs-lookup"><span data-stu-id="25400-141">Failures at this step are logged in SquirrelTemp.log.</span></span>
4. <span data-ttu-id="25400-142">**更新プログラムをインストール**します。</span><span class="sxs-lookup"><span data-stu-id="25400-142">**Install the update**.</span></span> <span data-ttu-id="25400-143">Teams を開始するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="25400-143">There are multiple ways to start Teams.</span></span> <span data-ttu-id="25400-144">ユーザーがログインしたとき、またはショートカットを使用してチームを起動したときに、システムによってチームが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="25400-144">The system automatically starts Teams when a user logs in or you can start Teams through a shortcut.</span></span> <span data-ttu-id="25400-145">この手順では、update.exe でステージングフォルダーの存在を確認し、もう一度コンテンツを検証し、ファイル操作を実行してアプリのステージを解除します。</span><span class="sxs-lookup"><span data-stu-id="25400-145">In this step, Update.exe checks for the presence of the staging folder, verifies the content again, and performs file operations to un-stage the app.</span></span> <span data-ttu-id="25400-146">%LocalAppData%\Microsoft\Teams\current の古いアプリケーションフォルダーは%LocalAppData%\Microsoft\Teams\previous にバックアップされ、stage フォルダー名は "current" に変更されます。</span><span class="sxs-lookup"><span data-stu-id="25400-146">The old application folder in %LocalAppData%\Microsoft\Teams\current is backed up to %LocalAppData%\Microsoft\Teams\previous and the stage folder is renamed to "current".</span></span> <span data-ttu-id="25400-147">この手順でのエラーは、SquirrelTemp に記録されます。</span><span class="sxs-lookup"><span data-stu-id="25400-147">Failures at this step are logged in SquirrelTemp.log.</span></span>

<span data-ttu-id="25400-148">SquirrelTemp または Logs には、基になる原因を特定するための十分な情報が含まれておらず、問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステムログを収集して分析](#collect-and-analyze-application-and-system-logs)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25400-148">If SquirrelTemp.log or Logs.txt don't contain sufficient information to determine the underlying cause and you need more information to troubleshoot the issue, go to [Collect and analyze application and system logs](#collect-and-analyze-application-and-system-logs).</span></span>

## <a name="collect-and-analyze-application-and-system-logs"></a><span data-ttu-id="25400-149">アプリケーションとシステムログの収集と分析</span><span class="sxs-lookup"><span data-stu-id="25400-149">Collect and analyze application and system logs</span></span>

<span data-ttu-id="25400-150">このセクションでは、アプリケーションとシステムログを収集して分析する方法について説明します。この問題を解決するための包括的な情報を入手します。</span><span class="sxs-lookup"><span data-stu-id="25400-150">This section describes how to collect and analyze application and system logs to get more comprehensive information to troubleshoot the issue.</span></span> <span data-ttu-id="25400-151">次の手順を実行するには、Sysinternals ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="25400-151">You'll use Sysinternals tools to complete these steps.</span></span> <span data-ttu-id="25400-152">詳細については、「 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25400-152">To learn more, see [Windows Sysinternals](https://docs.microsoft.com/sysinternals/).</span></span>

### <a name="collect-logs"></a><span data-ttu-id="25400-153">ログを収集する</span><span class="sxs-lookup"><span data-stu-id="25400-153">Collect logs</span></span>

1. <span data-ttu-id="25400-154">[Sysinternals ツール](https://download.sysinternals.com/files/SysinternalsSuite.zip)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="25400-154">Download the [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip).</span></span>
2. <span data-ttu-id="25400-155">ローカルドライブの% TEMP% フォルダーに zip ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="25400-155">Extract the zip file to the %TEMP% folder on your local drive.</span></span>
3. <span data-ttu-id="25400-156">管理者特権でコマンドプロンプトを開き、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="25400-156">Open an elevated command prompt, and then do the following:</span></span>

    1. <span data-ttu-id="25400-157">TEMP フォルダーに移動するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="25400-157">Run the following to go to your TEMP folder:</span></span>

        ```
        cd /d %TEMP%
        ```
    2. <span data-ttu-id="25400-158">セットアップログとアプリケーションログをコピーします。</span><span class="sxs-lookup"><span data-stu-id="25400-158">Copy the setup and application logs.</span></span> <span data-ttu-id="25400-159">エラーの原因によっては、これらのログの一部が表示されない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="25400-159">Note that depending on the point of failure, some of these logs may not be present.</span></span>

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. <span data-ttu-id="25400-160">開いているハンドルをキャプチャするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="25400-160">Run the following to capture the open handles.</span></span>

        ```
        handle > handles.txt
        ```

    4. <span data-ttu-id="25400-161">次のように実行して、開いている Dll をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="25400-161">Run the following to capture the opened DLLs.</span></span>

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. <span data-ttu-id="25400-162">実行されているドライバーをキャプチャするには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="25400-162">Run the following to capture the drivers that are running.</span></span>

        ```
        driverquery /v > driverquery.txt
        ```

    6. <span data-ttu-id="25400-163">Teams フォルダーのアクセス制御リスト (Acl) を取得するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="25400-163">Run the following to capture the access control lists (ACLs) of the Teams folder.</span></span>

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a><span data-ttu-id="25400-164">分析ログ (上級ユーザー向け)</span><span class="sxs-lookup"><span data-stu-id="25400-164">Analyze logs (for advanced users)</span></span>

<span data-ttu-id="25400-165">更新に失敗すると、アプリの予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25400-165">A failed update can result in unpredictable app behavior.</span></span> <span data-ttu-id="25400-166">たとえば、チームを終了したり、古いバージョンの Teams を使用したり、チームを開始したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="25400-166">For example, users may be unable to exit Teams, have a stale version of Teams, or can't start Teams.</span></span> <span data-ttu-id="25400-167">更新時に問題が発生した場合は、最初に原因を特定するための最初の場所は SquirrelTemp です。</span><span class="sxs-lookup"><span data-stu-id="25400-167">If you experience an issue during an update, the first place to look to find the cause is SquirrelTemp.log.</span></span> <span data-ttu-id="25400-168">ここでは、最も一般的な [最小] から [一般的] までのさまざまな更新エラー、およびログを使用した分析とトラブルシューティングの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="25400-168">Here are the different types of update failures, listed from most common to least common, and how to analyze and troubleshoot them using logs.</span></span>

#### <a name="unable-to-exit-teams"></a><span data-ttu-id="25400-169">チームを終了できません</span><span class="sxs-lookup"><span data-stu-id="25400-169">Unable to exit Teams</span></span>

<span data-ttu-id="25400-170">Teams によって、新しいバージョンに更新する必要があると判断された場合は、新しいアプリをダウンロードしてステージングし、次にコンピューターがアイドル状態になったときに、機会が自動的に再起動されるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="25400-170">As Teams determines that it needs to update itself to a newer version, it downloads and stages the new app, and then waits for an opportunity to restart itself the next time the machine is idle.</span></span> <span data-ttu-id="25400-171">このプロセスで一般的に発生する問題は、別のプロセスまたはファイルシステムドライバーによって Teams の .exe プロセスがロックされた場合です。これにより、Teams は終了できなくなります。</span><span class="sxs-lookup"><span data-stu-id="25400-171">A common issue during this process is when another process or a file system driver locks up the Teams.exe process, which prevents Teams.exe from exiting.</span></span> <span data-ttu-id="25400-172">このため、新しくダウンロードされたアプリと段階的に展開されたアプリで Teams アプリを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="25400-172">As a result, the Teams app can't be replaced by the newly-downloaded and staged app.</span></span>

<span data-ttu-id="25400-173">トラブルシューティングのヒント:</span><span class="sxs-lookup"><span data-stu-id="25400-173">Troubleshooting tips:</span></span>

- <span data-ttu-id="25400-174">発生している問題であることを確認するには、Teams を終了します (タスクバーの [チーム] を右クリックし、[**終了**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="25400-174">To confirm that is the issue that you're experiencing, quit Teams (right-click Teams on the task bar, and then click **Quit**).</span></span> <span data-ttu-id="25400-175">次に、Windows で [タスクマネージャー] を開いて、Teams のインスタンスがまだ実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25400-175">Then, open Task Manager in Windows to see whether an instance of Teams is still running.</span></span>  
- <span data-ttu-id="25400-176">この問題が発生しているコンピューターを使っていない場合は、この問題が発生しているコンピューターから収集された SquirrelTemp を調べて、"ログのプロセスを終了できません" というエントリを探します。</span><span class="sxs-lookup"><span data-stu-id="25400-176">If you’re not on the computer that's having this issue, inspect the SquirrelTemp.log collected from the computer that's experiencing this issue and look for a "Program: Unable to terminate the process in the log" entry.</span></span>
- <span data-ttu-id="25400-177">Teams の終了を妨げている原因を特定するには、file.txt のログを処理します。</span><span class="sxs-lookup"><span data-stu-id="25400-177">To determine what's preventing Teams.exe from exiting, look at the Dlls.txt and Handles.txt logs.</span></span> <span data-ttu-id="25400-178">これにより、チームが終了できないプロセスが示されます。</span><span class="sxs-lookup"><span data-stu-id="25400-178">These tell you the processes that prevented Teams from exiting.</span></span>
- <span data-ttu-id="25400-179">チームが終了するのを防ぐ別の原因として、カーネルモードのファイルシステムフィルタードライバーがあります。</span><span class="sxs-lookup"><span data-stu-id="25400-179">Another culprit that can prevent Teams from exiting is the kernel-mode file system filter driver.</span></span> <span data-ttu-id="25400-180">SysInternals tool、 [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)を使用して、実行```procdump -mk <pid>```することによってカーネルモードのプロセス<pid>ダンプを収集します。ここでは、Task MANAGER から取得したプロセス ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="25400-180">Use the SysInternals tool, [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump), to collect the kernel-mode process dump by running ```procdump -mk <pid>```, where <pid> is the process ID obtained from Task Manager.</span></span> <span data-ttu-id="25400-181">Driverquery ログファイルを調べて、Teams の妨げになる可能性のあるアクティブなフィルタードライバーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="25400-181">You can also inspect the Driverquery.txt log file to see the active filter drivers that may interfere with Teams.</span></span>
- <span data-ttu-id="25400-182">この状態から回復するには、コンピューターを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="25400-182">To recover from this state, restart the computer.</span></span>

#### <a name="file-permissions"></a><span data-ttu-id="25400-183">ファイルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="25400-183">File permissions</span></span>

<span data-ttu-id="25400-184">チームは、インストールと更新のプロセス全体を通じて、ユーザーのプロファイルにいくつかのサブフォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="25400-184">Teams creates a number of subfolders and files in the user's profile throughout the installation and update process.</span></span> <span data-ttu-id="25400-185">アプリとアップデーターは、昇格されていないユーザーとして実行されるため、読み取りと書き込みのアクセス許可は、次のフォルダーで許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25400-185">Because the app and the updater runs as a non-elevated user, read and write permissions must be granted on the following folders:</span></span>

|<span data-ttu-id="25400-186">]</span><span class="sxs-lookup"><span data-stu-id="25400-186">Folder</span></span>  |<span data-ttu-id="25400-187">使用者</span><span class="sxs-lookup"><span data-stu-id="25400-187">Used by</span></span>  |
|---------|---------|
|<span data-ttu-id="25400-188">%LocalAppData%\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="25400-188">%LocalAppData%\SquirrelTemp</span></span>     | <span data-ttu-id="25400-189">インストールフェーズでの Teams インストーラー (Teams_Windows_x64 など)</span><span class="sxs-lookup"><span data-stu-id="25400-189">Teams installer (for example, Teams_Windows_x64.exe) during installation phase</span></span>        |
|<span data-ttu-id="25400-190">%LocalAppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="25400-190">%LocalAppData%\Microsoft\Teams</span></span>  | <span data-ttu-id="25400-191">更新プロセス中にアプリパッケージを抽出してステージングするための Teams アップデーター (update.exe)</span><span class="sxs-lookup"><span data-stu-id="25400-191">Teams updater (Update.exe) to extract and stage the app package during update process</span></span>        |
|<span data-ttu-id="25400-192">%AppData%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="25400-192">%AppData%\Microsoft\Teams</span></span>   |  <span data-ttu-id="25400-193">設定、アプリの状態、および (段階的に) ダウンロードされた更新パッケージを保存するための teams アプリ (Teams)</span><span class="sxs-lookup"><span data-stu-id="25400-193">Teams app (Teams.exe) to save settings, app states, and the (pre-staged) downloaded update package</span></span>       |

<span data-ttu-id="25400-194">ファイルに書き込むことができないため、Teams でアクセスが拒否されている場合、別のソフトウェアアプリケーションが妨害しているか、セキュリティ記述子エントリがフォルダーへの書き込みアクセスを制限している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25400-194">If Teams is denied access because it can't write to a file, another software application may be interfering or a security descriptor entry may be limiting write access to a folder.</span></span>

<span data-ttu-id="25400-195">トラブルシューティングのヒント:</span><span class="sxs-lookup"><span data-stu-id="25400-195">Troubleshooting tips:</span></span>

- <span data-ttu-id="25400-196">SquirrelTemp または .log で "アクセス拒否" の証拠を探します。</span><span class="sxs-lookup"><span data-stu-id="25400-196">Look for "access denied" evidence in SquirrelTemp.log or Logs.txt.</span></span> <span data-ttu-id="25400-197">これらのファイルを確認して、失敗したファイルへの書き込みが試みられたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25400-197">Check these files to see whether there was an attempt to write to a file that failed.</span></span>
- <span data-ttu-id="25400-198">Icacls.exe を開いて、管理者以外のユーザーによる書き込み操作をブロックする有効なアクセス制御エントリ (ACE) を探します。通常、これは DACL エントリの1つです。</span><span class="sxs-lookup"><span data-stu-id="25400-198">Open Icacls.txt and look for the effective access control entry (ACE) that blocks write operations by a user who is not an admin. Typically, this is in one of the DACL entries.</span></span> <span data-ttu-id="25400-199">詳細については、「 [icacls.exe のドキュメント](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25400-199">For more information, see the [icacls documentation](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls).</span></span>

#### <a name="file-corrupted"></a><span data-ttu-id="25400-200">ファイルが壊れている</span><span class="sxs-lookup"><span data-stu-id="25400-200">File corrupted</span></span>

<span data-ttu-id="25400-201">場合によっては、暗号化ソフトウェアによって%LocalAppData%\Microsoft\Teams フォルダー内のファイルが変更されることがあります。これにより、チームの開始を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="25400-201">In some cases, encryption software can change files in the %LocalAppData%\Microsoft\Teams folder, which can prevent Teams from starting.</span></span> <span data-ttu-id="25400-202">これは、アプリが更新されていないときでも、いつでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25400-202">This can happen at any time, even when the app isn't being updated.</span></span> <span data-ttu-id="25400-203">残念ながら、ファイルが破損している場合、この状態から回復するには、Teams をアンインストールしてから再インストールする方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="25400-203">Unfortunately, when a file is corrupted, the only way to recover from this state is to uninstall and re-install Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="25400-204">以下のいずれかの手順を実行して、問題の基になる原因を特定できない場合は、[プロセスモニター](https://docs.microsoft.com/sysinternals/downloads/procmon)セッションを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="25400-204">If you can't determine the underlying cause of the issue by using any of these steps, you may want to try a [Process Monitor](https://docs.microsoft.com/sysinternals/downloads/procmon) session.</span></span> <span data-ttu-id="25400-205">プロセスモニターは、レジストリとファイルシステムへのアクセスを記録する Sysinternals ツールです。</span><span class="sxs-lookup"><span data-stu-id="25400-205">Process Monitor is a Sysinternals tool that records access to the registry and file system.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25400-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="25400-206">Related topics</span></span>

- [<span data-ttu-id="25400-207">Teams のクライアントを取得する</span><span class="sxs-lookup"><span data-stu-id="25400-207">Get clients for Teams</span></span>](get-clients.md)
- [<span data-ttu-id="25400-208">Teams クライアントの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="25400-208">Teams client updates</span></span>](teams-client-update.md)