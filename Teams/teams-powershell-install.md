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
ms.openlocfilehash: e6ba8545159f8b18ebe39e49356f64378f946b29
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874807"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="dc186-103">Microsoft Teams PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="dc186-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="dc186-104">この記事では [、PowerShellGet](/powershell/scripting/gallery/installing-psget)を使用して Microsoft Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc186-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="dc186-105">これらの手順は [、Azure Cloud Shell、Linux、macOS、Windows](/azure/cloud-shell/overview)プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="dc186-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="dc186-106">要件</span><span class="sxs-lookup"><span data-stu-id="dc186-106">Requirements</span></span>

<span data-ttu-id="dc186-107">Teams PowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc186-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="dc186-108">オペレーティング システム [で利用可能な最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc186-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="dc186-109">PowerShell 7 および Teams PowerShell には、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="dc186-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="dc186-110">最適なエクスペリエンスを得る場合は、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc186-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="dc186-111">Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="dc186-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="dc186-112">最適なエクスペリエンスを得る場合は、両方ではなく、一般提供 (GA) モジュールまたはパブリック プレビュー モジュールのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc186-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="dc186-113">これらは、一緒に作業するつもりではありません。</span><span class="sxs-lookup"><span data-stu-id="dc186-113">They're not intended to work together.</span></span>


<span data-ttu-id="dc186-114">**PowerShellGet コマンドレットを** 使用して、Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc186-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="dc186-115">システム上のすべてのユーザーにモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc186-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="dc186-116">Windows の [管理者として実行] を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="dc186-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="dc186-117">既定では、PowerShell ギャラリー (PSGallery) は PowerShellGet の信頼できるリポジトリ **として構成されていません**。</span><span class="sxs-lookup"><span data-stu-id="dc186-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="dc186-118">PSGallery を初めて使用すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc186-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="dc186-119">[ **はい]** または **[はい] から [すべて] に回答** して、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="dc186-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="dc186-120">Teams PowerShell パブリック プレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="dc186-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="dc186-121">Teams PowerShell のパブリック プレビュー 版を使用している場合は、最初に Skype for Business Online Connector をアンインストールすることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="dc186-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="dc186-122">システム上のすべてのユーザーに Teams PowerShell パブリック プレビュー モジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc186-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="dc186-123">Windows の [管理者として実行] を使用するか、macOS または Linux でコマンドを使用して `sudo` PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="dc186-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="dc186-124">PowerShell 5.1 を使用している場合は、事前に **PowerShellGet** モジュールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc186-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="dc186-125">**PowerShellGet を更新した** 後、昇格された PowerShell セッションを閉じてもう一度開き、最新の **PowerShellGet** が読み込まれるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc186-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="dc186-126">Teams PowerShell パブリック プレビューをインストールするには、以下の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc186-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="dc186-127">PowerShell ギャラリーまたは [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) で最新のプレビュー バージョンを見つけるには、"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions" を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc186-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="dc186-128">Skype for Business Online Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="dc186-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="dc186-129">Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc186-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="dc186-130">最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc186-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a><span data-ttu-id="dc186-131">サインイン</span><span class="sxs-lookup"><span data-stu-id="dc186-131">Sign in</span></span>

<span data-ttu-id="dc186-132">Teams PowerShell の使用を開始するには、Azure の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc186-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="dc186-133">最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc186-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="dc186-134">MFA と最新の認証を使用してサインインする</span><span class="sxs-lookup"><span data-stu-id="dc186-134">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="dc186-135">アカウントで多要素認証を使用している場合は、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc186-135">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="dc186-136">Teams PowerShell を更新する</span><span class="sxs-lookup"><span data-stu-id="dc186-136">Update Teams PowerShell</span></span>

<span data-ttu-id="dc186-137">Teams PowerShell を更新するには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc186-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="dc186-138">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc186-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="dc186-139">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="dc186-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="dc186-140">Teams PowerShell をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="dc186-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="dc186-141">Teams PowerShell をアンインストールするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc186-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="dc186-142">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dc186-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="dc186-143">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="dc186-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc186-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="dc186-144">Next Steps</span></span>

<span data-ttu-id="dc186-145">Teams PowerShell を使用して Teams を管理する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="dc186-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="dc186-146">使用 [を開始するには、「Teams PowerShell で Teams](teams-powershell-managing-teams.md) を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc186-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc186-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dc186-147">Related topics</span></span>

[<span data-ttu-id="dc186-148">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="dc186-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="dc186-149">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="dc186-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="dc186-150">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc186-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="dc186-151">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc186-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
