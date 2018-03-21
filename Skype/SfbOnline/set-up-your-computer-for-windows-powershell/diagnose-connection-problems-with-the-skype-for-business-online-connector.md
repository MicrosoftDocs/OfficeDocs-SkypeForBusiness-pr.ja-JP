---
title: "Skype for Business Online Connector との接続の問題を診断する"
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
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: 779786e073cf4ac420d75780472f8d45d67b292a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="506bc-103">Skype for Business Online Connector との接続の問題を診断する</span><span class="sxs-lookup"><span data-stu-id="506bc-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="506bc-p101">[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="506bc-p101">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:</span></span>
  
- [<span data-ttu-id="506bc-106">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="506bc-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="506bc-107">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="506bc-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="506bc-108">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="506bc-109">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="506bc-110">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="506bc-111">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="506bc-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="506bc-112">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="506bc-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="506bc-113">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している </span><span class="sxs-lookup"><span data-stu-id="506bc-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded </span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [<span data-ttu-id="506bc-114">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している </span><span class="sxs-lookup"><span data-stu-id="506bc-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded </span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="506bc-115">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="506bc-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="506bc-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="506bc-p102">PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="506bc-p102">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="506bc-120">**エラー**:*モジュールのインポート: ファイル c:\\プログラム ファイル\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 は、実行されているために、読み込むことができませんこのシステムでは、スクリプトが無効です。詳細については、https://go.microsoft.com/fwlink/?LinkID=135170 で about_Execution_Policies を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="506bc-120">**Error**: *Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.*</span></span>

- <span data-ttu-id="506bc-121">**解像度**この問題を解決するには、管理者は、PowerShell を開始し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="506bc-121">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="506bc-122">実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="506bc-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="506bc-123">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="506bc-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="506bc-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-124"></span></span>

<span data-ttu-id="506bc-p103">Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="506bc-p103">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0. If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="506bc-127">**エラー**: インポート モジュールの*: '2.0' は、読み込まれた PowerShell のバージョンです。モジュール ' d:\\Program Files\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnector.psd1' を実行するには、'3.0' の最小 PowerShell バージョンが必要です。PowerShell のインストールを確認して再試行してください*。</span><span class="sxs-lookup"><span data-stu-id="506bc-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="506bc-128">**解像度**: この問題を解決する唯一の方法は、 [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)Microsoft ダウンロード センターから利用される Windows PowerShell 3.0 をインストールするのには。</span><span class="sxs-lookup"><span data-stu-id="506bc-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="506bc-129">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="506bc-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-130"></span></span>

<span data-ttu-id="506bc-131">次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="506bc-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="506bc-132">**エラー**: *Get CsWebTicket: ライブ id サーバーの接続に失敗しました。プロキシが有効になっているマシンには、live id のサーバーへのネットワーク接続を確認します*。</span><span class="sxs-lookup"><span data-stu-id="506bc-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="506bc-133">**解像度**: このエラーが Microsoft オンライン サービス サインイン アシスタントが実行されていないことを意味することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="506bc-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="506bc-134">このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="506bc-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="506bc-135">サービスが実行していない場合は、このコマンドを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="506bc-135">If the service is not running, start the service by using this command:</span></span>
    ```
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="506bc-p105">サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。そこから Office 365 にログオンしてください。この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="506bc-p105">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server. To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Try logging on to Office 365 from there. If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="506bc-p106">稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。Office 365 サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="506bc-p106">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value. If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue. In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="506bc-143">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-143">Failed to load Live ID module</span></span>
<span data-ttu-id="506bc-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-144"></span></span>

<span data-ttu-id="506bc-p107">PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="506bc-p107">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="506bc-147">**エラー**: *Get CsWebTicket: Live Id モジュールを読み込むことはできません。Live Id サインイン アシスタントのバージョンがインストールされている修正がいることを確認します*。</span><span class="sxs-lookup"><span data-stu-id="506bc-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="506bc-148">**解像度**:「Microsoft オンライン サービス サインイン アシスタントは、 [Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナルの RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)に Microsoft ダウンロード センターで利用可能な</span><span class="sxs-lookup"><span data-stu-id="506bc-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="506bc-149">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="506bc-149">Logon failed for the user</span></span>
<span data-ttu-id="506bc-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-150"></span></span>

<span data-ttu-id="506bc-p108">Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。</span><span class="sxs-lookup"><span data-stu-id="506bc-p108">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account. If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="506bc-153">**エラー**: *Get CsWebTicket: 'kenmyer@litwareinc.com' のユーザーのログオンに失敗しました。正しいユーザー名とパスワードを使用していることを確認する、新しい PSCredential オブジェクトを作成してください*。</span><span class="sxs-lookup"><span data-stu-id="506bc-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="506bc-154">**解像度**: ログオンし直して、正しいパスワードがあると、有効なユーザー アカウントを使用するいると思われる場合。</span><span class="sxs-lookup"><span data-stu-id="506bc-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="506bc-155">失敗した場合、同じ資格情報を使用して、 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)にログオンしようとしてください。</span><span class="sxs-lookup"><span data-stu-id="506bc-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="506bc-156">そこでもログオンできない場合は、Office 365 サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="506bc-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="506bc-157">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="506bc-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="506bc-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-158"></span></span>

<span data-ttu-id="506bc-p110">テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="506bc-p110">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="506bc-161">**エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーからのデータの処理は、次のエラー メッセージで失敗しました: ユーザー 'user@foo.com' には、このテナントを管理する権限はありません。適切な RBAC の役割にユーザーを割り当てることにより、アクセス許可を与えることができます。詳細については、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="506bc-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="506bc-162">**解決方法**: Office 365 のサポートに連絡する必要があります、または、テナント管理者グループのメンバーであることになっていることと思われる場合。</span><span class="sxs-lookup"><span data-stu-id="506bc-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="506bc-163">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="506bc-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="506bc-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-164"></span></span>

<span data-ttu-id="506bc-p111">PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="506bc-p111">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="506bc-167">**エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーからのデータの処理は、次のエラー メッセージで失敗しました: リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。このテナントのテナント Powershell のポリシーを確認するのには、Lync ヘルプにお問い合わせください。詳細については、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="506bc-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="506bc-168">**解決方法**: Office 365 のサポートに連絡し、PowerShell のリモート アクセスを有効にする必要がありますこのエラー メッセージが表示された場合。</span><span class="sxs-lookup"><span data-stu-id="506bc-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="506bc-169">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="506bc-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="506bc-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-170"></span></span>

<span data-ttu-id="506bc-p112">各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="506bc-p112">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="506bc-173">**エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーへの接続は、次のエラー メッセージで失敗しました:、WS-Management サービスは要求を処理できません。このユーザーの同時実行のシェルの最大数を超えています。既存のシェルを閉じるか、このユーザーのクォータを生成します。詳細についてを参照してください、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="506bc-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="506bc-174">**解像度**: この問題を解決する唯一の方法は、1 つ以上の以前の接続を閉じることです。</span><span class="sxs-lookup"><span data-stu-id="506bc-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="506bc-175">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="506bc-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="506bc-176">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="506bc-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="506bc-177">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="506bc-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="506bc-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="506bc-178"></span></span>

<span data-ttu-id="506bc-p114">各管理者には 1つの Skype for Business Online テナントに対して 3 つの同時接続が許可されていますが、単一のテナントに許可されている同時接続は 9 つ以下です。たとえば、3 人の管理者それぞれが 3 つのセッションを開いているとします。4 人目の管理者が接続を確立しようとすると、結果として 10 の同時接続が発生するため、その管理者の接続は次のエラーメッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="506bc-p114">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections. For example, three administrators might each have three open sessions. If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="506bc-182">**エラー**: 新規 PSSession を*: [admin.vdomain.com] admin.vdomain.com のリモート サーバーへの接続は、次のエラー メッセージで失敗しました:、WS-Management サービスは要求を処理できません。このテナントの同時シェルの最大数を超えています。既存のシェルを閉じるか、このテナントのクォータを生成します。詳細についてを参照してください、[リモートでのトラブルシューティング](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="506bc-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="506bc-183">**解像度**: この問題を解決する唯一の方法は、1 つ以上の以前の接続を閉じることです。</span><span class="sxs-lookup"><span data-stu-id="506bc-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="506bc-184">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="506bc-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="506bc-185">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="506bc-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="506bc-186">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="506bc-186">Related topics</span></span>
[<span data-ttu-id="506bc-187">Windows PowerShell を使用してビジネスのオンライン管理のための skype には、コンピューターを設定します</span><span class="sxs-lookup"><span data-stu-id="506bc-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a><span data-ttu-id="506bc-188">フィードバックですか。</span><span class="sxs-lookup"><span data-stu-id="506bc-188">Feedback?</span></span>
<span data-ttu-id="506bc-189">製品に関するフィードバックを提供するには、かをお知らせいただいて、取り組み方は、 [Skype](https://www.skypefeedback.com)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="506bc-189">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
