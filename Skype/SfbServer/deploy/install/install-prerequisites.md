---
title: Skype for Business Server 2015 の前提条件のインストール
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="829fc-104">Skype for Business Server 2015 の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="829fc-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="829fc-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="829fc-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="829fc-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="829fc-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="829fc-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span><span class="sxs-lookup"><span data-stu-id="829fc-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="829fc-108">The requirements are based on the role the server will fulfill in the topology.</span><span class="sxs-lookup"><span data-stu-id="829fc-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="829fc-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="829fc-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="829fc-110">ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="829fc-111">Installing prerequisites is step 1 of 8.</span><span class="sxs-lookup"><span data-stu-id="829fc-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="829fc-113">Windows Server をセットアップする</span><span class="sxs-lookup"><span data-stu-id="829fc-113">Setup Windows Server</span></span>

<span data-ttu-id="829fc-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span><span class="sxs-lookup"><span data-stu-id="829fc-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="829fc-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="829fc-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="829fc-p105">この手順では Windows Server 2012 R2 を使用します。別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="829fc-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="829fc-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span><span class="sxs-lookup"><span data-stu-id="829fc-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="829fc-120">**前提条件のインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="829fc-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="829fc-121">フロントエンド サーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="829fc-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="829fc-122">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="829fc-123">[**開始する前に**] ページを読んで Windows Server への役割と機能のインストールについて理解を深めてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="829fc-124">[**役割ベースまたは機能ベースのインストール**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="829fc-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="829fc-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="829fc-126">役割として [**Web サーバー (IIS)**] を選択します。必要な機能に関するウィンドウが開いたら、[**機能の追加**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="829fc-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="829fc-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="829fc-128">Here's an abbreviated list:</span><span class="sxs-lookup"><span data-stu-id="829fc-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="829fc-129">.NET Framework Features</span><span class="sxs-lookup"><span data-stu-id="829fc-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="829fc-130">WCF サービス</span><span class="sxs-lookup"><span data-stu-id="829fc-130">WCF Services</span></span>
    
   - <span data-ttu-id="829fc-131">HTTP アクティブ化</span><span class="sxs-lookup"><span data-stu-id="829fc-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="829fc-p107">HTTP アクティブ化には追加の機能が必要です。[HTTP アクティブ化] を選択したときに表示される警告ダイアログ ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="829fc-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span><span class="sxs-lookup"><span data-stu-id="829fc-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="829fc-135">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="829fc-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="829fc-136">役割管理ツール</span><span class="sxs-lookup"><span data-stu-id="829fc-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="829fc-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="829fc-137">AD DS</span></span> 
    
   - <span data-ttu-id="829fc-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="829fc-138">AD LDS</span></span>
    
   - <span data-ttu-id="829fc-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="829fc-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="829fc-140">[**次へ**] をクリックして、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="829fc-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="829fc-141">**Web サーバー (IIS) の役割**に関する注意を読み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="829fc-142">**Web Server (IIS) の役割サービス**として次を選択します。</span><span class="sxs-lookup"><span data-stu-id="829fc-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="829fc-143">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="829fc-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="829fc-144">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="829fc-144">Default Document</span></span>
    
   - <span data-ttu-id="829fc-145">ディレクトリの参照</span><span class="sxs-lookup"><span data-stu-id="829fc-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="829fc-146">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="829fc-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="829fc-147">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="829fc-147">Static Content</span></span>
    
   - <span data-ttu-id="829fc-148">状態と診断</span><span class="sxs-lookup"><span data-stu-id="829fc-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="829fc-149">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="829fc-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="829fc-150">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="829fc-150">Logging Tools</span></span>
    
   - <span data-ttu-id="829fc-151">追跡</span><span class="sxs-lookup"><span data-stu-id="829fc-151">Tracing</span></span>
    
   - <span data-ttu-id="829fc-152">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="829fc-152">Performance</span></span>
    
   - <span data-ttu-id="829fc-153">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="829fc-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="829fc-154">動的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="829fc-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="829fc-155">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="829fc-155">Security</span></span>
    
   - <span data-ttu-id="829fc-156">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="829fc-156">Request Filtering</span></span>
    
   - <span data-ttu-id="829fc-157">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="829fc-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="829fc-158">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="829fc-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="829fc-159">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="829fc-159">Application Development</span></span>
    
   - <span data-ttu-id="829fc-160">.NET 拡張機能 3.5</span><span class="sxs-lookup"><span data-stu-id="829fc-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="829fc-161">.NET 拡張機能 4.5</span><span class="sxs-lookup"><span data-stu-id="829fc-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="829fc-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="829fc-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="829fc-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="829fc-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="829fc-164">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="829fc-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="829fc-165">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="829fc-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="829fc-166">管理ツール</span><span class="sxs-lookup"><span data-stu-id="829fc-166">Management Tools</span></span>
    
   - <span data-ttu-id="829fc-167">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="829fc-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="829fc-168">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="829fc-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="829fc-169">[**次へ**] をクリックして、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="829fc-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="829fc-170">インストールに関する選択を見直し、すべての要件が選択されていることを確認して、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="829fc-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="829fc-171">既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="829fc-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="829fc-172">サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="829fc-173">ソース ファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="829fc-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="829fc-174">たとえば、Windows Server 2012 R2 メディアをドライブ D に挿入した場合は、パスを `d:\sources\sxs` に設定します。</span><span class="sxs-lookup"><span data-stu-id="829fc-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="829fc-175">> It is important that you have the latest updates from Windows Update.</span><span class="sxs-lookup"><span data-stu-id="829fc-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="829fc-176">インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="829fc-177">ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="829fc-178">インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="829fc-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="829fc-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span><span class="sxs-lookup"><span data-stu-id="829fc-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="829fc-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="829fc-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="829fc-181">前提条件となる各機能は、次の PowerShell コマンドを実行してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="829fc-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="829fc-182">このコマンドがソース ファイルを探す順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="829fc-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="829fc-183">オンラインの場合、このコマンドは Windows Update にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="829fc-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="829fc-184">一方、オフラインの場合は、このコマンドがソース ファイルにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="829fc-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="829fc-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="829fc-186">前提条件となる機能のインストールが終わったら、PowerShell コマンドを使用した場合であっても、必ず Windows Update を再実行してください。</span><span class="sxs-lookup"><span data-stu-id="829fc-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="829fc-187">ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="829fc-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="829fc-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="829fc-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

