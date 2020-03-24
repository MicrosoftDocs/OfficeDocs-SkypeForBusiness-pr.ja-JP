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
ms.openlocfilehash: 084f6d4587bc279c4387cf44b8ed29d38d51d4a6
ms.sourcegitcommit: 613665c866f6fd0febfa6e26ad718241cdfbb207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42937601"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f9644-103">Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="f9644-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="f9644-104">Windows デスクトップクライアントの利点、その計画方法、展開方法については、次のセッションをご覧ください。 [Teams Windows デスクトップクライアント](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="f9644-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="f9644-105">Microsoft Endpoint Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル (32 ビットと 64 ビットの両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="f9644-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="f9644-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="f9644-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="f9644-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="f9644-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="f9644-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f9644-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="f9644-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9644-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="f9644-110">MSI ファイルへのリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9644-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="f9644-111">エンティティ</span><span class="sxs-lookup"><span data-stu-id="f9644-111">Entity</span></span>  |<span data-ttu-id="f9644-112">32ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-112">32-bit</span></span>      |<span data-ttu-id="f9644-113">64ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-113">64-bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="f9644-114">商用</span><span class="sxs-lookup"><span data-stu-id="f9644-114">Commercial</span></span>     | [<span data-ttu-id="f9644-115">32ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-115">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="f9644-116">64ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-116">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="f9644-117">政府機関向け - GCC</span><span class="sxs-lookup"><span data-stu-id="f9644-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="f9644-118">32ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-118">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="f9644-119">64ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-119">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="f9644-120">政府機関向け - GCC High</span><span class="sxs-lookup"><span data-stu-id="f9644-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="f9644-121">32ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-121">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="f9644-122">64ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-122">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="f9644-123">政府機関向け - DoD</span><span class="sxs-lookup"><span data-stu-id="f9644-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="f9644-124">32ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-124">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="f9644-125">64ビット</span><span class="sxs-lookup"><span data-stu-id="f9644-125">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> <span data-ttu-id="f9644-126">64ビット版の Teams を64ビットオペレーティングシステムにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9644-126">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="f9644-127">64ビット版の Teams を32ビットのオペレーティングシステムにインストールしようとしても、インストールが成功せず、現在エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f9644-127">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and  currently you won't receive an error message.</span></span>

<span data-ttu-id="f9644-128">Teams は、Office 365 ProPlus の展開に含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9644-128">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="f9644-129">詳細については、「[Office 365 ProPlus で Microsoft Teams を展開する](https://docs.microsoft.com/deployoffice/teams-install)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9644-129">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="f9644-130">Microsoft Endpoint Configuration Manager の詳細については、「[構成マネージャーとは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9644-130">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="f9644-131">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="f9644-131">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="f9644-132">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="f9644-132">Retrieve the latest package.</span></span>
2. <span data-ttu-id="f9644-133">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9644-133">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="f9644-134">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="f9644-134">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="f9644-135">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="f9644-135">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="f9644-136">PC インストール</span><span class="sxs-lookup"><span data-stu-id="f9644-136">PC installation</span></span>

<span data-ttu-id="f9644-137">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="f9644-137">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="f9644-138">ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリのコピーがそのユーザーの `AppData` フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f9644-138">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="f9644-139">ユーザーが既に `AppData` フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="f9644-139">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="f9644-140">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="f9644-140">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="f9644-141">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9644-141">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="f9644-142">MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します (VDI 環境を除く)。</span><span class="sxs-lookup"><span data-stu-id="f9644-142">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="f9644-143">非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="f9644-143">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="f9644-144">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f9644-144">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="f9644-145">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="f9644-145">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="f9644-146">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="f9644-146">Target computer requirements</span></span>

- <span data-ttu-id="f9644-147">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="f9644-147">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="f9644-148">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="f9644-148">Windows 8.1 or later</span></span>
- <span data-ttu-id="f9644-149">Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="f9644-149">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="f9644-150">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="f9644-150">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="f9644-151">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="f9644-151">VDI installation</span></span>

<span data-ttu-id="f9644-152">VDI に Teams デスクトップ アプリを展開する方法の詳細なガイダンスについては、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9644-152">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="f9644-153">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="f9644-153">Clean up and redeployment procedure</span></span>

<span data-ttu-id="f9644-154">ユーザーが自分のユーザープロファイルから Teams をアンインストールした場合、MSI installer は、ユーザーが Teams アプリをアンインストールして、そのユーザープロファイルの Teams をインストールしなくなったことを追跡します。</span><span class="sxs-lookup"><span data-stu-id="f9644-154">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="f9644-155">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9644-155">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="f9644-156">各ユーザープロファイルにインストールされている Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9644-156">Uninstall the Teams app installed for every user profile.</span></span>
2. <span data-ttu-id="f9644-157">アンインストール後、ディレクトリを再帰的に`%localappdata%\Microsoft\Teams\`削除します。</span><span class="sxs-lookup"><span data-stu-id="f9644-157">After uninstall, delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="f9644-158">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="f9644-158">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="f9644-159">インストール後に Teams が自動的に起動しないようにする</span><span class="sxs-lookup"><span data-stu-id="f9644-159">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="f9644-160">MSI の既定の動作では、ユーザーがサインインするとすぐに Teams アプリがインストールされ、Teams が自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="f9644-160">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="f9644-161">ユーザーがインストールした後に Teams が自動的に起動しないようにするには、グループ ポリシーを使用してポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f9644-161">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="f9644-162">グループ ポリシーを使用する (推奨)</span><span class="sxs-lookup"><span data-stu-id="f9644-162">Use Group Policy (recommended)</span></span>

<span data-ttu-id="f9644-163">**[Prevent Microsoft Teams from starting automatically after installation]**(インストール後に Microsoft Teams が自動的に起動しないようにする) グループ ポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f9644-163">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="f9644-164">このポリシー設定は、[ユーザー構成]\[ポリシー]\[管理用テンプレート]\[Microsoft Teams] にあります。</span><span class="sxs-lookup"><span data-stu-id="f9644-164">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="f9644-165">組織のニーズに合わせてポリシー設定を無効にも有効にもできるため、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9644-165">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="f9644-166">Teams がインストールされる前にこのポリシー設定を有効にしていると、ユーザーが Windows にログインしても Teams は自動起動しません。</span><span class="sxs-lookup"><span data-stu-id="f9644-166">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="f9644-167">ユーザーが初めて Teams にサインインすると、次にユーザーがログインしたときに Teams が自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="f9644-167">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="f9644-168">詳細については、「[グループ ポリシーを使用してインストール後に Microsoft Teams の自動起動を回避する](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9644-168">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="f9644-169">Teams を展開済みで、このポリシー設定で Teams の自動起動を無効にするには、最初にグループ ポリシー設定を必要な値に設定してから、ユーザーごとに [Teams 自動起動リセット スクリプト](scripts/powershell-script-teams-reset-autostart.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9644-169">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="f9644-170">MSI インストーラーの自動起動を無効にする</span><span class="sxs-lookup"><span data-stu-id="f9644-170">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="f9644-171">次のように **OPTIONS="noAutoStart=true"** パラメーターを使用することにより、MSI インストーラーの自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f9644-171">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="f9644-172">32ビット版の場合:</span><span class="sxs-lookup"><span data-stu-id="f9644-172">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="f9644-173">64ビット版の場合:</span><span class="sxs-lookup"><span data-stu-id="f9644-173">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="f9644-174">ユーザーが Windows にログインすると、Teams は MSI と一緒にインストールされ、Teams を起動するためのショートカットがユーザーのデスクトップに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f9644-174">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="f9644-175">そのユーザーが手動で Teams を起動するまで Teams は起動しません。</span><span class="sxs-lookup"><span data-stu-id="f9644-175">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="f9644-176">ユーザーが手動で Teams を起動すると、そのユーザーがログインするたびに Teams は自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="f9644-176">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="f9644-177">これらの例では、 **ALLUSERS = 1**パラメーターも使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9644-177">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="f9644-178">このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9644-178">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="f9644-179">すべてのユーザーは、コンピューターの管理者資格情報を持っている場合、Teams をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f9644-179">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="f9644-180">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="f9644-180">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="f9644-181">管理者として実行する場合でも、管理者特権で実行しない限り、インストーラーで自動起動を無効にするオプションを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9644-181">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
