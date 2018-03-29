---
title: Skype for Business Server 2015 の Statistics Manager のアップグレード
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: は、Skype のビジネス サーバー 2015 のマネージャーの統計情報をアップグレードする方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: e5a9dd230f16313388cbb9a51e50910979e6c79c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="f558f-103">Skype for Business Server 2015 の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="f558f-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f558f-104">**の概要:**Skype のビジネス サーバー 2015 のマネージャーの統計情報をアップグレードする方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f558f-105">Skype のビジネス サーバーの統計マネージャーの既存のインストールをアップグレードする方法について説明-Skype をビジネスのサーバーの稼働状態とパフォーマンスのデータをリアルタイムに表示できるようにする強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="f558f-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="f558f-106">数秒ごとに数百のサーバー間でのパフォーマンス データをポーリングし、統計マネージャーの web サイトですぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f558f-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="f558f-107">統計マネージャー」と「リリース 1.1 の新機能の詳細については、 [Skype のビジネス サーバー 2015 統計マネージャーのを計画](plan.md)し、、[ビジネス サーバー 2015 の Skype の統計マネージャー展開](deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="f558f-108">リリース 1.1 で修正された既知の問題については、「[リリース 1.1 で修正された既知の問題](upgrade.md#BKMK_Fixed)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="f558f-109">アップグレードには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="f558f-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="f558f-110">**自動アップグレード**。</span><span class="sxs-lookup"><span data-stu-id="f558f-110">**Automated upgrade.**</span></span> <span data-ttu-id="f558f-111">このメソッドでは、自動化されたスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f558f-111">This method uses an automated script.</span></span> <span data-ttu-id="f558f-112">最も簡単な方法し、すべてのアップグレード シナリオに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f558f-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="f558f-113">**手動アップグレード**。</span><span class="sxs-lookup"><span data-stu-id="f558f-113">**Manual upgrade.**</span></span> <span data-ttu-id="f558f-114">このメソッドは、自動アップグレードに失敗した場合は例外的なバックアップ計画として提供されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="f558f-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="f558f-115">Prerequisites</span></span>

<span data-ttu-id="f558f-116">アップグレードする前に、以下の情報を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f558f-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="f558f-117">アクティブなリスナーの証明書の拇印</span><span class="sxs-lookup"><span data-stu-id="f558f-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="f558f-118">リスナー サービスのパスワード (リスナーおよび各エージェントのインストール時に入力)</span><span class="sxs-lookup"><span data-stu-id="f558f-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="f558f-119">Web サイトの SSL 証明書の構成</span><span class="sxs-lookup"><span data-stu-id="f558f-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="f558f-120">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="f558f-120">Automated upgrade</span></span>

<span data-ttu-id="f558f-121">このスクリプトでは、使用している現在の証明書情報およびリスナー パスワードが収集され、製品の古いバージョンをアンインストールした後、製品の新しいバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f558f-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="f558f-122">サーバーにインストールされている Redis インスタンスは関与しないため、キャッシュに格納されているデータはすべてアップグレードの間も保持されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="f558f-123">リスナーのコンピューターで 1 つのフォルダーには、エージェント、リスナー、および更新プログラム StatsMan.ps1 のスクリプトと web サイトの新しいバージョンの MSI ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="f558f-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="f558f-124">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f558f-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f558f-125">リスナーのコンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f558f-125">Upgrade the Listener component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Listener
  ```

> [!NOTE]
> <span data-ttu-id="f558f-126">統計マネージャーのサービスのパスワードは、インストーラーに渡されると、コマンド ・ ラインでクリア テキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="f558f-127">必要に応じて、使用しているディスプレイの画面を隠すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f558f-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="f558f-128">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f558f-129">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="f558f-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="f558f-130">リスナー サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="f558f-131">(統計マネージャー リスナー サービスが停止されます) を終了するアプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="f558f-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="f558f-132">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="f558f-132">Continue the install process.</span></span> <span data-ttu-id="f558f-133">サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="f558f-134">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f558f-134">If not, add the values you saved before continuing.</span></span>
    
3. <span data-ttu-id="f558f-135">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f558f-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f558f-136">Web サイト コンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f558f-136">Upgrade the Website component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Website
  ```

1. <span data-ttu-id="f558f-137">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f558f-138">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="f558f-138">Answer Yes.</span></span>
    
2. <span data-ttu-id="f558f-139">エージェント サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="f558f-140">このアプリケーションを閉じることを許可します (StatsMan エージェント サービスが停止します)。</span><span class="sxs-lookup"><span data-stu-id="f558f-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
3. <span data-ttu-id="f558f-141">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="f558f-141">Continue the install process.</span></span> <span data-ttu-id="f558f-142">サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="f558f-143">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f558f-143">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="f558f-144">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f558f-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="f558f-145">エージェント コンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f558f-145">Upgrade the Agent component:</span></span>
    
  ```
  .\Update-StatsMan.ps1 -Service Agent
  ```

1. <span data-ttu-id="f558f-146">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f558f-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="f558f-147">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="f558f-147">Answer Yes.</span></span>
    
2. <span data-ttu-id="f558f-148">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="f558f-148">Continue the install process.</span></span> <span data-ttu-id="f558f-149">Web サイトのポートがあらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="f558f-150">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="f558f-150">If not, add the value you saved before continuing.</span></span>
    
3. <span data-ttu-id="f558f-151">ブラウザーを使用して、Web サイトが期待したとおりに機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f558f-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f558f-152">エージェントのアップグレードでは、-NoPrompt スイッチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f558f-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="f558f-153">このスイッチを使用すると、アンインストール プロセスやインストール プロセスでのメッセージの確認が省略でき、PSExec などのツールを使用して大量のサーバーのアップグレードをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="f558f-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="f558f-154">手動アップグレード</span><span class="sxs-lookup"><span data-stu-id="f558f-154">Manual upgrade</span></span>

<span data-ttu-id="f558f-155">何らかの理由で自動アップグレードが失敗する場合、いつでも手動アップグレードを以下の手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="f558f-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="f558f-156">	リスナーのコンピューターで、リスナー、Web サイト、およびエージェント (このエージェントがこのサーバーにインストールされている場合) を [プログラムと機能] コントロール パネルを使用してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f558f-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="f558f-157"> アップグレード プロセスを通して Redis のキャッシュ内のデータを維持できるように、Redis をインストールしたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="f558f-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="f558f-p119">	上記の手順で値の保存の確認メッセージが表示されたときに保存した値を含め、コンポーネントの新しいバージョンをインストールします。コンポーネントのインストールの詳細については、「[Statistics Manager の展開](deploy.md#BKMK_Deploy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="f558f-160">リリース 1.1 で修正された既知の問題</span><span class="sxs-lookup"><span data-stu-id="f558f-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="f558f-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="f558f-161"></span></span>

<span data-ttu-id="f558f-162">以下の既知の問題がリリース 1.1 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="f558f-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="f558f-163">UI とサーバーとエージェントの多数の重要な信頼性とパフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="f558f-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="f558f-164">UI のメイン フィルター コントロールここでは正しく並べ替えられますと異なる場合 (特定のだったときにシステムでは、サーバーがないと思われる人が先頭)</span><span class="sxs-lookup"><span data-stu-id="f558f-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="f558f-165">サーバー - サーバー コンポーネントを英語以外のサーバーにもインストールできるようになった</span><span class="sxs-lookup"><span data-stu-id="f558f-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="f558f-166">サーバー/エージェント - .NET 4.0 の特定バージョンであることが原因で、.NET エラーが発生してエージェント コンポーネントおよびサーバー コンポーネントがインストールされないことがあった。</span><span class="sxs-lookup"><span data-stu-id="f558f-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="f558f-167">この問題は、解決されました。</span><span class="sxs-lookup"><span data-stu-id="f558f-167">This has been resolved.</span></span>
    
- <span data-ttu-id="f558f-168">エージェント ・ StatsMan ・ エージェントの追加のイベント ログを拡張します。</span><span class="sxs-lookup"><span data-stu-id="f558f-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="f558f-169">トポロジではなくサーバーにインストールされている場合、エージェントはクラッシュしなく、これは他の多くの考えられるエラー状態と、イベント ログにログオンしています。</span><span class="sxs-lookup"><span data-stu-id="f558f-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="f558f-170">UI のクロムのブラウザーを使用して Web クライアントを参照してください複数のログイン プロンプトが同じ統計マネージャーの Web サーバーとドメインまたはワークグループに参加していないクライアント コンピューターを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="f558f-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="f558f-171">セッションごとに単一のログインのみが必要になりました。</span><span class="sxs-lookup"><span data-stu-id="f558f-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="f558f-172">関連情報</span><span class="sxs-lookup"><span data-stu-id="f558f-172">For more information</span></span>
<span data-ttu-id="f558f-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="f558f-173"></span></span>

<span data-ttu-id="f558f-174">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f558f-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="f558f-175">ビジネス サーバー 2015 Skype 統計マネージャーの計画します。</span><span class="sxs-lookup"><span data-stu-id="f558f-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="f558f-176">ビジネス サーバー 2015 の Skype の統計マネージャーの展開します。</span><span class="sxs-lookup"><span data-stu-id="f558f-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="f558f-177">ビジネス サーバー 2015 の Skype の統計マネージャーのトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f558f-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="f558f-178">Skype ビジネス サーバー統計マネージャーのブログ</span><span class="sxs-lookup"><span data-stu-id="f558f-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

