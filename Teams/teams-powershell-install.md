---
title: Microsoft Teams PowerShell をインストールする
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell コントロールを使用して Microsoft Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824938"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="4bc18-103">Microsoft Teams PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="4bc18-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="4bc18-104">この記事では [、PowerShellGet](/powershell/scripting/gallery/installing-psget)を使用して Microsoft Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="4bc18-105">以下の手順は [、Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS、および Windows プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4bc18-106">要件</span><span class="sxs-lookup"><span data-stu-id="4bc18-106">Requirements</span></span>

<span data-ttu-id="4bc18-107">Teams PowerShell を使用するには、すべてのプラットフォームでの PowerShell 5.1 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc18-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="4bc18-108">使用している [オペレーティング システムで利用可能な最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="4bc18-109">PowerShell 7 および Teams PowerShell に関して既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="4bc18-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="4bc18-110">最高の操作性を得るには、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="4bc18-111">Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="4bc18-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="4bc18-112">最高のエクスペリエンスを得るには、一般向け利用可能 (GA) モジュールまたはパブリック プレビュー モジュール (両方とも) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="4bc18-113">共同作業を行うことをおすすめでした。</span><span class="sxs-lookup"><span data-stu-id="4bc18-113">They're not intended to work together.</span></span>


<span data-ttu-id="4bc18-114">**PowerShellGet コマンド**レットを使用して、Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="4bc18-115">システム上のすべてのユーザーのモジュールをインストールするには、電子のアクセス可能なアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc18-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="4bc18-116">Windows で管理者として実行するか、macOS または**Run as administrator** `sudo` Linux 上のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="4bc18-117">既定では、PowerShell ギャラリー (PSGallery) は **PowerShellGet**の信頼できるリポジトリとして構成されません。</span><span class="sxs-lookup"><span data-stu-id="4bc18-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="4bc18-118">PSGallery を初めて使用する場合、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bc18-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="4bc18-119">インストール **を続** 行するには **、[はい] または [は** い] に答えます。</span><span class="sxs-lookup"><span data-stu-id="4bc18-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="4bc18-120">Teams PowerShell パブリック プレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="4bc18-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="4bc18-121">パブリック プレビュー版版の Teams PowerShell を使用している場合は、最初に Skype for Business Online Connector をアンインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="4bc18-122">システム上のすべてのユーザーに対して、Teams PowerShell パブリック プレビュー モジュールをインストールするには、電子のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bc18-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="4bc18-123">Windows で管理者として実行するか、macOS または**Run as administrator** `sudo` Linux 上のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="4bc18-124">PowerShell 5.1 を使用している場合は **、PowerShellGet** モジュールを前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bc18-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="4bc18-125">**PowerShellGet を更新したら、** 管理者向け PowerShell のスケッションを閉じて、再度開き、**最新の PowerShellGet が**読み込れるようにします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="4bc18-126">Teams PowerShell パブリック プレビューをインストールするには、下の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="4bc18-127">PowerShell ギャラリーまたは [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) で、"Find-Module MicrosoftTeams -AllowPrerelease" を実行して、最新のプレビュー版を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4bc18-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="4bc18-128">Skype for Business Online Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="4bc18-128">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="4bc18-129">Skype for Business Online Connector は、現在、Teams PowerShell パブリック プレビューに含されています。</span><span class="sxs-lookup"><span data-stu-id="4bc18-129">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="4bc18-130">この機能を Teams PowerShell の GA リリースにロールすると、Skype for Business Online Connector は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4bc18-130">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="4bc18-131">Skype for [Business PowerShell モジュールをダウンロードして](https://www.microsoft.com/download/details.aspx?id=39366)インストールし、PowerShell で次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-131">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="4bc18-132">サインイン</span><span class="sxs-lookup"><span data-stu-id="4bc18-132">Sign in</span></span>

<span data-ttu-id="4bc18-133">Teams PowerShell の使用を開始するには、Azure 資ーデンシャルでサインインします。</span><span class="sxs-lookup"><span data-stu-id="4bc18-133">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="4bc18-134">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースを使用している場合は、Skype for Business Online Connector をインストールする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="4bc18-134">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="4bc18-135">Teams PowerShell を更新する</span><span class="sxs-lookup"><span data-stu-id="4bc18-135">Update Teams PowerShell</span></span>

<span data-ttu-id="4bc18-136">Teams PowerShell を更新するには、新しい管理者向け PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-136">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="4bc18-137">PowerShell が既に PowerShell のスケッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-137">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="4bc18-138">PowerShell を閉じて、新しい、または管理された PowerShell のスケッションを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="4bc18-138">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="4bc18-139">Teams PowerShell をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="4bc18-139">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="4bc18-140">Teams PowerShell をアンインストールするには、新しい管理者用 PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bc18-140">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="4bc18-141">PowerShell のスケッションに既にインポートされている Teams の PowerShell がある場合、モジュールをアンインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bc18-141">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="4bc18-142">PowerShell を閉じて、新しい、または管理された PowerShell のスケッションを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="4bc18-142">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4bc18-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="4bc18-143">Next Steps</span></span>

<span data-ttu-id="4bc18-144">Teams PowerShell を使用して Teams を管理する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="4bc18-144">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="4bc18-145">開始 [するには、Teams PowerShell で Teams を](teams-powershell-managing-teams.md) 管理する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bc18-145">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bc18-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bc18-146">Related topics</span></span>

[<span data-ttu-id="4bc18-147">Teams PowerShell で Teams を管理する</span><span class="sxs-lookup"><span data-stu-id="4bc18-147">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="4bc18-148">Teams PowerShell リリース ノート</span><span class="sxs-lookup"><span data-stu-id="4bc18-148">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="4bc18-149">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="4bc18-149">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="4bc18-150">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="4bc18-150">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
