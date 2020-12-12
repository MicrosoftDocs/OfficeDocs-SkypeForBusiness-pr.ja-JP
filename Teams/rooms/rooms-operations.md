---
title: Microsoft Teams Rooms のメンテナンスと運用
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: このトピックでは、Skype Room Systems の後継である Microsoft Teams Roomsの管理について説明します。
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662462"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="bfa40-103">Microsoft Teams Rooms のメンテナンスと運用</span><span class="sxs-lookup"><span data-stu-id="bfa40-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="bfa40-104">このトピックでは、Skype Room Systems の後継である Microsoft Teams Roomsの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="bfa40-105">Microsoft Teams Roomsは、Microsoft の最新の会議ソリューションで、既存の会議室を機能豊富で共同作業に適したエクスペリエンスに変えられるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="bfa40-106">ユーザーは慣れ親しんだ Microsoft Teams または Skype for Business のインターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="bfa40-107">Microsoft Teams Roomsは、簡単にインストールして Microsoft Teams または Skype for Business を会議室に導入できるように、LCD パネルなどの既存の装置を使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="bfa40-108">「[Azure Monitor を使用して Microsoft Teams Roomsの管理を計画する](azure-monitor-plan.md)」、「[Azure Monitor を使用して Microsoft Teams Roomsの管理を展開する](azure-monitor-deploy.md)」、「[Azure Monitor を使用して Microsoft Teams Roomsのデバイスを管理する](azure-monitor-deploy.md)」で説明されているように、追加の構成を行えば Microsoft Azure Monitor を使用してリモート管理を行うことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="bfa40-109">[XML 構成ファイルを使用して、リモートで Microsoft Teams Roomsのコンソール設定を管理する](xml-config-file.md)こともできます。これには、カスタムの画面テーマの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="bfa40-110">Microsoft Teams Roomsでログを収集する</span><span class="sxs-lookup"><span data-stu-id="bfa40-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="bfa40-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="bfa40-112">ログを収集するには、Microsoft Teams Rooms アプリに付属のログ収集スクリプトを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="bfa40-113">管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="bfa40-114">ログは ZIP ファイルとして c:\rigel に出力されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="bfa40-115">前面の会議室ディスプレイの設定</span><span class="sxs-lookup"><span data-stu-id="bfa40-115">Front of Room Display Settings</span></span>
<span data-ttu-id="bfa40-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-116"><a name="Display"> </a></span></span>

<span data-ttu-id="bfa40-117">会議室ディスプレイのフロントカメラを拡張モードに設定します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="bfa40-118">この操作により、ディスプレイの電源を入れ替えたときにディスプレイ上にコンソール UI が重複しません。</span><span class="sxs-lookup"><span data-stu-id="bfa40-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfa40-119">ルームの前方ディスプレイを、ソースがスタンバイ モードから復帰したときにアクティブなビデオ ソース (MTR コンソールなど) に自動的に切り替える場合は、特定の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="bfa40-120">この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams Rooms ソフトウェアによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="bfa40-121">ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="bfa40-122">選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、Crestron 社の [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) や Extron 社の [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのコントローラーが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="bfa40-123">Microsoft Teams Rooms のリセット (工場出荷時の復元)</span><span class="sxs-lookup"><span data-stu-id="bfa40-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="bfa40-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="bfa40-125">Microsoft Teams Roomsが正常に動作していない場合は、出荷時の設定にリセットしてみてください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="bfa40-126">これを行うには、[Microsoft Teams Room 回復ツール](recovery-tool.md)を使用して、工場出荷時復元の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bfa40-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bfa40-127">Windows を初期状態に戻すプロセス中に、**[個人用ファイルを保持する - アプリと設定を削除しますが、個人用ファイルは保持します]** オプションが選択されている場合、Microsoft Teams Roomsが使用できなくなる可能性があるという既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="bfa40-128">このオプションは使用 *しない* でください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="bfa40-129">サポートされているリモート オプション</span><span class="sxs-lookup"><span data-stu-id="bfa40-129">Supported Remote Options</span></span>
<span data-ttu-id="bfa40-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="bfa40-131">次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="bfa40-132">ワークグループ</span><span class="sxs-lookup"><span data-stu-id="bfa40-132">Workgroup</span></span>|<span data-ttu-id="bfa40-133">ドメインに参加していない場合</span><span class="sxs-lookup"><span data-stu-id="bfa40-133">Not domain joined</span></span>|<span data-ttu-id="bfa40-134">ドメインに参加している場合</span><span class="sxs-lookup"><span data-stu-id="bfa40-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bfa40-135">再起動</span><span class="sxs-lookup"><span data-stu-id="bfa40-135">Restart</span></span>  <br/> |<span data-ttu-id="bfa40-136">リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="bfa40-136">Remote desktop</span></span>  <br/> <span data-ttu-id="bfa40-137">リモート Powershell</span><span class="sxs-lookup"><span data-stu-id="bfa40-137">Remote Powershell</span></span>  <br/> |<span data-ttu-id="bfa40-138">リモート デスクトップ (詳細な設定が必要)</span><span class="sxs-lookup"><span data-stu-id="bfa40-138">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="bfa40-139">リモート PowerShell (詳細な設定が必要)</span><span class="sxs-lookup"><span data-stu-id="bfa40-139">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="bfa40-140">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfa40-140">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="bfa40-141">OS の更新</span><span class="sxs-lookup"><span data-stu-id="bfa40-141">Update OS</span></span>  <br/> |<span data-ttu-id="bfa40-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="bfa40-142">Windows Update</span></span>  <br/> |<span data-ttu-id="bfa40-143">Windows Update</span><span class="sxs-lookup"><span data-stu-id="bfa40-143">Windows Update</span></span>  <br/> <span data-ttu-id="bfa40-144">WSUS</span><span class="sxs-lookup"><span data-stu-id="bfa40-144">WSUS</span></span>  <br/> |
|<span data-ttu-id="bfa40-145">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="bfa40-145">App update</span></span>  <br/> |<span data-ttu-id="bfa40-146">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="bfa40-146">Windows Store</span></span>  <br/> |<span data-ttu-id="bfa40-147">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="bfa40-147">Windows Store</span></span>  <br/> <span data-ttu-id="bfa40-148">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bfa40-148">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="bfa40-149">Skype アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="bfa40-149">Skype Account Config</span></span>  <br/> |<span data-ttu-id="bfa40-150">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="bfa40-150">Not currently supported</span></span>  <br/> |<span data-ttu-id="bfa40-151">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="bfa40-151">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="bfa40-152">ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="bfa40-152">Access logs</span></span>  <br/> |<span data-ttu-id="bfa40-153">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="bfa40-153">Not currently supported</span></span>  <br/> |<span data-ttu-id="bfa40-154">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="bfa40-154">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="bfa40-155">Microsoft Teams Rooms のグループ ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="bfa40-155">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="bfa40-156"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-156"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="bfa40-157">このセクションでは、Microsoft Teams Rooms が正常に機能するために依存するシステム設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-157">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="bfa40-158">Microsoft Teams Rooms をドメインに加えるときには、グループ ポリシーによって次の表の設定が上書きされないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-158">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="bfa40-159">設定</span><span class="sxs-lookup"><span data-stu-id="bfa40-159">Setting</span></span>|<span data-ttu-id="bfa40-160">許可されること</span><span class="sxs-lookup"><span data-stu-id="bfa40-160">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfa40-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="bfa40-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="bfa40-162">Microsoft Teams Rooms の起動を有効にする</span><span class="sxs-lookup"><span data-stu-id="bfa40-162">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="bfa40-163">電源管理 -\> AC で、10 分後に画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="bfa40-163">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="bfa40-164">電源管理 -\> AC で、システムをスリープさせない</span><span class="sxs-lookup"><span data-stu-id="bfa40-164">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="bfa40-165">接続されているディスプレイをオフにし、自動的にウェイク アップさせるように Microsoft Teams Rooms を有効化する</span><span class="sxs-lookup"><span data-stu-id="bfa40-165">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="bfa40-166">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="bfa40-166">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="bfa40-167">これは、ローカル アカウントでパスワードの有効期限を無効にすることに相当します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-167">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="bfa40-168">この操作を行わないと、最終的に Skype アカウントがログオンできなくなり、パスワードの有効期限が切れているという通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-168">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="bfa40-169">これは、コンピューター上のすべてのローカル アカウントに影響を与えるため、設定に失敗すると、ボックスの管理者アカウントも最終的に有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-169">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="bfa40-170">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="bfa40-170">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="bfa40-171">グループ ポリシーを使用してファイルを転送する方法については、「[ファイルの項目を構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-171">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="bfa40-172">Microsoft Teams Rooms のデバイスが Windows 10 OS の次回のバージョンと互換性がある場合、Windows Update により、デバイスは次回のバージョンに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-172">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="bfa40-173">Microsoft Teams Rooms のデバイスでは、Windows 10 の次回のリリースに手動でアップグレードしたり、GPO を介して Windows Update for Business (WUFB) グループ ポリシーの [受信する更新プログラムの Windows 準備レベルを選択する] と [プレビュー ビルドと機能更新プログラムを受信するタイミングを選択する] を有効にしたりしないでください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-173">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="bfa40-174">これらのグループ ポリシーが有効になっているデバイスでは、Microsoft Teams Rooms アプリによる Windows 10 OS 更新プログラムの問題が発生することがわかっています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-174">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="bfa40-175">PowerShell を使ったリモート管理</span><span class="sxs-lookup"><span data-stu-id="bfa40-175">Remote Management using PowerShell</span></span>
<span data-ttu-id="bfa40-176"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-176"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="bfa40-177">PowerShell を使用して、次の管理操作をリモートで実行できます (スクリプトのサンプルについては下記の表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bfa40-177">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="bfa40-178">接続されているデバイスの取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-178">Get attached devices</span></span>
- <span data-ttu-id="bfa40-179">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-179">Get app status</span></span>
- <span data-ttu-id="bfa40-180">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-180">Get system info</span></span>
- <span data-ttu-id="bfa40-181">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="bfa40-181">Reboot system</span></span>
- <span data-ttu-id="bfa40-182">ログの取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-182">Retrieve logs</span></span>
- <span data-ttu-id="bfa40-183">ファイルの転送 (ドメインに参加済み Microsoft Teams Rooms が必要)</span><span class="sxs-lookup"><span data-stu-id="bfa40-183">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="bfa40-184">この機能は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-184">This functionality is off by default.</span></span> <span data-ttu-id="bfa40-185">次に示す操作を実行するには、Microsoft Teams Rooms システムの環境でリモート PowerShell を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-185">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="bfa40-186">リモート PowerShell を有効にする方法の詳細については、**[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-186">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="bfa40-187">たとえば、次のようにしてリモート PowerShell を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-187">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="bfa40-188">Microsoft Teams Rooms のデバイスで、管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-188">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="bfa40-189">管理者特権で PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-189">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="bfa40-190">次のコマンドを入力します: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span><span class="sxs-lookup"><span data-stu-id="bfa40-190">Enter the following command: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span></span>
4. <span data-ttu-id="bfa40-191">ローカル セキュリティ ポリシーを開き、*[管理者]* セキュリティ グループを **[セキュリティの設定]** > **[ローカル ポリシー]** > **[ユーザー権利の割り当て]** > **[ネットワーク経由でコンピューターへアクセス]** に追加します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-191">Open the Local Security Policy and add the *Administrators* security group to **Security Settings** > **Local Policies** > **User Rights Assignment** > **Access this computer from the network**.</span></span>

<span data-ttu-id="bfa40-192">管理操作を実行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-192">To perform a management operation:</span></span>
  
1. <span data-ttu-id="bfa40-193">Microsoft Teams Rooms のデバイスで PowerShell コマンドを実行する権限を持つアカウントの資格情報を使用して PC にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-193">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="bfa40-194">PC で通常の PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-194">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="bfa40-195">次の表からコマンド テキストをコピーして、プロンプトに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-195">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="bfa40-196">お使いの環境に応じた適切な FQDN 値で `<Device fqdn>` フィールドを置換します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-196">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="bfa40-197">*\<path\>* をマスター SkypeSettings.xml 構成ファイル (またはテーマの画像) のファイル名とローカル パスで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-197">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="bfa40-198">接続されているデバイスを取得する場合</span><span class="sxs-lookup"><span data-stu-id="bfa40-198">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="bfa40-199">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-199">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="bfa40-200">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-200">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="bfa40-201">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="bfa40-201">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="bfa40-202">ログの取得</span><span class="sxs-lookup"><span data-stu-id="bfa40-202">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="bfa40-203">XML 構成ファイル (またはテーマのグラフィック) をプッシュする</span><span class="sxs-lookup"><span data-stu-id="bfa40-203">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="bfa40-204">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="bfa40-204">Software updates</span></span>
<span data-ttu-id="bfa40-205"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-205"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="bfa40-206">既定では、Microsoft Teams Roomsは Windows ストアに接続して、Microsoft Teams Rooms ソフトウェアの最新バージョンを入手しようとするため、デバイスは正常なインターネット アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-206">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="bfa40-207">サポートの問題について Microsoft に問い合わせる前に、Microsoft Teams Rooms のデバイスに最新バージョンのアプリが読み込まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-207">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="bfa40-208">既定では、Microsoft Teams Rooms は Windows Update に接続してオペレーティング システムと USB 周辺機器のファームウェアの更新プログラムを取得し、設定された業務時間外にインストールします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-208">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="bfa40-209">管理者アカウントにサインインし、設定アプリを実行して、業務時間を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-209">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="bfa40-210">更新を手動で管理するときに、[オフライン アプリの配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)を行うために、[ビジネス向け Microsoft Store](https://businessstore.microsoft.com/store) の通常の手順を実行できない場合は、[デプロイメント キット](https://go.microsoft.com/fwlink/?linkid=851168) ([Microsoft Teams Rooms コンソールの構成](console.md)を行うための操作指示に含まれる) から、Configuration Manager で使用できる適切な APPX ファイルと依存関係を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-210">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="bfa40-211">デプロイメント キットのリリースは、ストアのリリースよりも後になるため、最新の入手可能な最新ビルドに必ずしも一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-211">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="bfa40-212">PowerShell を使用して更新する場合</span><span class="sxs-lookup"><span data-stu-id="bfa40-212">To update using Powershell</span></span>

1. <span data-ttu-id="bfa40-213">インストール [MSI](https://go.microsoft.com/fwlink/?linkid=851168) から、デバイスがアクセスできる共有先にパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-213">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="bfa40-214">Microsoft Teams Rooms のデバイスを対象に次のスクリプトを実行します \<share\> は、該当するデバイス共有に変更します)。</span><span class="sxs-lookup"><span data-stu-id="bfa40-214">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="bfa40-215">管理者モードおよびデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="bfa40-215">Admin mode and device management</span></span>
<span data-ttu-id="bfa40-216"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-216"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="bfa40-217">プライベート CA 証明書の手動によるインストールのような一部の管理機能では、Surface Pro デバイスを管理者モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-217">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="bfa40-218">管理者モードに切り替え、Microsoft Teams Rooms アプリが実行されたら元に戻す</span><span class="sxs-lookup"><span data-stu-id="bfa40-218">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="bfa40-219">現在の通話を切って、ホーム画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-219">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="bfa40-220">歯車アイコンをクリックすると、メニューが表示されます (オプションは、**[設定]**、**[アクセシビリティ]**、**[デバイスを再起動]** です)。</span><span class="sxs-lookup"><span data-stu-id="bfa40-220">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="bfa40-221">**[設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-221">Select **Settings**.</span></span>
4. <span data-ttu-id="bfa40-222">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-222">Enter the Administrator Password.</span></span> <span data-ttu-id="bfa40-223">設定画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-223">The Setup screen will appear.</span></span>  <span data-ttu-id="bfa40-224">デバイスがドメインに参加していない場合、既定によりローカルの管理者アカウント (ユーザー名「Admin」) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-224">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="bfa40-225">このアカウントの既定のパスワードは 'sfb' です。できるだけ早くパスワードを変更してください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-225">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="bfa40-226">コンピューターがドメインに参加済みの場合、適切な権限のドメイン アカウントでサインインできます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-226">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="bfa40-227">左側の列で **[Windows の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-227">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="bfa40-228">[**管理サインインに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-228">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="bfa40-229">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-229">Enter the Administrator Password.</span></span> <span data-ttu-id="bfa40-230">これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-230">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="bfa40-231">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-231">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="bfa40-232">デバイスの管理に必要な権限を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-232">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="bfa40-233">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-233">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="bfa40-234">管理者アカウントからサイン アウトします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-234">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="bfa40-235">画面の左端にある [ユーザー アカウント] アイコンを選択し、**[Skype]** を選択して、Microsoft Teams Rooms に戻ります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-235">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="bfa40-236">**[Skype]** ユーザーがリストに表示されていない場合、**[他のユーザー]** を選択してからユーザー名として **.\skype** と入力し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-236">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="bfa40-237">コンソールは通常の操作モードに戻ります。次の手順では、デバイスにキーボードが接続されていない場合は接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-237">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="bfa40-238">管理者モードに切り替え、Microsoft Teams Rooms アプリがクラッシュしたら元に戻す</span><span class="sxs-lookup"><span data-stu-id="bfa40-238">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="bfa40-239">Windows キーを 5 回連続で、素早く押します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-239">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="bfa40-240">これによって、Windows のログオン画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-240">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="bfa40-241">管理者の資格情報を使用してデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-241">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="bfa40-242">必要な管理上のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-242">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="bfa40-243">終了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bfa40-243">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfa40-244">この方法は、Skype ユーザーをログオフさせたり、アプリを正常終了させることはありませんが、アプリが応答しない場合や、その他の方法が使用できない場合にのみ使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bfa40-244">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="bfa40-245">コンソールは通常の操作モードで再起動され、Microsoft Teams Rooms アプリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-245">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="bfa40-246">この手順を実行するためにキーボードが接続されていた場合は、取り外すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-246">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="bfa40-247">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="bfa40-247">Troubleshooting tips</span></span>
   <span data-ttu-id="bfa40-248"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="bfa40-248"><a name="TS"> </a></span></span>

- <span data-ttu-id="bfa40-249">会議の招待状は、ドメイン境界 (たとえば、2 つの会社間) を越えて送信すると表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-249">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="bfa40-250">このような場合、IT 管理者は外部ユーザーに対して会議のスケジュール設定を許可するかどうか決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-250">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="bfa40-251">Microsoft Teams Rooms では、Exchange 2010 経由での Exchange 自動検出リダイレクトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bfa40-251">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="bfa40-252">一般に、使用しないオーディオ エンドポイントを無効にするよう IT 管理者にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bfa40-252">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="bfa40-253">ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-253">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="bfa40-254">コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-254">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="bfa40-255">このような場合は、Microsoft Teams Rooms システムを再起動することで問題を解決できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfa40-255">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="bfa40-256">有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="bfa40-256">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="bfa40-257">このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="bfa40-257">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
