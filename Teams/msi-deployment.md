---
title: MSI を使用して Microsoft Teams をインストールする
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aaf355c1f1fc65855c7bffb7c5632929a084b88
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057604"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="e5f10-103">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="e5f10-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="e5f10-104">マイクロソフトは MSI ファイル ( [32 ビット](https://aka.ms/teams32bitmsi)と[64 ビット](https://aka.ms/teams64bitmsi)の両方) を選択するのにはチームの一括展開の管理者が使用できるを提供する広範な展開のシステム センター構成マネージャーでは、グループ ポリシー、または任意のサードパーティ製の配布メカニズムを使用して、ユーザーまたはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="e5f10-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="e5f10-105">管理者は、これらのファイルを使用して、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5f10-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="e5f10-106">展開されると、チームが自動的にそのコンピューター上でサインインしているすべてのユーザーに対して起動します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="e5f10-107">(アプリケーションのインストール後の自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-107">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="e5f10-108">[以下を参照してください](#disable-auto-lanuch-for-the-msi-installer))。マシンのすべての新しいユーザーは、この展開からな利点がありますので、コンピューターにパッケージを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-108">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="e5f10-109">SCCM の詳細については、[システム センター構成マネージャーの概要](https://docs.microsoft.com/sccm/core/understand/introduction)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f10-109">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="e5f10-110">(推奨) の展開手順</span><span class="sxs-lookup"><span data-stu-id="e5f10-110">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="e5f10-111">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-111">Retrieve the latest package.</span></span>
2. <span data-ttu-id="e5f10-112">MSI によって事前設定の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-112">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="e5f10-113">可能な場合にコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-113">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="e5f10-114">マイクロソフト チームの MSI パッケージが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="e5f10-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="e5f10-115">チームの msi ファイルには、プログラム ファイルのインストーラーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="e5f10-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="e5f10-116">ユーザーが新しい Windows ユーザー プロファイルにサインインするたびに、インストーラーが起動され、チームのアプリケーションのコピーをそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e5f10-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="e5f10-117">Appdata フォルダーにインストールされているチームのアプリケーションがユーザーに割り当てられている場合、MSI インストーラーはそのユーザーのプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="e5f10-118">クライアントが自動的に更新プログラムの新しいバージョンがサービスから利用可能なを検出したときのため、更新プログラムを展開する MSI を使わないでください。</span><span class="sxs-lookup"><span data-stu-id="e5f10-118">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="e5f10-119">再配置するのには、最新のインストーラーは、以下に示す MSI を再配置のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="e5f10-120">以前のバージョンの MSI パッケージを展開する場合、クライアントは自動更新可能な場合は、ユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="e5f10-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="e5f10-121">非常に古いバージョンを取得を展開する場合、ユーザーはチームを使用するのには、前に msi ファイルはアプリケーションの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="e5f10-122">この更新プログラムの流れが切れることは、デフォルトのインストール先を変更することお勧めしないです。</span><span class="sxs-lookup"><span data-stu-id="e5f10-122">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="e5f10-123">非常に古いバージョンを持つと、ユーザーがサービスにアクセスする、最終的にブロックします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-123">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="e5f10-124">対象のコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="e5f10-124">Target computer requirements</span></span>

- <span data-ttu-id="e5f10-125">4.5 またはそれ以降の .NET framework</span><span class="sxs-lookup"><span data-stu-id="e5f10-125">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="e5f10-126">Windows 7 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="e5f10-126">Windows 7 or later</span></span>
- <span data-ttu-id="e5f10-127">3 GB (推奨)、各ユーザー プロファイル用のディスク領域の</span><span class="sxs-lookup"><span data-stu-id="e5f10-127">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="e5f10-128">クリーンアップと再配置の手順</span><span class="sxs-lookup"><span data-stu-id="e5f10-128">Clean up and redeployment procedure</span></span>
<span data-ttu-id="e5f10-129">ユーザー プロファイルからチームをアンインストールすると、MSI インストーラーは、ユーザーがチームのアプリケーションがアンインストールされ、不要になったチームをそのユーザーのプロファイルのインストールに追跡します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-129">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="e5f10-130">アンインストールされた特定のコンピューターにこのユーザーのチームを再配置する、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e5f10-130">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="e5f10-131">チーム アプリケーションのすべてのユーザー プロファイルのインストールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-131">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="e5f10-132">アンインストール後、% の localappdata%\Microsoft\Teams\ の下を再帰的にディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="e5f10-133">その特定のコンピューターに MSI パッケージを再展開します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-133">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="e5f10-134">SCCM を使用して、手順 1 と 2 を実行するのには、[マイクロソフトのチームの配置のクリーンアップ](.\scripts\Powershell-script-teams-deployment-clean-up.md)スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5f10-134">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>  
                    
## <a name="disable-auto-lanuch-for-the-msi-installer"></a><span data-ttu-id="e5f10-135">MSI インストーラーの自動 lanuch を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e5f10-135">Disable auto lanuch for the MSI installer</span></span>

<span data-ttu-id="e5f10-136">自動起動を無効にする場合は、次のコマンド プロンプトを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f10-136">If you want to disable auto launch, enter the following command prompt:</span></span>

`msiexec /i Teams_windows.exe OPTIONS="noAutoStart=false"`

