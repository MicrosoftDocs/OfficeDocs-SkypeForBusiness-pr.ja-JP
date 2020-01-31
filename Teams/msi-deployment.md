---
title: Microsoft Endpoint Configuration Manager を使用して MSI を使用して Microsoft Teams をインストールする
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
ms.openlocfilehash: 2f6902ae52c04d0087bb6718b119ae66dd920ced
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628133"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="80933-103">Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="80933-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="80933-104">Windows Desktop Clientの効果、計画や展開の方法については、[Teams Windows Desktop Client](https://aka.ms/teams-clients) のセッションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80933-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="80933-105">Microsoft Endpoint Configuration Manager、またはグループポリシー、または広範な展開のためのサードパーティの配布メカニズムを使用するには、管理者がユーザーを選ぶためにチームの一括展開に使用できる MSI ファイル (32 ビットと64ビット) を提供しています。マシン.</span><span class="sxs-lookup"><span data-stu-id="80933-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="80933-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="80933-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="80933-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="80933-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="80933-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="80933-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="80933-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="80933-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="80933-110">MSI ファイルへのリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="80933-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="80933-111">エンティティ</span><span class="sxs-lookup"><span data-stu-id="80933-111">Entity</span></span>  |<span data-ttu-id="80933-112">32ビット</span><span class="sxs-lookup"><span data-stu-id="80933-112">32 bit</span></span>      |<span data-ttu-id="80933-113">64ビット</span><span class="sxs-lookup"><span data-stu-id="80933-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="80933-114">業者</span><span class="sxs-lookup"><span data-stu-id="80933-114">Commercial</span></span>     | [<span data-ttu-id="80933-115">32ビット</span><span class="sxs-lookup"><span data-stu-id="80933-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="80933-116">64ビット</span><span class="sxs-lookup"><span data-stu-id="80933-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="80933-117">米国連邦政府-GCC</span><span class="sxs-lookup"><span data-stu-id="80933-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="80933-118">32ビット</span><span class="sxs-lookup"><span data-stu-id="80933-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="80933-119">64ビット</span><span class="sxs-lookup"><span data-stu-id="80933-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="80933-120">米国連邦政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="80933-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="80933-121">32ビット</span><span class="sxs-lookup"><span data-stu-id="80933-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="80933-122">64ビット</span><span class="sxs-lookup"><span data-stu-id="80933-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="80933-123">米国連邦政府-DoD</span><span class="sxs-lookup"><span data-stu-id="80933-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="80933-124">32ビット</span><span class="sxs-lookup"><span data-stu-id="80933-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="80933-125">64ビット</span><span class="sxs-lookup"><span data-stu-id="80933-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="80933-126">Teams は、Office 365 ProPlus の展開に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="80933-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="80933-127">詳細については、「 [Office 365 を使用して Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/deployoffice/teams-install)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80933-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="80933-128">Microsoft Endpoint Configuration Manager の詳細については、「[構成マネージャーとは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80933-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="80933-129">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="80933-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="80933-130">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="80933-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="80933-131">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="80933-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="80933-132">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="80933-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="80933-133">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="80933-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="80933-134">PC のインストール</span><span class="sxs-lookup"><span data-stu-id="80933-134">PC installation</span></span>

<span data-ttu-id="80933-135">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="80933-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="80933-136">ユーザーが新しい Windows ユーザープロファイルにサインインするたびに、インストーラーが起動され、Teams アプリのコピーがそのユーザーの appdata フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="80933-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="80933-137">ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="80933-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="80933-138">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="80933-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="80933-139">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="80933-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="80933-140">以前のバージョンの MSI パッケージを展開する場合、クライアントは、可能な場合に、(VDI 環境を除く) 自動更新されます。</span><span class="sxs-lookup"><span data-stu-id="80933-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="80933-141">非常に古いバージョンが展開された場合、MSI は、ユーザーが Teams を使用できるようになる前に、アプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="80933-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="80933-142">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="80933-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="80933-143">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="80933-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="80933-144">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="80933-144">Target computer requirements</span></span>

- <span data-ttu-id="80933-145">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="80933-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="80933-146">Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="80933-146">Windows 7 or later</span></span>
- <span data-ttu-id="80933-147">Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="80933-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="80933-148">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="80933-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="80933-149">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="80933-149">VDI installation</span></span>

<span data-ttu-id="80933-150">VDI に Teams デスクトップアプリを展開する方法の詳細なガイダンスについては、「仮想化された[デスクトップインフラストラクチャの teams](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80933-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="80933-151">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="80933-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="80933-152">ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。</span><span class="sxs-lookup"><span data-stu-id="80933-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="80933-153">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80933-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="80933-154">それぞれのユーザー プロファイルにインストールされている Teams アプリをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="80933-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="80933-155">アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="80933-155">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="80933-156">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="80933-156">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="80933-157">[Microsoft Teams の展開クリーンアップ](scripts/Powershell-script-teams-deployment-clean-up.md)スクリプトを使用して、構成マネージャーで手順1と2を実行できます。</span><span class="sxs-lookup"><span data-stu-id="80933-157">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via Configuration Manager.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="80933-158">インストール後にチームが自動的に起動しないようにする</span><span class="sxs-lookup"><span data-stu-id="80933-158">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="80933-159">MSI の既定の動作では、ユーザーがサインインしてからチームを自動的に開始するとすぐに Teams アプリをインストールすることになります。</span><span class="sxs-lookup"><span data-stu-id="80933-159">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="80933-160">ユーザーがインストールした後にチームが自動的に起動しないようにするには、グループポリシーを使ってポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="80933-160">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="80933-161">グループポリシーを使用する (推奨)</span><span class="sxs-lookup"><span data-stu-id="80933-161">Use Group Policy (recommended)</span></span>

<span data-ttu-id="80933-162">[**インストール後に Microsoft Teams が自動的に起動しないよう**にする] グループポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="80933-162">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="80933-163">このポリシー設定は、User の microsoft Teams で確認できます。</span><span class="sxs-lookup"><span data-stu-id="80933-163">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="80933-164">この方法は、組織のニーズに合わせてポリシー設定をオフまたはオンにすることができるため、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="80933-164">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="80933-165">Teams をインストールする前にこのポリシー設定を有効にすると、ユーザーが Windows にログインしてもチームは自動的に開始されません。</span><span class="sxs-lookup"><span data-stu-id="80933-165">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="80933-166">ユーザーが初めて Teams にサインインすると、次回ユーザーがログインしたときに自動的にチームが開始されます。</span><span class="sxs-lookup"><span data-stu-id="80933-166">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="80933-167">詳細については、「グループポリシーを使用して、[インストール後にチームが自動的に起動しないように](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80933-167">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="80933-168">チームを既に展開していて、このポリシーを設定して Teams の自動開始を無効にしたい場合は、まず、グループポリシーの設定を必要な値に設定してから、チームの [ [autostart reset] スクリプト](scripts/powershell-script-teams-reset-autostart.md)をユーザーごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="80933-168">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="80933-169">MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="80933-169">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="80933-170">次のように**OPTIONS = "noAutoStart = true"** パラメーターを使用して、MSI インストーラーの自動起動を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="80933-170">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="80933-171">32 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="80933-171">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="80933-172">64 ビット 版向け</span><span class="sxs-lookup"><span data-stu-id="80933-172">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="80933-173">ユーザーが Windows にログインすると、Teams が MSI と共にインストールされ、チームを開始するためのショートカットがユーザーのデスクトップに追加されます。</span><span class="sxs-lookup"><span data-stu-id="80933-173">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="80933-174">ユーザーが Teams を手動で開始するまで、チームは開始されません。</span><span class="sxs-lookup"><span data-stu-id="80933-174">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="80933-175">ユーザーが手動でチームを開始すると、ユーザーがログインするたびにチームが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="80933-175">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="80933-176">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="80933-176">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="80933-177">管理者として実行しても、昇格されたアクセス許可で実行しなければ、インストーラーは自動開始を無効にするオプションを構成できません。</span><span class="sxs-lookup"><span data-stu-id="80933-177">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
