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
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63ee69d56cff0fd3d25ae6aa16a02fc45340dce4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014380"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="28a50-103">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="28a50-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="28a50-104">Windows デスクトップ クライアント、それを計画する方法および展開方法の利点について説明するのには次のセッションを監視する:[チームの Windows デスクトップ クライアント](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="28a50-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="28a50-105">マイクロソフトは MSI ファイル ( [32 ビット](https://aka.ms/teams32bitmsi)と[64 ビット](https://aka.ms/teams64bitmsi)の両方) を選択するのにはチームの一括展開の管理者が使用できるを提供する広範な展開のシステム センター構成マネージャーでは、グループ ポリシー、または任意のサードパーティ製の配布メカニズムを使用して、ユーザーまたはコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="28a50-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="28a50-106">管理者は、これらのファイルを使用して、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="28a50-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="28a50-107">展開されると、チームが自動的にそのコンピューター上でサインインしているすべてのユーザーに対して起動します。</span><span class="sxs-lookup"><span data-stu-id="28a50-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="28a50-108">(アプリケーションのインストール後の自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="28a50-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="28a50-109">[以下を参照してください](#disable-auto-lanuch-for-the-msi-installer))。マシンのすべての新しいユーザーは、この展開からな利点がありますので、コンピューターにパッケージを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28a50-109">[See below](#disable-auto-lanuch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="28a50-110">SCCM の詳細については、[システム センター構成マネージャーの概要](https://docs.microsoft.com/sccm/core/understand/introduction)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a50-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="28a50-111">(推奨) の展開手順</span><span class="sxs-lookup"><span data-stu-id="28a50-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="28a50-112">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="28a50-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="28a50-113">MSI によって事前設定の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="28a50-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="28a50-114">可能な場合にコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="28a50-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="28a50-115">マイクロソフト チームの MSI パッケージが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="28a50-115">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="28a50-116">チームの msi ファイルには、プログラム ファイルのインストーラーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="28a50-116">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="28a50-117">ユーザーが新しい Windows ユーザー プロファイルにサインインするたびに、インストーラーが起動され、チームのアプリケーションのコピーをそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="28a50-117">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="28a50-118">Appdata フォルダーにインストールされているチームのアプリケーションがユーザーに割り当てられている場合、MSI インストーラーはそのユーザーのプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="28a50-118">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="28a50-119">クライアントが自動的に更新プログラムの新しいバージョンがサービスから利用可能なを検出したときのため、更新プログラムを展開する MSI を使わないでください。</span><span class="sxs-lookup"><span data-stu-id="28a50-119">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="28a50-120">再配置するのには、最新のインストーラーは、以下に示す MSI を再配置のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="28a50-120">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="28a50-121">以前のバージョンの MSI パッケージを展開する場合、クライアントは自動更新可能な場合は、ユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="28a50-121">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="28a50-122">非常に古いバージョンを取得を展開する場合、ユーザーはチームを使用するのには、前に msi ファイルはアプリケーションの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="28a50-122">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="28a50-123">この更新プログラムの流れが切れることは、デフォルトのインストール先を変更することお勧めしないです。</span><span class="sxs-lookup"><span data-stu-id="28a50-123">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="28a50-124">非常に古いバージョンを持つと、ユーザーがサービスにアクセスする、最終的にブロックします。</span><span class="sxs-lookup"><span data-stu-id="28a50-124">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="28a50-125">対象のコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="28a50-125">Target computer requirements</span></span>

- <span data-ttu-id="28a50-126">4.5 またはそれ以降の .NET framework</span><span class="sxs-lookup"><span data-stu-id="28a50-126">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="28a50-127">Windows 7 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="28a50-127">Windows 7 or later</span></span>
- <span data-ttu-id="28a50-128">3 GB (推奨)、各ユーザー プロファイル用のディスク領域の</span><span class="sxs-lookup"><span data-stu-id="28a50-128">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="28a50-129">クリーンアップと再配置の手順</span><span class="sxs-lookup"><span data-stu-id="28a50-129">Clean up and redeployment procedure</span></span>
<span data-ttu-id="28a50-130">ユーザー プロファイルからチームをアンインストールすると、MSI インストーラーは、ユーザーがチームのアプリケーションがアンインストールされ、不要になったチームをそのユーザーのプロファイルのインストールに追跡します。</span><span class="sxs-lookup"><span data-stu-id="28a50-130">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="28a50-131">アンインストールされた特定のコンピューターにこのユーザーのチームを再配置する、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="28a50-131">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="28a50-132">チーム アプリケーションのすべてのユーザー プロファイルのインストールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="28a50-132">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="28a50-133">アンインストール後、% の localappdata%\Microsoft\Teams\ の下を再帰的にディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="28a50-133">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="28a50-134">その特定のコンピューターに MSI パッケージを再展開します。</span><span class="sxs-lookup"><span data-stu-id="28a50-134">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="28a50-135">SCCM を使用して、手順 1 と 2 を実行するのには、[マイクロソフトのチームの配置のクリーンアップ](.\scripts\Powershell-script-teams-deployment-clean-up.md)スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="28a50-135">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>  
                    
## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="28a50-136">MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="28a50-136">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="28a50-137">自動起動を無効にする場合は、次のコマンド プロンプトを入力します。</span><span class="sxs-lookup"><span data-stu-id="28a50-137">If you want to disable auto launch, enter the following command prompt:</span></span>

`msiexec /i Teams_windows.exe OPTIONS="noAutoStart=false"`

