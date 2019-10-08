---
title: Skype for Business Server の通話中オプションのインストールおよび構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Skype for Business Server で取り込み中のオプションをインストールして構成する方法について説明します。
ms.openlocfilehash: a0fd235d5db645035ac9a6344c233dfe12a78b7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240311"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="af24d-103">Skype for Business Server の通話中オプションのインストールおよび構成</span><span class="sxs-lookup"><span data-stu-id="af24d-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="af24d-104">Skype for Business Server で取り込み中のオプションをインストールして構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af24d-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="af24d-105">通話中オプションは、2016 年 7 月の累積更新プログラムで導入された新たなボイス ポリシーで、ユーザーが通話中や会議中の場合、または通話を保留にしている場合の着信処理方法を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="af24d-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="af24d-106">着信があった場合に、話中音を流すかボイスメールに転送できます。</span><span class="sxs-lookup"><span data-stu-id="af24d-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="af24d-107">通話中オプションが組織で有効になっていれば、エンタープライズ VoIP を使用するユーザーも使用しないユーザーも、エンタープライズ中の全ユーザーが次の構成オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af24d-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="af24d-108">通話中に話中音 - 通話中に別の着信があると、話中音を流して着信を拒否します。</span><span class="sxs-lookup"><span data-stu-id="af24d-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="af24d-109">通話中にボイスメール - 通話中に別の着信があると、ボイスメールに転送します。</span><span class="sxs-lookup"><span data-stu-id="af24d-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="af24d-110">通話中オプションがどう構成されていても、通話中や会議中または通話を保留にしているユーザーが、新たな発信や会議を開始できなくなるわけではありません。  </span><span class="sxs-lookup"><span data-stu-id="af24d-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="af24d-111">通話中オプション機能の詳細については、「 [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af24d-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="af24d-112">インストール </span><span class="sxs-lookup"><span data-stu-id="af24d-112">Install</span></span>

<span data-ttu-id="af24d-113">最新バージョンの Skype for Business Server がインストールされていて、最新の更新プログラムがインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af24d-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="af24d-114">これを行うには、まずすべてのサービスを停止してから、次のようにして Skype for Business Server 更新プログラムのインストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="af24d-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="af24d-115">Stop-CsWindowsService コマンドを実行する。</span><span class="sxs-lookup"><span data-stu-id="af24d-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="af24d-116">プール内のフロントエンド サーバーごとに SkypeServerUpdateInstaller.exe インストーラを実行する。</span><span class="sxs-lookup"><span data-stu-id="af24d-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="af24d-117">存続可能ブランチ サーバー (SBS) でのフェールオーバーをサポートしたい場合は、SBS ごとに SkypeServerUpdateInstaller.exe インストーラを実行する。</span><span class="sxs-lookup"><span data-stu-id="af24d-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="af24d-p103">インストーラーによって通話中オプション アプリケーションの最新バージョンが展開されますが、アプリケーションは既定で有効ではありません。次の手順で有効にします。</span><span class="sxs-lookup"><span data-stu-id="af24d-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="af24d-121">次の例に示すように、 [CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps)コマンドレットを実行して、ビジーオプションをグローバルに有効にします。</span><span class="sxs-lookup"><span data-stu-id="af24d-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="af24d-122">次に、サイトにボイス ポリシーがある場合は、次のようにボイス ポリシー用の通話中オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="af24d-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="af24d-123">最初に、[[次へ] を実行](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)して、サイトの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="af24d-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="af24d-124">Redmond1 サイトから取得した Id 値 (例: Site:) を使用して、次のようにサイトの音声ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="af24d-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="af24d-125">サイトのボイス ポリシーが存在していれば、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af24d-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="af24d-126">次に、[新しい-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps)コマンドレットを実行して、次の例に示すように、サーバーアプリケーションの一覧に取り込み中のオプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="af24d-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="af24d-127">% FQDN% は、特定のプールの完全修飾ドメイン名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="af24d-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="af24d-128">次に、次の例に示すように、[更新プログラム] と [ [CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) ] のコマンドレットを実行して、Busy オプションのコマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。</span><span class="sxs-lookup"><span data-stu-id="af24d-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="af24d-129">最後に、Busy オプションがインストールされて有効になっているすべてのプール内のすべてのフロントエンドサーバーで、Skype for Business Server の Windows サービスを開始します。[次の操作](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)を実行します。</span><span class="sxs-lookup"><span data-stu-id="af24d-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="af24d-130">構成</span><span class="sxs-lookup"><span data-stu-id="af24d-130">Configure</span></span>

<span data-ttu-id="af24d-131">通話中オプションを構成するには、[Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet を使用します。  </span><span class="sxs-lookup"><span data-stu-id="af24d-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="af24d-p104">たとえば、次のコマンドは「Ken Myer」というユーザーの通話中オプションを構成します。この構成では、通話中に「Ken Myer」への着信があると話中音を返します。</span><span class="sxs-lookup"><span data-stu-id="af24d-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="af24d-134">その次の例では、コマンドが「Chrystal Velasquez」というユーザーの通話中オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="af24d-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="af24d-135">この構成では、通話中に着信があるとボイスメールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="af24d-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="af24d-136">[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet を使用して、通話中オプションに関する構成情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="af24d-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="af24d-137">次の例では、"KenMyer@Contoso.com" の [取り込み中] オプションの設定を返します。</span><span class="sxs-lookup"><span data-stu-id="af24d-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="af24d-138">[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet を使用して、通話中オプションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="af24d-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="af24d-139">次のコマンドは「Ken Myer」の通話中オプションを削除します。</span><span class="sxs-lookup"><span data-stu-id="af24d-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="af24d-140">Busy のオプションを構成するために使用するコマンドレットの詳細については、「 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)、および[Remove](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)のテクニカルリファレンスコンテンツ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af24d-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="af24d-141">ログの有効化</span><span class="sxs-lookup"><span data-stu-id="af24d-141">Enable logging</span></span>

<span data-ttu-id="af24d-142">集中ログ サービスを使用して通話中オプションのログを有効にするには、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="af24d-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="af24d-143">確認とトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="af24d-143">Verify and troubleshoot</span></span>

<span data-ttu-id="af24d-144">[取り込み中] オプションをインストールした後、ユーザーが正常にインストールされたことを確認するには、 [CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps)コマンドレットを使用してサーバーアプリケーションの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="af24d-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="af24d-145">通話中オプションが正しくインストールされていれば、通話中オプション構成が次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="af24d-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="af24d-146">また、Windows イベントビューアーを使用して、取り込み中のオプションが正常にインストールされたこと、および Skype for Business Server で [取り込み中] オプションが正常に読み込まれたことを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="af24d-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="af24d-147">取り込み中のオプションを確認するには、イベントビューアーを開きます。 **\>アプリケーションとサービスログ\> -Skype (または Lync) サーバー**で、イベント ID = 30253 を検索します。</span><span class="sxs-lookup"><span data-stu-id="af24d-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
