---
title: Skype for Business Online Connector との接続の問題を診断する
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 0a5742c3e5c5681c9433d59b6a7464c8021ddc57
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Skype for Business Online Connector との接続の問題を診断する

[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID Server への接続の失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID モジュールへの接続の失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [ユーザーのログオンの失敗](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [Skype for Business Online でのこのテナントの同時シェルの最大数を超過している ](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
- **エラー**:*モジュールのインポート: ファイル c:\\プログラム ファイル\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 は、実行されているために、読み込むことができませんこのシステムでは、スクリプトが無効です。詳細についてを参照してくださいに about_Execution_Policieshttps://go.microsoft.com/fwlink/?LinkID=135170です*。

- **解像度**この問題を解決するには、管理者は、PowerShell を開始し、次のコマンドを実行します。
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。
  
  - **エラー**: インポート モジュールの*: '2.0' は、読み込まれた PowerShell のバージョンです。モジュール ' d:\\Program Files\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnector.psd1' を実行するには、'3.0' の最小 PowerShell バージョンが必要です。PowerShell のインストールを確認して再試行してください*。

- **解像度**: この問題を解決する唯一の方法は、Microsoft ダウンロード センターから入手可能ですが、Windows PowerShell 3.0 をインストールするのには、 [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID Server への接続の失敗
<a name="BKMKFailedConnect"> </a>

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。

  - **エラー**: *Get CsWebTicket: ライブ id サーバーの接続に失敗しました。プロキシが有効になっているマシンには、live id のサーバーへのネットワーク接続を確認します*。

- **解像度**: このエラーが Microsoft オンライン サービス サインイン アシスタントが実行されていないことを意味することがよくあります。 このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。 
    ```
    Get-Service "msoidsvc"
    ```
    サービスが実行していない場合は、このコマンドを使用して開始します。
    ```
    Start-Service "msoidsvc"
    ```

    サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。そこから Office 365 にログオンしてください。この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。
  
    稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。Office 365 サポートにお問い合わせください。
  
## <a name="failed-to-load-live-id-module"></a>Live ID モジュールへの接続の失敗
<a name="BKMKFailedLoad"> </a>

PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。

- **エラー**: *Get CsWebTicket: Live Id モジュールを読み込むことはできません。Live Id サインイン アシスタントのバージョンがインストールされている修正がいることを確認します*。

- **解像度**:「Microsoft オンライン サービス サインイン アシスタントは、 [Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナルの RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)に Microsoft ダウンロード センターで利用可能な

## <a name="logon-failed-for-the-user"></a>ユーザーのログオンの失敗
<a name="BKMKLogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。

- **エラー**: *Get CsWebTicket: 'kenmyer@litwareinc.com' のユーザーのログオンに失敗しました。正しいユーザー名とパスワードを使用していることを確認する、新しい PSCredential オブジェクトを作成してください*。

- **解像度**: ログオンし直して、正しいパスワードがあると、有効なユーザー アカウントを使用するいると思われる場合。 それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。 そこでもログオンできない場合は、Office 365 サポートにお問い合わせください。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>このテナントを管理する権限がユーザーにない
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーからのデータの処理は、次のエラー メッセージで失敗しました: ユーザー 'user@foo.com' には、このテナントを管理する権限はありません。適切な RBAC の役割にユーザーを割り当てることにより、アクセス許可を与えることができます。詳細については、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。

- **解決方法**: Office 365 のサポートに連絡する必要があります、または、テナント管理者グループのメンバーであることになっていることと思われる場合。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーからのデータの処理は、次のエラー メッセージで失敗しました: リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。このテナントのテナント Powershell のポリシーを確認するのには、Lync ヘルプにお問い合わせください。詳細については、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。

- **解決方法**: Office 365 のサポートに連絡し、PowerShell のリモート アクセスを有効にする必要がありますこのエラー メッセージが表示された場合。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。

- **エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーへの接続は、次のエラー メッセージで失敗しました:、WS-Management サービスは要求を処理できません。このユーザーの同時実行のシェルの最大数を超えています。既存のシェルを閉じるか、このユーザーのクォータを生成します。詳細については、[リモート トラブルシューティング] を参照してください (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解像度**: この問題を解決する唯一の方法は、1 つ以上の以前の接続を閉じることです。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者には 1つの Skype for Business Online テナントに対して 3 つの同時接続が許可されていますが、単一のテナントに許可されている同時接続は 9 つ以下です。たとえば、3 人の管理者それぞれが 3 つのセッションを開いているとします。4 人目の管理者が接続を確立しようとすると、結果として 10 の同時接続が発生するため、その管理者の接続は次のエラーメッセージにより失敗します。
  
- **エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーへの接続は、次のエラー メッセージで失敗しました:、WS-Management サービスは要求を処理できません。このテナントの同時シェルの最大数を超えています。既存のシェルを閉じるか、このテナントのクォータを生成します。詳細については、[リモート トラブルシューティング] を参照してください (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解像度**: この問題を解決する唯一の方法は、1 つ以上の以前の接続を閉じることです。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。  
 
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
[Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します](set-up-your-computer-for-windows-powershell.md)

  
 
