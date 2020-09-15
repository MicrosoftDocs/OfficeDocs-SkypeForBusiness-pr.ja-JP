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
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814466"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="5fe1b-103">Microsoft Teams PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="5fe1b-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="5fe1b-104">この記事では、 [PowerShellGet](/powershell/scripting/gallery/installing-psget)を使って Microsoft Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="5fe1b-105">これらの手順は、 [Azure Cloud Shell](/azure/cloud-shell/overview)、Linux、MacOS、Windows プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="5fe1b-106">要件</span><span class="sxs-lookup"><span data-stu-id="5fe1b-106">Requirements</span></span>

<span data-ttu-id="5fe1b-107">Teams PowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="5fe1b-108">使用しているオペレーティングシステムに対応した [最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="5fe1b-109">PowerShell 7 と Teams PowerShell について、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="5fe1b-110">最適なエクスペリエンスを実現するには、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="5fe1b-111">Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="5fe1b-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="5fe1b-112">最適なエクスペリエンスを実現するには、一般的な可用性 (GA) とパブリックプレビューモジュールのどちらも使用してください。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="5fe1b-113">共同作業を目的としているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-113">They're not intended to work together.</span></span>


<span data-ttu-id="5fe1b-114">**PowerShellGet**コマンドレットを使用して Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="5fe1b-115">システム上のすべてのユーザー用にモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="5fe1b-116">Windows の [ **管理者として実行** ] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="5fe1b-117">既定では、PowerShell ギャラリー (PSGallery) は、 **PowerShellGet**用の信頼できるリポジトリとして構成されていません。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="5fe1b-118">初めて PSGallery を使用するときは、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="5fe1b-119">**[はい]** または **[はい] を**選び、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="5fe1b-120">Teams PowerShell パブリックプレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="5fe1b-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="5fe1b-121">Teams PowerShell のパブリックプレビュー版を使用している場合は、まず Skype for Business Online Connector をアンインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="5fe1b-122">システム上のすべてのユーザー用に Teams PowerShell パブリックプレビューモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="5fe1b-123">Windows の [ **管理者として実行** ] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="5fe1b-124">PowerShell 5.1 を使用している場合は、 **PowerShellGet** モジュールを事前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="5fe1b-125">**PowerShellGet**を更新したら、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の**PowerShellGet**が読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="5fe1b-126">Teams PowerShell パブリックプレビューをインストールするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="5fe1b-127">最新のプレビューバージョンは、 [Powershell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams) または powershell で、"Find-Module microsoft Teams-allowprerelease リリース" を実行して確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="5fe1b-128">Skype for Business Online Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="5fe1b-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="5fe1b-129">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="5fe1b-130">最新の [Teams PowerShell パブリックリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="5fe1b-131">サインイン</span><span class="sxs-lookup"><span data-stu-id="5fe1b-131">Sign in</span></span>

<span data-ttu-id="5fe1b-132">Teams PowerShell の使用を開始するには、Azure の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="5fe1b-133">最新の [Teams PowerShell パブリックプレビューリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="5fe1b-134">Teams PowerShell の更新</span><span class="sxs-lookup"><span data-stu-id="5fe1b-134">Update Teams PowerShell</span></span>

<span data-ttu-id="5fe1b-135">Teams PowerShell を更新するには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="5fe1b-136">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="5fe1b-137">PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="5fe1b-138">Teams PowerShell をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5fe1b-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="5fe1b-139">Teams PowerShell をアンインストールするには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="5fe1b-140">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="5fe1b-141">PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fe1b-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="5fe1b-142">Next Steps</span></span>

<span data-ttu-id="5fe1b-143">これで、Teams PowerShell を使用してチームを管理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="5fe1b-144">始めるには、「 [Teams PowerShell で teams を管理](teams-powershell-managing-teams.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fe1b-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fe1b-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5fe1b-145">Related topics</span></span>

[<span data-ttu-id="5fe1b-146">Teams PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="5fe1b-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="5fe1b-147">Teams PowerShell リリースノート</span><span class="sxs-lookup"><span data-stu-id="5fe1b-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="5fe1b-148">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="5fe1b-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="5fe1b-149">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="5fe1b-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
