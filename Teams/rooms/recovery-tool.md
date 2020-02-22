---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。
ms.openlocfilehash: 755a85c9013d160197c8a8d57f74ef18b207e052
ms.sourcegitcommit: 3d393ceded4d64963411cfdc96931952d480ded5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225281"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="d8ec0-103">Microsoft Teams Rooms の回復ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="d8ec0-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="d8ec0-104">この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="d8ec0-105">このツールは、Microsoft Teams の [ルーム] コンソールに "システム構成の終了" エラーが表示された場合、またはプッシュボタンで[出荷時の復元](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)のリセットを実行する前の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8ec0-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d8ec0-106">Prerequisites</span></span>

<span data-ttu-id="d8ec0-107">最新の[Microsoft Teams ルームインストールパッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、それを USB メモリスティックまたは Microsoft teams 室デバイスにアクセスできるネットワーク共有に抽出します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ec0-108">MSI からファイルを抽出する方法は、さまざまな方法で実現できます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="d8ec0-109">すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムは受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="d8ec0-110">このような方法の1つは`msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` 、 `PathToMsi` Microsoft Teams Room インストールパッケージへの完全パスを示すコマンドを`PathToTarget`使うことです。また、ファイルを抽出するフォルダーのフルパスを表します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="d8ec0-111">ツールを実行する</span><span class="sxs-lookup"><span data-stu-id="d8ec0-111">Running the tool</span></span>

1) <span data-ttu-id="d8ec0-112">Microsoft Teams 室のデバイスで管理者アカウントにサインインして、管理者特権のコマンドプロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="d8ec0-113">Microsoft teams 室のインストールパッケージから抽出されたファイルに含ま`RecoveryTool.ps1 file`れている、microsoft Teams の会議室のデバイスで確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="d8ec0-114">キットは、前提条件を準備するときに使用したネットワーク共有または USB ドライブにあります。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="d8ec0-115">実行`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="d8ec0-116">出荷時の復元を実行している場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="d8ec0-117">スクリプトによってプロンプトが表示されたら、[オプション 2:**リセット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="d8ec0-118">BitLocker がオンになっている場合は、スクリプト出力の最後に示されている手順に従って、無効にします。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="d8ec0-119">出荷時の復元を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="d8ec0-120">**設定**アプリを開き、[**更新] &** の [セキュリティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="d8ec0-121">[**回復**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="d8ec0-122">[**この PC をリセット**する] の下で、[**はじめ**に] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="d8ec0-123">[**すべて削除**]、[**次へ**]、[**リセット**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="d8ec0-124">システムが複数回再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-124">The system will reboot multiple times.</span></span> <span data-ttu-id="d8ec0-125">リセットが完了すると、Windows OOBE 画面にシステムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="d8ec0-126">"古い" システムを修復する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="d8ec0-127">スクリプトによってメッセージが表示されたら、[オプション 1:**修復**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="d8ec0-128">完了したら、Microsoft Teams 室のデバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="d8ec0-129">自動的に再起動され、2回目の回復が完了します。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ec0-130">**[自分のファイルを保持する] でアプリと設定を削除**した場合、Microsoft Teams の会議室が使用できなくなるという既知の問題がありますが、Windows のリセットプロセス中に個人用ファイルオプションが選択されたままになります。</span><span class="sxs-lookup"><span data-stu-id="d8ec0-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="d8ec0-131">このオプション*は使用しないでください。*</span><span class="sxs-lookup"><span data-stu-id="d8ec0-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8ec0-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8ec0-132">See also</span></span>

[<span data-ttu-id="d8ec0-133">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="d8ec0-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="d8ec0-134">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="d8ec0-134">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
