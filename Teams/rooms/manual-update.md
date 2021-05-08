---
title: デバイスを手動Microsoft Teams ミーティングする
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: デバイスを特定のバージョンに手動Microsoft Teams ミーティング更新する方法について説明します。
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117515"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="b1188-103">デバイスを手動Microsoft Teams ミーティングする</span><span class="sxs-lookup"><span data-stu-id="b1188-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="b1188-104">アプリMicrosoft Teams ミーティングは、アプリを通じて配布Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="b1188-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="b1188-105">アプリの更新プログラムは、夜間のメンテナンス中Microsoft Storeから自動的にインストールされます。これは、更新プログラムを取得するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="b1188-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="b1188-106">ただし、一部のデバイスでは、Teams ミーティングデバイスから更新プログラムを受信できない場合Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="b1188-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="b1188-107">たとえば、セキュリティ ポリシーでは、デバイスがインターネットに接続できない場合や、デバイスからアプリをダウンロードできない場合Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="b1188-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="b1188-108">または、セットアップを実行する前にデバイスを更新する必要がある場合があります。その間Microsoft Storeは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b1188-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="b1188-109">Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリ更新 PowerShell スクリプトを使用して、Teams ミーティング デバイスを新しいバージョンの Teams ミーティング アプリに手動で更新できます。</span><span class="sxs-lookup"><span data-stu-id="b1188-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="b1188-110">この記事の手順に従って、デバイスを手動でTeams ミーティングします。</span><span class="sxs-lookup"><span data-stu-id="b1188-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="b1188-111">このプロセスでは、既にインストールされているTeams ミーティングデバイスを更新Teams ミーティング更新できます。</span><span class="sxs-lookup"><span data-stu-id="b1188-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="b1188-112">新しいインストールの実行には使用できません。</span><span class="sxs-lookup"><span data-stu-id="b1188-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="b1188-113">また、アプリを以前のバージョンにダウングレードするためにも使用できません。</span><span class="sxs-lookup"><span data-stu-id="b1188-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="b1188-114">Teams ミーティング アプリの新しいインストールを実行するには、デバイスの製造元に特定のメディアを問い合わせ、または「インストール メディアを準備する」[を参照してください](console.md#prepare-the-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="b1188-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="b1188-115">手順 1: オフライン アプリの更新スクリプトをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="b1188-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="b1188-116">まず、オフライン アプリ更新スクリプトの最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b1188-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="b1188-117">スクリプトをダウンロードするには、 をクリックします <https://go.microsoft.com/fwlink/?linkid=2151817> 。</span><span class="sxs-lookup"><span data-stu-id="b1188-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="b1188-118">スクリプトは、デバイスの既定のダウンロード フォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="b1188-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="b1188-119">ダウンロードしたファイルは、ダウンロードしたファイルがブロック済みとしてマークWindows。</span><span class="sxs-lookup"><span data-stu-id="b1188-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="b1188-120">操作を行わずにスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1188-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="b1188-121">スクリプトのブロックを解除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1188-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="b1188-122">エクスプローラーでファイルを右クリックする</span><span class="sxs-lookup"><span data-stu-id="b1188-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="b1188-123">[プロパティ] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="b1188-123">Click **Properties**</span></span>
3. <span data-ttu-id="b1188-124">[ブロック **の解除] を選択する**</span><span class="sxs-lookup"><span data-stu-id="b1188-124">Select **Unblock**</span></span>
4. <span data-ttu-id="b1188-125">**[OK] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="b1188-125">Click **OK**</span></span>

<span data-ttu-id="b1188-126">PowerShell を使用してスクリプトのブロックを解除するには、「ファイルのブロックを解除 [する」を参照してください](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。</span><span class="sxs-lookup"><span data-stu-id="b1188-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="b1188-127">オフライン アプリの更新スクリプトがダウンロードされた後、ファイルをデバイスにTeams ミーティングします。</span><span class="sxs-lookup"><span data-stu-id="b1188-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="b1188-128">USB ドライブを使用するか、デバイスの管理モードでネットワーク ファイル共有からファイルにアクセスして、デバイスにファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="b1188-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="b1188-129">デバイスでファイルを保存する場所をメモしてください。</span><span class="sxs-lookup"><span data-stu-id="b1188-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="b1188-130">手順 2: スクリプトを実行してアプリをTeams ミーティングする</span><span class="sxs-lookup"><span data-stu-id="b1188-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="b1188-131">オフライン アプリの更新スクリプトは、管理者特権でコマンド プロンプトから実行する必要があります。Skype ユーザー (アプリを実行するユーザー) はまだサインインしています。</span><span class="sxs-lookup"><span data-stu-id="b1188-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="b1188-132">Skype ユーザーがまだログインしている間に管理者アカウントにログインして管理者特権のコマンド プロンプトを使用する方法の詳細については、「管理者モードに切り替えて[、Microsoft Teams ミーティング](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)アプリが実行されているときに戻る」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1188-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="b1188-133">管理者特権のコマンド プロンプトからスクリプトを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1188-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="b1188-134">管理モードに切り替える</span><span class="sxs-lookup"><span data-stu-id="b1188-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="b1188-135">[スタート] アイコンをクリックし、「コマンド プロンプト」 **と入力** して、[管理者として **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b1188-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="b1188-136">次のコマンドを実行 `<path to script>` します。スクリプトへの完全なパスとスクリプト ファイルの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1188-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="b1188-137">たとえば、スクリプト ファイルが にあり、スクリプト ファイル名が である場合は、 `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1188-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="b1188-138">スクリプトの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="b1188-138">Allow the script to run.</span></span> <span data-ttu-id="b1188-139">完了すると、スクリプトはデバイスを再起動Teams ミーティングします。</span><span class="sxs-lookup"><span data-stu-id="b1188-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="b1188-140">リモート PowerShell を使用してスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1188-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="b1188-141">デバイスでリモート PowerShell を使用する方法の詳細Teams ミーティング PowerShell を使用したリモート[管理に関するページを参照してください](rooms-operations.md#remote-management-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b1188-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="b1188-142">手順 3: アプリが正常に更新されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="b1188-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="b1188-143">スクリプトが正常に実行されると、デバイスは新しいアプリTeams ミーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b1188-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="b1188-144">スクリプトで問題が発生した場合は、コマンド ラインで問題が発生したかどうかを示し、その出力をファイルに記録します。</span><span class="sxs-lookup"><span data-stu-id="b1188-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="b1188-145">スクリプトによって提供される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b1188-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="b1188-146">Microsoft サポートに連絡する必要がある場合は、サポート要求と共にログ ファイルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1188-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="b1188-147">スクリプトによって、ログ ファイルへのパスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b1188-147">The script will provide you with the path to the log file.</span></span>