---
title: MSI を使用して SCCM 経由で Microsoft Teams をインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281618"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="31b26-103">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="31b26-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="31b26-104">Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b26-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="31b26-105">System Center Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル ([32 ビット](https://aka.ms/teams32bitmsi)と [64 ビット](https://aka.ms/teams64bitmsi)の両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="31b26-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="31b26-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="31b26-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="31b26-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="31b26-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="31b26-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="31b26-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="31b26-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31b26-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="31b26-110">SCCM の詳細については、「[System Center Configuration Manager の概要](https://docs.microsoft.com/sccm/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b26-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="31b26-111">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="31b26-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="31b26-112">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="31b26-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="31b26-113">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="31b26-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="31b26-114">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="31b26-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="31b26-115">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="31b26-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="31b26-116">PC のインストール</span><span class="sxs-lookup"><span data-stu-id="31b26-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="31b26-117">仮想デスクトップインフラストラクチャ (VDI) 環境に Teams を展開する方法については、「 [vdi インストール](#vdi-installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b26-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="31b26-118">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="31b26-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="31b26-119">ユーザーが新しい Windows ユーザープロファイルにサインインするたびに、インストーラーが起動され、Teams アプリのコピーがそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="31b26-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="31b26-120">ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="31b26-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="31b26-121">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="31b26-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="31b26-122">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="31b26-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="31b26-123">MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="31b26-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="31b26-124">非常に古いバージョンが展開された場合、MSI は、ユーザーが Teams を使用できるようになる前に、アプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="31b26-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="31b26-125">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="31b26-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="31b26-126">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="31b26-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="31b26-127">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="31b26-127">Target computer requirements</span></span>

- <span data-ttu-id="31b26-128">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="31b26-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="31b26-129">Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="31b26-129">Windows 7 or later</span></span>
- <span data-ttu-id="31b26-130">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="31b26-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="31b26-131">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="31b26-131">VDI installation</span></span>

<span data-ttu-id="31b26-132">Teams デスクトップアプリを展開するプロセスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31b26-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="31b26-133">詳細なガイダンスについては、「仮想化された[デスクトップインフラストラクチャのチーム](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b26-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="31b26-134">環境に応じて、次のいずれかのリンクを使用して Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="31b26-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="31b26-135">64ビットのオペレーティングシステムを搭載した VDI VM の64ビットバージョンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31b26-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="31b26-136">32ビット版</span><span class="sxs-lookup"><span data-stu-id="31b26-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="31b26-137">64ビット版</span><span class="sxs-lookup"><span data-stu-id="31b26-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="31b26-138">MSI を VDI VM にインストールするには、次のコマンドを実行します (または完全な更新が必要です)。</span><span class="sxs-lookup"><span data-stu-id="31b26-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    <span data-ttu-id="31b26-139">これにより、チームがプログラムファイルにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="31b26-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="31b26-140">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="31b26-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="31b26-141">次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="31b26-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="31b26-142">ALLUSERS プロパティを使って team を VDI にインストールする場合、Teams の自動起動を無効にすることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="31b26-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSERS property.</span></span>

3. <span data-ttu-id="31b26-143">次のコマンドを実行して、MSI を VDI VM からアンインストールします (または、更新の準備を行います)。</span><span class="sxs-lookup"><span data-stu-id="31b26-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="31b26-144">これにより、プログラムファイルから Teams がアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="31b26-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="31b26-145">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="31b26-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="31b26-146">ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。</span><span class="sxs-lookup"><span data-stu-id="31b26-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="31b26-147">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="31b26-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="31b26-148">それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="31b26-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="31b26-149">アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="31b26-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="31b26-150">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="31b26-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="31b26-151">[Microsoft Teams の展開のクリーン アップ](scripts/Powershell-script-teams-deployment-clean-up.md) スクリプトを使用して、SCCM を介して手順 1 と 2 を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="31b26-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="31b26-152">MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="31b26-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="31b26-153">MSI の既定の動作では、ユーザーがサインインするとすぐに Teams クライアントをインストールしてから自動的に Teams を起動します。</span><span class="sxs-lookup"><span data-stu-id="31b26-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="31b26-154">次のように、以下のパラメーターを使用してこの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="31b26-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="31b26-155">ユーザーが Windows にログインする場合、Teams が MSI と一緒にインストールされる</span><span class="sxs-lookup"><span data-stu-id="31b26-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="31b26-156">ただし、ユーザーが Teams を手動で開始するまで、Teams のクライアントは起動しない</span><span class="sxs-lookup"><span data-stu-id="31b26-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="31b26-157">Teams を起動するショートカットは、ユーザーのデスクトップに追加される</span><span class="sxs-lookup"><span data-stu-id="31b26-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="31b26-158">手動で開始すると、ユーザーがログインするたびに Teams が自動的に起動する</span><span class="sxs-lookup"><span data-stu-id="31b26-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="31b26-159">32 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="31b26-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="31b26-160">64 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="31b26-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="31b26-161">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="31b26-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="31b26-162">昇格されたアクセス許可がなく、管理者として実行する場合でも、インストーラーは自動起動を無効にするオプションを構成できません。</span><span class="sxs-lookup"><span data-stu-id="31b26-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
