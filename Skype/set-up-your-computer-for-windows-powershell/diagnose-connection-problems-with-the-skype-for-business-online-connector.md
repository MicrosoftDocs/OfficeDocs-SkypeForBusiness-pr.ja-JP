---
title: "Skype for Business Online Connector との接続の問題を診断する"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Skype for Business Online Connector との接続の問題を診断する

このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_PowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_IncorrectVersion)
    
- [Live ID Server への接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedConnect)
    
- [Live ID モジュールへの接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedLoad)
    
- [ユーザーのログオンの失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_LogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_UserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_AbilityConnect)
    
- [Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [Skype for Business Online でのこのテナントの同時シェルの最大数を超過している ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMK_PowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

この問題を解決するには、管理者として PowerShell を開始し、次のコマンドを実行します。
  
```
Set-ExecutionPolicy RemoteSigned
```

実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。
  
## Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMK_IncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

この問題を解決する唯一の方法は、[http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939) の Microsoft ダウンロード センター から入手できる Windows PowerShell 3.0 をインストールすることです。
  
## Live ID Server への接続の失敗
<a name="BKMK_FailedConnect"> </a>

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

通常、このエラーは Microsoft Online Services サインイン アシスタント が実行していない場合に発生します。このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。
  
```
Get-Service "msoidsvc"
```

サービスが実行していない場合は、このコマンドを使用して開始します。
  
```
Start-Service "msoidsvc"
```

サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。そこから Office 365 にログオンしてください。この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。
  
稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。Office 365 サポートにお問い合わせください。
  
## Live ID モジュールへの接続の失敗
<a name="BKMK_FailedLoad"> </a>

PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

Microsoft Online Services サインイン アシスタント は、[IT プロフェッショナル 用 Microsoft Online Services サインイン アシスタント RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)の Microsoft ダウンロード センター から入手できます。
  
## ユーザーのログオンの失敗
<a name="BKMK_LogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

有効なユーザー アカウントと正しいパスワードを使用している場合は、再度ログオンを行ってください。それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。そこでもログオンできない場合は、Office 365 サポートにお問い合わせください。
  
## このテナントを管理する権限がユーザーにない
<a name="BKMK_UserPermission"> </a>

テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

テナント管理者グループのメンバーであると考えられる場合や、そうであると想定される場合は、Office 365 サポートにお問い合わせください。
  
## テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMK_AbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

このエラー メッセージが表示される場合は、Office 365 サポートに問い合わせて、リモート PowerShell アクセスを有効化してもらう必要があります。
  
## Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMK_MaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

この問題を解決するための唯一の方法は、それ以前の接続を 1 つ以上閉じることです。Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。そうすることにより、この問題が発生することを防ぐことができます。
  
## Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMK_MaxNumberShellsTenant"> </a>

各管理者には 1つの Skype for Business Online テナントに対して 3 つの同時接続が許可されていますが、単一のテナントに許可されている同時接続は 9 つ以下です。たとえば、3 人の管理者それぞれが 3 つのセッションを開いているとします。4 人目の管理者が接続を確立しようとすると、結果として 10 の同時接続が発生するため、その管理者の接続は次のエラーメッセージにより失敗します。
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

この問題を解決するための唯一の方法は、それ以前の接続を 1 つ以上閉じることです。Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。そうすることにより、この問題が発生することを防ぐことができます。
  

