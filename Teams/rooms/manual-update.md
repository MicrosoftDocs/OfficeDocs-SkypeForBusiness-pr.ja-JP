---
title: Microsoft Teams の会議室デバイスを手動で更新する
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
description: Microsoft Teams Rooms デバイスを特定のバージョンに手動で更新する方法について説明します。
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731395"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="191d5-103">Microsoft Teams の会議室デバイスを手動で更新する</span><span class="sxs-lookup"><span data-stu-id="191d5-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="191d5-104">Microsoft Teams Rooms アプリは、Microsoft Store を通じて配布されます。</span><span class="sxs-lookup"><span data-stu-id="191d5-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="191d5-105">夜間のメンテナンス中に、アプリの更新プログラムが Microsoft Store から自動的にインストールされます。これは、更新プログラムを取得するために推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="191d5-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="191d5-106">ただし、Teams Rooms デバイスが Microsoft Store から更新プログラムを受信できない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="191d5-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="191d5-107">たとえば、セキュリティ ポリシーによって、デバイスがインターネットに接続できない場合や、Microsoft Store からアプリをダウンロードできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="191d5-108">または、セットアップを実行する前にデバイスを更新して、Microsoft Store を利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="191d5-109">Microsoft Store から更新プログラムを取得できない場合は、オフライン アプリの更新 PowerShell スクリプトを使用して、Teams Rooms デバイスを新しいバージョンの Teams Rooms アプリに手動で更新できます。</span><span class="sxs-lookup"><span data-stu-id="191d5-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="191d5-110">Teams Rooms デバイスを手動で更新するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="191d5-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="191d5-111">このプロセスでは、Teams Rooms アプリが既にインストールされている Teams Rooms デバイスのみを更新できます。</span><span class="sxs-lookup"><span data-stu-id="191d5-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="191d5-112">新しいインストールを実行するために使用できません。</span><span class="sxs-lookup"><span data-stu-id="191d5-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="191d5-113">また、アプリを以前のバージョンにダウングレードするためにも使用できません。</span><span class="sxs-lookup"><span data-stu-id="191d5-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="191d5-114">Teams Rooms アプリの新しいインストールを実行するには、デバイスの製造元に問い合わせ、固有のメディアを確認するか、「インストール メディアを準備する [」を参照してください](console.md#prepare-the-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="191d5-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="191d5-115">手順 1: オフライン アプリの更新スクリプトをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="191d5-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="191d5-116">まず、オフライン アプリの更新スクリプトの最新バージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="191d5-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="191d5-117">スクリプトをダウンロードするには、[. <https://go.microsoft.com/fwlink/?linkid=2151817></span><span class="sxs-lookup"><span data-stu-id="191d5-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="191d5-118">スクリプトは、デバイスの既定のダウンロード フォルダーにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="191d5-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="191d5-119">ダウンロードしたファイルは、Windows によってブロック済みとしてマークされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="191d5-120">操作を行わずにスクリプトを実行する必要がある場合は、スクリプトのブロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="191d5-121">スクリプトのブロックを解除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="191d5-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="191d5-122">エクスプローラーでファイルを右クリックする</span><span class="sxs-lookup"><span data-stu-id="191d5-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="191d5-123">[プロパティ] を **クリックする**</span><span class="sxs-lookup"><span data-stu-id="191d5-123">Click **Properties**</span></span>
3. <span data-ttu-id="191d5-124">[ブロック **解除] を選択する**</span><span class="sxs-lookup"><span data-stu-id="191d5-124">Select **Unblock**</span></span>
4. <span data-ttu-id="191d5-125">[OK] を **クリックする**</span><span class="sxs-lookup"><span data-stu-id="191d5-125">Click **OK**</span></span>

<span data-ttu-id="191d5-126">PowerShell を使用してスクリプトのブロックを解除するには、「ファイルのブロック [を解除する」を参照してください](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。</span><span class="sxs-lookup"><span data-stu-id="191d5-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="191d5-127">オフライン アプリの更新スクリプトがダウンロードされた後、ファイルを Teams Rooms デバイスに転送します。</span><span class="sxs-lookup"><span data-stu-id="191d5-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="191d5-128">デバイスの管理モードで、USB ドライブを使用するか、ネットワーク ファイル共有からファイルにアクセスして、デバイスにファイルを転送できます。</span><span class="sxs-lookup"><span data-stu-id="191d5-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="191d5-129">デバイスでファイルを保存する場所をメモしてください。</span><span class="sxs-lookup"><span data-stu-id="191d5-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="191d5-130">手順 2: スクリプトを実行して Teams Rooms アプリを更新する</span><span class="sxs-lookup"><span data-stu-id="191d5-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="191d5-131">オフライン アプリの更新スクリプトは、Skype ユーザー (アプリを実行するユーザー) がまだサインインしている間、管理者特権のコマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="191d5-132">Skype ユーザーがまだログインしている間に管理者アカウントにログインして管理者特権のコマンド プロンプトを使用する方法の詳細については [、「Microsoft Teams Rooms](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)アプリの実行中に管理モードに切り替え、戻る」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191d5-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="191d5-133">管理者特権でコマンド プロンプトからスクリプトを実行するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="191d5-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="191d5-134">管理モードに切り替える</span><span class="sxs-lookup"><span data-stu-id="191d5-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="191d5-135">[スタート] アイコンをクリックし、「コマンド プロンプト **」と入力** して、[管理者として **実行] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="191d5-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="191d5-136">スクリプトのフル パスとスクリプト ファイルの名前を含む `<path to script>` 次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="191d5-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="191d5-137">たとえば、スクリプト ファイルが場所にあり、スクリプト ファイル名が次の `C:\Users\Admin\Downloads` `MTR-Update-4.5.6.7.ps1` 場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="191d5-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="191d5-138">スクリプトの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="191d5-138">Allow the script to run.</span></span> <span data-ttu-id="191d5-139">完了すると、スクリプトは Teams Rooms デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="191d5-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="191d5-140">リモート PowerShell を使用してスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="191d5-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="191d5-141">Teams 会議室デバイスでのリモート PowerShell の使用の詳細については、「PowerShell を使用したリモート [管理」を参照してください](rooms-operations.md#remote-management-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="191d5-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="191d5-142">手順 3: アプリが正常に更新されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="191d5-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="191d5-143">スクリプトが正常に実行されると、デバイスは Teams Rooms アプリに再起動します。</span><span class="sxs-lookup"><span data-stu-id="191d5-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="191d5-144">スクリプトで問題が発生した場合は、コマンド ラインの問題を示し、その出力をファイルに記録します。</span><span class="sxs-lookup"><span data-stu-id="191d5-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="191d5-145">スクリプトで提供される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="191d5-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="191d5-146">Microsoft サポートに連絡する必要がある場合は、サポート要求と共にログ ファイルを必ず含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="191d5-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="191d5-147">スクリプトによって、ログ ファイルへのパスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="191d5-147">The script will provide you with the path to the log file.</span></span>
