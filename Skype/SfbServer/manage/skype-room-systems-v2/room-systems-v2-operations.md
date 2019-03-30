---
title: マイクロソフト チームの会議室のメンテナンスと運用
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Skype ルーム システムの次世代をマイクロソフト チームの会議室の管理の詳細については、このトピックを参照してください。
ms.openlocfilehash: 907abcbe07e52369aefa5065a359f0a3769b20c5
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013044"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="f8e20-103">マイクロソフト チームの会議室のメンテナンスと運用</span><span class="sxs-lookup"><span data-stu-id="f8e20-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="f8e20-104">Skype ルーム システムの次世代をマイクロソフト チームの会議室の管理の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8e20-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="f8e20-105">マイクロソフト チームのルームは、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="f8e20-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="f8e20-106">ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="f8e20-107">マイクロソフト チームの会議室は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="f8e20-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="f8e20-108">リモート管理は、 [Azure のモニターを使用して Microsoft チームの部屋の計画の管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md)、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](../../deploy/deploy-clients/azure-monitor.md)、[管理の説明に従って、Microsoft Azure のモニターを使用して、追加の構成Azure のモニターを使用して Microsoft チーム室デバイス](azure-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e20-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor.md).</span></span> <span data-ttu-id="f8e20-109">また、[マイクロソフト チームのルームの管理コンソールの XML 構成ファイルでリモートでの設定](xml-config-file.md)、ユーザー設定の表示テーマを適用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="f8e20-110">マイクロソフト チームの会議室のログの収集</span><span class="sxs-lookup"><span data-stu-id="f8e20-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="f8e20-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-111"></span></span>

<span data-ttu-id="f8e20-112">ログを収集するには、マイクロソフト チームの会議室のアプリケーションに付属しているログ収集スクリプトを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="f8e20-113">管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="f8e20-114">ログは ZIP ファイルとして c:\rigel に出力されます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="f8e20-115">前面の会議室ディスプレイの設定</span><span class="sxs-lookup"><span data-stu-id="f8e20-115">Front of Room Display Settings</span></span>
<span data-ttu-id="f8e20-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-116"></span></span>

<span data-ttu-id="f8e20-117">前面の会議室ディスプレイを拡張モードに構成します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="f8e20-118">これが必ず、コンソールを表示するには、ディスプレイの電源を入れ直すと、UI は複製されません。</span><span class="sxs-lookup"><span data-stu-id="f8e20-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8e20-p105">屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。</span><span class="sxs-lookup"><span data-stu-id="f8e20-p105">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="f8e20-121">マイクロソフト チームの会議室のリセット (工場出荷時復元)</span><span class="sxs-lookup"><span data-stu-id="f8e20-121">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="f8e20-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-122"></span></span>

<span data-ttu-id="f8e20-123">マイクロソフト チームの会議室がうまく実行されていない、工場出荷時リセットを実行することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-123">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="f8e20-124">これで**この PC をリセット**するの下にある [**回復**] タブの [アプリケーションの設定を行うを選択**を開始**し、**すべて削除します。**</span><span class="sxs-lookup"><span data-stu-id="f8e20-124">This can be done in the Settings app on the **Recovery** tab. Beneath **Reset this PC**, select **Get started**, and then **Remove everything**.</span></span> <span data-ttu-id="f8e20-125">デバイスをリセットするのには、画面の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="f8e20-125">Follow the remaining prompts to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8e20-126">場所マイクロソフト チームの会議室が使用できなくなる場合 Windows のリセット処理中に、**アプリの削除と設定のファイルを保存、個人用ファイルを保持**] オプションが選択されている既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-126">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="f8e20-127">操作を行います_しない_このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-127">Do _not_ use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="f8e20-128">サポートされるリモート オプション</span><span class="sxs-lookup"><span data-stu-id="f8e20-128">Supported Remote Options</span></span>
<span data-ttu-id="f8e20-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-129"></span></span>

<span data-ttu-id="f8e20-130">次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="f8e20-131">\*\*ワークグループ \*\*</span><span class="sxs-lookup"><span data-stu-id="f8e20-131">**Workgroup**</span></span>|<span data-ttu-id="f8e20-132">**ドメインに参加していない場合**</span><span class="sxs-lookup"><span data-stu-id="f8e20-132">**Not domain joined**</span></span>|<span data-ttu-id="f8e20-133">**ドメインに参加している場合**</span><span class="sxs-lookup"><span data-stu-id="f8e20-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f8e20-134">再起動</span><span class="sxs-lookup"><span data-stu-id="f8e20-134">Restart</span></span>  <br/> |<span data-ttu-id="f8e20-135">リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="f8e20-135">Remote desktop</span></span>  <br/> <span data-ttu-id="f8e20-136">リモート Powershell</span><span class="sxs-lookup"><span data-stu-id="f8e20-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="f8e20-137">(さらに設定する必要があります)、リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="f8e20-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="f8e20-138">リモート Powershell を (さらに設定する必要があります)</span><span class="sxs-lookup"><span data-stu-id="f8e20-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="f8e20-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="f8e20-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="f8e20-140">OS の更新</span><span class="sxs-lookup"><span data-stu-id="f8e20-140">Update OS</span></span>  <br/> |<span data-ttu-id="f8e20-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="f8e20-141">Windows Update</span></span>  <br/> |<span data-ttu-id="f8e20-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="f8e20-142">Windows Update</span></span>  <br/> <span data-ttu-id="f8e20-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="f8e20-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="f8e20-144">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="f8e20-144">App update</span></span>  <br/> |<span data-ttu-id="f8e20-145">	Windows ストア</span><span class="sxs-lookup"><span data-stu-id="f8e20-145">Windows Store</span></span>  <br/> |<span data-ttu-id="f8e20-146">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="f8e20-146">Windows Store</span></span>  <br/> <span data-ttu-id="f8e20-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="f8e20-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="f8e20-148">Skype アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="f8e20-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="f8e20-149">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f8e20-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="f8e20-150">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f8e20-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="f8e20-151">ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="f8e20-151">Access logs</span></span>  <br/> |<span data-ttu-id="f8e20-152">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f8e20-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="f8e20-153">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f8e20-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="f8e20-154">マイクロソフト チームの会議室のグループ ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-154">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="f8e20-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-155"></span></span>

<span data-ttu-id="f8e20-156">このセクションでは、マイクロソフト チームの会議室が正しく機能するために依存しているシステムの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-156">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="f8e20-157">マイクロソフト チームの会議室をドメインに参加させるときは、グループ ポリシーが次の表の設定を上書きしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-157">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="f8e20-158">**設定**</span><span class="sxs-lookup"><span data-stu-id="f8e20-158">**Setting**</span></span>|<span data-ttu-id="f8e20-159">**により、**</span><span class="sxs-lookup"><span data-stu-id="f8e20-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8e20-160">HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="f8e20-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="f8e20-161">起動するように、マイクロソフト チームの会議室を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-161">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="f8e20-162">電源管理 -\> AC、画面をオフに 10 分後</span><span class="sxs-lookup"><span data-stu-id="f8e20-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="f8e20-163">電源管理 -\> Ac システムをスリープ状態を配置しません。</span><span class="sxs-lookup"><span data-stu-id="f8e20-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="f8e20-164">マイクロソフト チームの部屋に接続されている表示をオフにして、自動的にスリープを有効に</span><span class="sxs-lookup"><span data-stu-id="f8e20-164">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="f8e20-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="f8e20-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="f8e20-166">またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="f8e20-167">これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。</span><span class="sxs-lookup"><span data-stu-id="f8e20-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="f8e20-168">したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8e20-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="f8e20-169">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="f8e20-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="f8e20-170">グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)で説明します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="f8e20-171">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="f8e20-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="f8e20-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-172"></span></span>

<span data-ttu-id="f8e20-173">PowerShell を使用して、次の管理操作をリモートで実行することができます (スクリプトのサンプルについては、次の表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f8e20-173">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="f8e20-174">接続されているデバイスの取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-174">Get attached devices</span></span>
    
- <span data-ttu-id="f8e20-175">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-175">Get app status</span></span>
    
- <span data-ttu-id="f8e20-176">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-176">Get system info</span></span>
    
- <span data-ttu-id="f8e20-177">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="f8e20-177">Reboot system</span></span>
    
- <span data-ttu-id="f8e20-178">ログの取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-178">Retrieve logs</span></span>
    
- <span data-ttu-id="f8e20-179">ファイルを転送する (ドメインに参加している Microsoft チーム ルームが必要です)</span><span class="sxs-lookup"><span data-stu-id="f8e20-179">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="f8e20-180">既定では、この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="f8e20-180">This functionality is off by default.</span></span> <span data-ttu-id="f8e20-181">以下の操作を実行するのには、マイクロソフト チームの会議室のシステム環境のリモート PowerShell を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-181">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="f8e20-182">リモート PowerShell を有効にする方法についての情報を**[有効にする PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8e20-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="f8e20-183">たとえば、次のようにリモート PowerShell を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="f8e20-184">マイクロソフト チームの会議室のデバイスに管理者としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-184">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="f8e20-185">管理者特権の PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-185">Open an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="f8e20-186">次のコマンドを入力します。Enable-PSRemoting -force</span><span class="sxs-lookup"><span data-stu-id="f8e20-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="f8e20-187">管理操作を実行するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="f8e20-188">マイクロソフト チームの会議室のデバイスでの PowerShell コマンドを実行する権限を持つアカウントの資格情報で PC にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-188">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
    
2. <span data-ttu-id="f8e20-189">PC の通常の PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-189">Open a regular PowerShell command prompt on the PC.</span></span>
    
3. <span data-ttu-id="f8e20-190">コマンド テキストを次の表からコピーし、プロンプトに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-190">Copy the command text from the table below and paste it at the prompt.</span></span>
    
4. <span data-ttu-id="f8e20-191">交換`<Device fqdn>`FQDN の値を持つフィールドが、環境に対応します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="f8e20-192">交換*\<のパス\>* SkypeSettings.xml 構成ファイルのマスター (またはテーマのイメージ) のローカル パスとファイル名とします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="f8e20-193">接続されているデバイスを取得するには</span><span class="sxs-lookup"><span data-stu-id="f8e20-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="f8e20-194">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="f8e20-195">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="f8e20-196">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="f8e20-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="f8e20-197">ログの取得</span><span class="sxs-lookup"><span data-stu-id="f8e20-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="f8e20-198">XML 構成ファイル (またはテーマのグラフィック) をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-198">Push an XML configuration file (or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="f8e20-199">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="f8e20-199">Software updates</span></span>
<span data-ttu-id="f8e20-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-200"></span></span>

<span data-ttu-id="f8e20-201">既定では、マイクロソフト チームの会議室は、デバイスの通常のインターネット アクセスが必要なので、チームの会議室を Microsoft のソフトウェアの最新バージョンを取得する Windows ストアに接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-201">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="f8e20-202">必ずサポートの問題に関して、マイクロソフトに連絡する前にマイクロソフト チームの会議室のデバイス アプリケーションの最新バージョンがロードされます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-202">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="f8e20-203">既定は、マイクロソフト チームの会議室は、オペレーティング システムを取得するために Windows の更新プログラムと USB 周辺機器のファームウェアの更新に接続し、構成済みの業務時間外をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-203">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="f8e20-204">営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="f8e20-205">APPX の適切なファイルとの[『 導入ガイド 』](https://go.microsoft.com/fwlink/?linkid=851168) (からの依存関係を取得することをした場合、手動で更新プログラムを管理する通常の手順に従って、[ビジネス向けのマイクロソフト ストア](https://businessstore.microsoft.com/store)の[オフライン アプリケーションを配布](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)することはできません。[マイクロソフト チームの会議室のコンソールを構成](../../deploy/deploy-clients/console.md)する方法) と SCCM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="f8e20-206">展開キットのリリースも遅れて、ストアのリリースでは、最新の利用可能なビルドを常に一致可能性がありますように。</span><span class="sxs-lookup"><span data-stu-id="f8e20-206">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="f8e20-207">Powershell を使用して更新するのには</span><span class="sxs-lookup"><span data-stu-id="f8e20-207">To update using Powershell</span></span>

1. <span data-ttu-id="f8e20-208">共有デバイスには、 [MSI](https://go.microsoft.com/fwlink/?linkid=851168)にアクセスできるインストール パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
    
2. <span data-ttu-id="f8e20-209">デバイスの Microsoft チームの会議室の変更を対象とする次のスクリプトを実行\<共有\>デバイスには、必要に応じて共有します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-209">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="f8e20-210">管理者モードとデバイス管理</span><span class="sxs-lookup"><span data-stu-id="f8e20-210">Admin mode and device management</span></span>
<span data-ttu-id="f8e20-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-211"></span></span>

<span data-ttu-id="f8e20-212">プライベート CA 証明書を手動でインストールするように、一部の管理機能は、管理者モードで Surface Pro デバイスを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-212">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="f8e20-213">管理者モードとマイクロソフト チームの会議室のアプリケーションを実行しているときの切り替え</span><span class="sxs-lookup"><span data-stu-id="f8e20-213">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="f8e20-214">進行中の呼び出しを切断し、ホーム画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-214">Hang up any ongoing calls, and return to the home screen.</span></span>
    
2. <span data-ttu-id="f8e20-215">歯車のアイコンを選択し、メニューを表示 (オプションは、**設定**、**ユーザー補助の設定**、および**デバイスの再起動**) します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-215">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="f8e20-216">[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="f8e20-217">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-217">Enter the Administrator Password.</span></span> <span data-ttu-id="f8e20-218">セットアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8e20-219">場合は、デバイスでは、ドメインに参加していない場合は、ローカルの管理者アカウント (ユーザー名"Admin") は、既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-219">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="f8e20-220">このアカウントの既定のパスワードは「sfb」ですが、セキュリティ上の理由により所属する組織によってできるだけ早く変更されることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-220">The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible.</span></span> <span data-ttu-id="f8e20-221">コンピューターがドメインに参加している場合は、適切な特権を持つドメイン アカウントを使用して署名できます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-221">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
  
5. <span data-ttu-id="f8e20-222">左の列には、 **Windows の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-222">Select **Windows Settings** in the left column.</span></span>
    
6. <span data-ttu-id="f8e20-223">[**管理サインインに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="f8e20-224">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-224">Enter the Administrator Password.</span></span> <span data-ttu-id="f8e20-225">これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="f8e20-226">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-226">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="f8e20-227">デバイスを管理するために必要な特権があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-227">You'll have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="f8e20-228">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="f8e20-229">管理者アカウントからサイン アウトします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="f8e20-230">画面の左端にある [ユーザー アカウントのアイコンを選択し、 **Skype**では、マイクロソフト チームの会議室に戻ります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-230">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="f8e20-231">**Skype**ユーザーが一覧にない場合は**他のユーザー**を選択し、入力をする必要があります**です。 \skype**として、ユーザー名、およびサインインします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-231">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="f8e20-232">コンソールは、その通常の操作モードに戻るようになりました。次の手順では、1 つは既に接続されていない場合、デバイスにキーボードを接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="f8e20-233">管理者モードとマイクロソフト チーム ルーム アプリケーションがクラッシュしたときの切り替え</span><span class="sxs-lookup"><span data-stu-id="f8e20-233">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="f8e20-234">Windows キーを 5 回連続で、素早く押します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-234">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="f8e20-235">これによって、Windows のログオン画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-235">This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="f8e20-236">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-236">Log in to the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8e20-237">このメソッドは、Skype ユーザーをログオフまたは、アプリケーションを正常に終了しませんが、場合を使用してアプリケーションが応答していませんでしたし、使用可能なその他の方法がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="f8e20-237">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 
  
3. <span data-ttu-id="f8e20-238">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="f8e20-239">完了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-239">Restart the machine when you're finished.</span></span>
    
   <span data-ttu-id="f8e20-240">コンソールは、マイクロソフト チームの会議室のアプリケーションを実行して、通常の操作モードに再起動します。</span><span class="sxs-lookup"><span data-stu-id="f8e20-240">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="f8e20-241">キーボードを削除するには、この手順を実行するために割り当てられる場合。</span><span class="sxs-lookup"><span data-stu-id="f8e20-241">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="f8e20-242">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="f8e20-242">Troubleshooting tips</span></span>
   <span data-ttu-id="f8e20-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="f8e20-243"></span></span>

- <span data-ttu-id="f8e20-244">会議出席依頼があります (たとえば、2 つの企業では)、ドメインの境界を越えて送信される場合は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f8e20-244">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="f8e20-245">このような場合、IT 管理者は、会議をスケジュールするのには外部のユーザーを許可するかどうかを決める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-245">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="f8e20-246">マイクロソフト チームの会議室には、Exchange 2010 を使用して Exchange の自動検出リダイレクトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f8e20-246">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="f8e20-247">一般は、オーディオ エンドポイントを使用しないことを無効にする IT 管理者のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8e20-247">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
    
- <span data-ttu-id="f8e20-248">ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="f8e20-249">コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="f8e20-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="f8e20-250">このような場合は、マイクロソフト チームの会議室のシステムを再起動することによって問題が解決場合があります。</span><span class="sxs-lookup"><span data-stu-id="f8e20-250">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
    
- <span data-ttu-id="f8e20-251">有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="f8e20-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="f8e20-252">このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="f8e20-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
