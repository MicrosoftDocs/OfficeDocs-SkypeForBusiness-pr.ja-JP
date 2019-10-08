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
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Skype for Business Server の通話中オプションのインストールおよび構成

Skype for Business Server で取り込み中のオプションをインストールして構成する方法について説明します。

通話中オプションは、2016 年 7 月の累積更新プログラムで導入された新たなボイス ポリシーで、ユーザーが通話中や会議中の場合、または通話を保留にしている場合の着信処理方法を構成することができます。 着信があった場合に、話中音を流すかボイスメールに転送できます。

通話中オプションが組織で有効になっていれば、エンタープライズ VoIP を使用するユーザーも使用しないユーザーも、エンタープライズ中の全ユーザーが次の構成オプションを使用できます。

- 通話中に話中音 - 通話中に別の着信があると、話中音を流して着信を拒否します。

- 通話中にボイスメール - 通話中に別の着信があると、ボイスメールに転送します。

通話中オプションがどう構成されていても、通話中や会議中または通話を保留にしているユーザーが、新たな発信や会議を開始できなくなるわけではありません。  

通話中オプション機能の詳細については、「 [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)」を参照してください。

## <a name="install"></a>インストール 

最新バージョンの Skype for Business Server がインストールされていて、最新の更新プログラムがインストールされていることを確認してください。 これを行うには、まずすべてのサービスを停止してから、次のようにして Skype for Business Server 更新プログラムのインストーラーを実行します。

1. Stop-CsWindowsService コマンドを実行する。

2. プール内のフロントエンド サーバーごとに SkypeServerUpdateInstaller.exe インストーラを実行する。

3. 存続可能ブランチ サーバー (SBS) でのフェールオーバーをサポートしたい場合は、SBS ごとに SkypeServerUpdateInstaller.exe インストーラを実行する。

インストーラーによって通話中オプション アプリケーションの最新バージョンが展開されますが、アプリケーションは既定で有効ではありません。次の手順で有効にします。

1. 次の例に示すように、 [CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps)コマンドレットを実行して、ビジーオプションをグローバルに有効にします。

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 次に、サイトにボイス ポリシーがある場合は、次のようにボイス ポリシー用の通話中オプションを有効にします。

    最初に、[[次へ] を実行](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)して、サイトの名前を取得します。

   ```
   Get-CsSite
   ```

    Redmond1 サイトから取得した Id 値 (例: Site:) を使用して、次のようにサイトの音声ポリシーを取得します。

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    サイトのボイス ポリシーが存在していれば、次のコマンドを実行します。

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 次に、[新しい-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps)コマンドレットを実行して、次の例に示すように、サーバーアプリケーションの一覧に取り込み中のオプションを追加します。

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > % FQDN% は、特定のプールの完全修飾ドメイン名に置き換える必要があります。

4. 次に、次の例に示すように、[更新プログラム] と [ [CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) ] のコマンドレットを実行して、Busy オプションのコマンドレットの役割ベースのアクセス制御 (RBAC) の役割を更新します。

   ```
   Update-CsAdminRole
   ```

5. 最後に、Busy オプションがインストールされて有効になっているすべてのプール内のすべてのフロントエンドサーバーで、Skype for Business Server の Windows サービスを開始します。[次の操作](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)を実行します。

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>構成

通話中オプションを構成するには、[Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet を使用します。  

たとえば、次のコマンドは「Ken Myer」というユーザーの通話中オプションを構成します。この構成では、通話中に「Ken Myer」への着信があると話中音を返します。

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

その次の例では、コマンドが「Chrystal Velasquez」というユーザーの通話中オプションを構成します。 この構成では、通話中に着信があるとボイスメールに転送されます。

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet を使用して、通話中オプションに関する構成情報を取得できます。 次の例では、"KenMyer@Contoso.com" の [取り込み中] オプションの設定を返します。

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet を使用して、通話中オプションを削除できます。 次のコマンドは「Ken Myer」の通話中オプションを削除します。

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

Busy のオプションを構成するために使用するコマンドレットの詳細については、「 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)、および[Remove](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)のテクニカルリファレンスコンテンツ」を参照してください。

## <a name="enable-logging"></a>ログの有効化

集中ログ サービスを使用して通話中オプションのログを有効にするには、次のように指定します。

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>確認とトラブルシューティング

[取り込み中] オプションをインストールした後、ユーザーが正常にインストールされたことを確認するには、 [CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps)コマンドレットを使用してサーバーアプリケーションの一覧を取得します。 通話中オプションが正しくインストールされていれば、通話中オプション構成が次のように表示されます。

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

また、Windows イベントビューアーを使用して、取り込み中のオプションが正常にインストールされたこと、および Skype for Business Server で [取り込み中] オプションが正常に読み込まれたことを確認することもできます。 取り込み中のオプションを確認するには、イベントビューアーを開きます。 **\>アプリケーションとサービスログ\> -Skype (または Lync) サーバー**で、イベント ID = 30253 を検索します。
