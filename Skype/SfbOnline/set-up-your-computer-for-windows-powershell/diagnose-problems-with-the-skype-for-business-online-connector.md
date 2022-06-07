---
title: Skype for Business Online Connector との接続の問題を診断する
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913395"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Skype for Business Online Connector との接続の問題を診断する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [WinRM Basic 認証が無効になっていると、先進認証が失敗する](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Live ID Server への接続の失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [ユーザーのサインインに失敗しました](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Skype for Business Online のこのユーザーの同時シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Skype for Business Online のこのテナントの同時シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
- **エラー**: <em>Import-Module : ファイル C:\\Program Files Common Files\\\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 を読み込めません。実行中のスクリプトはこのシステムで無効になっているためです。詳細については、次のabout_Execution_Policieshttps://go.microsoft.com/fwlink/?LinkID=135170を参照してください。</em>

- **解像 度** この問題を解決するには、PowerShell を管理者として起動し、次のコマンドを実行します。
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーの詳細については、「[実行ポリシーについて](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。 以前のバージョンの PowerShell でモジュールをインポートしようとすると、インポート プロセスは失敗し、次のようなエラー メッセージが表示されます。
  
  - **エラー**: *Import-Module: 読み込まれた PowerShell のバージョンは '2.0' です。モジュール 'D:\\Program Files Common Files\\\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' を実行するには、最小 PowerShell バージョンの '3.0' が必要です。PowerShell のインストールを確認し、もう一度試してください。*

- **解決策**: この問題を解決する唯一の方法は、Microsoft ダウンロード センター [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)から入手できる Windows PowerShell 3.0 をインストールすることです。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>WinRM Basic 認証が無効になっていると、先進認証が失敗する
<a name="BKMKWinRMBasicAuth"> </a>

Skype for Business Online Connector モジュールの最新バージョンでは先進認証が使用されますが、基本認証を許可するように基になる Windows リモート管理 (WinRM) クライアントを構成する必要があります。  先進認証ではベアラー トークンが使用され、通常は *Authorization: Bearer* ヘッダーに渡されます。 Skype for Business PowerShell が構築されている Windows PowerShell では、このヘッダーの操作は許可されません。  代わりに、Skype for Business PowerShell は *Authorization: Basic* ヘッダーを使用してベアラー トークンを渡します。

基本認証で WinRM を有効にする方法については、 [Windows PowerShell のダウンロードとインストール](./download-and-install-windows-powershell-5-1.md) に関するページを参照してください。

## <a name="failed-to-connect-to-live-id-server"></a>Live ID Server への接続の失敗
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Skype For Business オンライン コネクタのライブ ID 認証は非推奨になりました。 Teams PowerShell モジュールを使用して、オンライン テナントを管理します。 ハイブリッド環境を管理する場合は、最新の累積的な更新プログラムにアップグレードするか、oAuth 認証を使用します。

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。

  - **エラー**: *Get-CsWebTicket : ライブ ID サーバーの接続に失敗しました。プロキシが有効になっているか、マシンがライブ ID サーバーにネットワーク接続されていることを確認します。*

- **解決策**: 多くの場合、このエラーは、Microsoft Online Services サインイン アシスタントが実行されないことを意味します。 このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    サービスが実行していない場合は、このコマンドを使用して開始します。
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。 この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。 そこから Microsoft 365 または Office 365 にログオンしてみてください。 この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。
  
    稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。 サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。 この場合は、Microsoft サポートにお問い合わせください。
  
## <a name="logon-failed-for-the-user"></a>ユーザーのログオンの失敗
<a name="BKMKLogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。 そうしないと、次のようなエラー メッセージと共にログオンが失敗します。

- **エラー**: *Get-CsWebTicket : ユーザー 'kenmyer@litwareinc.com' のログオンに失敗しました。新しい PSCredential オブジェクトを作成し、正しいユーザー名とパスワードを使用していることを確認します。*

- **解決策**: 有効なユーザー アカウントを使用していて、正しいパスワードを持っていると思われる場合は、もう一度ログオンしてください。 失敗した場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/)、 . サインインできない場合は、Microsoft サポートにお問い合わせください。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>このテナントを管理する権限がユーザーにない
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバーからのデータの処理 admin.vdomain.com 失敗し、次のエラー メッセージが表示されました。ユーザー 'user@foo.com' には、このテナントを管理するアクセス許可がありません。適切な RBAC ロールにユーザーを割り当てることで、アクセス許可を付与できます。詳細については、 [リモートトラブルシューティング](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )を参照してください。*

- **解決策**: テナント管理者グループのメンバーであると思われる場合、またはテナント管理者グループのメンバーであると思われる場合は、Microsoft サポートに問い合わせる必要があります。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバーからのデータの処理 admin.vdomain.com 失敗し、次のエラー メッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。このテナントのテナント PowerShell ポリシーを確認するには、Lync ヘルプにお問い合わせください。詳細については、 [リモートトラブルシューティング](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )を参照してください。*

- **解決策**: このエラー メッセージが表示された場合は、Microsoft サポートに問い合わせ、リモートの PowerShell アクセスを有効にする必要があります。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。 

- **エラー**: *New-PSSession : [admin.vdomain.com] 次のエラー メッセージでリモート サーバーへの接続 admin.vdomain.com 失敗しました: WS-Management サービスは要求を処理できません。このユーザーの同時シェルの最大数を超えました。既存のシェルを閉じるか、このユーザーのクォータを引き上げます。詳細については、 [リモートトラブルシューティング](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )を参照してください。*

- **解決策**: この問題を解決する唯一の方法は、前の接続の 1 つ以上を閉じることです。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者は、Skype for Business Online テナントに対して最大 3 つの同時接続を許可されていますが、1 つのテナントに 20 を超える同時接続を許可することはできません。 たとえば、6 人の管理者がそれぞれ 3 つのオープン セッションを持つ場合があります。 4 番目の管理者が 2 つ以上の接続を試行すると (合計 21 個の同時接続が発生します)、この試行は失敗し、次のエラー メッセージが表示されます。
  
- **エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバーへの接続 admin.vdomain.com 失敗し、次のエラー メッセージが表示されました。WS-Management サービスは要求を処理できません。このテナントの同時シェルの最大数を超えました。既存のシェルを閉じるか、このテナントのクォータを引き上げます。詳細については、 [リモートトラブルシューティング](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )を参照してください。*

- **解決策**: この問題を解決する唯一の方法は、前の接続の 1 つ以上を閉じることです。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。  
 
## <a name="related-topics"></a>関連項目
[Windows PowerShell を使用して Skype for Business オンライン管理用にコンピューターを設定する](set-up-your-computer-for-windows-powershell.md)

  
