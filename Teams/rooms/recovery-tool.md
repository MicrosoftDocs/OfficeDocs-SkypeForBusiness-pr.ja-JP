---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: dstrome
author: dstrome
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
description: この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態でサポートされている状態になります。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117495"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="312a8-103">Microsoft Teams Rooms の回復ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="312a8-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="312a8-104">この記事では、Microsoft Teams Rooms の回復ツールを使用する方法について説明します。このツールを使用すると、システムが最新の状態でサポートされている状態になります。</span><span class="sxs-lookup"><span data-stu-id="312a8-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="312a8-105">このツールは、Microsoft Teams Rooms 本体に "システム 構成が最新ではありません" というエラーが表示される場合、またはプッシュ ボタンのリセット出荷時の復元を実行する前に適用する [必要があります](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。</span><span class="sxs-lookup"><span data-stu-id="312a8-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="312a8-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="312a8-106">Prerequisites</span></span>

<span data-ttu-id="312a8-107">最新の [Microsoft Teams Rooms インストール パッケージを](https://go.microsoft.com/fwlink/?linkid=851168) ダウンロードし、Microsoft Teams Rooms デバイスからアクセス可能な USB メモリ スティックまたはネットワーク共有に展開します。</span><span class="sxs-lookup"><span data-stu-id="312a8-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="312a8-108">MSI からファイルを抽出するには、多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="312a8-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="312a8-109">すべてのファイルを抽出し、ディレクトリ構造を保持するメカニズムはすべて許容されます。</span><span class="sxs-lookup"><span data-stu-id="312a8-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="312a8-110">そのような方法の 1 つは、Microsoft Teams Room インストール パッケージへのフル パスを表し、ファイルを抽出するフォルダーへのフル パスを表すコマンドを `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="312a8-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="312a8-111">ツールを実行する</span><span class="sxs-lookup"><span data-stu-id="312a8-111">Running the tool</span></span>

1) <span data-ttu-id="312a8-112">Microsoft Teams Rooms デバイスで管理者アカウントにサインインし、管理者特権のコマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="312a8-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="312a8-113">Microsoft Teams Rooms のインストール パッケージから抽出されたファイルに含まれている、アクセスできる Microsoft Teams Rooms デバイス `RecoveryTool.ps1 file` から確認します。</span><span class="sxs-lookup"><span data-stu-id="312a8-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="312a8-114">このキットは、前提条件を準備するときに使用されるネットワーク共有または USB ドライブにあります。</span><span class="sxs-lookup"><span data-stu-id="312a8-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="312a8-115">[実行] を選択します `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。</span><span class="sxs-lookup"><span data-stu-id="312a8-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="312a8-116">出荷時の復元を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="312a8-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="312a8-117">スクリプトによって求めるメッセージが表示されたら、オプション 2: [リセット] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="312a8-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="312a8-118">BitLocker がオンの場合は、スクリプト出力の最後に表示される指示に従って無効にします。</span><span class="sxs-lookup"><span data-stu-id="312a8-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="312a8-119">出荷時の復元を実行します。</span><span class="sxs-lookup"><span data-stu-id="312a8-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="312a8-120">[設定] **アプリを開** き、[セキュリティの **更新&選択する**</span><span class="sxs-lookup"><span data-stu-id="312a8-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="312a8-121">[回復] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="312a8-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="312a8-122">[この **PC をリセットする] の下** の [開始 **] を選ぶ**</span><span class="sxs-lookup"><span data-stu-id="312a8-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="312a8-123">[すべて **削除]、次に**[次へ **]、および** [リセット] の順に **選択します。**</span><span class="sxs-lookup"><span data-stu-id="312a8-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="312a8-124">Microsoft Teams Rooms デバイスは、[ファイルを保持] **-** [アプリと設定を削除します] を選択した場合、使用できなくなる可能性がありますが、Windows のリセット プロセス中に個人用ファイルオプションが選択された状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="312a8-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="312a8-125">このオプションは選択しない。</span><span class="sxs-lookup"><span data-stu-id="312a8-125">Do not select this option.</span></span>
      5. <span data-ttu-id="312a8-126">システムは複数回再起動します。</span><span class="sxs-lookup"><span data-stu-id="312a8-126">The system will reboot multiple times.</span></span> <span data-ttu-id="312a8-127">リセットが完了すると、システムは Windows の "既定のエクスペリエンス" (OOBE) 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="312a8-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="312a8-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="312a8-128">See also</span></span>

[<span data-ttu-id="312a8-129">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="312a8-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="312a8-130">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="312a8-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)