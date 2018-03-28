---
title: MSI を使用してマイクロソフトのチームをインストールします。
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 管理者が一括してチームの msi ファイルを使用できますユーザーまたはコンピューターを選択するのには、マイクロソフトのチームを配置します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="68fc2-103">MSI を使用してマイクロソフトのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="68fc2-104">システム センター構成マネージャーで、またはグループ ポリシーでは、広範な展開に、サード パーティ配布メカニズムを活用して、マイクロソフトは管理者の一括展開時に活用するための MSI ファイル ( [32 ビット](http://aka.ms/teams32bitmsi)と[64 ビット](http://aka.ms/teams64bitmsi)の両方) を提供します。ユーザーまたはコンピューターを選択するのにはマイクロソフトのチームです。</span><span class="sxs-lookup"><span data-stu-id="68fc2-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="68fc2-105">管理者は、これらのファイルを使用して、リモートで展開するチームのユーザーがチームのアプリケーションを手動でダウンロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68fc2-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="68fc2-106">展開されると、チームが自動的にそのコンピューターでサインインするすべてのユーザーに対して起動します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="68fc2-107">マシンにすべての新しいユーザーは、この展開からな利点がありますので、コンピューターにパッケージを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="68fc2-108">SCCM の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68fc2-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="68fc2-109">System Center 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="68fc2-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="68fc2-110">展開手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="68fc2-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="68fc2-111">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="68fc2-112">MSI によって事前設定の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="68fc2-113">可能な場合は、マシンへの導入します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="68fc2-114">マイクロソフト チームの MSI パッケージが機能するしくみ</span><span class="sxs-lookup"><span data-stu-id="68fc2-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="68fc2-115">チームの msi ファイルには、プログラム ファイルのインストーラーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="68fc2-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="68fc2-116">ユーザーが新しい Windows ユーザー プロファイルにサインインするたびに、インストーラーが起動され、チームのアプリケーションのコピーをそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="68fc2-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="68fc2-117">Appdata フォルダーにインストールされているチームのアプリケーションがユーザーに割り当てられている場合、MSI インストーラーはそのユーザーのプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="68fc2-118">更新を展開する msi ファイルを活用していない、クライアントが自動的に更新プログラムの新しいバージョンがサービスから利用可能なを検出したとき。</span><span class="sxs-lookup"><span data-stu-id="68fc2-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="68fc2-119">再配置するのには、最新のインストーラーは、以下に示す MSI を再配置のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="68fc2-120">以前のバージョンの MSI パッケージを展開する場合、クライアントは自動更新可能な場合は、ユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="68fc2-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="68fc2-121">非常に古いバージョンを取得を展開する場合、ユーザーはチームを使用するのには、前に msi ファイルはアプリケーションの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="68fc2-122">いない任意のインストール場所を変更する更新プログラムの流れが切れることがこれをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="68fc2-123">最終的にブロックされますから、サービスにアクセスするユーザー。</span><span class="sxs-lookup"><span data-stu-id="68fc2-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="68fc2-124">ターゲット マシンの要件:</span><span class="sxs-lookup"><span data-stu-id="68fc2-124">Target machine requirements:</span></span>

1. <span data-ttu-id="68fc2-125">4.5 またはそれ以降の .NET framework</span><span class="sxs-lookup"><span data-stu-id="68fc2-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="68fc2-126">Windows 7 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="68fc2-126">Windows 7 or later</span></span>
2. <span data-ttu-id="68fc2-127">32 GB (推奨)、各ユーザー プロファイル用のディスク領域の</span><span class="sxs-lookup"><span data-stu-id="68fc2-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="68fc2-128">Up\redeployment プロシージャを削除します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="68fc2-129">それぞれのユーザー プロファイルからのチームをアンインストールすると、MSI インストーラーは、ユーザーがチームのアプリケーションがアンインストールされ、不要になったチームをそのユーザーのプロファイルのインストールに追跡します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="68fc2-130">特定のコンピューターにこのユーザーをアンインストールするためにチームを再展開するには、必要があります。</span><span class="sxs-lookup"><span data-stu-id="68fc2-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="68fc2-131">チーム アプリケーションのすべてのユーザー プロファイルのインストールをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="68fc2-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="68fc2-132">アンインストール後、ディレクトリを再帰的に %localappdata%\Microsoft\Teams\ の下の削除</span><span class="sxs-lookup"><span data-stu-id="68fc2-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="68fc2-133">その特定のコンピューターに MSI パッケージを再展開します。</span><span class="sxs-lookup"><span data-stu-id="68fc2-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="68fc2-134">SCCM を使用してこの手順 1 と 2 を実行する[マイクロソフトのチームの配置のクリーンアップ](.\scripts\Powershell-script-teams-deployment-clean-up.md)スクリプトを活用することができます。</span><span class="sxs-lookup"><span data-stu-id="68fc2-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

