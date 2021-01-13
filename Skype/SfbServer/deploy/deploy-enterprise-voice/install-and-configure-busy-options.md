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
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Skype for Business Server の通話中オプションをインストールおよび構成する

Skype for Business Server で通話中オプションをインストールおよび構成する方法について説明します。

通話中オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーで、ユーザーが既に通話中または電話会議中の場合や、通話を保留にした場合の着信の処理方法を構成できます。 新しい通話または着信呼び出しは、ビジー信号で拒否するか、ボイス メールに転送できます。

組織で [取り込み中オプション] が有効になっている場合、エンタープライズのすべてのユーザー (エンタープライズ VoIP ユーザーと エンタープライズ VoIP ユーザーの両方) は、次の構成オプションを使用できます。

- 取り込み中 - ユーザーがビジー状態の場合、新しい着信呼び出しがビジー信号で拒否されます。

- 通話中のボイスメール - ユーザーがビジー状態の場合に、新しい着信呼び出しがボイス メールに転送されます。

通話中オプションの構成方法に関係なく、通話中または電話会議中のユーザー、または通話が保留されているユーザーは、新しい通話や会議を開始する操作を妨げるものではありません。

通話中オプション機能の詳細については、「Skype for Business Server の通話中オプションを計画する [」を参照してください](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>インストール

Skype for Business Server の最新バージョンがインストール済みで、最新の修正プログラムがインストールされていることを確認します。 これを行うには、まずすべてのサービスを停止し、次のように Skype for Business Server 更新インストーラーを実行します。

1. 次のコマンドStop-CsWindowsServiceします。

2. プール内SkypeServerUpdateInstaller.exeフロント エンド サーバーで新しいインストーラーを実行します。

3. SBS でのフェールオーバーSkypeServerUpdateInstaller.exeサポートする場合は、各存続可能ブランチ サーバー (SBS) で新しいインストーラーを実行します。

インストーラーは、最新バージョンの取り込み中オプション アプリケーションを展開します。 ただし、アプリケーションは既定では有効になっていません。 アプリケーションを有効にするには、次の手順を実行します。

1. 次の [例に示すように、Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) コマンドレットを実行して、取り込み中オプションをグローバルに有効にします。

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 次に、サイトに音声ポリシーがある場合は、次のように音声ポリシーの通話中オプションを有効にする必要があります。

    まず [、Get-CsSite を実行して](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) サイトの名前を取得します。

   ```powershell
   Get-CsSite
   ```

    次のように、サイトの音声ポリシーを取得するには、Get-CsSite から取得した Identity 値 (Site:Redmond1 など) を使用します。

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    サイトに音声ポリシーが存在する場合は、次のコマンドを実行します。

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 次に [、New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) コマンドレットを実行して、次の例に示すように、サーバー アプリケーションの一覧に取り込み中オプションを追加します。

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > %FQDN% は、特定のプールの完全修飾ドメイン名に置き換える必要があります。

4. 次に [、Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) コマンドレットを実行して、次の例に示すように、取り込み中オプション コマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。

   ```powershell
   Update-CsAdminRole
   ```

5. 最後に [、Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) コマンドを実行して、通話中オプションがインストールされ、有効になっているすべてのプール内のすべてのフロントエンド サーバーで Skype for Business Server Windows サービスを開始します。

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>構成

取り込み中オプションを構成するには [、Set-CsBusyOptions コマンドレットを使用](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) します。

たとえば、次のコマンドは、ユーザー "Ken Myer" のビジー オプションを構成します。 この構成では、"Ken Myer" への呼び出しは、通話中にビジー信号を返します。

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

次の例では、コマンドはユーザー "Chrystal Velasquez" のビジー オプションを構成します。 この構成では、"Chrystal Velasquez" への新しい着信呼び出しは、通話中に既にボイス メールに転送されます。

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)コマンドレットを使用して、取り込み中オプションに関する構成情報を取得できます。 次の例では、"KenMyer@Contoso.com" の [取り込み中オプション] 設定を取得します。

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)コマンドレットを使用して、取り込み中オプションを削除できます。 次のコマンドは、"Ken Myer" の取り込み中オプションを削除します。

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

取り込み中オプションの構成に使用するコマンドレットの詳細については[、Set-CsBusyOptions、Get-CsBusyOptions、Remove-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)のテクニカル リファレンス コンテンツを参照してください。 [](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) [](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)

## <a name="enable-logging"></a>ログを有効にする

集中ログ サービスを使用して、取り込み中オプションのログを有効にするには、次を指定します。

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>確認とトラブルシューティング

取り込み中オプションをインストールした後 [、Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) コマンドレットを使用してサーバー アプリケーションの一覧を取得することで、インストールが成功したと確認できます。 取り込み中オプションが正しくインストールされている場合、コマンドレットの出力には、次のように、取り込み中オプションの構成が表示されます。

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

Windows イベント ビューアーを使用して、通話中オプションのインストールが成功し、Skype for Business Server が通話中オプションを正常に読み込んだか確認することもできます。 通話中オプションを確認するには、イベント ビューアー ( アプリケーションとサービス ログ **\> - Skype \> (または Lync) Server)** を開き、イベント ID = 30253 を検索します。
