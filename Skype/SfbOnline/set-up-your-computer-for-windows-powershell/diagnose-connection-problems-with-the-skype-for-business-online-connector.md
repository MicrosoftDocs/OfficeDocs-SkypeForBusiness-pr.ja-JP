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
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="40f1c-103">ビジネス Online コネクタの Skype の接続に関する問題を診断します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="40f1c-p101">ここでは、診断およびリモート Skype for Business Online に接続する Microsoft PowerShell セッションを作成しようとしたときに発生する可能性がある問題を解決するうえで役立つ情報を紹介します。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p101">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:</span></span>
  
- [<span data-ttu-id="40f1c-106">Windows PowerShell 実行ポリシーによるインポート モジュール エラー</span><span class="sxs-lookup"><span data-stu-id="40f1c-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="40f1c-107">不適切なバージョンの Windows PowerShell によるインポート モジュール エラー</span><span class="sxs-lookup"><span data-stu-id="40f1c-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="40f1c-108">Live ID サーバーへの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="40f1c-109">Live ID モジュールの読み込みに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="40f1c-110">ログオン ユーザー用に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="40f1c-111">ユーザーには、このテナントを管理する権限がないです。</span><span class="sxs-lookup"><span data-stu-id="40f1c-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="40f1c-112">テナントに接続する機能は skype for Business Online を無効になっています。</span><span class="sxs-lookup"><span data-stu-id="40f1c-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="40f1c-113">Skype for Business Online では、このユーザーの同時シェルの最大数を超えています</span><span class="sxs-lookup"><span data-stu-id="40f1c-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded </span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [<span data-ttu-id="40f1c-114">Skype for Business Online では、このテナントの同時シェルの最大数を超えています</span><span class="sxs-lookup"><span data-stu-id="40f1c-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded </span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="40f1c-115">Windows PowerShell 実行ポリシーによるインポート モジュール エラー</span><span class="sxs-lookup"><span data-stu-id="40f1c-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="40f1c-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-116"></span></span>

<span data-ttu-id="40f1c-p102">PowerShell 実行ポリシーにより、PowerShell コンソールにロードできる構成ファイルを確認して、コンソールからユーザー スクリプトを実行できます。最低でも、実行ポリシーが RemoteSigned に設定されていない限り、Skype for Business Online コネクタ モジュールをインポートできません。されない場合は、モジュールをインポートしようとしたときに、次のエラー メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p102">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="40f1c-120">**エラー**:*インポート モジュール: ファイル c:\\Program Files\\一般的なファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\実行されているために、LyncOnlineConnectorStartup.psm1 を読み込むことができませんこのシステムでは、スクリプトが無効にします。詳細については、https://go.microsoft.com/fwlink/?LinkID=135170 で about_Execution_Policies を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-120">**Error**: *Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.*</span></span>

- <span data-ttu-id="40f1c-121">**解決方法**この問題を解決するには、管理者は、PowerShell を起動し、[次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-121">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="40f1c-122">実行ポリシーについての詳細については、[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)参照してください。</span><span class="sxs-lookup"><span data-stu-id="40f1c-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="40f1c-123">不適切なバージョンの Windows PowerShell によるインポート モジュール エラー</span><span class="sxs-lookup"><span data-stu-id="40f1c-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="40f1c-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-124"></span></span>

<span data-ttu-id="40f1c-p103">Skype for Business Online コネクタ モジュールは、Windows PowerShell 3.0 でのみ実行できます。以前のバージョンの PowerShell モジュールをインポートしようとした場合、インポート プロセスは次のようなエラー メッセージが失敗します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p103">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0. If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="40f1c-127">**エラー**:*インポート モジュール: 読み込まれた PowerShell のバージョンが '2.0' します。モジュール ' d:\\Program Files\\一般的なファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnector.psd1' を実行するには、'3.0' の最小 PowerShell バージョンが必要です。[PowerShell のインストールを確認して、再試行してください*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="40f1c-128">**解決方法**: 対象と[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)に Microsoft ダウンロード センターから、Windows PowerShell 3.0 をインストールするのには、この問題を解決するしかします。</span><span class="sxs-lookup"><span data-stu-id="40f1c-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="40f1c-129">Live ID サーバーへの接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="40f1c-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-130"></span></span>

<span data-ttu-id="40f1c-131">通常は、次のエラー メッセージと、接続が失敗する理由 3 つの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="40f1c-132">**エラー**: *Get CsWebTicket: live id サーバーの接続に失敗しました。プロキシを有効にするか、コンピューターがネットワーク接続が id サーバーことを確認します*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="40f1c-p104">**解決方法**: 多くの場合、このエラーでは Microsoft Online Services サインイン アシスタントが実行されていないことを意味します。このサービスの状態を確認するには、PowerShell のプロンプトで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p104">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running. You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="40f1c-135">サービスが実行されていない場合は、このコマンドを使用して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-135">If the service is not running, start the service by using this command:</span></span>
    ```
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="40f1c-p105">場合は、サービスを実行すると、お使いのコンピューターと Microsoft Live ID 認証サーバー間でネットワーク接続を使って問題を発生する可能性があります。これを確認するには、Internet Explorer を開きに移動する[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) 。そこから Office 365 にログインしてみてください。これが失敗した場合は、おそらくネットワーク接続の問題を発生しています。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p105">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server. To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Try logging on to Office 365 from there. If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="40f1c-p106">あまり一般的には、Microsoft Live ID 認証サーバーの接続 URI が間違った値に設定されていることができます。場合は、サインイン アシスタントが実行されていると、そのネットワーク接続の問題が発生しない、問題がありますを既に決定します。この例では、Office 365 のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p106">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value. If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue. In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="40f1c-143">Live ID モジュールの読み込みに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-143">Failed to load Live ID module</span></span>
<span data-ttu-id="40f1c-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-144"></span></span>

<span data-ttu-id="40f1c-p107">Skype for Business Online の管理に PowerShell を使用するための前提条件のいずれかは、Microsoft Online Services サインイン アシスタントをインストールします。サインイン アシスタントがインストールされていない場合は、for Business Online の Skype とのリモート セッションを確立しようとしたときに次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p107">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="40f1c-147">**エラー**: *Get CsWebTicket: Live Id モジュールを読み込むことはできません。Live のサインイン時のアシスタントのバージョンがインストールされている修正はことを確認します*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="40f1c-148">**解決方法**: は、「Microsoft Online Services サインイン アシスタントを[Microsoft Online Services サインイン アシスタント IT プロフェッショナル RTW 用](https://www.microsoft.com/en-us/download/details.aspx?id=28177)に Microsoft ダウンロード センターからインストールできる</span><span class="sxs-lookup"><span data-stu-id="40f1c-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="40f1c-149">ログオン ユーザー用に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="40f1c-149">Logon failed for the user</span></span>
<span data-ttu-id="40f1c-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-150"></span></span>

<span data-ttu-id="40f1c-p108">Skype for Business Online リモート接続を作成しようとすると、ユーザー名とパスワードの有効な Skype for Business Online のユーザー アカウントを指定する必要があります。されない場合は、次のようなエラー メッセージとログオンは失敗します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p108">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account. If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="40f1c-153">**エラー**: *Get CsWebTicket: 'kenmyer@litwareinc.com' のユーザーのログオンに失敗しました。正しいユーザー名とパスワードを使用していることを確認、新しい PSCredential オブジェクトを作成してください*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="40f1c-p109">**解決方法**: ログオンし直して、正しいパスワードと有効なユーザー アカウントを使用するいると思われる場合があります。失敗した場合、同じ資格情報を使用し、 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)にログオンしようとしてください。ログオンが存在しない場合は、Office 365 のサポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p109">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again. If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/). If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="40f1c-157">ユーザーには、このテナントを管理する権限がないです。</span><span class="sxs-lookup"><span data-stu-id="40f1c-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="40f1c-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-158"></span></span>

<span data-ttu-id="40f1c-p110">テナント管理者グループのメンバーになっている場合を除き、for Business Online リモート PowerShell 接続 toSkype を作成することはできません。ではない場合、接続の試行が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p110">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="40f1c-161">**エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗しました: 'user@foo.com' のユーザーには、このテナントを管理する権限がないです。RBAC の役割を適切なユーザーに割り当てることにより、アクセス許可を付与できます。詳細については、[リモートのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="40f1c-162">**解決方法**: された、またはするには、テナント管理者グループのメンバーになっていると思われる場合は、Office 365 のサポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f1c-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="40f1c-163">テナントに接続する機能は skype for Business Online を無効になっています。</span><span class="sxs-lookup"><span data-stu-id="40f1c-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="40f1c-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-164"></span></span>

<span data-ttu-id="40f1c-p111">PowerShell を使用して、Skype for Business Online の管理] には、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティに設定する必要があります`True`します。ない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p111">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="40f1c-167">**エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗しました: リモート PowerShell セッションを使用してこのテナントに接続する機能を無効になっています。このテナントのテナント Powershell ポリシーを確認する Lync ヘルプにお問い合わせください。詳細については、[リモートのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="40f1c-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="40f1c-168">**解決方法**: このエラー メッセージが表示された場合は、Office 365 のサポートに連絡し、リモート PowerShell アクセスが有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40f1c-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="40f1c-169">Skype for Business Online では、このユーザーの同時シェルの最大数を超えています</span><span class="sxs-lookup"><span data-stu-id="40f1c-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="40f1c-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-170"></span></span>

<span data-ttu-id="40f1c-p112">各管理者は、最大 3 つ同時リモート接続 Skype for Business Online のことを許可します。3 つのリモート PowerShell 接続をセットアップし、実行して、4 番目を同時に作成しようとするがある場合、次のエラー メッセージが、その接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p112">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="40f1c-173">**エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗しました: [受け取りましたサービス要求を処理できません。このユーザーの同時シェルの最大数を超えています。既存のシェルを閉じるか、このユーザーのクォータが発生します。詳細については、次を参照してください、[リモート トラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* 。</span><span class="sxs-lookup"><span data-stu-id="40f1c-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="40f1c-p113">**解決方法**: 1 つ以上の以前の接続を閉じるには、この問題を解決するのにはしかします。完了したら、skype for Business Online のセッション、セッションを終了する、**削除 PSSession**コマンドレットを使用することをお勧めします。この問題を回避することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p113">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections. When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session. This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="40f1c-177">Skype for Business Online では、このテナントの同時シェルの最大数を超えています</span><span class="sxs-lookup"><span data-stu-id="40f1c-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="40f1c-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="40f1c-178"></span></span>

<span data-ttu-id="40f1c-p114">各管理者を Skype for Business Online のテナントに同時に 3 つの接続を許可するのでは、9 個を超える同時に接続する単一のテナントは許可されません。たとえば、次の 3 つの管理者の各があります開かれている 3 つのセッション。4 番目の管理者は、(10 同時接続の合計のようになります) に接続しようとすると、このは失敗します、次のエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p114">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections. For example, three administrators might each have three open sessions. If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="40f1c-182">**エラー**:*新規 PSSession: 次のエラー メッセージが [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗しました: [受け取りましたサービス要求を処理できません。このテナントの同時シェルの最大数を超えています。既存のシェルを閉じるか、このテナントのクォータが発生します。詳細については、次を参照してください、[リモート トラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* 。</span><span class="sxs-lookup"><span data-stu-id="40f1c-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="40f1c-p115">**解決方法**: 1 つ以上の以前の接続を閉じるには、この問題を解決するのにはしかします。完了したら、skype for Business Online のセッション、セッションを終了する、**削除 PSSession**コマンドレットを使用することをお勧めします。この問題を回避することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="40f1c-p115">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections. When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session. This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="40f1c-186">関連トピック</span><span class="sxs-lookup"><span data-stu-id="40f1c-186">Related topics</span></span>
[<span data-ttu-id="40f1c-187">Skype for business online 管理の Windows PowerShell を使用して、コンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="40f1c-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

