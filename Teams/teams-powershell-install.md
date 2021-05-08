---
title: PowerShell Microsoft Teamsインストールする
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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768343"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="493aa-103">PowerShell Microsoft Teamsインストールする</span><span class="sxs-lookup"><span data-stu-id="493aa-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="493aa-104">この記事では、PowerShellGet を使用して PowerShell Microsoft Teamsをインストールする[方法について説明します](/powershell/scripting/gallery/installing-psget)。</span><span class="sxs-lookup"><span data-stu-id="493aa-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="493aa-105">これらの手順は[、Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS、および Windowsで動作します。</span><span class="sxs-lookup"><span data-stu-id="493aa-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="493aa-106">要件</span><span class="sxs-lookup"><span data-stu-id="493aa-106">Requirements</span></span>

<span data-ttu-id="493aa-107">TeamsPowerShell には、すべてのプラットフォームで PowerShell 5.1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="493aa-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="493aa-108">オペレーティング システム [で使用できる最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="493aa-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="493aa-109">最適なエクスペリエンスを得る場合は、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="493aa-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="493aa-110">PowerShell モジュールTeamsインストールする</span><span class="sxs-lookup"><span data-stu-id="493aa-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="493aa-111">最適なエクスペリエンスを得る場合は、一般公開 (GA) モジュールまたはパブリック プレビュー モジュール (両方ではなく) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="493aa-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="493aa-112">これらは、一緒に作業することを目的としません。</span><span class="sxs-lookup"><span data-stu-id="493aa-112">They're not intended to work together.</span></span>


<span data-ttu-id="493aa-113">**PowerShellGet コマンドレットを** 使用して、PowerShell モジュールTeamsインストールします。</span><span class="sxs-lookup"><span data-stu-id="493aa-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="493aa-114">システム上のすべてのユーザーに対してモジュールをインストールするには、昇格された特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="493aa-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="493aa-115">[管理者として実行]**を使用** して PowerShell Windowsを開始するか、macOS または Linux で `sudo` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="493aa-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="493aa-116">既定では、PowerShell ギャラリー (PSGallery) は **、PowerShellGet** の信頼できるリポジトリとして構成されていません。</span><span class="sxs-lookup"><span data-stu-id="493aa-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="493aa-117">PSGallery を初めて使用すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="493aa-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="493aa-118">[ **はい]** または **[はい] を [すべて** ] に回答して、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="493aa-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="493aa-119">サインイン</span><span class="sxs-lookup"><span data-stu-id="493aa-119">Sign in</span></span>

<span data-ttu-id="493aa-120">PowerShell のTeamsするには、Azure 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="493aa-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="493aa-121">[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック プレビュー リリースTeams最新バージョンを使用している場合は、Skype for Business Online Connector をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="493aa-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="493aa-122">MFA と最新の認証を使用してサインインする</span><span class="sxs-lookup"><span data-stu-id="493aa-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="493aa-123">アカウントで多要素認証を使用する場合は、このセクションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="493aa-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="493aa-124">PowerShell Teams更新</span><span class="sxs-lookup"><span data-stu-id="493aa-124">Update Teams PowerShell</span></span>

<span data-ttu-id="493aa-125">PowerShell をTeamsするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="493aa-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="493aa-126">PowerShell Teams PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="493aa-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="493aa-127">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="493aa-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="493aa-128">PowerShell Teamsアンインストールする</span><span class="sxs-lookup"><span data-stu-id="493aa-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="493aa-129">PowerShell をTeamsするには、新しい管理者特権の PowerShell コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="493aa-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="493aa-130">PowerShell Teams PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="493aa-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="493aa-131">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="493aa-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="493aa-132">PowerShell Teams プレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="493aa-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="493aa-133">PowerShell のパブリック プレビュー バージョンを使用している場合は、Teams Online Connector をアンインストールすることを強Skype for Business勧めします。</span><span class="sxs-lookup"><span data-stu-id="493aa-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="493aa-134">システム上のすべてのTeams PowerShell パブリック プレビュー モジュールをインストールするには、昇格された特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="493aa-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="493aa-135">[管理者として実行]**を使用** して PowerShell セッションをWindows、macOS または Linux で `sudo` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="493aa-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="493aa-136">PowerShell 5.1 を使用している場合は、事前に **PowerShellGet モジュールを更新する** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="493aa-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="493aa-137">**PowerShellGet を更新した** 後、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の **PowerShellGet** が読み込まれるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="493aa-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="493aa-138">PowerShell パブリック Teamsインストールするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="493aa-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="493aa-139">最新のプレビュー バージョンは [、PowerShell ギャラリー](https://www.powershellgallery.com/packages/MicrosoftTeams) または PowerShell で見つけることができます。"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions" を実行します。</span><span class="sxs-lookup"><span data-stu-id="493aa-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="493aa-140">次のステップ</span><span class="sxs-lookup"><span data-stu-id="493aa-140">Next Steps</span></span>

<span data-ttu-id="493aa-141">これで、PowerShell を使用してTeams管理Teams準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="493aa-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="493aa-142">使用[を開始するにはTeams PowerShell Teamsの管理に関](teams-powershell-managing-teams.md)するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="493aa-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="493aa-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="493aa-143">Related topics</span></span>

[<span data-ttu-id="493aa-144">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="493aa-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="493aa-145">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="493aa-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="493aa-146">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="493aa-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="493aa-147">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="493aa-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
