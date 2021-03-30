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
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="4afdf-103">Skype for Business Online Connector との接続の問題を診断する</span><span class="sxs-lookup"><span data-stu-id="4afdf-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="4afdf-p101">[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p101">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:</span></span>
  
- [<span data-ttu-id="4afdf-106">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="4afdf-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="4afdf-107">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="4afdf-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="4afdf-108">WinRM Basic 認証が無効になっていると、モダン認証が失敗する</span><span class="sxs-lookup"><span data-stu-id="4afdf-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="4afdf-109">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="4afdf-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="4afdf-110">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="4afdf-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="4afdf-111">ユーザーのサインインに失敗しました</span><span class="sxs-lookup"><span data-stu-id="4afdf-111">Sign in failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="4afdf-112">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="4afdf-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="4afdf-113">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="4afdf-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="4afdf-114">Skype for Business Online のこのユーザーの同時シェルの最大数を超えました</span><span class="sxs-lookup"><span data-stu-id="4afdf-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="4afdf-115">Skype for Business Online のこのテナントの同時シェルの最大数を超えました</span><span class="sxs-lookup"><span data-stu-id="4afdf-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="4afdf-116">既定では、PowerShell セッションは 60 分後にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="4afdf-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="4afdf-117">再接続するには、セッションを閉じて、新しい PowerShell セッションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="4afdf-118">Skype for Business Online の新しいバージョンの [Windows PowerShell モジュール (2046.123 - 公開日: 2019/10/2)](https://www.microsoft.com/download/details.aspx?id=39366)が最近開始されました。これには、60 分間のタイムアウトの問題を軽減する **Enable-CsOnlineSessionForReconnection** という新しいコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4afdf-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="4afdf-119">PowerShell セッションは再接続と認証を行い、再接続するために新しいインスタンスを起動することなく再使用できます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="4afdf-120">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="4afdf-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="4afdf-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="4afdf-p103">PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p103">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="4afdf-125">**エラー**: <em>Import-Module : File C: \\ Program Files Common Files Microsoft Lync Server \\ \\ 2013 \\ Modules \\ \\ LyncOnlineConnector LyncOnlineConnectorStartup.psm1 は、このシステムで実行中のスクリプトが無効になっているため、読み込む必要があります。詳細については、次のabout_Execution_Policies参照してください https://go.microsoft.com/fwlink/?LinkID=135170 。</em></span><span class="sxs-lookup"><span data-stu-id="4afdf-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="4afdf-126">**解像度** この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="4afdf-127">実行ポリシーの詳細については、「[実行ポリシーについて](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-127">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="4afdf-128">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="4afdf-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="4afdf-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="4afdf-130">Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="4afdf-131">以前のバージョンの PowerShell でモジュールをインポートすると、次のようなエラー メッセージが表示されたインポート プロセスは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this message:</span></span>
  
  - <span data-ttu-id="4afdf-132">**エラー**: Import-Module: 読み込まれた PowerShell のバージョン *は '2.0' です。モジュール 'D: プログラム ファイルの共通ファイル \\ \\ Microsoft Lync Server \\ 2013 \\ モジュール \\ LyncOnlineConnectorLyncOnlineConnector.psd1' の実行には \\ 、最小 PowerShell バージョンの '3.0' が必要です。PowerShell のインストールを確認して、もう一度お試しください。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="4afdf-133">**解決** 方法: この問題を解決する唯一の方法は、microsoft ダウンロード センターからWindows PowerShell 3.0 をインストールすることです [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 。</span><span class="sxs-lookup"><span data-stu-id="4afdf-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="4afdf-134">WinRM Basic 認証が無効になっていると、モダン認証が失敗する</span><span class="sxs-lookup"><span data-stu-id="4afdf-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="4afdf-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="4afdf-136">Skype for Business Online Connector モジュールの最新バージョンでは、最新の認証が使用されますが、基本認証を許可するように、基になる Windows リモート管理 (WinRM) クライアントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="4afdf-137">最新の認証では、通常は Authorization: Bearer ヘッダーで渡される *、Bearer トークンを使用* します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-137">Modern authentication uses bearer tokens, which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="4afdf-138">Windows PowerShell Skype for Business PowerShell を作成する場合、このヘッダーの操作は許可されません。</span><span class="sxs-lookup"><span data-stu-id="4afdf-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="4afdf-139">代わりに、Skype for Business PowerShell は承認 *:* 基本ヘッダーを使用して、担い手トークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="4afdf-140">WinRM [for Basic 認証を有効Windows PowerShell](./download-and-install-windows-powershell-5-1.md) 方法については、「ダウンロードしてインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-140">See [Download and install Windows PowerShell](./download-and-install-windows-powershell-5-1.md) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="4afdf-141">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="4afdf-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="4afdf-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-142"><a name="BKMKFailedConnect"> </a></span></span>

> [!WARNING] 
> <span data-ttu-id="4afdf-143">Skype for Business Online Connector のライブ ID 認証は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4afdf-143">Live ID authentication has been deprecated for Skype For Business online Connector.</span></span> <span data-ttu-id="4afdf-144">Teams PowerShell モジュールを使用して、オンライン テナントを管理します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-144">Use the Teams PowerShell Module to manage the online tenant.</span></span> <span data-ttu-id="4afdf-145">ハイブリッド環境を管理する場合は、最新の累積的な更新プログラムにアップグレードするか、oAuth 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-145">When managing hybrid environments, upgrade to latest cumulative update or use oAuth authentication.</span></span>

<span data-ttu-id="4afdf-146">次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-146">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="4afdf-147">**エラー**: *Get-CsWebTicket : ライブ ID サーバーの接続に失敗しました。プロキシが有効になっているか、マシンがライブ ID サーバーへのネットワーク接続を持つ必要があります。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-147">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live ID servers.*</span></span>

- <span data-ttu-id="4afdf-148">**解決** 方法: 多くの場合、このエラーは、Microsoft Online Servicesアシスタントが実行されていない場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-148">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="4afdf-149">このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-149">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="4afdf-150">サービスが実行していない場合は、このコマンドを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-150">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="4afdf-151">サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-151">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="4afdf-152">この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-152">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="4afdf-153">そこから Microsoft 365 または Office 365 にログオンしてみてください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-153">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="4afdf-154">この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-154">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="4afdf-155">稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-155">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="4afdf-156">サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-156">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="4afdf-157">この場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-157">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="4afdf-158">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="4afdf-158">Failed to load Live ID module</span></span>
<span data-ttu-id="4afdf-159"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-159"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="4afdf-p110">PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p110">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="4afdf-162">**エラー**: *Get-CsWebTicket : Live ID モジュールを読み込めない。正しいバージョンの Live Id サインイン アシスタントがインストールされていることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-162">**Error**: *Get-CsWebTicket : Can't load Live ID module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="4afdf-163">**解決** 方法: Microsoft Online Services サインイン アシスタントは、MICROSOFT ダウンロード センターの IT プロフェッショナル向け [Microsoft Online Services Sign-In RTW で利用できます](https://www.microsoft.com/download/details.aspx?id=28177)。</span><span class="sxs-lookup"><span data-stu-id="4afdf-163">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="4afdf-164">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="4afdf-164">Logon failed for the user</span></span>
<span data-ttu-id="4afdf-165"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-165"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="4afdf-166">Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-166">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="4afdf-167">そうしない場合、次のメッセージのようなエラー メッセージと共にログオンは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-167">If you do not, logon will fail along with an error message similar to this message:</span></span>

- <span data-ttu-id="4afdf-168">**エラー**: *Get-CsWebTicket : ユーザーの 'kenmyer@litwareinc.com' に対するログオンに失敗しました。新しい PSCredential オブジェクトを作成し、正しいユーザー名とパスワードを使用していることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-168">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="4afdf-169">**解決** 方法: 有効なユーザー アカウントを使用し、正しいパスワードを持っている場合は、もう一度ログオンしてみてください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-169">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="4afdf-170">失敗した場合は、同じ資格情報を使用してサインインしてみてください [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。</span><span class="sxs-lookup"><span data-stu-id="4afdf-170">If that fails, use the same credentials and try to sign in at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="4afdf-171">サインインできない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-171">If you're unable to sign in there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="4afdf-172">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="4afdf-172">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="4afdf-173"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-173"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="4afdf-p113">テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p113">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="4afdf-176">**エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました。ユーザー 'user@foo.com' には、このテナントを管理するアクセス許可が与え込みではありません。 *適切な RBAC ロールにユーザーを割り当てると、アクセス許可を付与できます。詳細については、リモートトラブルシューティング [を参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-176">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="4afdf-177">**解決** 方法: テナント管理者グループのメンバーである、またはメンバーであるはずと考える場合は、Microsoft サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="4afdf-177">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="4afdf-178">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="4afdf-178">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="4afdf-179"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-179"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="4afdf-p114">PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p114">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="4afdf-182">**エラー**: *New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com からのデータの処理に失敗し、次のエラー メッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になっています。Lync ヘルプに問い合わせ、このテナントのテナント PowerShell ポリシーを確認します。詳細については、リモートトラブルシューティング [を参照してください](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-182">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="4afdf-183">**解決** 方法: このエラー メッセージが表示された場合は、Microsoft サポートに問い合わせ、リモート PowerShell アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-183">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="4afdf-184">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="4afdf-184">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="4afdf-185"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-185"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="4afdf-p115">各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="4afdf-p115">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="4afdf-188">**エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました:WS-Management サービスは要求を *処理できません。このユーザーの同時シェルの最大数を超えました。既存のシェルを閉じるか、このユーザーのクォータを上げる。詳細については、[リモート トラブルシューティング] を参照してください https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-188">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="4afdf-189">**解決** 方法: この問題を解決する唯一の方法は、1 つ以上の前の接続を閉じる方法です。</span><span class="sxs-lookup"><span data-stu-id="4afdf-189">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="4afdf-190">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4afdf-190">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="4afdf-191">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-191">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="4afdf-192">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="4afdf-192">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="4afdf-193"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="4afdf-193"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="4afdf-194">各管理者は、Skype for Business Online テナントへの同時接続を最大 3 つまで許可しますが、20 を超える同時接続を持つ 1 つのテナントは許可されません。</span><span class="sxs-lookup"><span data-stu-id="4afdf-194">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="4afdf-195">たとえば、6 人の管理者がそれぞれ 3 つのオープン セッションを持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4afdf-195">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="4afdf-196">4 人目の管理者が 3 つ以上の接続を行う場合 (その結果、21 の同時接続が発生します)、この試行は失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-196">If a fourth administrator tries to make more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="4afdf-197">**エラー**: New-PSSession : [admin.vdomain.com] リモート サーバー admin.vdomain.com への接続に失敗し、次のエラー メッセージが表示されました。WS-Management サービスは要求を *処理できません。このテナントの同時シェルの最大数を超えました。既存のシェルを閉じるか、このテナントのクォータを上げる。詳細については、[リモート トラブルシューティング] を参照してください https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 。*</span><span class="sxs-lookup"><span data-stu-id="4afdf-197">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message: The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="4afdf-198">**解決** 方法: この問題を解決する唯一の方法は、1 つ以上の前の接続を閉じる方法です。</span><span class="sxs-lookup"><span data-stu-id="4afdf-198">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="4afdf-199">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4afdf-199">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="4afdf-200">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="4afdf-200">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="4afdf-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="4afdf-201">Related topics</span></span>
[<span data-ttu-id="4afdf-202">Skype for Business Online 管理用にコンピューターをセットアップするには、次のWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4afdf-202">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
