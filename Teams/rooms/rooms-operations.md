---
title: Microsoft Teams の会議室のメンテナンスと操作
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。
ms.openlocfilehash: 626190406cf90cdbf09f2ab27d2b31f648f073c9
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269082"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="93313-103">Microsoft Teams の会議室のメンテナンスと操作</span><span class="sxs-lookup"><span data-stu-id="93313-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="93313-104">このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="93313-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="93313-105">Microsoft Teams room は、Microsoft の最新の会議ソリューションであり、会議室を豊かな共同作業環境に変革することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="93313-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="93313-106">ユーザーには、使い慣れた Microsoft Teams または Skype for Business インターフェイスが採用され、IT 管理者は、Windows 10 の Skype 会議アプリの展開と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="93313-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="93313-107">Microsoft Teams room は、インストールを容易にするために LCD パネルなどの既存の機器を活用して、Microsoft Teams または Skype for Business を会議室に持ち込むことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="93313-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="93313-108">追加の構成では、「 [Microsoft teams のルーム管理を Azure monitor と計画](azure-monitor-plan.md)する」および「azure monitor を使用して microsoft teams のルーム管理を[展開](azure-monitor-deploy.md)する」の説明に従って、microsoft teams を使用して microsoft teams を管理することが[できます。](azure-monitor-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="93313-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="93313-109">また、 [Microsoft Teams 会議コンソールの設定を XML 構成ファイルを使ってリモートで管理](xml-config-file.md)することもできます。これには、カスタム表示テーマの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="93313-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="93313-110">Microsoft Teams ルームでのログの収集</span><span class="sxs-lookup"><span data-stu-id="93313-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="93313-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-111"></span></span>

<span data-ttu-id="93313-112">ログを収集するには、Microsoft Teams のルームアプリに付属しているログ収集スクリプトを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="93313-113">管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="93313-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="93313-114">ログは ZIP ファイルとして c:\rigel に出力されます。</span><span class="sxs-lookup"><span data-stu-id="93313-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="93313-115">前面の会議室ディスプレイの設定</span><span class="sxs-lookup"><span data-stu-id="93313-115">Front of Room Display Settings</span></span>
<span data-ttu-id="93313-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-116"></span></span>

<span data-ttu-id="93313-117">前面の会議室ディスプレイを拡張モードに構成します。</span><span class="sxs-lookup"><span data-stu-id="93313-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="93313-118">この操作を行うと、ディスプレイの電源を入れたときに、そのディスプレイに本体の UI が複製されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="93313-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93313-119">会議室の表示の前に、ソースがスタンバイモードから復帰したときに、アクティブなビデオソース (MTR 本体など) に自動的に切り替える場合は、特定の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="93313-120">この機能はオプションですが、基盤となるハードウェアによって機能がサポートされている場合は、Microsoft Teams ルームソフトウェアでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="93313-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="93313-121">Room ディスプレイの正面に使用されている消費者のテレビでは、HDMI のコンシューマーエレクトロニクス制御 (CEC) 機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="93313-122">選択されているドックまたはコンソール (CEC をサポートしていない可能性があります) に応じて、適切な動作を実現するには、Extron on the または Extron the [HD CTL 100 で](https://www.extron.com/article/hdctl100ad)の[hd-RX-201-](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) -------------------------</span><span class="sxs-lookup"><span data-stu-id="93313-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="93313-123">Microsoft Teams の会議室のリセット (工場出荷時の復元)</span><span class="sxs-lookup"><span data-stu-id="93313-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="93313-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-124"></span></span>

<span data-ttu-id="93313-125">Microsoft Teams の会議室が正常に動作していない場合は、出荷時のリセットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="93313-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="93313-126">これを行うには、 [Microsoft Teams Room recovery ツール](recovery-tool.md)を使用して、出荷時の復元手順に従います。</span><span class="sxs-lookup"><span data-stu-id="93313-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="93313-127">**[自分のファイルを保持する] でアプリと設定を削除**した場合、Microsoft Teams の会議室が使用できなくなるという既知の問題がありますが、Windows のリセットプロセス中に個人用ファイルオプションが選択されたままになります。</span><span class="sxs-lookup"><span data-stu-id="93313-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="93313-128">このオプション*は使用しないでください。*</span><span class="sxs-lookup"><span data-stu-id="93313-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="93313-129">サポートされるリモート オプション</span><span class="sxs-lookup"><span data-stu-id="93313-129">Supported Remote Options</span></span>
<span data-ttu-id="93313-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-130"></span></span>

<span data-ttu-id="93313-131">次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="93313-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="93313-132">ワークグループ </span><span class="sxs-lookup"><span data-stu-id="93313-132">Workgroup</span></span>|<span data-ttu-id="93313-133">ドメインに参加していない場合</span><span class="sxs-lookup"><span data-stu-id="93313-133">Not domain joined</span></span>|<span data-ttu-id="93313-134">ドメインに参加している場合</span><span class="sxs-lookup"><span data-stu-id="93313-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="93313-135">再起動</span><span class="sxs-lookup"><span data-stu-id="93313-135">Restart</span></span>  <br/> |<span data-ttu-id="93313-136">リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="93313-136">Remote desktop</span></span>  <br/> <span data-ttu-id="93313-137">リモート Powershell</span><span class="sxs-lookup"><span data-stu-id="93313-137">Remote Powershell</span></span>  <br/> |<span data-ttu-id="93313-138">リモートデスクトップ (さらに構成が必要)</span><span class="sxs-lookup"><span data-stu-id="93313-138">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="93313-139">リモート Powershell (さらに構成が必要)</span><span class="sxs-lookup"><span data-stu-id="93313-139">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="93313-140">SCCM</span><span class="sxs-lookup"><span data-stu-id="93313-140">SCCM</span></span>  <br/> |
|<span data-ttu-id="93313-141">OS の更新</span><span class="sxs-lookup"><span data-stu-id="93313-141">Update OS</span></span>  <br/> |<span data-ttu-id="93313-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="93313-142">Windows Update</span></span>  <br/> |<span data-ttu-id="93313-143">Windows Update</span><span class="sxs-lookup"><span data-stu-id="93313-143">Windows Update</span></span>  <br/> <span data-ttu-id="93313-144">WSUS</span><span class="sxs-lookup"><span data-stu-id="93313-144">WSUS</span></span>  <br/> |
|<span data-ttu-id="93313-145">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="93313-145">App update</span></span>  <br/> |<span data-ttu-id="93313-146">	Windows ストア</span><span class="sxs-lookup"><span data-stu-id="93313-146">Windows Store</span></span>  <br/> |<span data-ttu-id="93313-147">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="93313-147">Windows Store</span></span>  <br/> <span data-ttu-id="93313-148">SCCM</span><span class="sxs-lookup"><span data-stu-id="93313-148">SCCM</span></span>  <br/> |
|<span data-ttu-id="93313-149">Skype アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="93313-149">Skype Account Config</span></span>  <br/> |<span data-ttu-id="93313-150">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="93313-150">Not currently supported</span></span>  <br/> |<span data-ttu-id="93313-151">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="93313-151">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="93313-152">ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="93313-152">Access logs</span></span>  <br/> |<span data-ttu-id="93313-153">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="93313-153">Not currently supported</span></span>  <br/> |<span data-ttu-id="93313-154">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="93313-154">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="93313-155">Microsoft Teams ルームのグループポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="93313-155">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="93313-156"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-156"></span></span>

<span data-ttu-id="93313-157">このセクションでは、Microsoft Teams のルームが適切に機能するために依存するシステム設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="93313-157">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="93313-158">Microsoft Teams のルームをドメインに参加させる場合は、次の表の設定を上書きしないようにグループポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="93313-158">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="93313-159">設定</span><span class="sxs-lookup"><span data-stu-id="93313-159">Setting</span></span>|<span data-ttu-id="93313-160">よう</span><span class="sxs-lookup"><span data-stu-id="93313-160">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="93313-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="93313-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="93313-162">Microsoft Teams のルームを起動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="93313-162">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="93313-163">電源管理-\> AC 電源、10分後に画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="93313-163">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="93313-164">電源管理-\> AC で、システムをスリープ状態にしない</span><span class="sxs-lookup"><span data-stu-id="93313-164">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="93313-165">Microsoft Teams の会議機能を有効にして、添付されたディスプレイをオフにし、自動的にスリープ状態を解除する</span><span class="sxs-lookup"><span data-stu-id="93313-165">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="93313-166">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="93313-166">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="93313-167">または、ローカルアカウントのパスワードの有効期限を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="93313-167">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="93313-168">そうしないと、有効期限が切れたパスワードについて、Skype アカウントがログオンに失敗することになります。</span><span class="sxs-lookup"><span data-stu-id="93313-168">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="93313-169">これは、マシン上のすべてのローカルアカウントに影響を与えるため、これを設定しないと、そのボックスの管理者アカウントも最終的に有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="93313-169">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="93313-170">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="93313-170">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="93313-171">グループポリシーを使用してファイルを転送する方法については[、「ファイルを構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)する」をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93313-171">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="93313-172">Microsoft Teams の会議室デバイスが次のバージョンの Windows 10 OS と互換性がある場合、デバイスは Windows Update 経由で次のバージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="93313-172">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="93313-173">Microsoft Teams 室のデバイスは、手動で、または「Windows Update for Business (WUFB) グループポリシーを有効にする」を使用して手動でアップグレードしないでください。受信する更新プログラムの Windows の準備レベルを選択する機能の更新プログラムは、GPO を通じて受信されます。</span><span class="sxs-lookup"><span data-stu-id="93313-173">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="93313-174">これらのグループポリシーが有効になっているデバイスでは、Microsoft Teams の会議アプリでの Windows 10 OS 更新プログラムで問題が発生することがわかっています。</span><span class="sxs-lookup"><span data-stu-id="93313-174">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="93313-175">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="93313-175">Remote Management using PowerShell</span></span>
<span data-ttu-id="93313-176"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-176"></span></span>

<span data-ttu-id="93313-177">PowerShell を使用して、次の管理操作をリモートで実行できます (スクリプトサンプルについては、以下の表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="93313-177">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="93313-178">接続されているデバイスの取得</span><span class="sxs-lookup"><span data-stu-id="93313-178">Get attached devices</span></span>
- <span data-ttu-id="93313-179">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="93313-179">Get app status</span></span>
- <span data-ttu-id="93313-180">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="93313-180">Get system info</span></span>
- <span data-ttu-id="93313-181">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="93313-181">Reboot system</span></span>
- <span data-ttu-id="93313-182">ログの取得</span><span class="sxs-lookup"><span data-stu-id="93313-182">Retrieve logs</span></span>
- <span data-ttu-id="93313-183">ファイルを転送する (ドメインに参加している Microsoft Teams ルームが必要)</span><span class="sxs-lookup"><span data-stu-id="93313-183">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="93313-184">既定では、この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="93313-184">This functionality is off by default.</span></span> <span data-ttu-id="93313-185">以下の操作を実行するには、Microsoft Teams のルームシステムの環境に対してリモート PowerShell を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-185">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="93313-186">リモート PowerShell を有効にする方法については、「 **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93313-186">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="93313-187">たとえば、次のようにリモート PowerShell を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="93313-187">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="93313-188">Microsoft Teams の会議室のデバイスで、管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="93313-188">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="93313-189">管理者特権の PowerShell コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="93313-189">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="93313-190">次のコマンドを入力します。Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="93313-190">Enter the following command: Enable-PSRemoting -force</span></span>

<span data-ttu-id="93313-191">管理操作を実行するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="93313-191">To perform a management operation:</span></span>
  
1. <span data-ttu-id="93313-192">Microsoft Teams 室のデバイスで PowerShell コマンドを実行する権限を持つ、アカウントの資格情報を使って PC にサインインします。</span><span class="sxs-lookup"><span data-stu-id="93313-192">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="93313-193">PC で通常の PowerShell コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="93313-193">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="93313-194">次の表からコマンドテキストをコピーし、メッセージに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="93313-194">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="93313-195">使用`<Device fqdn>`している環境に適した FQDN 値をフィールドに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="93313-195">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="93313-196">\* \<Path\> \*を、マスター skypesettings (またはテーマの画像) のファイル名とローカルパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="93313-196">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="93313-197">接続されているデバイスを取得するには</span><span class="sxs-lookup"><span data-stu-id="93313-197">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="93313-198">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="93313-198">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="93313-199">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="93313-199">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="93313-200">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="93313-200">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="93313-201">ログの取得</span><span class="sxs-lookup"><span data-stu-id="93313-201">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="93313-202">XML 構成ファイル (またはテーマグラフィック) をプッシュする</span><span class="sxs-lookup"><span data-stu-id="93313-202">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="93313-203">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="93313-203">Software updates</span></span>
<span data-ttu-id="93313-204"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-204"></span></span>

<span data-ttu-id="93313-205">既定では、Microsoft Teams の会議は、Microsoft Teams ルームソフトウェアの最新バージョンを取得するために Windows ストアに接続しようとします。そのため、デバイスでは、通常のインターネットアクセスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="93313-205">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="93313-206">サポートの問題が発生した場合は、Microsoft Teams の会議室のデバイスが最新バージョンのアプリと共に読み込まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="93313-206">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="93313-207">既定では、Microsoft Teams のルームは Windows Update に接続して、オペレーティングシステムと USB 周辺機器のファームウェア更新プログラムを取得し、構成された勤務時間外にインストールします。</span><span class="sxs-lookup"><span data-stu-id="93313-207">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="93313-208">営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="93313-208">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="93313-209">更新プログラムを手動で管理する必要がある場合に、一般[法人向け Microsoft ストア](https://businessstore.microsoft.com/store)の一般手順に従って[オフラインアプリを配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)することができない場合は、SCCM で使用できる、 [Microsoft Teams ルーム本体を構成](console.md)する手順から[展開キット](https://go.microsoft.com/fwlink/?linkid=851168)から適切な APPX ファイルと依存関係を取得できます。</span><span class="sxs-lookup"><span data-stu-id="93313-209">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="93313-210">展開キットのリリースがストアのリリースよりも遅れているため、常に最新のビルドと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93313-210">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="93313-211">Powershell を使用して更新するには</span><span class="sxs-lookup"><span data-stu-id="93313-211">To update using Powershell</span></span>

1. <span data-ttu-id="93313-212">インストール[MSI](https://go.microsoft.com/fwlink/?linkid=851168)からデバイスがアクセスできる共有にパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="93313-212">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="93313-213">次のスクリプトを実行して、Microsoft Teams の会議\<室\>のデバイスをターゲットにし、必要に応じて共有をデバイス共有に変更します。</span><span class="sxs-lookup"><span data-stu-id="93313-213">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="93313-214">管理者モードとデバイス管理</span><span class="sxs-lookup"><span data-stu-id="93313-214">Admin mode and device management</span></span>
<span data-ttu-id="93313-215"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-215"></span></span>

<span data-ttu-id="93313-216">プライベート CA 証明書を手動でインストールするなどの一部の管理機能には、Surface Pro デバイスを管理モードで配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-216">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="93313-217">Microsoft Teams のルームアプリが実行されているときに、管理モードに切り替えて戻る</span><span class="sxs-lookup"><span data-stu-id="93313-217">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="93313-218">進行中の通話を切断して、ホーム画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="93313-218">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="93313-219">歯車アイコンを選択し、メニューを開きます (オプションは [**設定**]、[**アクセシビリティ**]、[**デバイスの再起動**])。</span><span class="sxs-lookup"><span data-stu-id="93313-219">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="93313-220">[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="93313-220">Select **Settings**.</span></span>
4. <span data-ttu-id="93313-221">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="93313-221">Enter the Administrator Password.</span></span> <span data-ttu-id="93313-222">セットアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="93313-222">The Setup screen will appear.</span></span>  <span data-ttu-id="93313-223">デバイスがドメインに参加していない場合は、ローカルの管理者アカウント (ユーザー名 "管理者") が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="93313-223">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="93313-224">このアカウントの既定のパスワードは "sfb" で、できるだけ早くパスワードを変更してください。</span><span class="sxs-lookup"><span data-stu-id="93313-224">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="93313-225">コンピューターがドメインに参加している場合は、適切な権限を持つドメインアカウントでサインインできます。</span><span class="sxs-lookup"><span data-stu-id="93313-225">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="93313-226">左側の列で、[ **Windows の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="93313-226">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="93313-227">[**管理サインインに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="93313-227">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="93313-228">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="93313-228">Enter the Administrator Password.</span></span> <span data-ttu-id="93313-229">これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="93313-229">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="93313-230">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="93313-230">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="93313-231">デバイスを管理するために必要な権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="93313-231">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="93313-232">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="93313-232">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="93313-233">管理者アカウントからサイン アウトします。</span><span class="sxs-lookup"><span data-stu-id="93313-233">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="93313-234">画面左側のユーザーアカウントアイコンを選択し、[ **Skype**] を選択して、Microsoft Teams のルームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="93313-234">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="93313-235">**Skype**ユーザーが表示されていない場合は、[**他のユーザー** ] を選択し、ユーザー名として「 **.\skype** 」と入力して、サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="93313-235">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="93313-236">これで本体が通常の操作モードに戻ります。次の手順では、デバイスがまだ接続されていない場合は、そのデバイスにキーボードをアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-236">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="93313-237">Microsoft Teams の会議アプリがクラッシュしたときに、管理モードに切り替えて戻る</span><span class="sxs-lookup"><span data-stu-id="93313-237">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="93313-238">Windows キーを 5 回連続で、素早く押します。</span><span class="sxs-lookup"><span data-stu-id="93313-238">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="93313-239">これによって、Windows のログオン画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="93313-239">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="93313-240">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="93313-240">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="93313-241">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="93313-241">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="93313-242">完了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="93313-242">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="93313-243">この方法では、Skype ユーザをログオフしたり、アプリを正常に終了したりすることはありませんが、アプリが応答しなくなった場合や、その他の方法が利用できない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="93313-243">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="93313-244">本体は、Microsoft Teams のルームアプリを実行して、通常の操作モードで再起動します。</span><span class="sxs-lookup"><span data-stu-id="93313-244">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="93313-245">この手順を実行できるように設定されている場合は、キーボードを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="93313-245">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="93313-246">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="93313-246">Troubleshooting tips</span></span>
   <span data-ttu-id="93313-247"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="93313-247"></span></span>

- <span data-ttu-id="93313-248">会議の出席依頼は、(2 つの会社間など) ドメインの境界を越えて送信された場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="93313-248">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="93313-249">このような場合、IT 管理者は、外部ユーザーによる会議のスケジュールを許可するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93313-249">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="93313-250">Microsoft Teams のルームは、Exchange 2010 経由の Exchange 自動検出リダイレクトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="93313-250">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="93313-251">一般的に、IT 管理者が使用する必要のないオーディオエンドポイントを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93313-251">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="93313-252">ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。</span><span class="sxs-lookup"><span data-stu-id="93313-252">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="93313-253">コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="93313-253">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="93313-254">このような場合、Microsoft Teams のルームシステムを再起動すると、問題が解決されることがあります。</span><span class="sxs-lookup"><span data-stu-id="93313-254">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="93313-255">有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="93313-255">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="93313-256">このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="93313-256">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
