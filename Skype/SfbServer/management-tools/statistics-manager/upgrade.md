---
title: ビジネス サーバーの Skype の統計マネージャーをアップグレードします。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: は、Skype のビジネス サーバーの統計情報マネージャーをアップグレードする方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: e2118377fc782af6818d070bc0bd3f5ddacab99e
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297896"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="923be-103">ビジネス サーバーの Skype の統計マネージャーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="923be-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="923be-104">**の概要:** Skype のビジネス サーバーの統計情報マネージャーをアップグレードする方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="923be-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="923be-105">Skype のビジネス サーバーの統計マネージャーの既存のインストールをアップグレードする方法について説明-Skype をビジネスのサーバーの稼働状態とパフォーマンスのデータをリアルタイムに表示できるようにする強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="923be-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="923be-106">数秒ごとに数百のサーバー間でのパフォーマンス データをポーリングし、統計マネージャーの web サイトですぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="923be-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="923be-107">統計マネージャーおよびリリース 2.0 の新機能に関する詳細については、 [Skype のビジネス サーバー統計マネージャーを計画](plan.md)し、 [Skype のビジネス サーバーの統計マネージャーの展開](deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923be-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="923be-108">アップグレードには、以下の 2 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="923be-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="923be-109">**自動アップグレード**。</span><span class="sxs-lookup"><span data-stu-id="923be-109">**Automated upgrade.**</span></span> <span data-ttu-id="923be-110">このメソッドでは、自動化されたスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="923be-110">This method uses an automated script.</span></span> <span data-ttu-id="923be-111">最も簡単な方法し、すべてのアップグレード シナリオに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923be-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="923be-112">**手動アップグレード**。</span><span class="sxs-lookup"><span data-stu-id="923be-112">**Manual upgrade.**</span></span> <span data-ttu-id="923be-113">このメソッドは、自動アップグレードに失敗した場合は例外的なバックアップ計画として提供されます。</span><span class="sxs-lookup"><span data-stu-id="923be-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="923be-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="923be-114">Prerequisites</span></span>

<span data-ttu-id="923be-115">アップグレードする前に、以下の情報を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="923be-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="923be-116">アクティブなリスナーの証明書の拇印</span><span class="sxs-lookup"><span data-stu-id="923be-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="923be-117">リスナー サービスのパスワード (リスナーおよび各エージェントのインストール時に入力)</span><span class="sxs-lookup"><span data-stu-id="923be-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="923be-118">Web サイトの SSL 証明書の構成</span><span class="sxs-lookup"><span data-stu-id="923be-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="923be-119">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="923be-119">Automated upgrade</span></span>

<span data-ttu-id="923be-120">このスクリプトでは、使用している現在の証明書情報およびリスナー パスワードが収集され、製品の古いバージョンをアンインストールした後、製品の新しいバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="923be-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="923be-121">サーバーにインストールされている Redis インスタンスは関与しないため、キャッシュに格納されているデータはすべてアップグレードの間も保持されます。</span><span class="sxs-lookup"><span data-stu-id="923be-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="923be-122">リスナーのコンピューターで 1 つのフォルダーには、エージェント、リスナー、および更新プログラム StatsMan.ps1 のスクリプトと web サイトの新しいバージョンの MSI ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="923be-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="923be-123">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="923be-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="923be-124">リスナーのコンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="923be-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="923be-125">統計マネージャーのサービスのパスワードは、インストーラーに渡されると、コマンド ・ ラインでクリア テキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="923be-126">必要に応じて、使用しているディスプレイの画面を隠すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="923be-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="923be-127">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="923be-128">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="923be-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="923be-129">リスナー サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="923be-130">(統計マネージャー リスナー サービスが停止されます) を終了するアプリケーションを許可します。</span><span class="sxs-lookup"><span data-stu-id="923be-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="923be-131">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="923be-131">Continue the install process.</span></span> <span data-ttu-id="923be-132">サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="923be-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="923be-133">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="923be-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="923be-134">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="923be-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="923be-135">Web サイト コンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="923be-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="923be-136">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="923be-137">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="923be-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="923be-138">エージェント サービスが実行中の場合、継続する前にこのアプリケーションを閉じるかどうか確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="923be-139">このアプリケーションを閉じることを許可します (StatsMan エージェント サービスが停止します)。</span><span class="sxs-lookup"><span data-stu-id="923be-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="923be-140">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="923be-140">Continue the install process.</span></span> <span data-ttu-id="923be-141">サービス パスワードと証明書の拇印があらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="923be-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="923be-142">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="923be-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="923be-143">管理用の PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="923be-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="923be-144">エージェント コンポーネントを、以下の手順でアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="923be-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="923be-145">スクリプトの実行中に、製品の古いバージョンをアンインストールするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="923be-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="923be-146">「Yes (はい)」と答えます。</span><span class="sxs-lookup"><span data-stu-id="923be-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="923be-147">インストール プロセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="923be-147">Continue the install process.</span></span> <span data-ttu-id="923be-148">Web サイトのポートがあらかじめ入力されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="923be-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="923be-149">入力されていない場合は、継続する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="923be-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="923be-150">ブラウザーを使用して、Web サイトが期待したとおりに機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="923be-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="923be-151">エージェントのアップグレードでは、-NoPrompt スイッチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="923be-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="923be-152">このスイッチを使用すると、アンインストール プロセスやインストール プロセスでのメッセージの確認が省略でき、PSExec などのツールを使用して大量のサーバーのアップグレードをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="923be-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="923be-153">手動アップグレード</span><span class="sxs-lookup"><span data-stu-id="923be-153">Manual upgrade</span></span>

<span data-ttu-id="923be-154">何らかの理由で自動アップグレードが失敗する場合、いつでも手動アップグレードを以下の手順で実行できます。</span><span class="sxs-lookup"><span data-stu-id="923be-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="923be-155">	リスナーのコンピューターで、リスナー、Web サイト、およびエージェント (このエージェントがこのサーバーにインストールされている場合) を [プログラムと機能] コントロール パネルを使用してアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="923be-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="923be-156"> アップグレード プロセスを通して Redis のキャッシュ内のデータを維持できるように、Redis をインストールしたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="923be-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="923be-p118">	上記の手順で値の保存の確認メッセージが表示されたときに保存した値を含め、コンポーネントの新しいバージョンをインストールします。コンポーネントのインストールの詳細については、「[Statistics Manager の展開](deploy.md#BKMK_Deploy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923be-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="923be-159">関連情報</span><span class="sxs-lookup"><span data-stu-id="923be-159">For more information</span></span>
<span data-ttu-id="923be-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="923be-160"></span></span>

<span data-ttu-id="923be-161">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="923be-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="923be-162">Skype 統計マネージャーのビジネス サーバー計画します。</span><span class="sxs-lookup"><span data-stu-id="923be-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="923be-163">ビジネス サーバーの Skype の統計マネージャーを展開します。</span><span class="sxs-lookup"><span data-stu-id="923be-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="923be-164">統計マネージャーは、Skype のビジネス サーバーのトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="923be-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
