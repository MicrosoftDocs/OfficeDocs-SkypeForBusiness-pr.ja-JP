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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947568"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="e6870-103">PowerShell モジュールMicrosoft Teamsインストールする</span><span class="sxs-lookup"><span data-stu-id="e6870-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="e6870-104">この記事では、PowerShell ギャラリーを使用して powerShell Microsoft Teamsをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6870-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="e6870-105">PowerShell Microsoft Teamsは、すべてのプラットフォームでWindowsされます。</span><span class="sxs-lookup"><span data-stu-id="e6870-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="e6870-106">要件</span><span class="sxs-lookup"><span data-stu-id="e6870-106">Requirements</span></span>

<span data-ttu-id="e6870-107">Microsoft TeamsPowerShell モジュールには、すべてのプラットフォームで PowerShell 5.1 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="e6870-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="e6870-108">オペレーティング システム [で使用できる最新バージョンの PowerShell](/powershell/scripting/install/installing-powershell)   をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6870-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="e6870-109">PowerShell のバージョンを確認するには、PowerShell セッション内から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6870-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="e6870-110">PowerShell モジュールのインストールには、Install-Module コマンドレットを使用Microsoft Teamsすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e6870-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="e6870-111">PowerShell ギャラリー (PSGallery) が **PowerShellGet** の信頼できるリポジトリとして構成されていない場合は、PSGallery を初めて使用すると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6870-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="e6870-112">[ **はい]** または **[はい] を [すべて** ] に回答して、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="e6870-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="e6870-113">PowerShellGallery を使用したインストール</span><span class="sxs-lookup"><span data-stu-id="e6870-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="e6870-114">Microsoft TeamsPowerShell モジュールは、現在、PowerShell 5.1 で使用Windows。</span><span class="sxs-lookup"><span data-stu-id="e6870-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="e6870-115">モジュールをインストールするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e6870-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="e6870-116">[5.1 Windows PowerShell に更新](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="e6870-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="e6870-117">バージョン 1607 Windows 10を使用している場合は、PowerShell 5.1 が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e6870-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="e6870-118">[4.7.2 .NET Framework以降をインストール](/dotnet/framework/install)します。</span><span class="sxs-lookup"><span data-stu-id="e6870-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="e6870-119">次のコマンドを実行して、最新の PowerShellGet をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6870-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="e6870-120">PowerShell モジュールTeamsインストールします。</span><span class="sxs-lookup"><span data-stu-id="e6870-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="e6870-121">オフライン インストール</span><span class="sxs-lookup"><span data-stu-id="e6870-121">Offline Installation</span></span> 

<span data-ttu-id="e6870-122">一部の環境では、PowerShell ギャラリーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="e6870-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="e6870-123">このような場合は、次の手動インストール [手順に従ってください](https://aka.ms/psgallery-manualdownload)。</span><span class="sxs-lookup"><span data-stu-id="e6870-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="e6870-124">サインイン</span><span class="sxs-lookup"><span data-stu-id="e6870-124">Sign in</span></span>

<span data-ttu-id="e6870-125">PowerShell モジュールのMicrosoft Teamsするには、Azure 資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="e6870-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="e6870-126">PowerShell Teams更新</span><span class="sxs-lookup"><span data-stu-id="e6870-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="e6870-127">PowerShell モジュールを更新するには、モジュールのインストールに使用したのと同じ方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6870-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="e6870-128">たとえば、最初に Install-Module を使用した場合は [、Update-Module](/powershell/module/powershellget/update-module) を使用して最新バージョンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6870-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="e6870-129">PowerShell Teams PowerShell セッションにインポートされている場合、モジュールの更新は失敗します。</span><span class="sxs-lookup"><span data-stu-id="e6870-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="e6870-130">PowerShell を閉じて、新しい管理者特権の PowerShell セッションを再び開きます。</span><span class="sxs-lookup"><span data-stu-id="e6870-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="e6870-131">PowerShell Teamsアンインストールする</span><span class="sxs-lookup"><span data-stu-id="e6870-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="e6870-132">PowerShell をMicrosoft Teamsするには、新しい PowerShell コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e6870-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="e6870-133">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e6870-133">Next Steps</span></span> 

<span data-ttu-id="e6870-134">これで、PowerShell を使用してMicrosoft Teams管理Microsoft Teams準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="e6870-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="e6870-135">使用[を開始するにはTeams PowerShell Teamsの管理に関](teams-powershell-managing-teams.md)するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6870-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e6870-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6870-136">Related topics</span></span>

[<span data-ttu-id="e6870-137">Teams PowerShell での Teams の管理</span><span class="sxs-lookup"><span data-stu-id="e6870-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="e6870-138">Teams PowerShell のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="e6870-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="e6870-139">Microsoft Teams コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="e6870-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="e6870-140">Skype for Business コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="e6870-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
