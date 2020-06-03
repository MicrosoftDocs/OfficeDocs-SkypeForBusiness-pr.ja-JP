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
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204878"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="b1f53-103">Skype for Business Online Connector との接続の問題を診断する</span><span class="sxs-lookup"><span data-stu-id="b1f53-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="b1f53-p101">[] このトピックでは、Microsoft PowerShell に接続するリモート Skype for Business Online セッションを作成するときに発生する可能性のある問題を診断、解決するのに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p101">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online. See the following sections:</span></span>
  
- [<span data-ttu-id="b1f53-106">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="b1f53-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="b1f53-107">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="b1f53-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="b1f53-108">WinRM Basic 認証が無効になっている場合、先進認証が失敗する</span><span class="sxs-lookup"><span data-stu-id="b1f53-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="b1f53-109">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="b1f53-110">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="b1f53-111">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-111">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="b1f53-112">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="b1f53-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="b1f53-113">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="b1f53-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="b1f53-114">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="b1f53-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="b1f53-115">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="b1f53-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="b1f53-116">既定では、PowerShell セッションは60分後にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="b1f53-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="b1f53-117">再接続するには、セッションを終了し、新しい PowerShell セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="b1f53-118">新しいバージョンの[Skype For Business Online、Windows PowerShell Module (2046.123-公開 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366)が最近開始されました。これには、60分間のタイムアウトの**問題を軽減する、** 新しいコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1f53-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="b1f53-119">PowerShell セッションは再接続して認証を行い、再利用を許可します。新しいインスタンスを起動して再接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="b1f53-120">Windows PowerShell 実行ポリシーによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="b1f53-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="b1f53-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="b1f53-p103">PowerShell 実行ポリシーは、PowerShell コンソールに読み込む構成ファイルやそのコンソールからユーザーが実行できるスクリプトを決定するのに役立ちます。実行ポリシーを RemoteSigned に設定していない場合、Skype for Business Online Connector モジュール をインポートすることはできません。この設定を行っていない場合にモジュールをインポートしようとすると、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p103">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console. At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned. If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="b1f53-125">**エラー**:<em>インポート-モジュール: ファイル C: \\ プログラムファイル \\ 共通ファイル \\ Microsoft Lync Server 2013 \\ モジュール \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup は、このシステムで実行中のスクリプトが無効になっているため、読み込めません。詳細については、「about_Execution_Policies」を参照してください https://go.microsoft.com/fwlink/?LinkID=135170 。</em></span><span class="sxs-lookup"><span data-stu-id="b1f53-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="b1f53-126">**解決策**この問題を解決するには、管理者として PowerShell を起動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="b1f53-127">実行ポリシーの詳細については、「[実行ポリシーについて](https://go.microsoft.com/fwlink/?LinkID=135170)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-127">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="b1f53-128">Windows PowerShell の不正なバージョンによる Import-Module エラー</span><span class="sxs-lookup"><span data-stu-id="b1f53-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="b1f53-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="b1f53-p104">Skype for Business Online Connector モジュール は、Windows PowerShell 3.0 のバージョンでのみ実行できます。PowerShell より前のバージョンでモジュールをインポートしようとすると、インポート処理が次のようなエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p104">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0. If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="b1f53-132">**エラー**:*インポート-モジュール: 読み込まれた PowerShell のバージョンは ' 2.0 ' です。このモジュールでは、 \\ Program Files \\ の一般的なファイル \\ Microsoft Lync Server 2013 \\ モジュール \\ LyncOnlineConnector \\ LyncOnlineConnector ' を実行するには、少なくとが PowerShell バージョンの ' 3.0 ' が必要です。PowerShell のインストールを確認して、もう一度やり直してください。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="b1f53-133">**解決策**: この問題を解決するには、Microsoft ダウンロードセンターから入手できる Windows PowerShell 3.0 をインストールする方法しかあり [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) ません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="b1f53-134">WinRM Basic 認証が無効になっている場合、先進認証が失敗する</span><span class="sxs-lookup"><span data-stu-id="b1f53-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="b1f53-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="b1f53-136">最新バージョンの Skype for Business Online Connector モジュールは先進認証を使用しますが、基になる Windows リモート管理 (WinRM) クライアントは、基本認証を許可するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="b1f53-137">先進認証では、通常は*Authorization: bearer* header に渡される bearer トークンを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-137">Modern authentication uses bearer tokens which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="b1f53-138">Windows PowerShell (Skype for Business PowerShell が構築されている場合) では、このヘッダーの操作は許可されません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="b1f53-139">代わりに、Skype for Business PowerShell は*Authorization: Basic*ヘッダーを使って bearer トークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="b1f53-140">WinRM で基本認証を有効にする方法については[、「Windows PowerShell をダウンロードしてインストール](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-140">See [Download and install Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="b1f53-141">Live ID Server への接続の失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="b1f53-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-142"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="b1f53-143">次のエラー メッセージにより接続が失敗する場合は、通常 3 つの原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-143">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="b1f53-144">**エラー**: *Get-cswebticket: live id サーバーへの接続に失敗しました。プロキシが有効になっていることを確認するか、マシンに live id サーバへのネットワーク接続があることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-144">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="b1f53-145">**解決策**: 多くの場合、このエラーは Microsoft Online Services サインインアシスタントが実行されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-145">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="b1f53-146">このサービスの状況を確認するには、PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-146">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="b1f53-147">サービスが実行していない場合は、このコマンドを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-147">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="b1f53-148">サービスが実行している場合は、コンピュータと Microsoft Live ID 認証サーバーとの間でネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-148">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="b1f53-149">この問題が発生しているかどうかを確認するには、Internet Explorer を開き、[https://login.microsoftonline.com/](https://login.microsoftonline.com/.) に移動します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-149">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="b1f53-150">Microsoft 365 または Office 365 にログオンしてみてください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-150">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="b1f53-151">この操作が失敗する場合は、ネットワーク接続の問題が発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-151">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="b1f53-152">稀なケースとして、Microsoft Live ID 認証サーバーの接続 URI が不正な値に設定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-152">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="b1f53-153">サインイン アシスタントが実行中であり、ネットワーク接続の問題が発生していないことを既に確認している場合は、この問題が原因であることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-153">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="b1f53-154">この場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-154">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="b1f53-155">Live ID モジュールへの接続の失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-155">Failed to load Live ID module</span></span>
<span data-ttu-id="b1f53-156"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-156"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="b1f53-p109">PowerShell を使用して Skype for Business Online を管理するための前提条件として、Microsoft Online Services サインイン アシスタント のインストールがあります。サインイン アシスタントをインストールしていない場合は、Skype for Business Online でリモート セッションを確立しようとすると次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p109">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant. If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="b1f53-159">**エラー**: *Get-Cswebticket: Live Id モジュールを読み込むことができません。正しいバージョンの Live Id サインインアシスタントがインストールされていることを確認します。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-159">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="b1f53-160">**解決**方法: microsoft Online services サインインアシスタントは、 [it プロフェッショナル向けの Microsoft Online SERVICES サインインアシスタントプロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123](https://www.microsoft.com/download/details.aspx?id=28177)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-160">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="b1f53-161">ユーザーのログオンの失敗</span><span class="sxs-lookup"><span data-stu-id="b1f53-161">Logon failed for the user</span></span>
<span data-ttu-id="b1f53-162"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-162"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="b1f53-p110">Skype for Business Online にリモート接続するには、有効な Skype for Business Online ユーザー アカウントのユーザー名とパスワードを提供する必要があります。正しい資格情報を提供しないと、次のようなエラー メッセージによりログオンが失敗します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p110">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account. If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="b1f53-165">**エラー**: *Get-cswebticket: ユーザー ' Kenmyer@litwareinc.com ' のログオンに失敗しました。新しい PSCredential オブジェクトを作成して、正しいユーザー名とパスワードを使用していることを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-165">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="b1f53-166">**解決策**: 有効なユーザーアカウントを使用していて、正しいパスワードを持っていると思われる場合は、もう一度ログインしてみてください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-166">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="b1f53-167">それでも失敗する場合は、同じ資格情報を使用して [https://login.microsoftonline.com/](https://login.microsoftonline.com/) にログオンしてみてください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-167">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="b1f53-168">ログオンできない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b1f53-168">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="b1f53-169">このテナントを管理する権限がユーザーにない</span><span class="sxs-lookup"><span data-stu-id="b1f53-169">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="b1f53-170"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-170"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="b1f53-p112">テナント管理者グループのメンバー以外は、PowerShell へのリモート Skype for Business Online 接続を行うことはできません。メンバーでない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p112">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group. If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="b1f53-173">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。ユーザー ' user@foo.com ' にはこのテナントを管理する権限がありません。権限を付与するには、適切な RBAC の役割をユーザーに割り当てます。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-173">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="b1f53-174">**解像度**: テナント管理者グループのメンバーであると考えられる場合は、Microsoft サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-174">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="b1f53-175">テナントに接続する機能が Skype for Business Online で無効化されている</span><span class="sxs-lookup"><span data-stu-id="b1f53-175">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="b1f53-176"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-176"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="b1f53-p113">PowerShell を使用して Skype for Business Online を管理するには、テナント PowerShell ポリシーの EnableRemotePowerShellAccess プロパティを  `True` に設定する必要があります。この設定を行っていない場合は、接続が失敗し、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p113">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`. If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="b1f53-179">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com からデータを処理するときに、次のエラーメッセージが表示されました。リモート PowerShell セッションを使用してこのテナントに接続する機能が無効になりました。このテナントのテナント Powershell ポリシーを確認するには、Lync のヘルプにお問い合わせください。詳細については、「[リモートのトラブルシューティング](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)」を参照してください。*</span><span class="sxs-lookup"><span data-stu-id="b1f53-179">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="b1f53-180">**解決策**: このエラーメッセージが表示される場合は、Microsoft サポートに問い合わせて、リモート PowerShell アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-180">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="b1f53-181">Skype for Business Online でのこのユーザーの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="b1f53-181">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="b1f53-182"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-182"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="b1f53-p114">各管理者は、Skype for Business Online への同時リモート接続の最大数が 3 に設定されています。3 つのリモート PowerShell 接続を開始し、実行している場合に 4 つ目の同時接続を試行すると、次のエラー メッセージにより失敗します。</span><span class="sxs-lookup"><span data-stu-id="b1f53-p114">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online. If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="b1f53-185">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このユーザーの同時シェルの最大数を超過しています。このユーザーの既存のシェルを閉じるか、またはクォータを増やします。詳細については、「[リモートトラブルシューティング https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="b1f53-185">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="b1f53-186">**解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-186">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="b1f53-187">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1f53-187">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="b1f53-188">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-188">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="b1f53-189">Skype for Business Online でのこのテナントの同時シェルの最大数を超過している</span><span class="sxs-lookup"><span data-stu-id="b1f53-189">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="b1f53-190"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="b1f53-190"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="b1f53-191">各管理者には、Skype for Business Online テナントへの同時接続が最大3つまで許可されていますが、1つのテナントで同時接続を20個以下にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-191">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="b1f53-192">たとえば、6人の管理者が開いたセッションを3つ持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1f53-192">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="b1f53-193">4つの管理者が2つ以上の接続を試みる場合 (合計21個の同時接続の結果)、この試みは失敗し、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-193">If a fourth administrator tries to make more than 2 connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="b1f53-194">**エラー**:*新しい-PSSession: [admin.vdomain.com] リモートサーバー admin.vdomain.com に接続できませんでした。次のエラーメッセージが表示されます: ws-management サービスは要求を処理できません。このテナントの同時シェルの最大数を超過しています。既存のシェルを閉じるか、このテナントのクォータを上げます。詳細については、「[リモートトラブルシューティング https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ]」を参照してください*。</span><span class="sxs-lookup"><span data-stu-id="b1f53-194">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="b1f53-195">**解決策**: この問題を解決するには、1つまたは複数の以前の接続を閉じる方法しかありません。</span><span class="sxs-lookup"><span data-stu-id="b1f53-195">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="b1f53-196">Skype for Business Online セッションが終了したら、 **Remove-PSSession** コマンドレットを使用してそのセッションを切断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1f53-196">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="b1f53-197">そうすることにより、この問題が発生することを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b1f53-197">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="b1f53-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1f53-198">Related topics</span></span>
[<span data-ttu-id="b1f53-199">Windows PowerShell を使用して skype for business online 管理用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b1f53-199">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
