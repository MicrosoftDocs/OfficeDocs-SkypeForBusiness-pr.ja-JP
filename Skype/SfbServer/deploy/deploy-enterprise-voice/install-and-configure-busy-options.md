---
title: Skype for Business Server の通話中オプションをインストールおよび構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype for Business Server で通話中オプションをインストールおよび構成する方法について説明します。
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830807"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="6e071-103">Skype for Business Server の通話中オプションをインストールおよび構成する</span><span class="sxs-lookup"><span data-stu-id="6e071-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="6e071-104">Skype for Business Server で通話中オプションをインストールおよび構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e071-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="6e071-105">通話中オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーで、ユーザーが既に通話中または電話会議中の場合や、通話を保留にした場合の着信の処理方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="6e071-106">新しい通話または着信呼び出しは、ビジー信号で拒否するか、ボイス メールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="6e071-107">組織で [取り込み中オプション] が有効になっている場合、エンタープライズのすべてのユーザー (エンタープライズ VoIP ユーザーと エンタープライズ VoIP ユーザーの両方) は、次の構成オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="6e071-108">取り込み中 - ユーザーがビジー状態の場合、新しい着信呼び出しがビジー信号で拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6e071-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="6e071-109">通話中のボイスメール - ユーザーがビジー状態の場合に、新しい着信呼び出しがボイス メールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="6e071-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="6e071-110">通話中オプションの構成方法に関係なく、通話中または電話会議中のユーザー、または通話が保留されているユーザーは、新しい通話や会議を開始する操作を妨げるものではありません。</span><span class="sxs-lookup"><span data-stu-id="6e071-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="6e071-111">通話中オプション機能の詳細については、「Skype for Business Server の通話中オプションを計画する [」を参照してください](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="6e071-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="6e071-112">インストール</span><span class="sxs-lookup"><span data-stu-id="6e071-112">Install</span></span>

<span data-ttu-id="6e071-113">Skype for Business Server の最新バージョンがインストール済みで、最新の修正プログラムがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e071-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="6e071-114">これを行うには、まずすべてのサービスを停止し、次のように Skype for Business Server 更新インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e071-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="6e071-115">次のコマンドStop-CsWindowsServiceします。</span><span class="sxs-lookup"><span data-stu-id="6e071-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="6e071-116">プール内SkypeServerUpdateInstaller.exeフロント エンド サーバーで新しいインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e071-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="6e071-117">SBS でのフェールオーバーSkypeServerUpdateInstaller.exeサポートする場合は、各存続可能ブランチ サーバー (SBS) で新しいインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e071-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="6e071-118">インストーラーは、最新バージョンの取り込み中オプション アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6e071-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="6e071-119">ただし、アプリケーションは既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6e071-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="6e071-120">アプリケーションを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e071-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="6e071-121">次の [例に示すように、Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) コマンドレットを実行して、取り込み中オプションをグローバルに有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e071-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="6e071-122">次に、サイトに音声ポリシーがある場合は、次のように音声ポリシーの通話中オプションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e071-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="6e071-123">まず [、Get-CsSite を実行して](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) サイトの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e071-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="6e071-124">次のように、サイトの音声ポリシーを取得するには、Get-CsSite から取得した Identity 値 (Site:Redmond1 など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e071-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="6e071-125">サイトに音声ポリシーが存在する場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e071-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="6e071-126">次に [、New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) コマンドレットを実行して、次の例に示すように、サーバー アプリケーションの一覧に取り込み中オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e071-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="6e071-127">%FQDN% は、特定のプールの完全修飾ドメイン名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e071-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="6e071-128">次に [、Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) コマンドレットを実行して、次の例に示すように、取り込み中オプション コマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="6e071-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="6e071-129">最後に [、Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) コマンドを実行して、通話中オプションがインストールされ、有効になっているすべてのプール内のすべてのフロントエンド サーバーで Skype for Business Server Windows サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="6e071-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="6e071-130">構成</span><span class="sxs-lookup"><span data-stu-id="6e071-130">Configure</span></span>

<span data-ttu-id="6e071-131">取り込み中オプションを構成するには [、Set-CsBusyOptions コマンドレットを使用](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) します。</span><span class="sxs-lookup"><span data-stu-id="6e071-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="6e071-132">たとえば、次のコマンドは、ユーザー "Ken Myer" のビジー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e071-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="6e071-133">この構成では、"Ken Myer" への呼び出しは、通話中にビジー信号を返します。</span><span class="sxs-lookup"><span data-stu-id="6e071-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="6e071-134">次の例では、コマンドはユーザー "Chrystal Velasquez" のビジー オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e071-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="6e071-135">この構成では、"Chrystal Velasquez" への新しい着信呼び出しは、通話中に既にボイス メールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="6e071-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="6e071-136">[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)コマンドレットを使用して、取り込み中オプションに関する構成情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="6e071-137">次の例では、"KenMyer@Contoso.com" の [取り込み中オプション] 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e071-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="6e071-138">[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)コマンドレットを使用して、取り込み中オプションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="6e071-139">次のコマンドは、"Ken Myer" の取り込み中オプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="6e071-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="6e071-140">取り込み中オプションの構成に使用するコマンドレットの詳細については[、Set-CsBusyOptions、Get-CsBusyOptions、Remove-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)のテクニカル リファレンス コンテンツを参照してください。 [](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) [](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)</span><span class="sxs-lookup"><span data-stu-id="6e071-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="6e071-141">ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="6e071-141">Enable logging</span></span>

<span data-ttu-id="6e071-142">集中ログ サービスを使用して、取り込み中オプションのログを有効にするには、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e071-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="6e071-143">確認とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6e071-143">Verify and troubleshoot</span></span>

<span data-ttu-id="6e071-144">取り込み中オプションをインストールした後 [、Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) コマンドレットを使用してサーバー アプリケーションの一覧を取得することで、インストールが成功したと確認できます。</span><span class="sxs-lookup"><span data-stu-id="6e071-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="6e071-145">取り込み中オプションが正しくインストールされている場合、コマンドレットの出力には、次のように、取り込み中オプションの構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e071-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

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

<span data-ttu-id="6e071-146">Windows イベント ビューアーを使用して、通話中オプションのインストールが成功し、Skype for Business Server が通話中オプションを正常に読み込んだか確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e071-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="6e071-147">通話中オプションを確認するには、イベント ビューアー ( アプリケーションとサービス ログ **\> - Skype \> (または Lync) Server)** を開き、イベント ID = 30253 を検索します。</span><span class="sxs-lookup"><span data-stu-id="6e071-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
