---
title: Skype for Business Server の統計情報マネージャーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '概要: このトピックでは、Skype for Business Server の統計情報マネージャーを展開する方法について説明します。'
ms.openlocfilehash: c70bb596914142fb03e87ccd7e2f1df606aac31f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33864905"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="5e10f-103">Skype for Business Server の統計情報マネージャーの展開</span><span class="sxs-lookup"><span data-stu-id="5e10f-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="5e10f-104">**概要:** このトピックでは、Skype for Business Server の 統計情報マネージャーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="5e10f-105">Skype for Business Server 統計情報マネージャーは、リアルタイムでビジネス サーバーの状態とパフォーマンス データを Skype で表示する事ができる強力なツールです。  </span><span class="sxs-lookup"><span data-stu-id="5e10f-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="5e10f-106">数秒ごとに数百のサーバーのパフォーマンス データをポーリングでき、その結果をすぐに統計情報 マネージャーのウェブ サイト上に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="5e10f-107">統計情報マネージャーをインストールする前に、ソフトウェア、ネットワーク、ハードウェアの要件について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="5e10f-108">詳細については、[Skype for Business Server の統計情報マネージャーの計画](plan.md)を参照ください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e10f-109">統計情報マネージャーを以前のバージョンからアップグレードする場合は、[Skype for Business Server の統計情報マネージャーのアップグレード](upgrade.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5e10f-110">統計情報マネージャーのウェブ サイトはテスト済みで Internet Explorer 11 以降、Edge 20.10240 以降、Chrome 46 以降 (現在広く使用されているバージョン) で正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="5e10f-111">下記のリンクで統計情報マネージャーをダウンロードできます。[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)</span><span class="sxs-lookup"><span data-stu-id="5e10f-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="5e10f-112">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="5e10f-113">Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="5e10f-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="5e10f-114">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5e10f-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="5e10f-115">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="5e10f-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="5e10f-116">Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="5e10f-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="5e10f-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="5e10f-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="5e10f-118">統計情報マネージャーを展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="5e10f-119">リスナーのホスト コンピューターを準備します。その際は、Redis メモリ内キャッシュ システムをインストールすることと、適切な証明書をインストールしたことを確認することが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="5e10f-120">リスナー サービスをホスト コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="5e10f-121">Web サイトをホスト コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="5e10f-122">監視したい各 Skype for Business Server にエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="5e10f-123">監視しているサーバーのトポロジをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5e10f-124">Redis、リスナー サービス、Web サイトは同一のホスト コンピューターにインストールされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e10f-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="5e10f-125">ホスト コンピューターに Skype for Business Server がインストールされていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="5e10f-126">リスナーのホスト コンピューターの準備</span><span class="sxs-lookup"><span data-stu-id="5e10f-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="5e10f-127">ホスト コンピューターを準備するには、Redis メモリ内キャッシュ システムをインストールして、有効な証明書がコンピューター上にあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e10f-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="5e10f-128">Microsoft は Redis 3.0 の最新の安定したビルドをインストールすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="5e10f-129">統計情報マネージャー バージョン 2.0 は Redis 3.2.100でテストされました。</span><span class="sxs-lookup"><span data-stu-id="5e10f-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="5e10f-130">下記のサイトから Redis をダウンロードしてください。[https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)</span><span class="sxs-lookup"><span data-stu-id="5e10f-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="5e10f-131">下記のサイトから符号なしのインストーラーをダウンロードできます。[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="5e10f-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="5e10f-132">必要な場合には、下記のサイトから符号付きのバイナリを、有名なパッケージ マネージャー経由で入手できます。[Nuget](https://www.nuget.org/packages/Redis-64/) と [Choclatey](https://chocolatey.org/packages/redis-64)</span><span class="sxs-lookup"><span data-stu-id="5e10f-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="5e10f-133">提供された msi を実行してプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="5e10f-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="5e10f-134">ファイアウォールのルールを追加するチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="5e10f-135">リスナー サービスは証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="5e10f-136">Microsoft は、信用のある認証機関によって署名された証明書を使用することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="5e10f-137">ラボでのテスト目的で自己署名証明書を使用するような場合には、「[自己署名証明書の作成](deploy.md#BKMK_SelfCert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="5e10f-p106">エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。</span><span class="sxs-lookup"><span data-stu-id="5e10f-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="5e10f-140">リスナー サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="5e10f-140">Install the Listener service</span></span>

<span data-ttu-id="5e10f-141">StatsManPerfAgentListener.msi を実行し、以下を指定することによって、ホスト コンピューターにリスナー サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="5e10f-142">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="5e10f-143">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="5e10f-144">**サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="5e10f-145">**Service Port:** これはリスナーがエージェントと通信するために使用する HTTPS ポート番号です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="5e10f-146">インストール時に、このポートはローカル ファイアウォールによって許可され、URL ACL が作成され、SSL 証明書がこのポートに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="5e10f-147">デフォルトは 8443 です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="5e10f-148">**証明書の拇印:** これはリスナーが HTTPS プロトコルを暗号化するために使用する証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="5e10f-149">ネットワーク サービスは、秘密キーへの読み取りアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="5e10f-150">[**選択...**] をクリックして拇印を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="5e10f-151">証明書マネージャーを使用するか、次の PowerShell コマンドを使用して証明書の拇印を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="5e10f-152">**インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="5e10f-153">**ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="5e10f-154">**AppData ディレクトリ:** これはログ フォルダーとその他のデータが保存されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="5e10f-155">デフォルトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-155">You may change it from the default.</span></span> <span data-ttu-id="5e10f-156">アンインストールしても、削除されません。</span><span class="sxs-lookup"><span data-stu-id="5e10f-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="5e10f-157">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-157">Click **Install**.</span></span>
    
<span data-ttu-id="5e10f-158">インストールを検証するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="5e10f-159">ブラウザーを開き、https://localhost:\<service-port\>/healthcheck/ に移動します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="5e10f-160">既定では、(別のポートを指定済みでない限り) サービス ポートは 8443 です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="5e10f-161">リスナーが適切にインストールされていることを確認するには、次について調べます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="5e10f-162">正常性チェックのページが表示される場合は、リスナーのインストールは正常に完了しています。</span><span class="sxs-lookup"><span data-stu-id="5e10f-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="5e10f-163">KnownServerCount が 1 以上の場合は、Redis への接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="5e10f-164">数秒間経過してから、および少なくとも 1 つのエージェントがインストールされてから、ValuesWritten カウンターの数値が増えていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="5e10f-165">Web サイトのインストール</span><span class="sxs-lookup"><span data-stu-id="5e10f-165">Install the Website</span></span>

<span data-ttu-id="5e10f-166">([Skype for Business Server、リアルタイム 統計情報マネージャー (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)に含まれる) StatsManWebSite.msi を実行し、ホスト コンピューターにウェブサイトをインストールし、以下の指定をします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="5e10f-167">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="5e10f-168">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="5e10f-169">**サービス ポート:** これはウェブサイトがリッスンするポート番号です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="5e10f-170">この番号は後で IIS マネージャーのバインドを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="5e10f-171">インストール時に、このポートはローカル ファイアウォールによって許可されます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="5e10f-172">**インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="5e10f-173">**ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="5e10f-174">**AppData ディレクトリ:** これはログ フォルダーとその他のデータが保存されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="5e10f-175">デフォルトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-175">You may change it from the default.</span></span> <span data-ttu-id="5e10f-176">アンインストールしても、削除されません。</span><span class="sxs-lookup"><span data-stu-id="5e10f-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="5e10f-177">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-177">Click **Install**.</span></span>
    
<span data-ttu-id="5e10f-178">ウェブサイトを表示するには、ブラウザーを開いてhttp://localhost、ウェブ ポート\>/ に移動します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="5e10f-179">状態の情報のみを表示するには、ブラウザーを開いてhttp://localhost:\<webport\>/healthcheck/に移動します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="5e10f-180">既定では、Web ポート番号は 8080 です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="5e10f-181">IIS マネージャーを使用して Web サイトのポートのバインドを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="5e10f-182">Web インストーラーは StatsManWebSiteUsers というローカル セキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="5e10f-183">アカウントをこのセキュリティ グループに追加して Web サイトへのアクセスを付与することができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="5e10f-184">エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="5e10f-184">Install the Agents</span></span>

<span data-ttu-id="5e10f-185">StatsManPerfAgent.msi を実行して以下を指定することによって、監視したい各 Skype for Business Server にエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="5e10f-186">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="5e10f-187">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="5e10f-188">**サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="5e10f-189">**サービス URI:** これはリスナーが存在する URI です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="5e10f-190">https://name:portのフォーマットを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e10f-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="5e10f-191">NETBIOS の名前または FQDN を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="5e10f-192">リスナー サービスの証明書の**Subject** または **Subject Alternative Names** としても指定されている名前を使用できますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="5e10f-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="5e10f-193">**サービス 拇印:** これはリスナーが使用している SSL 証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="5e10f-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="5e10f-194">エージェントはリスナーを認証するためにこの拇印を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="5e10f-195">(自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。)</span><span class="sxs-lookup"><span data-stu-id="5e10f-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="5e10f-196">**インストール ディレクトリ:** これはバイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="5e10f-197">**ブラウズ...** ボタンを使用することによって、デフォルトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="5e10f-198">**AppData ディレクトリ:** これはログ フォルダーと暗号化された password.txt ファイルが保存されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="5e10f-199">ディフォルトから変更することができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-199">You may thanks change it from the default.</span></span> <span data-ttu-id="5e10f-200">アンインストールしても、削除されません。</span><span class="sxs-lookup"><span data-stu-id="5e10f-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="5e10f-201">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-201">Click **Install**.</span></span>
    
<span data-ttu-id="5e10f-p121">エージェントを多数のコンピューターにインストールしている場合、その操作を無人モードで実行する方が望ましい場合が考えられます。例:</span><span class="sxs-lookup"><span data-stu-id="5e10f-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="5e10f-204">トポロジのインポート</span><span class="sxs-lookup"><span data-stu-id="5e10f-204">Import the topology</span></span>
<span data-ttu-id="5e10f-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="5e10f-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="5e10f-206">統計情報マネージャーがインストールされ起動した後で、統計情報マネージャーが、各サーバーのサイト、プール、ロールを認識できるようにするため、Skype for Business Server トポロジをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e10f-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="5e10f-207">Skype for Business Server トポロジをインポートするには、[Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) コマンドレットを使用して、組織で使用中の各プールについての情報を検索し、その情報を統計情報マネージャーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="5e10f-208">Skype for Business Server トポロジをインポートするには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="5e10f-209">Skype for Business Server PowerShell コマンドレットのあるホスト：</span><span class="sxs-lookup"><span data-stu-id="5e10f-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="5e10f-210">a.</span><span class="sxs-lookup"><span data-stu-id="5e10f-210">a.</span></span> <span data-ttu-id="5e10f-211">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="5e10f-212">b.</span><span class="sxs-lookup"><span data-stu-id="5e10f-212">b.</span></span> <span data-ttu-id="5e10f-213">"mypoolinfo.xml" ファイルを、リスナーを実行するサーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="5e10f-214">リスナーを実行するホスト：</span><span class="sxs-lookup"><span data-stu-id="5e10f-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="5e10f-215">a.</span><span class="sxs-lookup"><span data-stu-id="5e10f-215">a.</span></span> <span data-ttu-id="5e10f-216">PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="5e10f-217">b.</span><span class="sxs-lookup"><span data-stu-id="5e10f-217">b.</span></span> <span data-ttu-id="5e10f-218">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="5e10f-219">既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="5e10f-220">どのサーバーが追加および更新されているかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="5e10f-221">次のコマンドで、すべてのオプションを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="5e10f-222">現在のインポート済みのサーバー情報を表示するには、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="5e10f-223">Skype for Business Server トポロジにないサーバー (例えば Exchange Server) を監視する場合には、リスナーを実行するホスト上で単一サーバーのインポートができます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="5e10f-224">単一サーバーのインポートを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="5e10f-225">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="5e10f-226">既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e10f-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="5e10f-227">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="5e10f-228">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5e10f-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="5e10f-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="5e10f-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="5e10f-230">エージェントを開始できない場合は、以下のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="5e10f-231">統計情報 マネージャーにエージェントが登録されているか？</span><span class="sxs-lookup"><span data-stu-id="5e10f-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="5e10f-p129">	トポロジのインポートの手順に従っていることを確認します。「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="5e10f-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="5e10f-234">このトポロジ内のリストに記述されていないサーバーにエージェントがある場合 (たとえば、SQL AlwaysOn クラスタ内のノード)、「[トポロジのインポート](deploy.md#BKMK_ImportTopology)」にある手順に従ってエージェントを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e10f-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="5e10f-235">エージェントがリスナーと連絡することができるか</span><span class="sxs-lookup"><span data-stu-id="5e10f-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="5e10f-236">リスナー サービスが実行中であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="5e10f-237">実行中でない場合は、Redis が実行していることを確認して、リスナーの再起動を試行します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="5e10f-238">ポートがリスナー サービスに対して開いていて、エージェントのコンピューターがポートと通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="5e10f-239">統計情報 マネージャーがデータを収集していることを確認するには、以下のように CSV ファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="5e10f-240">次のコマンドで、カウンターのストレージ名を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="5e10f-241">次のコマンドで指定したカウンターの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="5e10f-242">アプリケーション イベント ログで確認できるすべてのイベントについての情報は、[Skype for Business Server の統計情報マネージャーの トラブルシューティング ](troubleshoot.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="5e10f-243">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="5e10f-243">Create a self-signed certificate</span></span>
<span data-ttu-id="5e10f-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="5e10f-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="5e10f-245">Microsoft は、必ず信頼済みの認証局によって署名された証明書を使用することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="5e10f-246">ただし、自己署名証明書をテストの目的で使用する場合は、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="5e10f-247">PowerShell コンソールから、管理者としてログ オンしている状態で、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="5e10f-248">`certlm.msc` と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="5e10f-249">これにより、ローカル コンピューターの証明書マネージャーが開きます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="5e10f-250">**個人** に移動して、 **証明書**を開きます。</span><span class="sxs-lookup"><span data-stu-id="5e10f-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="5e10f-251">**StatsManListener-\>を右クリックして、すべてのタスク-\>秘密キーの管理…** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="5e10f-252">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="5e10f-253">[**選択するオブジェクト名を入力してください**] ボックスに、「Network Service」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5e10f-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="5e10f-254">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="5e10f-p132">[**フル コントロール**] で、[**許可**] チェック ボックスをオフにします。(読み取りアクセス権のみが必要です。)</span><span class="sxs-lookup"><span data-stu-id="5e10f-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="5e10f-257">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e10f-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="5e10f-258">関連情報</span><span class="sxs-lookup"><span data-stu-id="5e10f-258">For more information</span></span>
<span data-ttu-id="5e10f-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="5e10f-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="5e10f-260">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e10f-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="5e10f-261">Skype for Business Server の統計情報マネージャーの計画</span><span class="sxs-lookup"><span data-stu-id="5e10f-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="5e10f-262">Skype for Business Server の統計情報マネージャーのアップグレード</span><span class="sxs-lookup"><span data-stu-id="5e10f-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="5e10f-263">[Skype for Business Server の統計情報マネージャーのトラブルシューティング](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="5e10f-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
