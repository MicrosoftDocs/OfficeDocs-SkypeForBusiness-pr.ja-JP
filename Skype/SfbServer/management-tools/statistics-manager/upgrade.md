---
title: Skype for Business Server の統計情報マネージャーのアップグレード
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager をアップグレードする方法について説明します。'
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821767"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="b5eff-103">Skype for Business Server の統計情報マネージャーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="b5eff-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="b5eff-104">**概要:** このトピックでは、Skype for Business Server の Statistics Manager をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="b5eff-105">このトピックでは、Skype for Business Server の Statistics Manager の既存のインストールをアップグレードする方法について説明します。これは、Skype for Business Server の正常性とパフォーマンスのデータをリアルタイムで表示できる強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="b5eff-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="b5eff-106">数秒ごとに数百のサーバーでパフォーマンス データをポーリングし、統計情報マネージャー Web サイトで即座に結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="b5eff-107">Statistics Manager とリリース 2.0 の新機能の詳細については [、「Plan for Statistics Manager for Skype for Business Server」](plan.md) および [「Deploy Statistics Manager for Skype for Business Server」](deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5eff-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="b5eff-108">アップグレードには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="b5eff-109">**自動アップグレード。**</span><span class="sxs-lookup"><span data-stu-id="b5eff-109">**Automated upgrade.**</span></span> <span data-ttu-id="b5eff-110">このメソッドでは、自動化されたスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-110">This method uses an automated script.</span></span> <span data-ttu-id="b5eff-111">これは最も簡単な方法であり、すべてのアップグレード シナリオに適用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="b5eff-112">**手動アップグレード。**</span><span class="sxs-lookup"><span data-stu-id="b5eff-112">**Manual upgrade.**</span></span> <span data-ttu-id="b5eff-113">この方法は、自動アップグレードが失敗する異常な場合のバックアップ計画として提供されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="b5eff-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="b5eff-114">Prerequisites</span></span>

<span data-ttu-id="b5eff-115">アップグレードする前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b5eff-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="b5eff-116">アクティブ リスナー証明書の拇印</span><span class="sxs-lookup"><span data-stu-id="b5eff-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="b5eff-117">リスナー サービス パスワード (リスナーとすべてのエージェントのインストール時に入力)</span><span class="sxs-lookup"><span data-stu-id="b5eff-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="b5eff-118">Web サイトの SSL 証明書の構成</span><span class="sxs-lookup"><span data-stu-id="b5eff-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="b5eff-119">自動アップグレード</span><span class="sxs-lookup"><span data-stu-id="b5eff-119">Automated upgrade</span></span>

<span data-ttu-id="b5eff-120">スクリプトは、現在の証明書情報とリスナーパスワードを収集し、古いバージョンの製品をアンインストールしてから、製品の新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b5eff-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="b5eff-121">サーバーにインストールされている Redis インスタンスにはアクセスしないので、キャッシュに格納されているデータはアップグレード プロセスを通じて保持されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="b5eff-122">新しいバージョンのエージェント、リスナー、Web サイトの MSI ファイルを、Update-StatsMan.ps1 スクリプトと共にリスナー コンピューター上の 1 つのフォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="b5eff-123">管理用 PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="b5eff-124">リスナー コンポーネントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="b5eff-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="b5eff-125">Statistics Manager サービスのパスワードは、インストーラーに渡されるコマンド ラインにクリア テキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="b5eff-126">必要に応じて、必ずモニターをシールドしてください。</span><span class="sxs-lookup"><span data-stu-id="b5eff-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="b5eff-127">スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="b5eff-128">回答はい。</span><span class="sxs-lookup"><span data-stu-id="b5eff-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="b5eff-129">リスナー サービスが実行されている場合は、続行する前にアプリケーションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="b5eff-130">アプリケーションの終了を許可します (Statistics Manager リスナー サービスが停止します)。</span><span class="sxs-lookup"><span data-stu-id="b5eff-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="b5eff-131">インストール プロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-131">Continue the install process.</span></span> <span data-ttu-id="b5eff-132">サービス パスワードと証明書の拇印が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="b5eff-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="b5eff-133">設定されていない場合は、続行する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="b5eff-134">管理用 PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="b5eff-135">Web サイト コンポーネントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="b5eff-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="b5eff-136">スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="b5eff-137">「はい」と答えます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="b5eff-138">エージェント サービスが実行されている場合は、続行する前にアプリケーションを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="b5eff-139">アプリケーションの終了を許可します (StatsMan エージェント サービスが停止します)。</span><span class="sxs-lookup"><span data-stu-id="b5eff-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="b5eff-140">インストール プロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-140">Continue the install process.</span></span> <span data-ttu-id="b5eff-141">サービス パスワードと証明書の拇印が事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="b5eff-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="b5eff-142">設定されていない場合は、続行する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="b5eff-143">管理用 PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="b5eff-144">エージェント コンポーネントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="b5eff-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="b5eff-145">スクリプトを実行すると、製品の古いバージョンをアンインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="b5eff-146">回答はい。</span><span class="sxs-lookup"><span data-stu-id="b5eff-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="b5eff-147">インストール プロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-147">Continue the install process.</span></span> <span data-ttu-id="b5eff-148">Web サイトのポートが事前に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5eff-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="b5eff-149">設定されていない場合は、続行する前に保存した値を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="b5eff-150">ブラウザーを使用して Web サイトが期待通り動作しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5eff-151">エージェント アップグレードは -NoPrompt スイッチと一緒に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="b5eff-152">これにより、アンインストール/インストール プロセスをサイレント モードで実行でき、PSExec などのツールは多数のサーバーでリモートでアップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="b5eff-153">手動アップグレード</span><span class="sxs-lookup"><span data-stu-id="b5eff-153">Manual upgrade</span></span>

<span data-ttu-id="b5eff-154">何らかの理由で自動アップグレードが失敗した場合は、次のようにいつでも手動アップグレードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="b5eff-155">リスナー コンピューターで、リスナー、Web サイト、およびエージェント (このサーバーにインストールされている場合) を、次のコントロール パネルプログラムと機能アンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b5eff-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="b5eff-156">アップグレード プロセスを通じてキャッシュ内のデータを維持するために、Redis をインストールした状態に維持します。</span><span class="sxs-lookup"><span data-stu-id="b5eff-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="b5eff-157">新しいバージョンのコンポーネントをインストールします。これらのコンポーネントの入力を求めるメッセージが表示されたら、上記で保存した値も含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5eff-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="b5eff-158">コンポーネントのインストールの詳細については、「Statistics Manager の展開」 [を参照してください。](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="b5eff-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="b5eff-159">関連情報</span><span class="sxs-lookup"><span data-stu-id="b5eff-159">For more information</span></span>
<span data-ttu-id="b5eff-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="b5eff-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="b5eff-161">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5eff-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="b5eff-162">Skype for Business Server の Statistics Manager の計画</span><span class="sxs-lookup"><span data-stu-id="b5eff-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="b5eff-163">Skype for Business Server の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="b5eff-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="b5eff-164">Skype for Business Server の Statistics Manager のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b5eff-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
