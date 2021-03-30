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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: b7cc45c0ea09c254f05d1cdd7609faea8877f299
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418745"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Skype for Business Online Connector との接続の問題を診断する

[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [WinRM Basic 認証が無効になっていると、モダン認証が失敗する](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Live ID Server への接続の失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID モジュールへの接続の失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [ユーザーのサインインに失敗しました](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Skype for Business Online のこのユーザーの同時シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Skype for Business Online のこのテナントの同時シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> 既定では、PowerShell セッションは 60 分後にタイムアウトします。 再接続するには、セッションを閉じて、新しい PowerShell セッションを起動する必要があります。 Skype for Business Online の新しいバージョンの [Windows PowerShell モジュール (2046.123 - 公開日: 2019/10/2)](https://www.microsoft.com/download/details.aspx?id=39366)が最近開始されました。これには、60 分間のタイムアウトの問題を軽減する **Enable-CsOnlineSessionForReconnection** という新しいコマンドレットが含まれています。
> PowerShell セッションは再接続と認証を行い、再接続するために新しいインスタンスを起動することなく再使用できます。



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
- **エラー**: <em>Import-Module : File C: \\ Program Files Common Files Microsoft Lync Server \\ \\ 2013 \\ Modules \\ \\ LyncOnlineConnector LyncOnlineConnectorStartup.psm1 は、このシステムで実行中のスクリプトが無効になっているため、読み込む必要があります。詳細については、次のabout_Execution_Policies参照してください https://go.microsoft.com/fwlink/?LinkID=135170 。</em>

- **解像度** この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーの詳細については、「[実行ポリシーについて](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。 以前のバージョンの PowerShell でモジュールをインポートすると、次のようなエラー メッセージが表示されたインポート プロセスは失敗します。
  
  - **エラー**: Import-Module: 読み込まれた PowerShell のバージョン *は '2.0' です。モジュール 'D: プログラム ファイルの共通ファイル \\ \\ Microsoft Lync Server \\ 2013 \\ モジュール \\ LyncOnlineConnectorLyncOnlineConnector.psd1' の実行には \\ 、最小 PowerShell バージョンの '3.0' が必要です。PowerShell のインストールを確認して、もう一度お試しください。*

- **解決** 方法: この問題を解決する唯一の方法は、microsoft ダウンロード センターからWindows PowerShell 3.0 をインストールすることです [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>WinRM Basic 認証が無効になっていると、モダン認証が失敗する
<a name="BKMKWinRMBasicAuth"> </a>

Skype for Business Online Connector モジュールの最新バージョンでは、最新の認証が使用されますが、基本認証を許可するように、基になる Windows リモート管理 (WinRM) クライアントを構成する必要があります。  最新の認証では、通常は Authorization: Bearer ヘッダーで渡される *、Bearer トークンを使用* します。 Windows PowerShell Skype for Business PowerShell を作成する場合、このヘッダーの操作は許可されません。  代わりに、Skype for Business PowerShell は承認 *:* 基本ヘッダーを使用して、担い手トークンを渡します。

WinRM [for Basic 認証を有効Windows PowerShell](./download-and-install-windows-powershell-5-1.md) 方法については、「ダウンロードしてインストールする」を参照してください。

## <a name="failed-to-connect-to-live-id-server"></a>Live ID Server への接続の失敗
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Skype for Business Online Connector のライブ ID 認証は廃止されました。 Teams PowerShell モジュールを使用して、オンライン テナントを管理します。 ハイブリッド環境を管理する場合は、最新の累積的な更新プログラムにアップグレードするか、oAuth 認証を使用します。

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。

  - **エラー**: *Get-CsWebTicket : ライブ ID サーバーの接続に失敗しました。プロキシが有効になっているか、マシンがライブ ID サーバーへのネットワーク接続を持つ必要があります。*

- **解決** 方法: 多くの場合、このエラーは、Microsoft Online Servicesアシスタントが実行されていない場合を意味します。 このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    サービスが実行していない場合は、このコマンドを使用して開始します。
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。 この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。 そこから Microsoft 365 または Office 365 にログオンしてみてください。 この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。
  
    稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。 サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。 この場合は、Microsoft サポートにお問い合わせください。
  
## <a name="failed-to-load-live-id-module"></a>Live ID モジュールへの接続の失敗
<a name="BKMKFailedLoad"> </a>

PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。

- **エラー**: *Get-CsWebTicket : Live ID モジュールを読み込めない。正しいバージョンの Live Id サインイン アシスタントがインストールされていることを確認します。*

- **解決** 方法: Microsoft Online Services サインイン アシスタントは、MICROSOFT ダウンロード センターの IT プロフェッショナル向け [Microsoft Online Services Sign-In RTW で利用できます](https://www.microsoft.com/download/details.aspx?id=28177)。

## <a name="logon-failed-for-the-user"></a>ユーザーのログオンの失敗
<a name="BKMKLogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。 そうしない場合、次のメッセージのようなエラー メッセージと共にログオンは失敗します。

- **エラー**: *Get-CsWebTicket : ユーザーの 'kenmyer@litwareinc.com' に対するログオンに失敗しました。新しい PSCredential オブジェクトを作成し、正しいユーザー名とパスワードを使用していることを確認します。*

- **解決** 方法: 有効なユーザー アカウントを使用し、正しいパスワードを持っている場合は、もう一度ログオンしてみてください。 失敗した場合は、同じ資格情報を使用してサインインしてみてください [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。 サインインできない場合は、Microsoft サポートにお問い合わせください。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>このテナントを管理する権限がユーザーにない
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました。ユーザー 'user@foo.com' には、このテナントを管理するアクセス許可が与え込みではありません。 *適切な RBAC ロールにユーザーを割り当てると、アクセス許可を付与できます。詳細については、リモートトラブルシューティング [を参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解決** 方法: テナント管理者グループのメンバーである、またはメンバーであるはずと考える場合は、Microsoft サポートに問い合わせてください。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。Lync ヘルプに問い合わせ、このテナントのテナント PowerShell ポリシーを確認します。詳細については、リモートトラブルシューティング [を参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解決** 方法: このエラー メッセージが表示された場合は、Microsoft サポートに問い合わせ、リモート PowerShell アクセスを有効にする必要があります。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。

- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました:WS-Management サービスは要求を *処理できません。このユーザーの同時シェルの最大数を超えました。既存のシェルを閉じるか、このユーザーのクォータを上げる。詳細については、[リモート トラブルシューティング] を参照してください https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 。*

- **解決** 方法: この問題を解決する唯一の方法は、1 つ以上の前の接続を閉じる方法です。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者は、Skype for Business Online テナントへの同時接続を最大 3 つまで許可しますが、20 を超える同時接続を持つ 1 つのテナントは許可されません。 たとえば、6 人の管理者がそれぞれ 3 つのオープン セッションを持っている場合があります。 4 人目の管理者が 3 つ以上の接続を行う場合 (その結果、21 の同時接続が発生します)、この試行は失敗し、次のエラー メッセージが表示されます。
  
- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました。WS-Management サービスは要求を *処理できません。このテナントの同時シェルの最大数を超えました。既存のシェルを閉じるか、このテナントのクォータを上げる。詳細については、[リモート トラブルシューティング] を参照してください https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 。*

- **解決** 方法: この問題を解決する唯一の方法は、1 つ以上の前の接続を閉じる方法です。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。  
 
## <a name="related-topics"></a>関連項目
[Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
