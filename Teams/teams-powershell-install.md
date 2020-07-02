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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944110"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="68e1e-103">Microsoft Teams PowerShell をインストールする</span><span class="sxs-lookup"><span data-stu-id="68e1e-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="68e1e-104">この記事では、 [PowerShellGet](/powershell/scripting/gallery/installing-psget)を使って Microsoft Teams PowerShell モジュールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="68e1e-105">これらの手順は、 [Azure Cloud Shell](/azure/cloud-shell/overview)、Linux、MacOS、Windows プラットフォームで動作します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="68e1e-106">要件</span><span class="sxs-lookup"><span data-stu-id="68e1e-106">Requirements</span></span>

<span data-ttu-id="68e1e-107">Teams PowerShell は、すべてのプラットフォームで PowerShell 6.2.4 以降で動作します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-107">Teams PowerShell works with PowerShell 6.2.4 and later on all platforms.</span></span> <span data-ttu-id="68e1e-108">また、Windows の PowerShell 5.1 でもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="68e1e-108">It is also supported with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="68e1e-109">使用しているオペレーティングシステムに対応した[最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="68e1e-109">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> <span data-ttu-id="68e1e-110">PowerShell 6.2.4 以降で実行する場合、Teams PowerShell には追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="68e1e-110">Teams PowerShell has no additional requirements when run on PowerShell 6.2.4 and later.</span></span>

> [!WARNING]
> <span data-ttu-id="68e1e-111">PowerShell 7 と Teams PowerShell について、既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="68e1e-111">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="68e1e-112">最適なエクスペリエンスを実現するには、PowerShell 5.1 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68e1e-112">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="68e1e-113">Teams PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="68e1e-113">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="68e1e-114">最適なエクスペリエンスを実現するには、一般的な可用性 (GA) とパブリックプレビューモジュールのどちらも使用してください。</span><span class="sxs-lookup"><span data-stu-id="68e1e-114">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="68e1e-115">共同作業を目的としているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="68e1e-115">They're not intended to work together.</span></span>


<span data-ttu-id="68e1e-116">**PowerShellGet**コマンドレットを使用して Teams PowerShell モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="68e1e-116">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="68e1e-117">システム上のすべてのユーザー用にモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="68e1e-117">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="68e1e-118">Windows の [**管理者として実行**] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-118">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="68e1e-119">既定では、PowerShell ギャラリー (PSGallery) は、 **PowerShellGet**用の信頼できるリポジトリとして構成されていません。</span><span class="sxs-lookup"><span data-stu-id="68e1e-119">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="68e1e-120">初めて PSGallery を使用するときは、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68e1e-120">The first time you use the PSGallery, you'll see the following message:</span></span>

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="68e1e-121">応答 `Yes` `Yes to All` するか、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-121">Answer `Yes` or `Yes to All` to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="68e1e-122">Teams PowerShell パブリックプレビューをインストールする</span><span class="sxs-lookup"><span data-stu-id="68e1e-122">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="68e1e-123">Teams PowerShell のパブリックプレビュー版を使用している場合は、まず Skype for Business Online Connector をアンインストールすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68e1e-123">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="68e1e-124">システム上のすべてのユーザー用に Teams PowerShell パブリックプレビューモジュールをインストールするには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="68e1e-124">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="68e1e-125">Windows の [**管理者として実行**] を使って PowerShell セッションを開始するか、 `sudo` MacOS または Linux のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-125">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="68e1e-126">PowerShell 5.1 を使用している場合は、 **PowerShellGet**モジュールを事前に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e1e-126">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="68e1e-127">**PowerShellGet**を更新したら、管理者特権の PowerShell セッションを閉じてもう一度開き、最新の**PowerShellGet**が読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-127">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="68e1e-128">Teams Powershell パブリックプレビューをインストールするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-128">To install Teams Powershell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="68e1e-129">Skype for Business Online Connector をインストールする</span><span class="sxs-lookup"><span data-stu-id="68e1e-129">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="68e1e-130">Skype for Business Online Connector は現在、Teams PowerShell パブリックプレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="68e1e-130">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="68e1e-131">この機能を Teams PowerShell の GA リリースにロールアウトすると、Skype for Business Online Connector は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="68e1e-131">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="68e1e-132">[Skype For Business PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をダウンロードしてインストールし、PowerShell で次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-132">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="68e1e-133">サインイン</span><span class="sxs-lookup"><span data-stu-id="68e1e-133">Sign in</span></span>

<span data-ttu-id="68e1e-134">Teams PowerShell の使用を開始するには、Azure の資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="68e1e-134">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="68e1e-135">最新の[Teams PowerShell パブリックプレビューリリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)を使用している場合は、Skype For Business Online Connector をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68e1e-135">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="68e1e-136">Teams PowerShell の更新</span><span class="sxs-lookup"><span data-stu-id="68e1e-136">Update Teams PowerShell</span></span>

<span data-ttu-id="68e1e-137">Teams PowerShell を更新するには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="68e1e-138">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="68e1e-139">PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="68e1e-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="68e1e-140">Teams PowerShell をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="68e1e-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="68e1e-141">Teams PowerShell をアンインストールするには、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="68e1e-142">Teams PowerShell が既に PowerShell セッションにインポートされている場合、モジュールのアンインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="68e1e-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="68e1e-143">PowerShell を閉じ、新しい昇格された PowerShell セッションをもう一度開きます。</span><span class="sxs-lookup"><span data-stu-id="68e1e-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68e1e-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="68e1e-144">Next Steps</span></span>

<span data-ttu-id="68e1e-145">これで、Teams PowerShell を使用してチームを管理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="68e1e-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="68e1e-146">始めるには、「 [Teams PowerShell で teams を管理](teams-powershell-managing-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e1e-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="68e1e-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="68e1e-147">Related topics</span></span>

[<span data-ttu-id="68e1e-148">Teams PowerShell を使用してチームを管理する</span><span class="sxs-lookup"><span data-stu-id="68e1e-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="68e1e-149">Teams PowerShell リリースノート</span><span class="sxs-lookup"><span data-stu-id="68e1e-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="68e1e-150">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="68e1e-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="68e1e-151">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="68e1e-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
