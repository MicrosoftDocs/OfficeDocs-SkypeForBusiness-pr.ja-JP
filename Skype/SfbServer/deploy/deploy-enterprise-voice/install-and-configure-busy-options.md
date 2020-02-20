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
ms.openlocfilehash: 5078041401c710a249470ed6d3871f38a98a7420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113120"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Skype for Business Server の通話中オプションのインストールと構成

Skype for Business Server で通話中オプションをインストールおよび構成する方法について確認します。

通話中オプションは、2016年7月の累積的な更新プログラムで導入された新しい音声ポリシーです。これにより、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に着信呼び出しを処理する方法を構成できます。 通話中、またはボイスメールに転送された新規または着信通話を拒否することができます。

[通話中] オプションが組織で有効になっている場合は、エンタープライズ voip ユーザーとエンタープライズ Voip ユーザーの両方で、エンタープライズのすべてのユーザーが次の構成オプションを使用できます。

- ビジー状態で、ユーザーが通話中の場合は、通話中に新しい着信が拒否されます。

- ビジー状態のボイスメール。ユーザーが通話中の場合は、新しい着信通話がボイスメールに転送されます。

通話中オプションの構成方法に関係なく、電話または電話会議のユーザー、または通話を保留にしているユーザーは、新しい通話または会議を開始できません。

通話中オプション機能の詳細については、「 [Plan For Busy options For Skype For Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)」を参照してください。

## <a name="install"></a>Install

最新バージョンの Skype for Business Server がインストールされており、最新のパッチがインストールされていることを確認してください。 これを行うには、まずすべてのサービスを停止してから、次のように Skype for Business Server 更新プログラムのインストーラーを実行します。

1. Stop-CsWindowsService コマンドを実行します。

2. プール内の各フロントエンドサーバーで SkypeServerUpdateInstaller .exe を実行します。

3. SBS でのフェールオーバーのサポートを確認するには、各存続可能ブランチサーバー (SBS) で SkypeServerUpdateInstaller のインストーラーを実行します。

インストーラーは、通話中オプションアプリケーションの最新バージョンを展開します。 ただし、アプリケーションは既定では有効になっていません。 アプリケーションを有効にするには、次の手順を実行します。

1. 次の例に示すように、 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps)コマンドレットを実行して、通話中オプションをグローバルに有効にします。

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 次に、サイトで音声ポリシーが設定されている場合は、音声ポリシーの通話中オプションを次のように有効にする必要があります。

    最初に、 [Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)を実行してサイトの名前を取得します。

   ```powershell
   Get-CsSite
   ```

    Redmond1 というサイトから取得した Id 値 (例: Site:) を使用して、サイトの音声ポリシーを次のように取得します。

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    サイトの音声ポリシーが存在する場合は、次のコマンドを実行します。

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 次に、次の例に示すように、[新しい-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps)コマンドレットを実行して、サーバーアプリケーションの一覧に通話中オプションを追加します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > % FQDN% は特定のプールの完全修飾ドメイン名に置き換える必要があります。

4. 次に、次の例に示すように、「[更新-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps)コマンドレット」を実行して、Busy オプションコマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。

   ```powershell
   Update-CsAdminRole
   ```

5. 最後に、[次へ] を[実行して](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)、通話中オプションがインストールされて有効になっているすべてのプール内のすべてのフロントエンドサーバーで、Skype For Business Server Windows サービスを開始します。

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configure

通話中オプションを構成するには、 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)コマンドレットを使用します。

たとえば、次のコマンドを実行すると、ユーザー "Ken Myer" の通話中オプションが構成されます。 この構成では、"Ken Myer" へのすべての呼び出しは、既に通話中の場合にビジー信号を返します。

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

次の例では、コマンドによって、"Chrystal と" というユーザーの通話中オプションが構成されます。 この構成では、既に通話中の場合、"Chrystal と" への新しい着信呼び出しがボイスメールに転送されます。

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[Set-csbusyoptions cmdlet](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)コマンドレットを使用して、通話中オプションに関する構成情報を取得できます。 次の例では、"KenMyer@Contoso.com" の通話中オプションの設定を取得します。

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[Set-csbusyoptions cmdlet](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)コマンドレットを使用して、通話中オプションを削除できます。 次のコマンドは、"Ken Myer" の通話中オプションを削除します。

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

通話中オプションの構成に使用するコマンドレットの詳細については、「 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)」、「 [set-csbusyoptions cmdlet](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)」、および「 [Remove-set-csbusyoptions cmdlet](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)」のテクニカルリファレンスコンテンツを参照してください。

## <a name="enable-logging"></a>ログを有効にする

集中ログサービスを使用して通話中オプションのログ記録を有効にするには、次のように指定します。

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>確認およびトラブルシューティング

通話中オプションをインストールした後、サーバーアプリケーションの一覧を取得するために、 [Get-help Serverapplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps)コマンドレットを使用して、インストールが正常に完了したことを確認できます。 通話中オプションが適切にインストールされている場合は、コマンドレットの出力で、次のように通話中オプションの構成を表示する必要があります。

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

Windows イベントビューアーを使用して、通話中オプションが正常にインストールされたことと、Skype for Business Server が正常にビジーオプションを正常に読み込みしたことを確認することもできます。 通話中オプションを確認するには、**イベントビューア-\>アプリケーションと\>サービスログ-Skype (または Lync) サーバー**を開き、イベント ID = 30253 を検索します。
