---
title: Skype for Business Online Connector で接続の問題を診断する
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
description: Import-Module、コンカレント シェル、Live ID、アクセス許可エラーなど、Skype for Business Online に接続するためのリモート PowerShell セッションの作成に関するトラブルシューティングを行います。
ms.openlocfilehash: 81b612b8b3e2ab82f0986110b2aa612fafe6402f
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58407016"
---
# <a name="diagnose-connection-problems-in-the-skype-for-business-online-connector"></a>Skype for Business Online Connector で接続の問題を診断する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。
  
- [Windows PowerShell 実行ポリシーによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell の不正なバージョンによる Import-Module エラー](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID Server への接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID モジュールへの接続の失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [ユーザーのログオンの失敗](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [このテナントを管理する権限がユーザーにない](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [テナントに接続する機能が Skype for Business Online で無効化されている](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [Skype for Business Online でのこのユーザーの同時シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Skype for Business Online でこのテナントの同時実行シェルの最大数を超えました](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 実行ポリシーによる Import-Module エラー
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。 少なくとも、実行ポリシーが RemoteSigned に設定されていない限り、Skype for Business Online Connector モジュールをインポートできます。 インポートされていない場合は、モジュールをインポートしようとすると、次のエラー メッセージが表示されます。
  
- **エラー**: <em>Import-Module : File C: \\ Program Files Common Files Microsoft Lync Server \\ \\ 2013 \\ Modules \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 は、このシステムで実行中のスクリプトが無効になっているため、読み込めないことです。詳細については、 を参照about_Execution_Policiesしてください https://go.microsoft.com/fwlink/?LinkID=135170 。</em>

- **解決策**: この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    実行ポリシーの詳細については、「[実行ポリシーについて](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Windows PowerShell の不正なバージョンによる Import-Module エラー
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。 以前のバージョンの PowerShell でモジュールをインポートすると、インポート プロセスは失敗し、次のようなエラー メッセージが表示されます。
  
  - **エラー**: *Import-Module : 読み込まれた PowerShell のバージョンは '2.0' です。モジュール 'D: \\ Program Files Common Files Microsoft Lync Server \\ \\ 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' を実行するには、PowerShell の最小バージョン \\ '3.0' が必要です。PowerShell のインストールを確認して、もう一度やり直してください。*

- **解決策**: この問題を解決する唯一の方法は、Microsoft ダウンロード センター () からWindows PowerShell 3.0 をインストールすることです [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 。
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID Server への接続の失敗
<a name="BKMKFailedConnect"> </a>

次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。

  - **エラー**: *Get-CsWebTicket : ライブ ID サーバーの接続に失敗しました。プロキシが有効になっているか、マシンがライブ ID サーバーにネットワーク接続を持つ必要があります。*

- **解決策**: 多くの場合、このエラーは、Microsoft Online Services アシスタントが実行されていない状態を意味します。 このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    サービスが実行されていない場合は、次のコマンドを使用してサービスを開始します。
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。 この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。 そこから、Microsoft 365またはOffice 365を試してください。 できない場合は、ネットワーク接続の問題が発生している可能性があります。
  
    あまり一般的には、Microsoft Live ID Authentication Server の接続 URI が正しい値に構成されていない可能性があります。 Sign-In Assistant が実行され、ネットワークの問題が発生していないと既に判断している場合は、この構成が問題である可能性があります。 この場合は、Microsoft サポートにお問い合わせください。
  
## <a name="failed-to-load-live-id-module"></a>Live ID モジュールへの接続の失敗
<a name="BKMKFailedLoad"> </a>

PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。 サインイン アシスタントがインストールされていない場合は、Skype for Business Online とのリモート セッションを確立しようとするときに、次のエラー メッセージが表示されます。

- **エラー**: *Get-CsWebTicket : Live Id モジュールを読み込めない。正しいバージョンの Live Id サインイン アシスタントがインストールされていることを確認します。*

- **解決策**: Microsoft Online Services サインイン アシスタントは、MICROSOFT ダウンロード センターの it プロフェッショナル向け Microsoft Online Services Sign-In [RTW で利用できます。](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>ユーザーのログオンの失敗
<a name="BKMKLogonFailed"> </a>

Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。 そうしない場合、次のようなエラー メッセージと共にログオンが失敗します。

- **エラー**: *Get-CsWebTicket: ユーザー 'kenmyer@litwareinc.com' のログオンに失敗しました。正しいユーザー名とパスワードを使用していることを確認して、新しい PSCredential オブジェクトを作成してください。*

- **解決策**: 有効なユーザー アカウントを使用し、正しいパスワードを持っている場合は、もう一度ログオンしてみてください。 それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。 そこでログオンできない場合は、Microsoft サポートにお問い合わせください。 

  
## <a name="the-user-doesnt-have-permission-to-manage-this-tenant"></a>ユーザーにこのテナントを管理するアクセス許可が与えら
<a name="BKMKUserPermission"> </a>

テナント管理者グループのメンバーである場合を限り、Skype for Business Online へのリモート PowerShell 接続を確立することはできません。 接続できない場合、接続の試行は失敗し、次のエラー メッセージが表示されます。

- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました: ユーザー 'user@foo.com' には、このテナントを管理するアクセス許可が付与されません。 *適切な RBAC ロールにユーザーを割り当てると、アクセス許可を付与できます。詳細については、リモートトラブルシューティングに関 [するページを参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)。*

- **解決策**: 自分がテナント管理者グループのメンバーである、またはメンバーになっていると思う場合は、Microsoft サポートにお問い合わせください。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>テナントに接続する機能が Skype for Business Online で無効化されている
<a name="BKMKAbilityConnect"> </a>

PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。 接続されていない場合、接続は失敗し、次のエラー メッセージが表示されます。

- **エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました:リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。このテナントのテナント Powershell ポリシーを確認するには、Lync ヘルプにお問い合わせください。詳細については、リモートトラブルシューティングに関 [するページを参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)。*

- **解決策**: このエラー メッセージが表示された場合は、Microsoft サポートに問い合わせ、リモート PowerShell アクセスを有効にする必要があります。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsUser"> </a>

各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。

- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました *: WS-Management サービスは要求を処理できません。このユーザーの同時実行シェルの最大数を超えました。既存のシェルを閉じるか、このユーザーのクォータを上げる。詳細については、リモートトラブルシューティングに関 [するページを参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)。*

- **解決策**: この問題を解決する唯一の方法は、前の接続の 1 つ以上を閉じる方法です。 Skype for Business Online セッションが終了したら **、Remove-PSSession** コマンドレットを使用してセッションを終了することをお勧めします。 この操作は、この問題を防ぐのに役立ちます。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Skype for Business Online でのこのテナントの同時シェルの最大数を超過している
<a name="BKMKMaxNumberShellsTenant"> </a>

各管理者は、Skype for Business Online テナントに対して最大 3 つの同時接続を持つ場合でも、20 を超える同時接続を持つシングル テナントはありません。 たとえば、6 人の管理者がそれぞれ 3 つのオープン セッションを持つ場合があります。 7 番目の管理者が 2 つ以上の接続を開こうとすると (合計 21 の同時接続が発生する)、この試行は失敗し、次のエラー メッセージが表示されます。
  
- **エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました *: WS-Management サービスは要求を処理できません。このテナントの同時実行シェルの最大数を超えました。既存のシェルを閉じるか、このテナントのクォータを上げてください。詳細については、リモート トラブルシューティングに関 [するページを参照してください。](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **解決策**: この問題を解決する唯一の方法は、前の接続の 1 つ以上を閉じる方法です。 Skype for Business Online セッションが終了したら **、Remove-PSSession** コマンドレットを使用してそのセッションを終了することをお勧めします。 これは、この問題を防ぐのに役立ちます。  
 
## <a name="related-topics"></a>関連項目
[Skype for Business のオンライン管理用にコンピューターをセットアップするには、Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
