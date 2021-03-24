---
title: Skype for Business Server の統計情報マネージャーの展開
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '概要: Skype for Business Server の統計マネージャーを展開する方法については、このトピックを参照してください。'
ms.openlocfilehash: 406f4188347d32111bea4952815237b7f1015574
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105383"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="dc0b8-103">Skype for Business Server の統計情報マネージャーの展開</span><span class="sxs-lookup"><span data-stu-id="dc0b8-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="dc0b8-104">**概要:** Skype for Business Server の統計マネージャーを展開する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="dc0b8-105">Skype for Business Server の統計マネージャーは、Skype for Business Server の正常性とパフォーマンス データをリアルタイムで表示できる強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="dc0b8-106">数百のサーバーでパフォーマンス データを数秒ごとにポーリングし、統計マネージャー Web サイトで即座に結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="dc0b8-107">Statistics Manager のインストールを試みる前に、ソフトウェア、ネットワーク、およびハードウェアの要件に精通していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="dc0b8-108">詳細については [、「Plan for Statistics Manager for Skype for Business Server」を参照してください](plan.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc0b8-109">以前のバージョンの Statistics Manager からアップグレードする場合は [、「Upgrade Statistics Manager for Skype for Business Server」を参照してください](upgrade.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dc0b8-110">Statistics Manager Web サイトは、Internet Explorer 11+、Edge 20.10240+、および Chrome 46+ (現在の常緑樹バージョン) でテストされ、正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="dc0b8-111">統計マネージャーは、次のページからダウンロードできます [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) 。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="dc0b8-112">このトピックは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="dc0b8-113">統計マネージャーの展開</span><span class="sxs-lookup"><span data-stu-id="dc0b8-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="dc0b8-114">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dc0b8-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="dc0b8-115">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="dc0b8-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="dc0b8-116">統計マネージャーの展開</span><span class="sxs-lookup"><span data-stu-id="dc0b8-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="dc0b8-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0b8-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="dc0b8-118">Statistics Manager を展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="dc0b8-119">Redis インメモリ キャッシュ システムをインストールし、適切な証明書がインストールされていることを確認して、リスナー ホスト コンピューターを準備します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="dc0b8-120">ホスト コンピューターにリスナー サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="dc0b8-121">ホスト コンピューターに Web サイトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="dc0b8-122">監視する各 Skype for Business Server コンピューターにエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="dc0b8-123">監視しているサーバーのトポロジをインポートします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dc0b8-124">Redis、Listener サービス、および Web サイトは、すべて同じホスト コンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="dc0b8-125">ホスト コンピューターに Skype for Business Server がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="dc0b8-126">リスナー ホスト コンピューターを準備する</span><span class="sxs-lookup"><span data-stu-id="dc0b8-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="dc0b8-127">ホスト コンピューターを準備するには、Redis インメモリ キャッシュ システムをインストールし、有効な証明書がコンピューター上にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="dc0b8-128">Redis 3.0 の最新の安定したビルドをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="dc0b8-129">Statistics Manager バージョン 2.0 は Redis 3.2.100 でテストされました。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="dc0b8-130">次のサイトから Redis をダウンロードします [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) 。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="dc0b8-131">署名されていないインストーラーは、次の場所からダウンロードできます。 [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="dc0b8-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="dc0b8-132">必要に応じて、署名されたバイナリは、一般的なパッケージ マネージャー [(Nuget](https://www.nuget.org/packages/Redis-64/) と [Choclatey) を通じて利用できます](https://chocolatey.org/packages/redis-64)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="dc0b8-133">指定された msi を実行し、プロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="dc0b8-134">ファイアウォール ルールを追加する場合は、このチェック ボックスをオンにしない。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="dc0b8-135">リスナー サービスには証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="dc0b8-136">信頼できる証明機関によって署名された証明書を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="dc0b8-137">自己署名証明書を使用する場合は、たとえば、「自己署名証明書を作成する」を [参照してください](deploy.md#BKMK_SelfCert)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="dc0b8-138">エージェントは証明書の拇印検証を使用します (チェーン検証の代わりに)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="dc0b8-139">自己署名証明書を使用できるので、完全な証明書の検証は実行しません。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="dc0b8-140">リスナー サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="dc0b8-140">Install the Listener service</span></span>

<span data-ttu-id="dc0b8-141">ホスト コンピューターにリスナー サービスをインストールするには、次のStatsManPerfAgentListener.msiを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="dc0b8-142">使用許諾契約書を確認し、同意する場合は、[使用許諾契約書の条項に同意する] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="dc0b8-143">次のページで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="dc0b8-144">**サービス パスワード:** これは、リモート エージェントがリスナー サービスへの認証に使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="dc0b8-145">**サービス ポート:** これは、リスナーがエージェントとの通信に使用する HTTPS ポート番号です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="dc0b8-146">インストール時に、このポートはローカル ファイアウォール経由で許可され、URL ACL が作成され、SSL 証明書はこのポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="dc0b8-147">既定値は 8443 です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="dc0b8-148">**証明書の拇印:** これは、リスナーが HTTPS プロトコルの暗号化に使用する証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="dc0b8-149">ネットワーク サービスには、プライベート キーへの読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="dc0b8-150">**[Select....] ボタン** をクリックして拇印を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="dc0b8-151">証明書の拇印は、証明書マネージャーを使用するか、次の PowerShell コマンドを使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="dc0b8-152">**Install Dir:** これは、バイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="dc0b8-153">[参照...] ボタンを使用して、既定 **から変更** できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="dc0b8-154">**AppData Dir:** これは、Logs フォルダーと他のデータが格納されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="dc0b8-155">既定から変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-155">You may change it from the default.</span></span> <span data-ttu-id="dc0b8-156">アンインストール時に削除されません。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="dc0b8-157">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-157">Click **Install**.</span></span>
    
<span data-ttu-id="dc0b8-158">インストールを検証するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="dc0b8-159">ブラウザーを開き https://localhost: \<service-port\> 、[/healthcheck/ ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="dc0b8-160">既定では、サービス ポートは 8443 です (別のポートを指定しない限り)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="dc0b8-161">リスナーが正しくインストールされていることを確認するには、次の情報を探します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="dc0b8-162">正常性チェック ページが表示された場合は、リスナーのインストールが成功しました。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="dc0b8-163">KnownServerCount が 1 以上の場合、Redis への接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="dc0b8-164">数分待った後、少なくとも 1 つのエージェントがインストールされた後で、Valueswritten カウンターがインクリメントされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="dc0b8-165">Web サイトのインストール</span><span class="sxs-lookup"><span data-stu-id="dc0b8-165">Install the Website</span></span>

<span data-ttu-id="dc0b8-166">StatsManWebSite.msi [(Skype for Business Server、Real-Time Statistics Manager (64 ビット)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)に含まれる) を実行し、以下を指定して、ホスト コンピューターに Web サイトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="dc0b8-167">使用許諾契約書を確認し、同意する場合は、[使用許諾契約書の条項に同意する] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="dc0b8-168">次のページで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="dc0b8-169">**サービス ポート:** これは、Web サイトがリッスンするポート番号です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="dc0b8-170">後で IIS マネージャー バインドを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="dc0b8-171">インストール時に、このポートはローカル ファイアウォール経由で許可されます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="dc0b8-172">**Install Dir:** これは、バイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="dc0b8-173">[参照...] ボタンを使用して、既定 **から変更** できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="dc0b8-174">**AppData Dir:** これは、Logs フォルダーと他のデータが格納されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="dc0b8-175">既定から変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-175">You may change it from the default.</span></span> <span data-ttu-id="dc0b8-176">アンインストール時に削除されません。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="dc0b8-177">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-177">Click **Install**.</span></span>
    
<span data-ttu-id="dc0b8-178">Web サイトを表示するには、ブラウザーを開き http://localhost 、[,webport \> /] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="dc0b8-179">正常性情報のみを表示するには、ブラウザーを開き http://localhost: \<webport\> 、[/healthcheck/] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="dc0b8-180">既定では、Web ポート番号は 8080 です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="dc0b8-181">IIS マネージャーを使用して、Web サイトのポート バインドを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="dc0b8-182">Web インストーラーは、StatsManWebSiteUsers というローカル セキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="dc0b8-183">このセキュリティ グループにアカウントを追加して、Web サイトへのアクセスを許可できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="dc0b8-184">エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="dc0b8-184">Install the Agents</span></span>

<span data-ttu-id="dc0b8-185">監視する各 Skype for Business Server にエージェントをインストールするには、次のStatsManPerfAgent.msiを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="dc0b8-186">使用許諾契約書を確認し、同意する場合は、[使用許諾契約書の条項に同意する] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="dc0b8-187">次のページで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="dc0b8-188">**サービス パスワード:** これは、リモート エージェントがリスナー サービスへの認証に使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="dc0b8-189">**サービス URI:** これは、リスナーが存在する URI です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="dc0b8-190">この形式を使用 https://name:port する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="dc0b8-191">NETBIOS 名または FQDN を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="dc0b8-192">リスナー サービスで証明書のサブジェクトまたはサブジェクトの代替名として指定されている名前を使用できますが、これは要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="dc0b8-193">**サービス拇印:** これは、リスナーが使用している SSL 証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="dc0b8-194">エージェントは、この拇印を使用してリスナーに対する認証を行います。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="dc0b8-195">(自己署名証明書を使用できるので、完全な証明書の検証は実行しません)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="dc0b8-196">**Install Dir:** これは、バイナリがインストールされるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="dc0b8-197">[参照...] ボタンを使用して、既定 **から変更** できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="dc0b8-198">**AppData Dir:** これは、Logs フォルダーと暗号化されたファイルが格納password.txtディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="dc0b8-199">既定の設定から変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-199">You may thanks change it from the default.</span></span> <span data-ttu-id="dc0b8-200">アンインストール時に削除されません。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="dc0b8-201">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-201">Click **Install**.</span></span>
    
<span data-ttu-id="dc0b8-202">多数のコンピューターにエージェントをインストールする場合は、無人モードでこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="dc0b8-203">例:</span><span class="sxs-lookup"><span data-stu-id="dc0b8-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="dc0b8-204">トポロジのインポート</span><span class="sxs-lookup"><span data-stu-id="dc0b8-204">Import the topology</span></span>
<span data-ttu-id="dc0b8-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0b8-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="dc0b8-206">Statistics Manager をインストールして実行した後、統計マネージャーが各サーバーのサイト、プール、および役割を知る Skype for Business Server トポロジをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="dc0b8-207">Skype for Business Server トポロジをインポートするには [、Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) コマンドレットを使用して、組織内で使用されている各プールに関する情報を取得し、この情報を統計マネージャーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="dc0b8-208">Skype for Business Server トポロジをインポートするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="dc0b8-209">Skype for Business Server PowerShell コマンドレットを持つホストでは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="dc0b8-210">a.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-210">a.</span></span> <span data-ttu-id="dc0b8-211">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="dc0b8-212">b.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-212">b.</span></span> <span data-ttu-id="dc0b8-213">"mypoolinfo.xml" ファイルをリスナーを実行するサーバーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="dc0b8-214">リスナーを実行するホストで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="dc0b8-215">a.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-215">a.</span></span> <span data-ttu-id="dc0b8-216">PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="dc0b8-217">b.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-217">b.</span></span> <span data-ttu-id="dc0b8-218">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="dc0b8-219">既定値は次の値です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="dc0b8-220">追加および更新されるサーバーを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="dc0b8-221">次のコマンドを使用すると、すべてのオプションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="dc0b8-222">現在インポートされているサーバー情報を表示するには、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="dc0b8-223">たとえば、Skype for Business Server トポロジ (Exchange Server) に含されていないサーバーを監視する場合は、リスナーを実行するホストで単一サーバーのインポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="dc0b8-224">単一サーバーのインポートを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="dc0b8-225">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="dc0b8-226">既定値は次の値です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="dc0b8-227">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="dc0b8-228">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dc0b8-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="dc0b8-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0b8-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="dc0b8-230">エージェントの起動に失敗した場合は、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="dc0b8-231">エージェントは統計マネージャーに登録されていますか?</span><span class="sxs-lookup"><span data-stu-id="dc0b8-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="dc0b8-232">トポロジをインポートする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="dc0b8-233">「 [トポロジのインポート」を参照してください](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="dc0b8-234">エージェントがトポロジにリストされていないサーバー (たとえば、SQL AlwaysOn クラスター内のノード) にある場合は、「トポロジのインポート」の手順に従って手動でエージェントを追加する必要 [があります](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="dc0b8-235">エージェントはリスナーに連絡できますか?</span><span class="sxs-lookup"><span data-stu-id="dc0b8-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="dc0b8-236">リスナー サービスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="dc0b8-237">実行されていない場合は、Redis が実行されている状態を確認し、リスナーの再起動を試みる。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="dc0b8-238">ポートがリスナー サービスに対して開いていると、エージェント コンピューターがポートと通信可能なポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="dc0b8-239">統計マネージャーがデータを収集するために、CSV ファイルを次のように確認できます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="dc0b8-240">次のコマンドは、カウンター ストレージ名を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="dc0b8-241">次のコマンドは、指定したカウンターの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="dc0b8-242">アプリケーション イベント ログに表示される可能性があるすべてのイベントの詳細については [、「Troubleshoot Statistics Manager for Skype for Business Server」を参照してください](troubleshoot.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="dc0b8-243">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="dc0b8-243">Create a self-signed certificate</span></span>
<span data-ttu-id="dc0b8-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0b8-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="dc0b8-245">Microsoft では、信頼できる証明機関によって署名された証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="dc0b8-246">ただし、テスト目的で自己署名証明書を使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="dc0b8-247">管理者としてログオンしている間に PowerShell コンソールから、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="dc0b8-248">Type  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="dc0b8-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="dc0b8-249">これにより、ローカル コンピューターの証明書マネージャーが開きます。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="dc0b8-250">[個人用] **に移動** し、[証明書] **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="dc0b8-251">**StatsManListener- All \> Tasks- \> Manage Private Keys... を右クリックします。**</span><span class="sxs-lookup"><span data-stu-id="dc0b8-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="dc0b8-252">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="dc0b8-253">[選択 **するオブジェクト名を入力する** ] ボックスに、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="dc0b8-254">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="dc0b8-255">[ **フル コントロール] で**、[許可] チェック **ボックスを** オフにします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="dc0b8-256">(読み取りアクセスのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="dc0b8-257">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="dc0b8-258">関連情報</span><span class="sxs-lookup"><span data-stu-id="dc0b8-258">For more information</span></span>
<span data-ttu-id="dc0b8-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="dc0b8-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="dc0b8-260">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0b8-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="dc0b8-261">Skype for Business Server の Statistics Manager の計画</span><span class="sxs-lookup"><span data-stu-id="dc0b8-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="dc0b8-262">Skype for Business Server の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="dc0b8-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="dc0b8-263">Skype for Business Server ß の[統計マネージャーの](troubleshoot.md)トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dc0b8-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>