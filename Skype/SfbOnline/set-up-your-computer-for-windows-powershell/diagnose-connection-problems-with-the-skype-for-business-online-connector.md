---
title: "ビジネス Online コネクタの Skype の接続に関する問題を診断します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Skype for Business Online、インポート モジュール、同時シェル、Live ID では、アクセス許可のエラーを含むに接続するリモート PowerShell セッションを作成するトラブルシューティングを行います。"
ms.openlocfilehash: b98acefed673c08f6b986055fafef82847902f1a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>ビジネス Online コネクタの Skype の接続に関する問題を診断します。

ここでは、診断およびリモート Skype for Business Online に接続する Microsoft PowerShell セッションを作成しようとしたときに発生する可能性がある問題を解決するうえで役立つ情報を紹介します。次のセクションを参照してください。
  
- [Windows PowerShell 実行ポリシーによるインポート モジュール エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [不適切なバージョンの Windows PowerShell によるインポート モジュール エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID サーバーへの接続に失敗しました。](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID モジュールの読み込みに失敗しました。](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [ログオン ユーザー用に失敗しました。](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [ユーザーには、このテナントを管理する権限がないです。](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能は skype for Business Online を無効になっています。](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Skype for Business Online では、このユーザーの同時シェルの最大数を超えています](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Skype for Business Online では、このテナントの同時シェルの最大数を超えています](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによるインポート モジュール エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーにより、PowerShell コンソールにロードできる構成ファイルを確認して、コンソールからユーザー スクリプトを実行できます。最低でも、実行ポリシーが RemoteSigned に設定されていない限り、Skype for Business Online コネクタ モジュールをインポートできません。されない場合は、モジュールをインポートしようとしたときに、次のエラー メッセージが受信されます。
  
- **エラー**:*インポート モジュール: ファイル c:\\Program Files\\一般的なファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\実行されているために、LyncOnlineConnectorStartup.psm1 を読み込むことができませんこのシステムでは、スクリプトが無効にします。詳細については、https://go.microsoft.com/fwlink/?LinkID=135170 で about_Execution_Policies を参照してください*。

- **解決方法**この問題を解決するには、管理者は、PowerShell を起動し、[次のコマンドを実行します。
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーについての詳細については、[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>不適切なバージョンの Windows PowerShell によるインポート モジュール エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online コネクタ モジュールは、Windows PowerShell 3.0 でのみ実行できます。以前のバージョンの PowerShell モジュールをインポートしようとした場合、インポート プロセスは次のようなエラー メッセージが失敗します。
  
  - **エラー**:*インポート モジュール: 読み込まれた PowerShell のバージョンが '2.0' します。モジュール ' d:\\Program Files\\一般的なファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnector.psd1' を実行するには、'3.0' の最小 PowerShell バージョンが必要です。[PowerShell のインストールを確認して、再試行してください*。

- **解決方法**: 対象と[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)に Microsoft ダウンロード センターから、Windows PowerShell 3.0 をインストールするのには、この問題を解決するしかします。
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID サーバーへの接続に失敗しました。
<a name="BKMKFailedConnect"> </a>

通常は、次のエラー メッセージと、接続が失敗する理由 3 つの理由が考えられます。

  - **エラー**: *Get CsWebTicket: live id サーバーの接続に失敗しました。プロキシを有効にするか、コンピューターがネットワーク接続が id サーバーことを確認します*。

- **解決方法**: 多くの場合、このエラーでは Microsoft Online Services サインイン アシスタントが実行されていないことを意味します。このサービスの状態を確認するには、PowerShell のプロンプトで、次のコマンドを実行します。 
    ```
    Get-Service "msoidsvc"
    ```
    サービスが実行されていない場合は、このコマンドを使用して、サービスを開始します。
    ```
    Start-Service "msoidsvc"
    ```

    場合は、サービスを実行すると、お使いのコンピューターと Microsoft Live ID 認証サーバー間でネットワーク接続を使って問題を発生する可能性があります。これを確認するには、Internet Explorer を開きに移動する[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) 。そこから Office 365 にログインしてみてください。これが失敗した場合は、おそらくネットワーク接続の問題を発生しています。
  
    あまり一般的には、Microsoft Live ID 認証サーバーの接続 URI が間違った値に設定されていることができます。場合は、サインイン アシスタントが実行されていると、そのネットワーク接続の問題が発生しない、問題がありますを既に決定します。この例では、Office 365 のサポートに問い合わせてください。
  
## <a name="failed-to-load-live-id-module"></a>Live ID モジュールの読み込みに失敗しました。
<a name="BKMKFailedLoad"> </a>

Skype for Business Online の管理に PowerShell を使用するための前提条件のいずれかは、Microsoft Online Services サインイン アシスタントをインストールします。サインイン アシスタントがインストールされていない場合は、for Business Online の Skype とのリモート セッションを確立しようとしたときに次のエラー メッセージが表示されます。

- **エラー**: *Get CsWebTicket: Live Id モジュールを読み込むことはできません。Live のサインイン時のアシスタントのバージョンがインストールされている修正はことを確認します*。

- **解決方法**: は、「Microsoft Online Services サインイン アシスタントを[Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW 用](https://www.microsoft.com/en-us/download/details.aspx?id=28177)に Microsoft ダウンロード センターからインストールできる

## <a name="logon-failed-for-the-user"></a>ログオン ユーザー用に失敗しました。
<a name="BKMKLogonFailed"> </a>

Skype for Business Online リモート接続を作成しようとすると、ユーザー名とパスワードの有効な Skype for Business Online のユーザー アカウントを指定する必要があります。されない場合は、次のようなエラー メッセージとログオンは失敗します。

- **エラー**: *Get CsWebTicket: 'kenmyer@litwareinc.com' のユーザーのログオンに失敗しました。正しいユーザー名とパスワードを使用していることを確認、新しい PSCredential オブジェクトを作成してください*。

- **解決方法**: ログオンし直して、正しいパスワードと有効なユーザー アカウントを使用するいると思われる場合があります。失敗した場合、同じ資格情報を使用し、 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)にログオンしようとしてください。ログオンが存在しない場合は、Office 365 のサポートに問い合わせてください。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>ユーザーには、このテナントを管理する権限がないです。
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバーになっている場合を除き、for Business Online リモート PowerShell 接続 toSkype を作成することはできません。ではない場合、接続の試行が失敗し、次のエラー メッセージが表示されます。

- **エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗しました: 'user@foo.com' のユーザーには、このテナントを管理する権限がないです。RBAC の役割を適切なユーザーに割り当てることにより、アクセス許可を付与できます。詳細については、[リモートのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。

- **解決方法**: された、またはするには、テナント管理者グループのメンバーになっていると思われる場合は、Office 365 のサポートに連絡する必要があります。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能は skype for Business Online を無効になっています。
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して、Skype for Business Online の管理] には、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティに設定する必要があります`True`します。ない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗しました: リモート PowerShell セッションを使用してこのテナントに接続する機能を無効になっています。このテナントのテナント Powershell ポリシーを確認する Lync ヘルプにお問い合わせください。詳細については、[リモートのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。

- **解決方法**: このエラー メッセージが表示された場合は、Office 365 のサポートに連絡し、リモート PowerShell アクセスが有効にする必要があります。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online では、このユーザーの同時シェルの最大数を超えています
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、最大 3 つ同時リモート接続 Skype for Business Online のことを許可します。3 つのリモート PowerShell 接続をセットアップし、実行して、4 番目を同時に作成しようとするがある場合、次のエラー メッセージが、その接続は失敗します。

- **エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗しました: [受け取りましたサービス要求を処理できません。このユーザーの同時シェルの最大数を超えています。既存のシェルを閉じるか、このユーザーのクォータが発生します。詳細については、次を参照してください、[リモート トラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* 。

- **解決方法**: 1 つ以上の以前の接続を閉じるには、この問題を解決するのにはしかします。完了したら、skype for Business Online のセッション、セッションを終了する、**削除 PSSession**コマンドレットを使用することをお勧めします。この問題を回避することが役立ちます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online では、このテナントの同時シェルの最大数を超えています
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者を Skype for Business Online のテナントに同時に 3 つの接続を許可するのでは、9 個を超える同時に接続する単一のテナントは許可されません。たとえば、次の 3 つの管理者の各があります開かれている 3 つのセッション。4 番目の管理者は、(10 同時接続の合計のようになります) に接続しようとすると、このは失敗します、次のエラー メッセージ。
  
- **エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗しました: [受け取りましたサービス要求を処理できません。このテナントの同時シェルの最大数を超えています。既存のシェルを閉じるか、このテナントのクォータが発生します。詳細については、次を参照してください、[リモート トラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* 。

- **解決方法**: 1 つ以上の以前の接続を閉じるには、この問題を解決するのにはしかします。完了したら、skype for Business Online のセッション、セッションを終了する、**削除 PSSession**コマンドレットを使用することをお勧めします。この問題を回避することが役立ちます。  
 
## <a name="related-topics"></a>関連トピック
[Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。](set-up-your-computer-for-windows-powershell.md)

