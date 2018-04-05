---
title: Skype Room Systems バージョン 2 を管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Skype ルーム システムの次世代を Skype ルーム システム v2 では、管理の詳細については、このトピックを参照してください。
ms.openlocfilehash: 562dbeea19fb732caf9348e2bfd632da3579e71a
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="manage-skype-room-systems-v2"></a><span data-ttu-id="4ee28-103">Skype Room Systems バージョン 2 を管理する</span><span class="sxs-lookup"><span data-stu-id="4ee28-103">Manage Skype Room Systems v2</span></span>
 
<span data-ttu-id="4ee28-104">Skype ルーム システムの次世代を Skype ルーム システム v2 では、管理の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-104">Read this topic to learn about management of Skype Room Systems v2, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="4ee28-105">Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="4ee28-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="4ee28-106">ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="4ee28-107">Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="4ee28-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="4ee28-108">リモート管理は、 [Skype ルーム システムの計画 v2 管理 OMS を使用して](../../plan-your-deployment/clients-and-devices/oms-management.md)、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](../../deploy/deploy-clients/with-oms.md)、および管理の[で説明したように運用管理スイート (OMS) を使用して、追加の構成OMS を使用して Skype ルーム システム v2 のデバイス](oms.md)。</span><span class="sxs-lookup"><span data-stu-id="4ee28-108">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](oms.md).</span></span> <span data-ttu-id="4ee28-109">[Skype ルーム システム v2 の管理コンソールの設定を XML 構成ファイルでリモートから](xml-config-file.md)、カスタムの表示テーマを適用する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="4ee28-109">You may also [Manage a Skype Room Systems v2 console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a><span data-ttu-id="4ee28-110">Skype Room Systems バージョン 2 でのログの収集</span><span class="sxs-lookup"><span data-stu-id="4ee28-110">Collecting logs on Skype Room Systems v2</span></span>
<span data-ttu-id="4ee28-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-111"></span></span>

<span data-ttu-id="4ee28-112">ログを収集するには、Skype ルーム システム v2 のアプリケーションに付属しているログ収集スクリプトを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-112">To collect logs, you must invoke the log collection script that ships with the Skype Room Systems v2 app.</span></span> <span data-ttu-id="4ee28-113">管理者モードで、管理者特権のコマンド プロンプトを開始して、次のコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="4ee28-114">ログは ZIP ファイルとして c:\rigel に出力されます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="4ee28-115">前面の会議室ディスプレイの設定</span><span class="sxs-lookup"><span data-stu-id="4ee28-115">Front of Room Display Settings</span></span>
<span data-ttu-id="4ee28-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-116"></span></span>

<span data-ttu-id="4ee28-117">前面の会議室ディスプレイを拡張モードに構成します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="4ee28-118">この操作により、ディスプレイの電源サイクル時にディスプレイ上にコンソール UI が重複しません。</span><span class="sxs-lookup"><span data-stu-id="4ee28-118">Doing so will ensure that the console UI is not duplicated on that display when power cycling the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ee28-119">屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-119">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="4ee28-120">この機能はすべての TV でサポートされるものではありません。</span><span class="sxs-lookup"><span data-stu-id="4ee28-120">This feature is not supported on all TVs.</span></span> 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a><span data-ttu-id="4ee28-121">Skype Room Systems バージョン 2 のリセット (工場出荷時状態への復元)</span><span class="sxs-lookup"><span data-stu-id="4ee28-121">Skype Room Systems v2 Reset (Factory Restore)</span></span>
<span data-ttu-id="4ee28-122"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-122"></span></span>

<span data-ttu-id="4ee28-123">Skype ルーム システム v2 がうまく実行されていない、工場出荷時リセットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-123">If Skype Room Systems v2 isn't running well, performing a factory reset may help.</span></span> <span data-ttu-id="4ee28-124">これの設定のアプリケーションで、[このコンピューターのリセット」ヘッダーの下に「回復」タブから、選択"開始"の後に「"すべて削除するです。</span><span class="sxs-lookup"><span data-stu-id="4ee28-124">This can be done in the Settings app from the "Recovery" tab. Beneath the "Reset this PC" header, select "Get started" followed by "Remove everything."</span></span> <span data-ttu-id="4ee28-125">残りのプロンプトの求めに従って、デバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-125">Follow the remaining prompts as desired to reset the device.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ee28-126">Skype ルーム システム v2 が Windows のリセット処理中に「ファイルを保存 - アプリケーションと設定が削除が、個人用ファイルを保持」オプションが選択されている場合に使用できなくなる既知問題があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-126">There is a known issue where the Skype Room Systems v2 can become unusable if the "Keep my files - Removes Apps and settings, but keeps your personal files" option is selected during the Windows Reset process.</span></span> <span data-ttu-id="4ee28-127">このオプションは使用**しない**でください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-127">**Do not** use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="4ee28-128">サポートされるリモート オプション</span><span class="sxs-lookup"><span data-stu-id="4ee28-128">Supported Remote Options</span></span>
<span data-ttu-id="4ee28-129"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-129"></span></span>

<span data-ttu-id="4ee28-130">次の表に、可能なリモート操作とそれを実行するために使用できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-130">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="4ee28-131">**ワークグループ**</span><span class="sxs-lookup"><span data-stu-id="4ee28-131">**Workgroup**</span></span>|<span data-ttu-id="4ee28-132">**ドメインに参加していません。**</span><span class="sxs-lookup"><span data-stu-id="4ee28-132">**Not domain joined**</span></span>|<span data-ttu-id="4ee28-133">**ドメインに参加して**</span><span class="sxs-lookup"><span data-stu-id="4ee28-133">**Domain joined**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4ee28-134">再起動</span><span class="sxs-lookup"><span data-stu-id="4ee28-134">Restart</span></span>  <br/> |<span data-ttu-id="4ee28-135">リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="4ee28-135">Remote desktop</span></span>  <br/> <span data-ttu-id="4ee28-136">リモート Powershell</span><span class="sxs-lookup"><span data-stu-id="4ee28-136">Remote Powershell</span></span>  <br/> |<span data-ttu-id="4ee28-137">(さらに設定する必要があります)、リモート デスクトップ</span><span class="sxs-lookup"><span data-stu-id="4ee28-137">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ee28-138">リモート Powershell を (さらに設定する必要があります)</span><span class="sxs-lookup"><span data-stu-id="4ee28-138">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="4ee28-139">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ee28-139">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ee28-140">OS の更新</span><span class="sxs-lookup"><span data-stu-id="4ee28-140">Update OS</span></span>  <br/> |<span data-ttu-id="4ee28-141">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4ee28-141">Windows Update</span></span>  <br/> |<span data-ttu-id="4ee28-142">Windows Update</span><span class="sxs-lookup"><span data-stu-id="4ee28-142">Windows Update</span></span>  <br/> <span data-ttu-id="4ee28-143">WSUS</span><span class="sxs-lookup"><span data-stu-id="4ee28-143">WSUS</span></span>  <br/> |
|<span data-ttu-id="4ee28-144">アプリの更新</span><span class="sxs-lookup"><span data-stu-id="4ee28-144">App update</span></span>  <br/> |<span data-ttu-id="4ee28-145">	Windows ストア</span><span class="sxs-lookup"><span data-stu-id="4ee28-145">Windows Store</span></span>  <br/> |<span data-ttu-id="4ee28-146">Windows ストア</span><span class="sxs-lookup"><span data-stu-id="4ee28-146">Windows Store</span></span>  <br/> <span data-ttu-id="4ee28-147">SCCM</span><span class="sxs-lookup"><span data-stu-id="4ee28-147">SCCM</span></span>  <br/> |
|<span data-ttu-id="4ee28-148">Skype アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="4ee28-148">Skype Account Config</span></span>  <br/> |<span data-ttu-id="4ee28-149">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="4ee28-149">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ee28-150">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="4ee28-150">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="4ee28-151">ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4ee28-151">Access logs</span></span>  <br/> |<span data-ttu-id="4ee28-152">現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="4ee28-152">Not currently supported</span></span>  <br/> |<span data-ttu-id="4ee28-153">	現在サポートされていません</span><span class="sxs-lookup"><span data-stu-id="4ee28-153">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a><span data-ttu-id="4ee28-154">Skype Room Systems バージョン 2 のグループ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="4ee28-154">Configuring Group Policy for Skype Room Systems v2</span></span>
<span data-ttu-id="4ee28-155"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-155"></span></span>

<span data-ttu-id="4ee28-156">このセクションでは、Skype ルーム システム v2 が正しく機能するために依存しているシステムの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-156">This section covers system settings that Skype Room Systems v2 depends on to function properly.</span></span> <span data-ttu-id="4ee28-157">Skype ルーム システム v2 をドメインに参加させるときに、グループ ポリシーが次の設定をオーバーライドしないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-157">When joining Skype Room Systems v2 to a domain, please ensure that your group policy does not override the following settings:</span></span>
  

|<span data-ttu-id="4ee28-158">**設定**</span><span class="sxs-lookup"><span data-stu-id="4ee28-158">**Setting**</span></span>|<span data-ttu-id="4ee28-159">**により、**</span><span class="sxs-lookup"><span data-stu-id="4ee28-159">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ee28-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="4ee28-160">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="4ee28-161">起動するように Skype ルーム システム v2 を有効に</span><span class="sxs-lookup"><span data-stu-id="4ee28-161">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="4ee28-162">電源管理 -\> AC、画面をオフに 10 分後</span><span class="sxs-lookup"><span data-stu-id="4ee28-162">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="4ee28-163">電源管理 -\> Ac システムをスリープ状態を配置しません。</span><span class="sxs-lookup"><span data-stu-id="4ee28-163">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="4ee28-164">により、接続されている表示をオフにして、自動的に復帰する Skype ルーム システム v2</span><span class="sxs-lookup"><span data-stu-id="4ee28-164">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="4ee28-165">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="4ee28-165">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="4ee28-166">またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-166">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="4ee28-167">これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。</span><span class="sxs-lookup"><span data-stu-id="4ee28-167">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="4ee28-168">したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-168">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="4ee28-169">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="4ee28-169">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="4ee28-170">グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-170">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="4ee28-171">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="4ee28-171">Remote Management using PowerShell</span></span>
<span data-ttu-id="4ee28-172"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-172"></span></span>

<span data-ttu-id="4ee28-173">PowerShell を使用して次の管理操作をリモートで実行できます (スクリプトのサンプルについては下記の表を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4ee28-173">You can perform the following management operations remotely using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="4ee28-174">接続されているデバイスの取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-174">Get attached devices</span></span>
    
- <span data-ttu-id="4ee28-175">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-175">Get app status</span></span>
    
- <span data-ttu-id="4ee28-176">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-176">Get system info</span></span>
    
- <span data-ttu-id="4ee28-177">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="4ee28-177">Reboot system</span></span>
    
- <span data-ttu-id="4ee28-178">ログの取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-178">Retrieve logs</span></span>
    
- <span data-ttu-id="4ee28-179">ファイル転送 (Skype ルーム システム v2 がドメインに参加している必要があります)</span><span class="sxs-lookup"><span data-stu-id="4ee28-179">Transfer files (requires a domain joined Skype Room Systems v2)</span></span>
    
> [!NOTE]
> <span data-ttu-id="4ee28-180">既定では、この機能はオフです。</span><span class="sxs-lookup"><span data-stu-id="4ee28-180">This functionality is off by default.</span></span> <span data-ttu-id="4ee28-181">Skype ルーム システム v2 システムの環境に次の操作を実行するリモートの PowerShell を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-181">You need to enable remote PowerShell for your environment on the Skype Room Systems v2 system to perform the operations below.</span></span> <span data-ttu-id="4ee28-182">リモート PowerShell を有効にする方法については**[有効にする PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)**のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-182">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** for information on how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="4ee28-183">たとえば、次のようにリモート PowerShell を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-183">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="4ee28-184">Skype ルーム システム v2 デバイスの管理者のユーザーとしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-184">Sign in as Admin on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="4ee28-185">管理者特権で PowerShell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-185">Launch an elevated PowerShell command prompt.</span></span>
    
3. <span data-ttu-id="4ee28-186">次のコマンドを入力してください: 有効にする-PSRemoting - 強制</span><span class="sxs-lookup"><span data-stu-id="4ee28-186">Enter the following command: Enable-PSRemoting -force</span></span>
    
<span data-ttu-id="4ee28-187">管理操作を実行するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-187">To perform a management operation:</span></span>
  
1. <span data-ttu-id="4ee28-188">Skype ルーム システム v2 のデバイスでの PowerShell コマンドを実行する権限を持つアカウントの資格情報を持つ PC にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-188">Sign into a PC with account credentials that have permission to run PowerShell commands on a Skype Room Systems v2 device.</span></span>
    
2. <span data-ttu-id="4ee28-189">PC で通常の PowerShell コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-189">Launch a regular PowerShell command prompt on your PC.</span></span>
    
3. <span data-ttu-id="4ee28-190">次の表からコマンド テキストをコピーして、プロンプトに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-190">Copy the command text from the table below and paste it into the prompt.</span></span>
    
4. <span data-ttu-id="4ee28-191">交換`<Device fqdn>`FQDN の値を持つフィールドが、環境に対応します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-191">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
    
5. <span data-ttu-id="4ee28-192">交換*\<のパス\>*SkypeSettings.xml 構成ファイルのマスター (またはテーマのイメージ) のローカル パスとファイル名とします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-192">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="4ee28-193">接続されているデバイスを取得するには</span><span class="sxs-lookup"><span data-stu-id="4ee28-193">To Get Attached Devices</span></span>
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ee28-194">アプリの状態の取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-194">Get App Status</span></span>
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="4ee28-195">システム情報の取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-195">Get System Info</span></span>
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="4ee28-196">システムの再起動</span><span class="sxs-lookup"><span data-stu-id="4ee28-196">Reboot System</span></span>
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="4ee28-197">ログの取得</span><span class="sxs-lookup"><span data-stu-id="4ee28-197">Retrieve Logs</span></span>
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="4ee28-198">XML 構成ファイルまたはテーマのグラフィックをプッシュします)</span><span class="sxs-lookup"><span data-stu-id="4ee28-198">Push an XML configuration file or theme graphic)</span></span>
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="4ee28-199">ソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="4ee28-199">Software updates</span></span>
<span data-ttu-id="4ee28-200"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-200"></span></span>

<span data-ttu-id="4ee28-201">既定では、Skype ルーム システム v2 はデバイスの通常のインターネット アクセスが必要なので、Skype ルーム システム v2 のソフトウェアの最新バージョンを取得する Windows ストアへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-201">By default, Skype Room Systems v2 will attempt to connect to the Windows Store to get the latest version of Skype Room Systems v2 software, so the device will require regular internet access.</span></span> <span data-ttu-id="4ee28-202">Skype ルーム システム v2 デバイスが読み込まれるアプリケーションの最新バージョンとサポートの問題をマイクロソフトに連絡する前に必ずしてください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-202">Be sure the Skype Room Systems v2 device is loaded with the latest version of the app, before contacting Microsoft with support issues.</span></span>
  
<span data-ttu-id="4ee28-203">既定では、Skype ルーム システム v2 は OS の取得と USB 周辺機器のファームウェアの更新プログラム Windows Update に接続し、構成済みの業務時間外にインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-203">By default, Skype Room Systems v2 will connect to Windows Update to retrieve OS as well as USB peripheral firmware updates and install them outside of configured business hours.</span></span> <span data-ttu-id="4ee28-204">営業時間を設定するには、管理者アカウントでサインインし、設定アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-204">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="4ee28-205">APPX の適切なファイルとの[『 導入ガイド 』](https://go.microsoft.com/fwlink/?linkid=851168) (からの依存関係を取得することをした場合、手動で更新プログラムを管理する通常の手順に従って、[ビジネス向けのマイクロソフト ストア](https://businessstore.microsoft.com/en-us/store)の[オフライン アプリケーションを配布](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps)することはできません。[Skype ルーム システム v2 のコンソールを構成](../../deploy/deploy-clients/console.md)する方法) と SCCM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-205">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/en-us/store) to [Distribute offline apps](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Skype Room Systems v2 console](../../deploy/deploy-clients/console.md)) that can be used with SCCM.</span></span> <span data-ttu-id="4ee28-206">デプロイメント キットのリリースは、ストアのリリースよりも後になるため、最新の入手可能な最新ビルドに必ずしも一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-206">The deployment kit release lags behind the store release, so it may not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="4ee28-207">Powershell を使用して更新するのには</span><span class="sxs-lookup"><span data-stu-id="4ee28-207">To update using Powershell</span></span>

1. <span data-ttu-id="4ee28-208">[MSI](https://go.microsoft.com/fwlink/?linkid=851168)のインストールとデバイスのアクセス可能な共有にパッケージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-208">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a device accessible share.</span></span>
    
2. <span data-ttu-id="4ee28-209">Skype ルーム システム v2 ・ デバイスを使用し、変更することを対象とする次のスクリプトを実行\<共有\>デバイスには、必要に応じて共有します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-209">Run the following script targeting the Skype Room Systems v2 devices, changing \<share\> to the device share as appropriate:</span></span>
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="4ee28-210">管理者モードとデバイス管理</span><span class="sxs-lookup"><span data-stu-id="4ee28-210">Admin mode and device management</span></span>
<span data-ttu-id="4ee28-211"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-211"></span></span>

<span data-ttu-id="4ee28-212">プライベート CA 証明書の手動によるインストールのような一部の管理機能では、Surface 4 デバイスを管理者モードにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-212">Some management functions, like manually installing a private CA certificate, require placing the Surface 4 device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a><span data-ttu-id="4ee28-213">管理者モードと Skype ルーム システム v2 のアプリケーションを実行しているときの切り替え</span><span class="sxs-lookup"><span data-stu-id="4ee28-213">Switching to Admin Mode and back when the Skype Room Systems v2 app is running</span></span>

1. <span data-ttu-id="4ee28-214">現在の通話を切って、ホーム画面に戻ります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-214">Hang up any ongoing calls and return to the home screen.</span></span>
    
2. <span data-ttu-id="4ee28-215">歯車のアイコンをクリックし、メニューを表示 (オプションは、**設定**、**ユーザー補助の設定**、および**デバイスの再起動**) します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-215">Click on the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
    
3. <span data-ttu-id="4ee28-216">[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-216">Select **Settings**.</span></span>
    
4. <span data-ttu-id="4ee28-217">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-217">Enter the Administrator Password.</span></span> <span data-ttu-id="4ee28-218">セットアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-218">The Setup screen will appear.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ee28-p115">デバイスがドメインに参加していない場合、既定によりローカルの管理アカウント (ユーザー名「Admin」) が使用されます。このアカウントの既定のパスワードは「sfb」ですが、セキュリティ上の理由により所属する組織によってできるだけ早く変更されることが推奨されます。コンピューターがドメインに参加している場合、適切な権限のドメイン アカウントでサインインできます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-p115">If the device is not domain joined, the local administrative account (username "Admin") will be used by default. The default password for this account is 'sfb' but it is recommended that your organization change this for security reasons as soon as possible. If the machine is domain joined, you can sign in with an appropriately-privileged domain account.</span></span> 
  
5. <span data-ttu-id="4ee28-222">左列にある [**Windows の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-222">Click on **Windows Settings** on the left column.</span></span>
    
6. <span data-ttu-id="4ee28-223">[**管理サインインに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-223">Choose **Go to Admin Sign-in**.</span></span>
    
7. <span data-ttu-id="4ee28-224">管理者パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-224">Enter the Administrator Password.</span></span> <span data-ttu-id="4ee28-225">これによって、アプリから正常にログオフされ、Windows のログイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-225">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
    
8. <span data-ttu-id="4ee28-p117">管理者の資格情報でデスクトップにログインします。デバイスの管理に必要な権限を持つことになります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-p117">Log in to the desktop with your administrative credentials. You will have the necessary privileges to manage the device.</span></span>
    
9. <span data-ttu-id="4ee28-228">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-228">Perform the necessary administrative tasks.</span></span>
    
10. <span data-ttu-id="4ee28-229">管理者アカウントからサイン アウトします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-229">Sign out from the Admin account.</span></span>
    
11. <span data-ttu-id="4ee28-230">画面の一番左上のユーザー アカウントのアイコンを選択して Skype ルーム システム v2 に戻るし、 **Skype**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-230">Return to Skype Room Systems v2 by selecting the user account icon on the far left of the screen and select **Skype**.</span></span>
    
    <span data-ttu-id="4ee28-231">**Skype**ユーザーが一覧にない場合は**他のユーザー**を選択し、入力をする必要があります**です。 \skype**として、ユーザー名、およびサインインします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-231">If the **Skype** user is not listed, you may have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
 <span data-ttu-id="4ee28-232">コンソールは、その通常の操作モードに戻るようになりました。次の手順では、1 つは既に接続されていない場合、デバイスにキーボードを接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-232">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a><span data-ttu-id="4ee28-233">管理者モードと Skype ルーム システム v2 のアプリケーションがクラッシュしたときの切り替え</span><span class="sxs-lookup"><span data-stu-id="4ee28-233">Switching to Admin Mode and back when the Skype Room Systems v2 app crashes</span></span>

1. <span data-ttu-id="4ee28-p118">Windows キーを 5 回連続で、素早く押します。これによって、Windows のログオン画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-p118">Press the Windows key five times in rapid succession. This will bring you to the Windows logon screen.</span></span> 
    
2. <span data-ttu-id="4ee28-236">管理者の資格情報でデスクトップにログインします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-236">Log into the desktop with your administrative credentials.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ee28-237">この方法は、Skype ユーザーをログオフさせたりアプリを正常終了させることはありませんが、アプリが応答しない場合やその他の方法が使用できない場合にのみ使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4ee28-237">This method does not log the Skype user off or gracefully terminate the app, but you would only use it if the app was not responding and the other method was not available.</span></span> 
  
3. <span data-ttu-id="4ee28-238">必要な管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-238">Perform the necessary administrative tasks.</span></span>
    
4. <span data-ttu-id="4ee28-239">終了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-239">Restart the machine when you are finished.</span></span>
    
 <span data-ttu-id="4ee28-240">Skype ルーム システム v2 のアプリケーションを実行して、通常の操作モードに、コンソールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-240">The console restarts into its normal operation mode, running the Skype Room Systems v2 app.</span></span> <span data-ttu-id="4ee28-241">キーボードが接続されている場合は、取り外してこの手順を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-241">You may remove the keyboard if it was attached to allow you to perform this procedure.</span></span>
## <a name="troubleshooting-tips"></a><span data-ttu-id="4ee28-242">トラブルシューティングのヒント</span><span class="sxs-lookup"><span data-stu-id="4ee28-242">Troubleshooting tips</span></span>
<span data-ttu-id="4ee28-243"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-243"></span></span>

- <span data-ttu-id="4ee28-244">会議の招待状は、ドメイン境界 (たとえば、2 つの会社間) を越えて送信すると表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-244">Meeting invitations may not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="4ee28-245">このような場合、IT 管理者は外部ユーザーに対して会議のスケジュール設定を許可するかどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-245">In such cases, IT admins should decide whether or not to allow external users to schedule a meeting.</span></span>
    
- <span data-ttu-id="4ee28-246">Skype ルーム システム v2 では、Exchange 2010 を使用して Exchange の自動検出リダイレクトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4ee28-246">Skype Room Systems v2 does not support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
    
- <span data-ttu-id="4ee28-247">通常、IT 管理者は使用する予定のないオーディオ エンドポイントをすべて無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ee28-247">In general, it is a good practice for IT admins to disable any audio endpoints not intended for use.</span></span>
    
- <span data-ttu-id="4ee28-248">ルームのプレビューにミラー イメージが表示される場合、IT 管理者はカメラの電源をいったんオフにして再びオンにするか、カメラのリモート制御を使用してイメージの向きを反転させることでミラー イメージを修正できます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-248">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
    
- <span data-ttu-id="4ee28-249">コンソールのタッチスクリーンへのアクセスが機能しなくなる問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="4ee28-249">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="4ee28-250">このような場合は、Skype ルーム システム v2 のシステムを再起動することによって問題が解決場合があります。</span><span class="sxs-lookup"><span data-stu-id="4ee28-250">In such cases, the issue is sometimes resolved by restarting the Skype Room Systems v2 system.</span></span>
    
- <span data-ttu-id="4ee28-251">有線取り込みを介して PC をコンソールに接続すると、ローカルの音声が消失する問題が発生することが知られています。</span><span class="sxs-lookup"><span data-stu-id="4ee28-251">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="4ee28-252">このような場合は、PC を再起動することでローカルの音声再生の問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="4ee28-252">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ee28-253">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-253">See also</span></span>
<span data-ttu-id="4ee28-254"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="4ee28-254"></span></span>

#### 

[<span data-ttu-id="4ee28-255">Skype ルームの計画システム v2</span><span class="sxs-lookup"><span data-stu-id="4ee28-255">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="4ee28-256">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="4ee28-256">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="4ee28-257">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-257">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="4ee28-258">Skype ルーム システム v2 のコンソールの設定を XML 構成ファイルを使用してリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="4ee28-258">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)

