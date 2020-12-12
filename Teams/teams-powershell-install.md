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
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662022"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="32d55-103">Microsoft Teams PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="32d55-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="32d55-104">この記事では [、PowerShellGet](/powershell/scripting/gallery/installing-psget)を使用して Microsoft Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32d55-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="32d55-105">これらの手順は [、Azure Cloud Shell、Linux、macOS、Windows](/azure/cloud-shell/overview)プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="32d55-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="32d55-106">要件</span><span class="sxs-lookup"><span data-stu-id="32d55-106">Requirements</span></span>

<span data-ttu-id="32d55-107">Teams PowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="32d55-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="32d55-108">オペレーティング システム [で利用可能な最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="32d55-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="32d55-109">PowerShell 7 および Teams PowerShell には、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="32d55-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="32d55-110">最適なエクスペリエンスを得る場合は、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32d55-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="32d55-111">Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="32d55-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="32d55-112">最適なエクスペリエンスを得る場合は、両方ではなく、一般提供 (GA) モジュールまたはパブリック プレビュー モジュールのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="32d55-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="32d55-113">これらは、一緒に作業するつもりではありません。</span><span class="sxs-lookup"><span data-stu-id="32d55-113">They're not intended to work together.</span></span>


<span data-ttu-id="32d55-114">**PowerShellGet コマンドレットを** 使用して、Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="32d55-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="32d55-115">システム上のすべてのユーザーにモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="32d55-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="32d55-116">Windows の [管理者として実行] を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="32d55-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="32d55-117">既定では、PowerShell ギャラリー (PSGallery) は PowerShellGet の信頼できるリポジトリ **として構成されていません**。</span><span class="sxs-lookup"><span data-stu-id="32d55-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="32d55-118">PSGallery を初めて使用すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="32d55-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="32d55-119">[ **はい]** または **[はい] から [すべて] に応答** して、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="32d55-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="32d55-120">Teams PowerShell パブリック プレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="32d55-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="32d55-121">Teams PowerShell のパブリック プレビュー 版を使用している場合は、最初に Skype for Business Online Connector をアンインストールすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="32d55-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="32d55-122">システム上のすべてのユーザーに Teams PowerShell パブリック プレビュー モジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="32d55-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="32d55-123">Windows の管理者として実行を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="32d55-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="32d55-124">PowerShell 5.1 を使用している場合は、事前に **PowerShellGet** モジュールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d55-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="32d55-125">**PowerShellGet を更新した** 後、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の **PowerShellGet** が読み込まれるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="32d55-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="32d55-126">Teams PowerShell パブリック プレビューをインストールするには、以下の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="32d55-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="32d55-127">PowerShell ギャラリーまたは [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) で最新のプレビュー バージョンを見つけるには、"Find-Module MicrosoftTeams -AllowPrerelease" を実行します。</span><span class="sxs-lookup"><span data-stu-id="32d55-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="32d55-128">Skype for Business Online Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="32d55-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="32d55-129">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールの一部です。</span><span class="sxs-lookup"><span data-stu-id="32d55-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="32d55-130">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d55-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="32d55-131">サインイン</span><span class="sxs-lookup"><span data-stu-id="32d55-131">Sign in</span></span>

<span data-ttu-id="32d55-132">Teams PowerShell の使用を開始するには、Azure の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="32d55-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="32d55-133">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d55-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="32d55-134">Teams PowerShell を更新する</span><span class="sxs-lookup"><span data-stu-id="32d55-134">Update Teams PowerShell</span></span>

<span data-ttu-id="32d55-135">Teams PowerShell を更新するには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="32d55-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="32d55-136">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="32d55-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="32d55-137">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="32d55-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="32d55-138">Teams PowerShell をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="32d55-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="32d55-139">Teams PowerShell をアンインストールするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="32d55-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="32d55-140">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="32d55-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="32d55-141">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="32d55-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32d55-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="32d55-142">Next Steps</span></span>

<span data-ttu-id="32d55-143">Teams PowerShell を使用して Teams を管理する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="32d55-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="32d55-144">使用 [を開始するには、「Teams PowerShell で Teams](teams-powershell-managing-teams.md) を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d55-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32d55-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="32d55-145">Related topics</span></span>

[<span data-ttu-id="32d55-146">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="32d55-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="32d55-147">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="32d55-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="32d55-148">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="32d55-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="32d55-149">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="32d55-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
