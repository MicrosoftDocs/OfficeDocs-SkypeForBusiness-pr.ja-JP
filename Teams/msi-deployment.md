---
title: Microsoft Endpoint Configuration Manager から MSI を使用して Microsoft Teams をインストールする
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327829"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="a6f65-103">Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="a6f65-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="a6f65-104">Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f65-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="a6f65-105">Microsoft Endpoint Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル (32 ビットと 64 ビットの両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="a6f65-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="a6f65-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="a6f65-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="a6f65-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="a6f65-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="a6f65-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="a6f65-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="a6f65-110">MSI ファイルへのリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="a6f65-111">エンティティ</span><span class="sxs-lookup"><span data-stu-id="a6f65-111">Entity</span></span>  |<span data-ttu-id="a6f65-112">32 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-112">32 bit</span></span>      |<span data-ttu-id="a6f65-113">64 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="a6f65-114">商用</span><span class="sxs-lookup"><span data-stu-id="a6f65-114">Commercial</span></span>     | [<span data-ttu-id="a6f65-115">32 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="a6f65-116">64 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="a6f65-117">政府機関向け - GCC</span><span class="sxs-lookup"><span data-stu-id="a6f65-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="a6f65-118">32 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="a6f65-119">64 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="a6f65-120">政府機関向け - GCC High</span><span class="sxs-lookup"><span data-stu-id="a6f65-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="a6f65-121">32 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="a6f65-122">64 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="a6f65-123">政府機関向け - DoD</span><span class="sxs-lookup"><span data-stu-id="a6f65-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="a6f65-124">32 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="a6f65-125">64 ビット</span><span class="sxs-lookup"><span data-stu-id="a6f65-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="a6f65-126">Teams は、Office 365 ProPlus の展開に含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6f65-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="a6f65-127">詳細については、「[Office 365 ProPlus で Microsoft Teams を展開する](https://docs.microsoft.com/deployoffice/teams-install)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6f65-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="a6f65-128">Microsoft Endpoint Configuration Manager について詳しくは、「[Configuration Manager とは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f65-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="a6f65-129">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="a6f65-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="a6f65-130">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="a6f65-131">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="a6f65-132">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="a6f65-133">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="a6f65-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="a6f65-134">PC インストール</span><span class="sxs-lookup"><span data-stu-id="a6f65-134">PC installation</span></span>

<span data-ttu-id="a6f65-135">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="a6f65-136">ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリのコピーがそのユーザーの `AppData` フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="a6f65-137">ユーザーが既に `AppData` フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-137">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="a6f65-138">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="a6f65-139">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="a6f65-140">MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します (VDI 環境を除く)。</span><span class="sxs-lookup"><span data-stu-id="a6f65-140">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="a6f65-141">非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="a6f65-142">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a6f65-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="a6f65-143">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="a6f65-144">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="a6f65-144">Target computer requirements</span></span>

- <span data-ttu-id="a6f65-145">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="a6f65-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="a6f65-146">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="a6f65-146">Windows 8.1 or later</span></span>
- <span data-ttu-id="a6f65-147">Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="a6f65-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="a6f65-148">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="a6f65-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="a6f65-149">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="a6f65-149">VDI installation</span></span>

<span data-ttu-id="a6f65-150">VDI に Teams デスクトップ アプリを展開する方法の詳細なガイダンスについては、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f65-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="a6f65-151">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="a6f65-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="a6f65-152">ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="a6f65-153">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="a6f65-154">それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="a6f65-155">アンインストール後、`%localappdata%\Microsoft\Teams\` 以下のディレクトリを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-155">After uninstall, delete directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="a6f65-156">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-156">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="a6f65-157">インストール後に Teams が自動的に起動しないようにする</span><span class="sxs-lookup"><span data-stu-id="a6f65-157">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="a6f65-158">MSI の既定の動作では、ユーザーがサインインするとすぐに Teams アプリがインストールされ、Teams が自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-158">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="a6f65-159">ユーザーがインストールした後に Teams が自動的に起動しないようにするには、グループ ポリシーを使用してポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-159">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="a6f65-160">グループ ポリシーを使用する (推奨)</span><span class="sxs-lookup"><span data-stu-id="a6f65-160">Use Group Policy (recommended)</span></span>

<span data-ttu-id="a6f65-161">**[Prevent Microsoft Teams from starting automatically after installation]**(インストール後に Microsoft Teams が自動的に起動しないようにする) グループ ポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-161">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="a6f65-162">このポリシー設定は、[ユーザー構成]\[ポリシー]\[管理用テンプレート]\[Microsoft Teams] にあります。</span><span class="sxs-lookup"><span data-stu-id="a6f65-162">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="a6f65-163">組織のニーズに合わせてポリシー設定を無効にも有効にもできるため、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6f65-163">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="a6f65-164">Teams がインストールされる前にこのポリシー設定を有効にしていると、ユーザーが Windows にログインしても Teams は自動起動しません。</span><span class="sxs-lookup"><span data-stu-id="a6f65-164">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="a6f65-165">ユーザーが初めて Teams にサインインすると、次にユーザーがログインしたときに Teams が自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="a6f65-165">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="a6f65-166">詳細については、「[グループ ポリシーを使用してインストール後に Microsoft Teams の自動起動を回避する](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6f65-166">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="a6f65-167">Teams を展開済みで、このポリシー設定で Teams の自動起動を無効にするには、最初にグループ ポリシー設定を必要な値に設定してから、ユーザーごとに [Teams 自動起動リセット スクリプト](scripts/powershell-script-teams-reset-autostart.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-167">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="a6f65-168">MSI インストーラーの自動起動を無効にする</span><span class="sxs-lookup"><span data-stu-id="a6f65-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="a6f65-169">次のように **OPTIONS="noAutoStart=true"** パラメーターを使用することにより、MSI インストーラーの自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="a6f65-170">32 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="a6f65-170">For the 32-bit version</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="a6f65-171">64 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="a6f65-171">For the 64-bit version</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="a6f65-172">ユーザーが Windows にログインすると、Teams は MSI と一緒にインストールされ、Teams を起動するためのショートカットがユーザーのデスクトップに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a6f65-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="a6f65-173">そのユーザーが手動で Teams を起動するまで Teams は起動しません。</span><span class="sxs-lookup"><span data-stu-id="a6f65-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="a6f65-174">ユーザーが手動で Teams を起動すると、そのユーザーがログインするたびに Teams は自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="a6f65-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="a6f65-175">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="a6f65-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="a6f65-176">管理者として実行する場合でも、管理者特権で実行しない限り、インストーラーで自動起動を無効にするオプションを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6f65-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
