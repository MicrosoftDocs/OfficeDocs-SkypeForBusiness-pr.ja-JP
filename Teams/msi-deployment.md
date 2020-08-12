---
title: Microsoft Endpoint Configuration Manager を使用してチームをインストールする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: Microsoft Endpoint Configuration Manager を使用して、Microsoft Teams を一括展開してユーザーまたはコンピューターを選択します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55a514aa6aec6991e331b445a2fbb6e9c602ac91
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640832"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="61d93-103">Microsoft Endpoint Configuration Manager を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="61d93-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="61d93-104">Windows デスクトップクライアントの利点、その計画方法、展開方法については、次のセッションをご覧ください。 [Teams Windows デスクトップクライアント](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="61d93-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="61d93-105">Microsoft Endpoint Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用できる MSI ファイル (32 ビットと 64 ビットの両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="61d93-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="61d93-106">管理者はこれらのファイルを使用してリモートで Teams を展開できます。そのため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="61d93-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="61d93-107">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します</span><span class="sxs-lookup"><span data-stu-id="61d93-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="61d93-108">(アプリのインストール後に自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="61d93-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="61d93-109">[以下を参照してください](#disable-auto-launch-for-the-msi-installer))。コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開による効果を得られるようにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61d93-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="61d93-110">MSI ファイルへのリンクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="61d93-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="61d93-111">エンティティ</span><span class="sxs-lookup"><span data-stu-id="61d93-111">Entity</span></span>  |<span data-ttu-id="61d93-112">32ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-112">32-bit</span></span>      |<span data-ttu-id="61d93-113">64ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-113">64-bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="61d93-114">商用</span><span class="sxs-lookup"><span data-stu-id="61d93-114">Commercial</span></span>     | [<span data-ttu-id="61d93-115">32ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-115">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="61d93-116">64ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-116">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="61d93-117">政府機関向け - GCC</span><span class="sxs-lookup"><span data-stu-id="61d93-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="61d93-118">32ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-118">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="61d93-119">64ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-119">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="61d93-120">政府機関向け - GCC High</span><span class="sxs-lookup"><span data-stu-id="61d93-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="61d93-121">32ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-121">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="61d93-122">64ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-122">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="61d93-123">政府機関向け - DoD</span><span class="sxs-lookup"><span data-stu-id="61d93-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="61d93-124">32ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-124">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="61d93-125">64ビット</span><span class="sxs-lookup"><span data-stu-id="61d93-125">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="61d93-126">**展開を成功させるには、次の点に注意してください。**</span><span class="sxs-lookup"><span data-stu-id="61d93-126">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="61d93-127">64ビット版の Teams を64ビットオペレーティングシステムにインストールします。</span><span class="sxs-lookup"><span data-stu-id="61d93-127">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="61d93-128">64ビット版の Teams を32ビットのオペレーティングシステムにインストールしようとしても、インストールが成功せず、現在エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="61d93-128">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="61d93-129">顧客テナントが GCCH または DoD クラウド上にある場合は、レジストリの**HKEY_CURRENT_USER \software\policies\microsoft\office\16.0\teams**キーに**cloudtype**値を追加して、ユーザーがレジストリの初期エンドポイントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61d93-129">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="61d93-130">**Cloudtype**の型は**DWORD**と値です (0 = Unset、1 = 商業、2 = GCC、3 = GCCH、4 = DOD)。</span><span class="sxs-lookup"><span data-stu-id="61d93-130">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="61d93-131">レジストリキーを使用してエンドポイントを設定すると、チームは、チームとのサインイン時に適切なクラウドエンドポイントに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="61d93-131">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="61d93-132">Teams は、enterprise 用の Microsoft 365 アプリの展開に含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="61d93-132">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="61d93-133">詳細については、「 [microsoft 365 アプリで企業向けの Microsoft Teams を展開する](https://docs.microsoft.com/deployoffice/teams-install)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-133">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

- <span data-ttu-id="61d93-134">Microsoft Endpoint Configuration Manager の詳細については、「[構成マネージャーとは](https://docs.microsoft.com/configmgr/core/understand/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-134">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="61d93-135">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="61d93-135">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="61d93-136">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="61d93-136">Retrieve the latest package.</span></span>
2. <span data-ttu-id="61d93-137">MSI が事前に入力した既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="61d93-137">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="61d93-138">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="61d93-138">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="61d93-139">Microsoft Teams MSI パッケージの仕組み</span><span class="sxs-lookup"><span data-stu-id="61d93-139">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="61d93-140">PC インストール</span><span class="sxs-lookup"><span data-stu-id="61d93-140">PC installation</span></span>

<span data-ttu-id="61d93-141">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="61d93-141">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="61d93-142">ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリのコピーがそのユーザーの `AppData` フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="61d93-142">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="61d93-143">ユーザーが既に `AppData` フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="61d93-143">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="61d93-144">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="61d93-144">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="61d93-145">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="61d93-145">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="61d93-146">MSI パッケージの以前のバージョンを展開すると、クライアントはそのユーザーが可能なときに自動更新を実行します (VDI 環境を除く)。</span><span class="sxs-lookup"><span data-stu-id="61d93-146">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="61d93-147">非常に昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="61d93-147">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="61d93-148">既定のインストール場所を変更すると、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="61d93-148">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="61d93-149">非常に昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="61d93-149">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="61d93-150">対象となるコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="61d93-150">Target computer requirements</span></span>

- <span data-ttu-id="61d93-151">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="61d93-151">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="61d93-152">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="61d93-152">Windows 8.1 or later</span></span>
- <span data-ttu-id="61d93-153">Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="61d93-153">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="61d93-154">各ユーザー プロファイルに 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="61d93-154">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="61d93-155">VDI インストール</span><span class="sxs-lookup"><span data-stu-id="61d93-155">VDI installation</span></span>

<span data-ttu-id="61d93-156">VDI に Teams デスクトップ アプリを展開する方法の詳細なガイダンスについては、「[仮想デスクトップ インフラストラクチャ用の Teams](teams-for-vdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-156">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="61d93-157">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="61d93-157">Clean up and redeployment procedure</span></span>

<span data-ttu-id="61d93-158">ユーザーが自分のユーザープロファイルから Teams をアンインストールした場合、MSI installer は、ユーザーが Teams アプリをアンインストールして、そのユーザープロファイルの Teams をインストールしなくなったことを追跡します。</span><span class="sxs-lookup"><span data-stu-id="61d93-158">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="61d93-159">このユーザーのために Teams がアンインストールされた特定のコンピューター上で Teams を再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61d93-159">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61d93-160">次の手順には、レジストリの変更方法についての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="61d93-160">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="61d93-161">レジストリを変更する前に必ずバックアップし、問題が発生した場合にレジストリを復元する方法について確認してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-161">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="61d93-162">レジストリのバックアップ、復元、変更の詳細については、「[上級ユーザー向けの Windows レジストリ情報](https://support.microsoft.com/help/256986)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-162">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="61d93-163">各ユーザープロファイルにインストールされている Teams アプリをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="61d93-163">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="61d93-164">詳細については、「 [Microsoft Teams をアンインストール](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-164">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="61d93-165">ディレクトリを再帰的に削除 `%localappdata%\Microsoft\Teams\` します。</span><span class="sxs-lookup"><span data-stu-id="61d93-165">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="61d93-166">`HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`レジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="61d93-166">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="61d93-167">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="61d93-167">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="61d93-168">インストール後に Teams が自動的に起動しないようにする</span><span class="sxs-lookup"><span data-stu-id="61d93-168">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="61d93-169">MSI の既定の動作では、ユーザーがサインインするとすぐに Teams アプリがインストールされ、Teams が自動的に起動されます。</span><span class="sxs-lookup"><span data-stu-id="61d93-169">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="61d93-170">ユーザーがインストールした後に Teams が自動的に起動しないようにするには、グループ ポリシーを使用してポリシー設定を設定するか、MSI インストーラーの自動起動を無効にします。</span><span class="sxs-lookup"><span data-stu-id="61d93-170">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="61d93-171">グループ ポリシーを使用する (推奨)</span><span class="sxs-lookup"><span data-stu-id="61d93-171">Use Group Policy (recommended)</span></span>

<span data-ttu-id="61d93-172">**[Prevent Microsoft Teams from starting automatically after installation]**(インストール後に Microsoft Teams が自動的に起動しないようにする) グループ ポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="61d93-172">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="61d93-173">このポリシー設定は、[ユーザー構成]\[ポリシー]\[管理用テンプレート]\[Microsoft Teams] にあります。</span><span class="sxs-lookup"><span data-stu-id="61d93-173">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="61d93-174">組織のニーズに合わせてポリシー設定を無効にも有効にもできるため、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61d93-174">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="61d93-175">Teams がインストールされる前にこのポリシー設定を有効にしていると、ユーザーが Windows にログインしても Teams は自動起動しません。</span><span class="sxs-lookup"><span data-stu-id="61d93-175">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="61d93-176">ユーザーが初めて Teams にサインインすると、次にユーザーがログインしたときに Teams が自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="61d93-176">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="61d93-177">詳細については、「[グループ ポリシーを使用してインストール後に Microsoft Teams の自動起動を回避する](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-177">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="61d93-178">Teams を展開済みで、このポリシー設定で Teams の自動起動を無効にするには、最初にグループ ポリシー設定を必要な値に設定してから、ユーザーごとに [Teams 自動起動リセット スクリプト](scripts/powershell-script-teams-reset-autostart.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="61d93-178">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="61d93-179">MSI インストーラーの自動起動を無効にする</span><span class="sxs-lookup"><span data-stu-id="61d93-179">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="61d93-180">次のように **OPTIONS="noAutoStart=true"** パラメーターを使用することにより、MSI インストーラーの自動起動を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="61d93-180">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="61d93-181">32ビット版の場合:</span><span class="sxs-lookup"><span data-stu-id="61d93-181">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="61d93-182">64ビット版の場合:</span><span class="sxs-lookup"><span data-stu-id="61d93-182">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="61d93-183">ユーザーが Windows にログインすると、Teams は MSI と一緒にインストールされ、Teams を起動するためのショートカットがユーザーのデスクトップに追加されます。</span><span class="sxs-lookup"><span data-stu-id="61d93-183">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="61d93-184">そのユーザーが手動で Teams を起動するまで Teams は起動しません。</span><span class="sxs-lookup"><span data-stu-id="61d93-184">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="61d93-185">ユーザーが手動で Teams を起動すると、そのユーザーがログインするたびに Teams は自動起動するようになります。</span><span class="sxs-lookup"><span data-stu-id="61d93-185">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="61d93-186">これらの例では、 **ALLUSERS = 1**パラメーターも使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="61d93-186">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="61d93-187">このパラメーターを設定すると、チームのコンピューター全体のインストーラーがコントロールパネルの [プログラムと機能] に表示され、[アプリ] では、コンピューターのすべてのユーザーの Windows 設定の & 機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="61d93-187">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="61d93-188">すべてのユーザーは、コンピューターの管理者資格情報を持っている場合、Teams をアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="61d93-188">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="61d93-189">MSI を手動で実行する場合は、昇格されたアクセス許可で実行します。</span><span class="sxs-lookup"><span data-stu-id="61d93-189">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="61d93-190">管理者として実行する場合でも、管理者特権で実行しない限り、インストーラーで自動起動を無効にするオプションを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="61d93-190">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
