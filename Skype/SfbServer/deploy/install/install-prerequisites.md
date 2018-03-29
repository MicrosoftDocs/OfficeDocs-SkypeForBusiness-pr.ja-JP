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
description: '概要: については、サーバーとサーバーの役割がビジネス サーバー 2015 の Skype をインストールする前に構成する必要があります。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="c358f-104">Skype for Business Server 2015 の前提条件のインストール</span><span class="sxs-lookup"><span data-stu-id="c358f-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c358f-105">**の概要:**サーバーとビジネス サーバー 2015 の Skype をインストールする前に構成する必要がありますサーバーの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="c358f-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="c358f-106">[マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からサーバー 2015 をビジネス用には、Skype の無料試用版をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c358f-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="c358f-107">必須コンポーネントのインストールは、トポロジ内のサーバーごとに必要な役割と機能をインストールすることによって Windows のサーバーを設定するので構成されます。</span><span class="sxs-lookup"><span data-stu-id="c358f-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="c358f-108">要件は、サーバーをトポロジに満たす役割に基づいています。</span><span class="sxs-lookup"><span data-stu-id="c358f-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="c358f-109">手順 1 ～ 5 は任意の順序で実行できます。</span><span class="sxs-lookup"><span data-stu-id="c358f-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="c358f-110">ただし、手順 6、7、8 は、図に説明されているように手順 1 ～ 5 の後で順番どおりに行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="c358f-111">8 のステップ 1 は、必須コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c358f-111">Installing prerequisites is step 1 of 8.</span></span>
  
![概要図 - インストールの前提条件](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="c358f-113">Windows Server をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c358f-113">Setup Windows Server</span></span>

<span data-ttu-id="c358f-114">ビジネス サーバー 2015 の Skype では、インストールする前に Windows サーバー オペレーティング システムおよび前提条件の多くを必要です。</span><span class="sxs-lookup"><span data-stu-id="c358f-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="c358f-115">前提条件の計画に関する詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="c358f-p105">この手順では Windows Server 2012 R2 を使用します。別のバージョンの Windows Server を使用する場合は、手順が若干異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="c358f-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c358f-118">作業を開始する前に、Windows Server は、Windows Update を使用して最新の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c358f-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server を最新の状態にする](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="c358f-120">**前提条件のインストール**手順に関するビデオを見てください。</span><span class="sxs-lookup"><span data-stu-id="c358f-120">Watch the video steps for **install prerequisites**:</span></span>
  
![ブラウザーがビデオをサポートしていません。Microsoft Silverlight、Adobe Flash Player、または Internet Explorer 9 をインストールしてください。](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="c358f-123">フロントエンド サーバーに必要な役割と機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="c358f-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="c358f-124">サーバー マネージャーを開き、[**役割と機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="c358f-125">[**開始する前に**] ページを読んで Windows Server への役割と機能のインストールについて理解を深めてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="c358f-126">[**役割ベースまたは機能ベースのインストール**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="c358f-127">サーバーにするビジネス サーバー 2015 年の Skype をインストールしてする [**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c358f-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="c358f-128">役割として [**Web サーバー (IIS)**] を選択します。必要な機能に関するウィンドウが開いたら、[**機能の追加**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c358f-129">ビジネス サーバー 2015 の Skype を実行するサーバーでは、[サーバー 2015 のビジネスを展開するため、Skype の前にインストールするソフトウェア](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software)に記載されているソフトウェアの機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="c358f-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="c358f-130">省略形の一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c358f-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="c358f-131">.NET Framework の機能</span><span class="sxs-lookup"><span data-stu-id="c358f-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="c358f-132">WCF サービス</span><span class="sxs-lookup"><span data-stu-id="c358f-132">WCF Services</span></span>
    
   - <span data-ttu-id="c358f-133">HTTP アクティブ化</span><span class="sxs-lookup"><span data-stu-id="c358f-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c358f-p108">HTTP アクティブ化には追加の機能が必要です。[HTTP アクティブ化] を選択したときに表示される警告ダイアログ ボックスで、[**機能の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="c358f-136">メディアの基礎 (会議のために使用されるフロント エンド サーバーと Standard Edition のサーバーで必要な)。</span><span class="sxs-lookup"><span data-stu-id="c358f-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="c358f-137">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="c358f-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="c358f-138">役割管理ツール</span><span class="sxs-lookup"><span data-stu-id="c358f-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="c358f-139">AD DS</span><span class="sxs-lookup"><span data-stu-id="c358f-139">AD DS</span></span> 
    
   - <span data-ttu-id="c358f-140">AD LDS</span><span class="sxs-lookup"><span data-stu-id="c358f-140">AD LDS</span></span>
    
   - <span data-ttu-id="c358f-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="c358f-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="c358f-142">[**次へ**] をクリックして、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="c358f-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="c358f-143">**Web サーバー (IIS) の役割**に関する注意を読み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="c358f-144">**Web Server (IIS) の役割サービス**として次を選択します。</span><span class="sxs-lookup"><span data-stu-id="c358f-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="c358f-145">HTTP 共通機能</span><span class="sxs-lookup"><span data-stu-id="c358f-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="c358f-146">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="c358f-146">Default Document</span></span>
    
   - <span data-ttu-id="c358f-147">ディレクトリの参照</span><span class="sxs-lookup"><span data-stu-id="c358f-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="c358f-148">HTTP エラー</span><span class="sxs-lookup"><span data-stu-id="c358f-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="c358f-149">静的コンテンツ</span><span class="sxs-lookup"><span data-stu-id="c358f-149">Static Content</span></span>
    
   - <span data-ttu-id="c358f-150">状態と診断</span><span class="sxs-lookup"><span data-stu-id="c358f-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="c358f-151">HTTP ログ</span><span class="sxs-lookup"><span data-stu-id="c358f-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="c358f-152">ログ ツール</span><span class="sxs-lookup"><span data-stu-id="c358f-152">Logging Tools</span></span>
    
   - <span data-ttu-id="c358f-153">追跡</span><span class="sxs-lookup"><span data-stu-id="c358f-153">Tracing</span></span>
    
   - <span data-ttu-id="c358f-154">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c358f-154">Performance</span></span>
    
   - <span data-ttu-id="c358f-155">静的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="c358f-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="c358f-156">動的コンテンツ圧縮</span><span class="sxs-lookup"><span data-stu-id="c358f-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="c358f-157">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c358f-157">Security</span></span>
    
   - <span data-ttu-id="c358f-158">要求のフィルタリング</span><span class="sxs-lookup"><span data-stu-id="c358f-158">Request Filtering</span></span>
    
   - <span data-ttu-id="c358f-159">クライアント証明書マッピング認証</span><span class="sxs-lookup"><span data-stu-id="c358f-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="c358f-160">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="c358f-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="c358f-161">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="c358f-161">Application Development</span></span>
    
   - <span data-ttu-id="c358f-162">.NET 拡張機能 3.5</span><span class="sxs-lookup"><span data-stu-id="c358f-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="c358f-163">.NET 拡張機能 4.5</span><span class="sxs-lookup"><span data-stu-id="c358f-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="c358f-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="c358f-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="c358f-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="c358f-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="c358f-166">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="c358f-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="c358f-167">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="c358f-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="c358f-168">管理ツール</span><span class="sxs-lookup"><span data-stu-id="c358f-168">Management Tools</span></span>
    
   - <span data-ttu-id="c358f-169">IIS 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="c358f-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="c358f-170">IIS 管理スクリプトおよびツール</span><span class="sxs-lookup"><span data-stu-id="c358f-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="c358f-171">[**次へ**] をクリックして、ウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="c358f-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="c358f-172">インストールに関する選択を見直し、すべての要件が選択されていることを確認して、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c358f-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c358f-173">既定では、必要な機能のソース ファイルのすべてが Windows Server 2012 R2 でインストールされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c358f-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="c358f-174">サーバーがインターネットに接続されていない場合は、必要な機能をインストールするために、Windows Server 2012 R2 メディアを挿入し、[**代替ソース パスの指定**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="c358f-175">ソース ファイルは sources\sxs ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="c358f-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="c358f-176">たとえば、Windows Server 2012 R2 メディアをドライブ D に挿入した場合は、パスを `d:\sources\sxs` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c358f-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="c358f-177">> その方法は、Windows Update から最新の更新プログラムがあることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c358f-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="c358f-178">インターネットに接続していない場合は、関連するすべての更新プログラムと、必要な更新プログラムの前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="c358f-179">ダイアログ ボックスにインストールの完了が通知されたら、サーバーを再起動して処理を完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="c358f-180">インストールした役割とサービスの更新プログラムがないかどうかを確認するために、**Windows Update** を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="c358f-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="c358f-181">使用する Skype ビジネス サーバーのコントロール パネルのこのサーバーの場合、Silverlight もインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="c358f-182">Silverlight をインストールするには、 [Microsoft Silverlight](https://www.microsoft.com/silverlight/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="c358f-183">前提条件となる各機能は、次の PowerShell コマンドを実行してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c358f-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="c358f-184">このコマンドがソース ファイルを探す順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="c358f-185">オンラインの場合、このコマンドは Windows Update にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c358f-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="c358f-186">一方、オフラインの場合は、このコマンドがソース ファイルにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="c358f-187">PowerShell を使用して、役割と機能をインストールする詳細については、[インストールまたはアンインストールの役割、役割サービス、または機能](https://technet.microsoft.com/en-us/library/hh831809.aspx)と[インストール WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="c358f-188">前提条件となる機能のインストールが終わったら、PowerShell コマンドを使用した場合であっても、必ず Windows Update を再実行してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="c358f-189">ディレクター、常設チャット、エッジなど、フロントエンド サーバー以外の役割を実行するサーバーには、また別の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="c358f-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="c358f-190">サーバーの種類ごとに必要な正確な前提条件の詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c358f-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

