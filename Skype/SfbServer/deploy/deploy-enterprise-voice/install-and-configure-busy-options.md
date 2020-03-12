---
title: Skype for Business Server の通話中オプションのインストールと構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Skype for Business Server で通話中オプションをインストールおよび構成する方法について確認します。
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604214"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="79d98-103">Skype for Business Server の通話中オプションのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="79d98-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="79d98-104">Skype for Business Server で通話中オプションをインストールおよび構成する方法について確認します。</span><span class="sxs-lookup"><span data-stu-id="79d98-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="79d98-105">通話中オプションは、2016年7月の累積的な更新プログラムで導入された新しい音声ポリシーです。これにより、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に着信呼び出しを処理する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="79d98-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="79d98-106">通話中、またはボイスメールに転送された新規または着信通話を拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="79d98-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="79d98-107">[通話中] オプションが組織で有効になっている場合は、エンタープライズ voip ユーザーとエンタープライズ Voip ユーザーの両方で、エンタープライズのすべてのユーザーが次の構成オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="79d98-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="79d98-108">ビジー状態で、ユーザーが通話中の場合は、通話中に新しい着信が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="79d98-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="79d98-109">ビジー状態のボイスメール。ユーザーが通話中の場合は、新しい着信通話がボイスメールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="79d98-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="79d98-110">通話中オプションの構成方法に関係なく、電話または電話会議のユーザー、または通話を保留にしているユーザーは、新しい通話または会議を開始できません。</span><span class="sxs-lookup"><span data-stu-id="79d98-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="79d98-111">通話中オプション機能の詳細については、「 [Plan For Busy options For Skype For Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d98-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="79d98-112">Install</span><span class="sxs-lookup"><span data-stu-id="79d98-112">Install</span></span>

<span data-ttu-id="79d98-113">最新バージョンの Skype for Business Server がインストールされており、最新のパッチがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="79d98-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="79d98-114">これを行うには、まずすべてのサービスを停止してから、次のように Skype for Business Server 更新プログラムのインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="79d98-115">Stop-CsWindowsService コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="79d98-116">プール内の各フロントエンドサーバーで SkypeServerUpdateInstaller .exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="79d98-117">SBS でのフェールオーバーのサポートを確認するには、各存続可能ブランチサーバー (SBS) で SkypeServerUpdateInstaller のインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="79d98-118">インストーラーは、通話中オプションアプリケーションの最新バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="79d98-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="79d98-119">ただし、アプリケーションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="79d98-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="79d98-120">アプリケーションを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="79d98-121">次の例に示すように、 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps)コマンドレットを実行して、通話中オプションをグローバルに有効にします。</span><span class="sxs-lookup"><span data-stu-id="79d98-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="79d98-122">次に、サイトで音声ポリシーが設定されている場合は、音声ポリシーの通話中オプションを次のように有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d98-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="79d98-123">最初に、 [Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)を実行してサイトの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="79d98-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="79d98-124">Redmond1 というサイトから取得した Id 値 (例: Site:) を使用して、サイトの音声ポリシーを次のように取得します。</span><span class="sxs-lookup"><span data-stu-id="79d98-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="79d98-125">サイトの音声ポリシーが存在する場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="79d98-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="79d98-126">次に、次の例に示すように、[新しい-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps)コマンドレットを実行して、サーバーアプリケーションの一覧に通話中オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="79d98-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="79d98-127">% FQDN% は特定のプールの完全修飾ドメイン名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d98-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="79d98-128">次に、次の例に示すように、「[更新-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps)コマンドレット」を実行して、Busy オプションコマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="79d98-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="79d98-129">最後に、[次へ] を[実行して](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)、通話中オプションがインストールされて有効になっているすべてのプール内のすべてのフロントエンドサーバーで、Skype For Business Server Windows サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="79d98-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="79d98-130">Configure</span><span class="sxs-lookup"><span data-stu-id="79d98-130">Configure</span></span>

<span data-ttu-id="79d98-131">通話中オプションを構成するには、 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79d98-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="79d98-132">たとえば、次のコマンドを実行すると、ユーザー "Ken Myer" の通話中オプションが構成されます。</span><span class="sxs-lookup"><span data-stu-id="79d98-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="79d98-133">この構成では、"Ken Myer" へのすべての呼び出しは、既に通話中の場合にビジー信号を返します。</span><span class="sxs-lookup"><span data-stu-id="79d98-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="79d98-134">次の例では、コマンドによって、"Chrystal と" というユーザーの通話中オプションが構成されます。</span><span class="sxs-lookup"><span data-stu-id="79d98-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="79d98-135">この構成では、既に通話中の場合、"Chrystal と" への新しい着信呼び出しがボイスメールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="79d98-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="79d98-136">[Set-csbusyoptions cmdlet](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)コマンドレットを使用して、通話中オプションに関する構成情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="79d98-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="79d98-137">次の例では、"KenMyer@Contoso.com" の通話中オプションの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="79d98-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="79d98-138">[Set-csbusyoptions cmdlet](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)コマンドレットを使用して、通話中オプションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="79d98-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="79d98-139">次のコマンドは、"Ken Myer" の通話中オプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="79d98-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="79d98-140">通話中オプションの構成に使用するコマンドレットの詳細については、「 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)」、「 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)」、および「 [Remove-set-csbusyoptions cmdlet](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)」のテクニカルリファレンスコンテンツを参照してください。</span><span class="sxs-lookup"><span data-stu-id="79d98-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="79d98-141">ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="79d98-141">Enable logging</span></span>

<span data-ttu-id="79d98-142">集中ログサービスを使用して通話中オプションのログ記録を有効にするには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="79d98-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="79d98-143">確認およびトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="79d98-143">Verify and troubleshoot</span></span>

<span data-ttu-id="79d98-144">通話中オプションをインストールした後、サーバーアプリケーションの一覧を取得するために、 [Get-help Serverapplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps)コマンドレットを使用して、インストールが正常に完了したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="79d98-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="79d98-145">通話中オプションが適切にインストールされている場合は、コマンドレットの出力で、次のように通話中オプションの構成を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79d98-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="79d98-146">Windows イベントビューアーを使用して、通話中オプションが正常にインストールされたことと、Skype for Business Server が正常にビジーオプションを正常に読み込みしたことを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="79d98-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="79d98-147">通話中オプションを確認するには、**イベントビューア-\>アプリケーションと\>サービスログ-Skype (または Lync) サーバー**を開き、イベント ID = 30253 を検索します。</span><span class="sxs-lookup"><span data-stu-id="79d98-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
