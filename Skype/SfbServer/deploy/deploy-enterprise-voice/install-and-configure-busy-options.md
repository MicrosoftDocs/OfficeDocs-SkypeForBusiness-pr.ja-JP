---
title: Skype for Business Server のビジー オプションのインストールと構成
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
description: Skype for Business Server でビジー オプションをインストールして構成する方法について説明します。
ms.openlocfilehash: 04690e9f2c7fbf16b67432526fe5c8fd6e5b95af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106313"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Skype for Business Server のビジー オプションのインストールと構成

Skype for Business Server でビジー オプションをインストールして構成する方法について説明します。

ビジー オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーで、ユーザーが既に通話または会議に参加している場合、または通話が保留状態に設定されている場合の着信呼び出しの処理方法を構成できます。 新しい通話または着信呼び出しは、ビジー信号で拒否するか、ボイス メールに転送できます。

組織でビジー オプションが有効になっている場合は、エンタープライズのすべてのユーザー (エンタープライズ VoIP ユーザーと非ユーザーユーザーエンタープライズ VoIP、次の構成オプションを使用できます。

- Busy on Busy - ユーザーがビジー状態の場合、新しい着信呼び出しがビジーシグナルで拒否されます。

- [通話中のボイスメール] - ユーザーがビジー状態の場合、新しい着信通話がボイス メールに転送されます。

通話中のオプションの構成方法に関係なく、通話または会議のユーザー、または通話を保留にしているユーザーは、新しい通話や会議を開始しません。

ビジー オプション機能の詳細については [、「Plan for Busy Options for Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>インストール

Skype for Business Server の最新バージョンがインストール済みで、最新のパッチがインストールされていることを確認します。 これを行うには、まずすべてのサービスを停止し、次のように Skype for Business Server 更新プログラム インストーラーを実行します。

1. コマンドを実行Stop-CsWindowsServiceします。

2. プール内SkypeServerUpdateInstaller.exeフロント エンド サーバーで、新しいインストーラーを実行します。

3. SBS でのSkypeServerUpdateInstaller.exeサポートを確実に行う場合は、各存続可能ブランチ サーバー (SBS) でサーバー インストーラーを実行します。

インストーラーは、最新バージョンの Busy Options アプリケーションを展開します。 ただし、アプリケーションは既定では有効になっていません。 アプリケーションを有効にするには、次の手順を実行します。

1. [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps)コマンドレットを実行して、次の例に示すように、ビジー オプションをグローバルに有効にします。

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 次に、サイトに音声ポリシーが設定されている場合は、次のように音声ポリシーのビジー オプションを有効にする必要があります。

    最初に [、Get-CsSite を実行して](/powershell/module/skype/get-cssite?view=skype-ps) サイトの名前を取得します。

   ```powershell
   Get-CsSite
   ```

    次のように、Id 値 (例: Site:Redmond1) を使用して、Get-CsSiteの音声ポリシーを取得します。

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    サイトに音声ポリシーが存在する場合は、次のコマンドを実行します。

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 次に [、New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) コマンドレットを実行して、次の例に示すように、ビジー オプションをサーバー アプリケーションの一覧に追加します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > %FQDN% を特定のプールの完全修飾ドメイン名に置き換える必要があります。

4. 次に [、Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) コマンドレットを実行して、次の例に示すように、ビジー オプション コマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。

   ```powershell
   Update-CsAdminRole
   ```

5. 最後に [、Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) コマンドを実行して、Busy Options がインストールされ、有効にされたすべてのプール内のすべてのフロントエンド サーバーで Skype for Business Server Windows サービスを開始します。

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>構成

ビジー オプションを構成するには [、Set-CsBusyOptions コマンドレットを使用](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) します。

たとえば、次のコマンドは、ユーザー "Ken Myer" のビジー オプションを構成します。 この構成では、"Ken Myer" への呼び出しは、既に通話中のビジーシグナルを返します。

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

次の例では、コマンドはユーザー "Chrystal Velasquez" のビジー オプションを構成します。 この構成では、"Chrystal Velasquez" への新しい着信呼び出しは、既に通話中のボイス メールに転送されます。

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)コマンドレットを使用して、ビジー オプションに関する構成情報を取得できます。 次の使用例は、"ビジー オプション" の設定を KenMyer@Contoso.com します。

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[Remove-CsBusyOptions コマンドレット](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)を使用して、ビジー オプションを削除できます。 次のコマンドは、"Ken Myer" のビジー オプションを削除します。

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

ビジー オプションの構成に使用するコマンドレットの詳細については [、Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [、Get-CsBusyOptions、および Remove-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)のテクニカル リファレンス コンテンツを [参照](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)してください。

## <a name="enable-logging"></a>ログを有効にする

集中ログ サービスを使用してビジー オプションのログを有効にするには、次の値を指定します。

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>確認とトラブルシューティング

ビジー オプションのインストール後 [、Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) コマンドレットを使用してサーバー アプリケーションの一覧を取得することで、インストールが成功したと確認できます。 ビジー オプションが正しくインストールされている場合、コマンドレットの出力には次のようにビジー オプション構成が表示されます。

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

Windows イベント ビューアーを使用して、ビジー オプションのインストールが成功し、Skype for Business Server が正常に読み込まれたビジー オプションを確認することもできます。 ビジー オプションを確認するには、イベント ビューアー - アプリケーションログとサービス ログ - Skype (または **\> \> Lync) Server** を開き、イベント ID = 30253 を検索します。