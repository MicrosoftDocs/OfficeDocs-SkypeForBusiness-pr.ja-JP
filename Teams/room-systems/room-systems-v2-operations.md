---
title: Microsoft Teams の会議室のメンテナンスと操作
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。
ms.openlocfilehash: c764490df9912ca464b1f11d56a2cb376b96c388
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573607"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="d496c-103">Microsoft Teams の会議室のメンテナンスと操作</span><span class="sxs-lookup"><span data-stu-id="d496c-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="d496c-104">このトピックでは、次世代の Skype Room Systems である Microsoft Teams のルームの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="d496c-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="d496c-105">Microsoft Teams room は、Microsoft の最新の会議ソリューションであり、会議室を豊かな共同作業環境に変革することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d496c-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="d496c-106">ユーザーには、使い慣れた Microsoft Teams または Skype for Business インターフェイスが採用され、IT 管理者は、Windows 10 の Skype 会議アプリの展開と管理が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d496c-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="d496c-107">Microsoft Teams room は、インストールを容易にするために LCD パネルなどの既存の機器を活用して、Microsoft Teams または Skype for Business を会議室に持ち込むことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d496c-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="d496c-108">追加の構成では、「 [Microsoft teams のルーム管理を Azure monitor で計画](azure-monitor-plan.md)する」および「azure モニターを使用して[Microsoft teams のルーム管理を展開](azure-monitor-deploy.md)する」の説明に従って、microsoft azure モニターを使用してリモート管理を行うことができます。 [Microsoft Teams は、Azure モニターを使用して](azure-monitor-deploy.md)います。</span><span class="sxs-lookup"><span data-stu-id="d496c-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="d496c-109">また、 [Microsoft Teams 会議コンソールの設定を XML 構成ファイルを使ってリモートで管理](xml-config-file.md)することもできます。これには、カスタム表示テーマの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d496c-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="d496c-110">Microsoft Teams ルームでのログの収集</span><span class="sxs-lookup"><span data-stu-id="d496c-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="d496c-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-111"></span></span>

<span data-ttu-id="d496c-112">ログを収集するには、Microsoft Teams のルームアプリに付属しているログ収集スクリプトを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="d496c-113">管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="d496c-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="d496c-114">ログは ZIP ファイルとして c:\rigel に出力されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="d496c-115">前面の会議室ディスプレイの設定</span><span class="sxs-lookup"><span data-stu-id="d496c-115">Front of Room Display Settings</span></span>
<span data-ttu-id="d496c-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-116"></span></span>

<span data-ttu-id="d496c-117">前面の会議室ディスプレイを拡張モードに構成します。</span><span class="sxs-lookup"><span data-stu-id="d496c-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="d496c-118">この操作を行うと、ディスプレイの電源を入れたときに、そのディスプレイに本体の UI が複製されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="d496c-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d496c-119">会議室の表示の前に、ソースがスタンバイモードから復帰したときに、アクティブなビデオソース (MTR 本体など) に自動的に切り替える場合は、特定の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="d496c-120">この機能はオプションですが、基盤となるハードウェアによって機能がサポートされている場合は、Microsoft Teams ルームソフトウェアでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d496c-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="d496c-121">Room ディスプレイの正面に使用されている消費者のテレビでは、HDMI のコンシューマーエレクトロニクス制御 (CEC) 機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="d496c-122">選択されているドックまたはコンソール (CEC をサポートしていない可能性があります) [201](https://www.crestron.com/en-US/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 、また[100](https://www.extron.com/article/hdctl100ad)は、メーカーのサポートドキュメントを参照してください。必要に応じて、お客様は、お客様が必要な機能を有効にする必要があります。状況.</span><span class="sxs-lookup"><span data-stu-id="d496c-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/en-US/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="d496c-123">Microsoft Teams の会議室のリセット (工場出荷時の復元)</span><span class="sxs-lookup"><span data-stu-id="d496c-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="d496c-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-124"></span></span>

<span data-ttu-id="d496c-125">Microsoft Teams の会議室が正常に動作していない場合は、出荷時のリセットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="d496c-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="d496c-126">この操作は、[**回復**] タブの [設定] アプリで行うことができます。 [**この PC のリセット**] で、[**作業の開始**] を選び、[**すべて削除**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d496c-126">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="d496c-127">残りの指示に従って、デバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="d496c-127">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d496c-128">**[自分のファイルを保持する] でアプリと設定を削除**した場合、Microsoft Teams の会議室が使用できなくなるという既知の問題がありますが、Windows のリセットプロセス中に個人用ファイルオプションが選択されたままになります。</span><span class="sxs-lookup"><span data-stu-id="d496c-128">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="d496c-129">このオプション_は使用しないでください。_</span><span class="sxs-lookup"><span data-stu-id="d496c-129">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="d496c-130">サポートされるリモート オプション</span><span class="sxs-lookup"><span data-stu-id="d496c-130">Supported Remote Options</span></span>
<span data-ttu-id="d496c-131"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-131"></span></span>

<span data-ttu-id="d496c-132">次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d496c-132">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="d496c-133">ワークグループ </span><span class="sxs-lookup"><span data-stu-id="d496c-133">Workgroup</span></span>|<span data-ttu-id="d496c-134">ドメインに参加していない場合</span><span class="sxs-lookup"><span data-stu-id="d496c-134">Not domain joined</span></span>|<span data-ttu-id="d496c-135">ドメインに参加している場合</span><span class="sxs-lookup"><span data-stu-id="d496c-135">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d496c-136">再起動</span><span class="sxs-lookup"><span data-stu-id="d496c-136">Restart</span></span>  <br/> |<span data-ttu-id="d496c-137">リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="d496c-137">Remote desktop</span></span>  <br/> <span data-ttu-id="d496c-138">リモート Powershell</span><span class="sxs-lookup"><span data-stu-id="d496c-138">Remote Powershell</span></span>  <br/> |<span data-ttu-id="d496c-139">リモートデスクトップ (さらに構成が必要)</span><span class="sxs-lookup"><span data-stu-id="d496c-139">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="d496c-140">リモート Powershell (さらに構成が必要)</span><span class="sxs-lookup"><span data-stu-id="d496c-140">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="d496c-141">SCCM</span><span class="sxs-lookup"><span data-stu-id="d496c-141">SCCM</span></span>  <br/> |
|<span data-ttu-id="d496c-142">OS の更新</span><span class="sxs-lookup"><span data-stu-id="d496c-142">Update OS</span></span>  <br/> |<span data-ttu-id="d496c-143">Windows Update</span><span class="sxs-lookup"><span data-stu-id="d496c-143">Windows Update</span></span>  <br/> |<span data-ttu-id="d496c-144">Windows Update</span><span class="sxs-lookup"><span data-stu-id="d496c-144">Windows Update</span></span>  <br/> <span data-ttu-id="d496c-145">WSUS</span><span class="sxs-lookup"><span data-stu-id="d496c-145">WSUS</span></span>  <br/> |
|<span data-ttu-id="d496c-146">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="d496c-146">App update</span></span>  <br/> |<span data-ttu-id="d496c-147">	Windows ストア</span><span class="sxs-lookup"><span data-stu-id="d496c-147">Windows Store</span></span>  <br/> |<span data-ttu-id="d496c-148">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="d496c-148">Windows Store</span></span>  <br/> <span data-ttu-id="d496c-149">SCCM</span><span class="sxs-lookup"><span data-stu-id="d496c-149">SCCM</span></span>  <br/> |
|<span data-ttu-id="d496c-150">Skype アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="d496c-150">Skype Account Config</span></span>  <br/> |<span data-ttu-id="d496c-151">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d496c-151">Not currently supported</span></span>  <br/> |<span data-ttu-id="d496c-152">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d496c-152">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="d496c-153">ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d496c-153">Access logs</span></span>  <br/> |<span data-ttu-id="d496c-154">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d496c-154">Not currently supported</span></span>  <br/> |<span data-ttu-id="d496c-155">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="d496c-155">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="d496c-156">Microsoft Teams ルームのグループポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="d496c-156">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="d496c-157"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-157"></span></span>

<span data-ttu-id="d496c-158">このセクションでは、Microsoft Teams のルームが適切に機能するために依存するシステム設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d496c-158">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="d496c-159">Microsoft Teams のルームをドメインに参加させる場合は、次の表の設定を上書きしないようにグループポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d496c-159">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="d496c-160">設定</span><span class="sxs-lookup"><span data-stu-id="d496c-160">Setting</span></span>|<span data-ttu-id="d496c-161">よう</span><span class="sxs-lookup"><span data-stu-id="d496c-161">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="d496c-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="d496c-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="d496c-163">Microsoft Teams のルームを起動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d496c-163">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="d496c-164">電源管理-\> AC 電源、10分後に画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="d496c-164">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="d496c-165">電源管理-\> AC で、システムをスリープ状態にしない</span><span class="sxs-lookup"><span data-stu-id="d496c-165">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="d496c-166">Microsoft Teams の会議機能を有効にして、添付されたディスプレイをオフにし、自動的にスリープ状態を解除する</span><span class="sxs-lookup"><span data-stu-id="d496c-166">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="d496c-167">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="d496c-167">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="d496c-168">または、ローカルアカウントのパスワードの有効期限を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d496c-168">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="d496c-169">そうしないと、有効期限が切れたパスワードについて、Skype アカウントがログオンに失敗することになります。</span><span class="sxs-lookup"><span data-stu-id="d496c-169">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="d496c-170">これは、マシン上のすべてのローカルアカウントに影響を与えるため、これを設定しないと、そのボックスの管理者アカウントも最終的に有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="d496c-170">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="d496c-171">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="d496c-171">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="d496c-172">グループポリシーを使用してファイルを転送する方法については[、「ファイルを構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)する」をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d496c-172">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="d496c-173">Microsoft Teams の会議室デバイスが次のバージョンの Windows 10 OS と互換性がある場合、デバイスは Windows Update 経由で次のバージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-173">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="d496c-174">Microsoft Teams 室のデバイスは、手動で、または「Windows Update for Business (WUFB) グループポリシーを有効にする」を使用して手動でアップグレードしないでください。受信する更新プログラムの Windows の準備レベルを選択する機能の更新プログラムは、GPO を通じて受信されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-174">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="d496c-175">これらのグループポリシーが有効になっているデバイスでは、Microsoft Teams の会議アプリでの Windows 10 OS 更新プログラムで問題が発生することがわかっています。</span><span class="sxs-lookup"><span data-stu-id="d496c-175">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="d496c-176">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="d496c-176">Remote Management using PowerShell</span></span>
<span data-ttu-id="d496c-177"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-177"></span></span>

<span data-ttu-id="d496c-178">PowerShell を使用して、次の管理操作をリモートで実行できます (スクリプトサンプルについては、以下の表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="d496c-178">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="d496c-179">接続されているデバイスの取得</span><span class="sxs-lookup"><span data-stu-id="d496c-179">Get attached devices</span></span>
- <span data-ttu-id="d496c-180">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="d496c-180">Get app status</span></span>
- <span data-ttu-id="d496c-181">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="d496c-181">Get system info</span></span>
- <span data-ttu-id="d496c-182">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="d496c-182">Reboot system</span></span>
- <span data-ttu-id="d496c-183">ログの取得</span><span class="sxs-lookup"><span data-stu-id="d496c-183">Retrieve logs</span></span>
- <span data-ttu-id="d496c-184">ファイルを転送する (ドメインに参加している Microsoft Teams ルームが必要)</span><span class="sxs-lookup"><span data-stu-id="d496c-184">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="d496c-185">既定では、この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="d496c-185">This functionality is off by default.</span></span> <span data-ttu-id="d496c-186">以下の操作を実行するには、Microsoft Teams のルームシステムの環境に対してリモート PowerShell を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-186">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="d496c-187">リモート PowerShell を有効にする方法については、「 **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d496c-187">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="d496c-188">たとえば、次のようにリモート PowerShell を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d496c-188">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="d496c-189">Microsoft Teams の会議室のデバイスで、管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="d496c-189">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="d496c-190">管理者特権の PowerShell コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d496c-190">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="d496c-191">次のコマンドを入力します。Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="d496c-191">Enter the following command: Enable-PSRemoting -force</span></span>

<span data-ttu-id="d496c-192">管理操作を実行するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d496c-192">To perform a management operation:</span></span>
  
1. <span data-ttu-id="d496c-193">Microsoft Teams 室のデバイスで PowerShell コマンドを実行する権限を持つ、アカウントの資格情報を使って PC にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d496c-193">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="d496c-194">PC で通常の PowerShell コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d496c-194">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="d496c-195">次の表からコマンドテキストをコピーし、メッセージに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d496c-195">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="d496c-196">使用`<Device fqdn>`している環境に適した FQDN 値をフィールドに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d496c-196">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="d496c-197">\* \<Path\> \*を、マスター skypesettings (またはテーマの画像) のファイル名とローカルパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d496c-197">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="d496c-198">接続されているデバイスを取得するには</span><span class="sxs-lookup"><span data-stu-id="d496c-198">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="d496c-199">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="d496c-199">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="d496c-200">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="d496c-200">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="d496c-201">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="d496c-201">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="d496c-202">ログの取得</span><span class="sxs-lookup"><span data-stu-id="d496c-202">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="d496c-203">XML 構成ファイル (またはテーマグラフィック) をプッシュする</span><span class="sxs-lookup"><span data-stu-id="d496c-203">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="d496c-204">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="d496c-204">Software updates</span></span>
<span data-ttu-id="d496c-205"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-205"></span></span>

<span data-ttu-id="d496c-206">既定では、Microsoft Teams の会議は、Microsoft Teams ルームソフトウェアの最新バージョンを取得するために Windows ストアに接続しようとします。そのため、デバイスでは、通常のインターネットアクセスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d496c-206">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="d496c-207">サポートの問題が発生した場合は、Microsoft Teams の会議室のデバイスが最新バージョンのアプリと共に読み込まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d496c-207">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="d496c-208">既定では、Microsoft Teams のルームは Windows Update に接続して、オペレーティングシステムと USB 周辺機器のファームウェア更新プログラムを取得し、構成された勤務時間外にインストールします。</span><span class="sxs-lookup"><span data-stu-id="d496c-208">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="d496c-209">営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d496c-209">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="d496c-210">更新プログラムを手動で管理する必要があるが、一般[法人向け Microsoft Store](https://businessstore.microsoft.com/store)の通常の手順に従って[オフラインアプリの配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)を行うことができない場合は、適切な APPX ファイルと依存関係を[展開キット](https://go.microsoft.com/fwlink/?linkid=851168)から入手できます (fromSCCM で使用できる[Microsoft Teams のルーム本体を構成](console.md)する手順)。</span><span class="sxs-lookup"><span data-stu-id="d496c-210">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="d496c-211">展開キットのリリースがストアのリリースよりも遅れているため、常に最新のビルドと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-211">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="d496c-212">Powershell を使用して更新するには</span><span class="sxs-lookup"><span data-stu-id="d496c-212">To update using Powershell</span></span>

1. <span data-ttu-id="d496c-213">インストール[MSI](https://go.microsoft.com/fwlink/?linkid=851168)からデバイスがアクセスできる共有にパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d496c-213">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="d496c-214">次のスクリプトを実行して、Microsoft Teams の会議\<室\>のデバイスをターゲットにし、必要に応じて共有をデバイス共有に変更します。</span><span class="sxs-lookup"><span data-stu-id="d496c-214">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="d496c-215">管理者モードとデバイス管理</span><span class="sxs-lookup"><span data-stu-id="d496c-215">Admin mode and device management</span></span>
<span data-ttu-id="d496c-216"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-216"></span></span>

<span data-ttu-id="d496c-217">プライベート CA 証明書を手動でインストールするなどの一部の管理機能には、Surface Pro デバイスを管理モードで配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-217">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="d496c-218">Microsoft Teams のルームアプリが実行されているときに、管理モードに切り替えて戻る</span><span class="sxs-lookup"><span data-stu-id="d496c-218">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="d496c-219">進行中の通話を切断して、ホーム画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="d496c-219">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="d496c-220">歯車アイコンを選択し、メニューを開きます (オプションは [**設定**]、[**アクセシビリティ**]、[**デバイスの再起動**])。</span><span class="sxs-lookup"><span data-stu-id="d496c-220">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="d496c-221">[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d496c-221">Select **Settings**.</span></span>
4. <span data-ttu-id="d496c-222">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d496c-222">Enter the Administrator Password.</span></span> <span data-ttu-id="d496c-223">セットアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-223">The Setup screen will appear.</span></span>  <span data-ttu-id="d496c-224">デバイスがドメインに参加していない場合は、ローカルの管理者アカウント (ユーザー名 "管理者") が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-224">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="d496c-225">このアカウントの既定のパスワードは "sfb" で、できるだけ早くパスワードを変更してください。</span><span class="sxs-lookup"><span data-stu-id="d496c-225">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="d496c-226">コンピューターがドメインに参加している場合は、適切な権限を持つドメインアカウントでサインインできます。</span><span class="sxs-lookup"><span data-stu-id="d496c-226">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="d496c-227">左側の列で、[ **Windows の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d496c-227">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="d496c-228">[**管理サインインに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d496c-228">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="d496c-229">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d496c-229">Enter the Administrator Password.</span></span> <span data-ttu-id="d496c-230">これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d496c-230">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="d496c-231">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="d496c-231">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="d496c-232">デバイスを管理するために必要な権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="d496c-232">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="d496c-233">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d496c-233">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="d496c-234">管理者アカウントからサイン アウトします。</span><span class="sxs-lookup"><span data-stu-id="d496c-234">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="d496c-235">画面左側のユーザーアカウントアイコンを選択し、[ **Skype**] を選択して、Microsoft Teams のルームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d496c-235">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="d496c-236">**Skype**ユーザーが表示されていない場合は、[**他のユーザー** ] を選択し、ユーザー名として「 **.\skype** 」と入力して、サインインしなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-236">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="d496c-237">これで本体が通常の操作モードに戻ります。次の手順では、デバイスがまだ接続されていない場合は、そのデバイスにキーボードをアタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-237">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="d496c-238">Microsoft Teams の会議アプリがクラッシュしたときに、管理モードに切り替えて戻る</span><span class="sxs-lookup"><span data-stu-id="d496c-238">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="d496c-239">Windows キーを 5 回連続で、素早く押します。</span><span class="sxs-lookup"><span data-stu-id="d496c-239">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="d496c-240">これによって、Windows のログオン画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="d496c-240">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="d496c-241">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="d496c-241">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="d496c-242">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d496c-242">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="d496c-243">完了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d496c-243">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d496c-244">この方法では、Skype ユーザをログオフしたり、アプリを正常に終了したりすることはありませんが、アプリが応答しなくなった場合や、その他の方法が利用できない場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d496c-244">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="d496c-245">本体は、Microsoft Teams のルームアプリを実行して、通常の操作モードで再起動します。</span><span class="sxs-lookup"><span data-stu-id="d496c-245">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="d496c-246">この手順を実行できるように設定されている場合は、キーボードを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d496c-246">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="d496c-247">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="d496c-247">Troubleshooting tips</span></span>
   <span data-ttu-id="d496c-248"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="d496c-248"></span></span>

- <span data-ttu-id="d496c-249">会議の出席依頼は、(2 つの会社間など) ドメインの境界を越えて送信された場合には表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-249">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="d496c-250">このような場合、IT 管理者は、外部ユーザーによる会議のスケジュールを許可するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d496c-250">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="d496c-251">Microsoft Teams のルームは、Exchange 2010 経由の Exchange 自動検出リダイレクトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d496c-251">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="d496c-252">一般的に、IT 管理者が使用する必要のないオーディオエンドポイントを無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d496c-252">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="d496c-253">ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。</span><span class="sxs-lookup"><span data-stu-id="d496c-253">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="d496c-254">コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="d496c-254">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="d496c-255">このような場合、Microsoft Teams のルームシステムを再起動すると、問題が解決されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d496c-255">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="d496c-256">有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="d496c-256">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="d496c-257">このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="d496c-257">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
