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
f1keywords: None
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 38f6195a6c8e0c2a5f963d476e26abeb46f6ff4f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991322"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Skype for Business Online Connector との接続の問題を診断する

[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID Server への接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID モジュールへの接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [ユーザーのログオンの失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Skype for Business Online でのこのテナントの同時シェルの最大数を超過している](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
- **エラー**:<em>インポート-モジュール: ファイル C:\\プログラムファイル\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnectorStartup は、このシステムで実行中のスクリプトが無効になっているため、読み込めません。詳細については、「 https://go.microsoft.com/fwlink/?LinkID=135170about_Execution_Policies」を参照してください。</em>

- **解決策**: この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。
  
  - **エラー**:*インポート-モジュール: 読み込まれた PowerShell のバージョンは ' 2.0 ' です。このモジュールでは\\、Program\\Files の\\一般的なファイル Microsoft\\Lync\\Server\\2013 モジュール LyncOnlineConnector LyncOnlineConnector ' を実行するには、少なくとが PowerShell バージョンの ' 3.0 ' が必要です。PowerShell のインストールを確認して、もう一度やり直してください。*

- **解決策**: この問題を解決するには、Microsoft ダウンロードセンターから入手できる Windows PowerShell 3.0 をインストールする方法しか[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)ありません。
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID Server への接続の失敗
<a name="BKMKFailedConnect"> </a>

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。

  - **エラー**: *Get-cswebticket: live id サーバーへの接続に失敗しました。プロキシが有効になっていることを確認するか、マシンに live id サーバへのネットワーク接続があることを確認します。*

- **解決策**: 多くの場合、このエラーは Microsoft Online Services サインインアシスタントが実行されていないことを意味します。 このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    サービスが実行していない場合は、このコマンドを使用して開始します。
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。そこから Office 365 にログオンしてください。この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。
  
    稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。Office 365 サポートにお問い合わせください。
  
## <a name="failed-to-load-live-id-module"></a>Live ID モジュールへの接続の失敗
<a name="BKMKFailedLoad"> </a>

PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。

- **エラー**: *Get-Cswebticket: Live Id モジュールを読み込むことができません。正しいバージョンの Live Id サインインアシスタントがインストールされていることを確認します。*

- **解決**方法: microsoft Online services サインインアシスタントは、 [it プロフェッショナル向けの Microsoft Online SERVICES サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123](https://www.microsoft.com/en-us/download/details.aspx?id=28177)を参照してください。

## <a name="logon-failed-for-the-user"></a>ユーザーのログオンの失敗
<a name="BKMKLogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。

- **エラー**: *Get-cswebticket: ユーザー ' Kenmyer@litwareinc.com ' のログオンに失敗しました。新しい PSCredential オブジェクトを作成して、正しいユーザー名とパスワードを使用していることを確認してください。*

- **解決策**: 有効なユーザーアカウントを使用していて、正しいパスワードを持っていると思われる場合は、もう一度ログインしてみてください。 それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。 そこでもログオンできない場合は、Office 365 サポートにお問い合わせください。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>このテナントを管理する権限がユーザーにない
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。ユーザー ' user@foo.com ' にはこのテナントを管理する権限がありません。権限を付与するには、適切な RBAC の役割をユーザーに割り当てます。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*

- **解決策**: テナント管理者グループのメンバーであると考えられる場合は、Office 365 サポートに連絡する必要があります。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。

- **エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になりました。このテナントのテナント Powershell ポリシーを確認するには、Lync のヘルプにお問い合わせください。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*

- **解決策**: このエラーメッセージが表示される場合は、Office 365 サポートに連絡して、リモート PowerShell アクセスを有効にする必要があります。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。

- **エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このユーザーの同時シェルの最大数を超過しています。このユーザーの既存のシェルを閉じるか、またはクォータを増やします。詳細については、「[リモートトラブルシューティングhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。

- **解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者には 1つの Skype for Business Online テナントに対して 3 つの同時接続が許可されていますが、単一のテナントに許可されている同時接続は 9 つ以下です。たとえば、3 人の管理者それぞれが 3 つのセッションを開いているとします。4 人目の管理者が接続を確立しようとすると、結果として 10 の同時接続が発生するため、その管理者の接続は次のエラーメッセージにより失敗します。
  
- **エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このテナントの同時シェルの最大数を超過しています。既存のシェルを閉じるか、このテナントのクォータを上げます。詳細については、「[リモートトラブルシューティングhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。

- **解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。 Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。 そうすることにより、この問題が発生することを防ぐことができます。  
 
## <a name="related-topics"></a>関連項目
[Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする](set-up-your-computer-for-windows-powershell.md)

  
 
