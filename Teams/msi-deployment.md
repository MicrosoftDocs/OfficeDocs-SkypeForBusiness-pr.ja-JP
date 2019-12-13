---
title: MSI を使用して SCCM 経由で Microsoft Teams をインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002231"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="a3e01-103">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="a3e01-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="a3e01-104">Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e01-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="a3e01-105">System Center Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル (32 ビットと 64 ビットの両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="a3e01-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="a3e01-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="a3e01-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="a3e01-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="a3e01-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="a3e01-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="a3e01-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3e01-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="a3e01-110">MSI ファイルへのリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="a3e01-111">エンティティ</span><span class="sxs-lookup"><span data-stu-id="a3e01-111">Entity</span></span>  |<span data-ttu-id="a3e01-112">32ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-112">32 bit</span></span>      |<span data-ttu-id="a3e01-113">64ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="a3e01-114">業者</span><span class="sxs-lookup"><span data-stu-id="a3e01-114">Commercial</span></span>     | [<span data-ttu-id="a3e01-115">32ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="a3e01-116">64ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="a3e01-117">米国連邦政府-GCC</span><span class="sxs-lookup"><span data-stu-id="a3e01-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="a3e01-118">32ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="a3e01-119">64ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="a3e01-120">米国連邦政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="a3e01-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="a3e01-121">32ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="a3e01-122">64ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="a3e01-123">米国連邦政府-DoD</span><span class="sxs-lookup"><span data-stu-id="a3e01-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="a3e01-124">32ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="a3e01-125">64ビット</span><span class="sxs-lookup"><span data-stu-id="a3e01-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="a3e01-126">Teams は、Office 365 ProPlus の展開に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="a3e01-127">詳細については、「 [Office 365 を使用して Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/deployoffice/teams-install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e01-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="a3e01-128">SCCM の詳細については、「[System Center Configuration Manager の概要](https://docs.microsoft.com/sccm/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e01-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="a3e01-129">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="a3e01-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="a3e01-130">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="a3e01-131">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="a3e01-132">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="a3e01-133">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="a3e01-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="a3e01-134">PC のインストール</span><span class="sxs-lookup"><span data-stu-id="a3e01-134">PC installation</span></span>

<span data-ttu-id="a3e01-135">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="a3e01-136">ユーザーが新しい Windows ユーザープロファイルにサインインするたびに、インストーラーが起動され、Teams アプリのコピーがそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="a3e01-137">ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a3e01-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="a3e01-138">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="a3e01-139">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="a3e01-140">以前のバージョンの MSI パッケージを展開する場合、クライアントは、可能な場合に、(VDI 環境を除く) 自動更新されます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="a3e01-141">非常に古いバージョンが展開された場合、MSI は、ユーザーが Teams を使用できるようになる前に、アプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="a3e01-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="a3e01-142">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a3e01-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="a3e01-143">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="a3e01-144">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="a3e01-144">Target computer requirements</span></span>

- <span data-ttu-id="a3e01-145">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="a3e01-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="a3e01-146">Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="a3e01-146">Windows 7 or later</span></span>
- <span data-ttu-id="a3e01-147">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="a3e01-147">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="a3e01-148">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="a3e01-148">VDI installation</span></span>

<span data-ttu-id="a3e01-149">VDI に Teams デスクトップアプリを展開する方法の詳細なガイダンスについては、「仮想化された[デスクトップインフラストラクチャの teams](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3e01-149">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="a3e01-150">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="a3e01-150">Clean up and redeployment procedure</span></span>

<span data-ttu-id="a3e01-151">ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-151">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="a3e01-152">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-152">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="a3e01-153">それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3e01-153">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="a3e01-154">アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-154">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="a3e01-155">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-155">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="a3e01-156">[Microsoft Teams の展開のクリーン アップ](scripts/Powershell-script-teams-deployment-clean-up.md) スクリプトを使用して、SCCM を介して手順 1 と 2 を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-156">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="a3e01-157">MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a3e01-157">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="a3e01-158">MSI の既定の動作では、ユーザーがサインインするとすぐに Teams クライアントをインストールしてから自動的に Teams を起動します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-158">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="a3e01-159">次のように、以下のパラメーターを使用してこの動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a3e01-159">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="a3e01-160">ユーザーが Windows にログインする場合、Teams が MSI と一緒にインストールされる</span><span class="sxs-lookup"><span data-stu-id="a3e01-160">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="a3e01-161">ただし、ユーザーが Teams を手動で開始するまで、Teams のクライアントは起動しない</span><span class="sxs-lookup"><span data-stu-id="a3e01-161">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="a3e01-162">Teams を起動するショートカットは、ユーザーのデスクトップに追加される</span><span class="sxs-lookup"><span data-stu-id="a3e01-162">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="a3e01-163">手動で開始すると、ユーザーがログインするたびに Teams が自動的に起動する</span><span class="sxs-lookup"><span data-stu-id="a3e01-163">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="a3e01-164">32 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="a3e01-164">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="a3e01-165">64 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="a3e01-165">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> <span data-ttu-id="a3e01-166">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="a3e01-166">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="a3e01-167">昇格されたアクセス許可がなく、管理者として実行する場合でも、インストーラーは自動起動を無効にするオプションを構成できません。</span><span class="sxs-lookup"><span data-stu-id="a3e01-167">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
