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
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="c3d08-103">Skype for Business Online Connector との接続の問題を診断する</span><span class="sxs-lookup"><span data-stu-id="c3d08-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="c3d08-p101">[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p101">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:</span></span>
  
- [<span data-ttu-id="c3d08-106">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="c3d08-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="c3d08-107">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="c3d08-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="c3d08-108">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="c3d08-109">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="c3d08-110">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="c3d08-111">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="c3d08-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="c3d08-112">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="c3d08-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [<span data-ttu-id="c3d08-113">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="c3d08-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="c3d08-114">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="c3d08-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="c3d08-115">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="c3d08-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="c3d08-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-116"></span></span>

<span data-ttu-id="c3d08-p102">PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p102">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="c3d08-120">**エラー**:<em>インポート-モジュール: ファイル C:\\プログラムファイル\\共通ファイル\\Microsoft Lync Server 2013\\モジュール\\LyncOnlineConnector\\LyncOnlineConnectorStartup は、このシステムで実行中のスクリプトが無効になっているため、読み込めません。詳細については、「 https://go.microsoft.com/fwlink/?LinkID=135170about_Execution_Policies」を参照してください。</em></span><span class="sxs-lookup"><span data-stu-id="c3d08-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="c3d08-121">**解決策**: この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="c3d08-122">実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="c3d08-123">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="c3d08-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="c3d08-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-124"></span></span>

<span data-ttu-id="c3d08-p103">Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p103">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0. If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="c3d08-127">**エラー**:*インポート-モジュール: 読み込まれた PowerShell のバージョンは ' 2.0 ' です。このモジュールでは\\、Program\\Files の\\一般的なファイル Microsoft\\Lync\\Server\\2013 モジュール LyncOnlineConnector LyncOnlineConnector ' を実行するには、少なくとが PowerShell バージョンの ' 3.0 ' が必要です。PowerShell のインストールを確認して、もう一度やり直してください。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="c3d08-128">**解決策**: この問題を解決するには、Microsoft ダウンロードセンターから入手できる Windows PowerShell 3.0 をインストールする方法しか[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)ありません。</span><span class="sxs-lookup"><span data-stu-id="c3d08-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="c3d08-129">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="c3d08-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-130"></span></span>

<span data-ttu-id="c3d08-131">次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="c3d08-132">**エラー**: *Get-cswebticket: live id サーバーへの接続に失敗しました。プロキシが有効になっていることを確認するか、マシンに live id サーバへのネットワーク接続があることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="c3d08-133">**解決策**: 多くの場合、このエラーは Microsoft Online Services サインインアシスタントが実行されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="c3d08-134">このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="c3d08-135">サービスが実行していない場合は、このコマンドを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-135">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="c3d08-p105">サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。そこから Office 365 にログオンしてください。この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p105">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server. To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Try logging on to Office 365 from there. If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="c3d08-p106">稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。Office 365 サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p106">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value. If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue. In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="c3d08-143">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-143">Failed to load Live ID module</span></span>
<span data-ttu-id="c3d08-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-144"></span></span>

<span data-ttu-id="c3d08-p107">PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p107">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="c3d08-147">**エラー**: *Get-Cswebticket: Live Id モジュールを読み込むことができません。正しいバージョンの Live Id サインインアシスタントがインストールされていることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="c3d08-148">**解決**方法: microsoft Online services サインインアシスタントは、 [it プロフェッショナル向けの Microsoft Online SERVICES サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123](https://www.microsoft.com/en-us/download/details.aspx?id=28177)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="c3d08-149">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="c3d08-149">Logon failed for the user</span></span>
<span data-ttu-id="c3d08-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-150"></span></span>

<span data-ttu-id="c3d08-p108">Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p108">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account. If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="c3d08-153">**エラー**: *Get-cswebticket: ユーザー ' Kenmyer@litwareinc.com ' のログオンに失敗しました。新しい PSCredential オブジェクトを作成して、正しいユーザー名とパスワードを使用していることを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="c3d08-154">**解決策**: 有効なユーザーアカウントを使用していて、正しいパスワードを持っていると思われる場合は、もう一度ログインしてみてください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="c3d08-155">それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="c3d08-156">そこでもログオンできない場合は、Office 365 サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c3d08-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="c3d08-157">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="c3d08-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="c3d08-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-158"></span></span>

<span data-ttu-id="c3d08-p110">テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p110">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="c3d08-161">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。ユーザー ' user@foo.com ' にはこのテナントを管理する権限がありません。権限を付与するには、適切な RBAC の役割をユーザーに割り当てます。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="c3d08-162">**解決策**: テナント管理者グループのメンバーであると考えられる場合は、Office 365 サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3d08-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="c3d08-163">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="c3d08-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="c3d08-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-164"></span></span>

<span data-ttu-id="c3d08-p111">PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p111">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="c3d08-167">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になりました。このテナントのテナント Powershell ポリシーを確認するには、Lync のヘルプにお問い合わせください。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="c3d08-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="c3d08-168">**解決策**: このエラーメッセージが表示される場合は、Office 365 サポートに連絡して、リモート PowerShell アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3d08-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="c3d08-169">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="c3d08-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="c3d08-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-170"></span></span>

<span data-ttu-id="c3d08-p112">各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p112">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="c3d08-173">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このユーザーの同時シェルの最大数を超過しています。このユーザーの既存のシェルを閉じるか、またはクォータを増やします。詳細については、「[リモートトラブルシューティングhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="c3d08-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="c3d08-174">**解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="c3d08-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="c3d08-175">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3d08-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="c3d08-176">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="c3d08-177">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="c3d08-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="c3d08-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="c3d08-178"></span></span>

<span data-ttu-id="c3d08-p114">各管理者には 1つの Skype for Business Online テナントに対して 3 つの同時接続が許可されていますが、単一のテナントに許可されている同時接続は 9 つ以下です。たとえば、3 人の管理者それぞれが 3 つのセッションを開いているとします。4 人目の管理者が接続を確立しようとすると、結果として 10 の同時接続が発生するため、その管理者の接続は次のエラーメッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="c3d08-p114">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections. For example, three administrators might each have three open sessions. If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="c3d08-182">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このテナントの同時シェルの最大数を超過しています。既存のシェルを閉じるか、このテナントのクォータを上げます。詳細については、「[リモートトラブルシューティングhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="c3d08-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="c3d08-183">**解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="c3d08-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="c3d08-184">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3d08-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="c3d08-185">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="c3d08-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="c3d08-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3d08-186">Related topics</span></span>
[<span data-ttu-id="c3d08-187">Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c3d08-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
