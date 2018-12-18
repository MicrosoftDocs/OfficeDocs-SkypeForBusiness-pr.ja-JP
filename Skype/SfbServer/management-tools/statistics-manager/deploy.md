---
title: ビジネス サーバーの Skype の統計マネージャーを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '概要: は、Skype のビジネス サーバーの統計情報マネージャーを展開する方法の詳細については、このトピックを読みます。'
ms.openlocfilehash: ef2dd51306dc2806161fc0c0d4b11087a2f466ea
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297700"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="99b3d-103">ビジネス サーバーの Skype の統計マネージャーを展開します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="99b3d-104">**の概要:** Skype のビジネス サーバーの統計情報マネージャーを展開する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="99b3d-105">Skype ビジネス サーバーの統計情報マネージャーとは、Skype をビジネスのサーバーの稼働状態とパフォーマンスのデータをリアルタイムに表示できるようにする強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="99b3d-106">数秒ごとに数百のサーバー間でのパフォーマンス データをポーリングし、統計マネージャーの web サイトですぐに結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="99b3d-107">統計マネージャーをインストールしようとすると、前に、ソフトウェア、ネットワーク、およびハードウェア要件を熟知していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="99b3d-108">詳細については、 [Skype ビジネス サーバーの統計情報マネージャーの計画](plan.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="99b3d-109">統計マネージャーの以前のバージョンからアップグレードする場合は、 [Skype のビジネス サーバーの統計マネージャーのアップグレード](upgrade.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="99b3d-110">Statistics Manager の Web サイトはテスト済みで Internet Explorer 11 以降、Edge 20.10240 以降、Chrome 46 以降 (現在広く使用されているバージョン) で正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="99b3d-111">ダウンロード可能な統計マネージャーを見つけることができます[https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)。</span><span class="sxs-lookup"><span data-stu-id="99b3d-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="99b3d-112">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="99b3d-113">Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="99b3d-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="99b3d-114">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="99b3d-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="99b3d-115">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="99b3d-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="99b3d-116">Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="99b3d-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="99b3d-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="99b3d-117"></span></span>

<span data-ttu-id="99b3d-118">統計マネージャーを展開するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="99b3d-119">リスナーのホスト コンピューターを準備します。その際は、Redis メモリ内キャッシュ システムをインストールすることと、適切な証明書をインストールしたことを確認することが必要です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="99b3d-120">リスナー サービスをホスト コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="99b3d-121">Web サイトをホスト コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="99b3d-122">各 Skype をビジネスのサーバー コンピューターを監視するためにエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="99b3d-123">監視しているサーバーのトポロジをインポートします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99b3d-124">Redis、リスナー サービス、Web サイトは同一のホスト コンピューターにインストールされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="99b3d-125">ホスト ・ マシンが Skype のビジネス サーバーがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="99b3d-126">リスナーのホスト コンピューターの準備</span><span class="sxs-lookup"><span data-stu-id="99b3d-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="99b3d-127">ホスト コンピューターを準備するには、Redis メモリ内キャッシュ システムをインストールして、有効な証明書がコンピューター上にあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="99b3d-128">Microsoft は Redis 3.0 の最新の安定したビルドをインストールすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="99b3d-129">統計マネージャーのバージョン 2.0 は、Redis 3.2.100 でテストされました。</span><span class="sxs-lookup"><span data-stu-id="99b3d-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="99b3d-130">Redis の次のサイトからダウンロード: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)。</span><span class="sxs-lookup"><span data-stu-id="99b3d-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="99b3d-131">符号なしのインストーラーをダウンロードできます。[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="99b3d-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="99b3d-132">必要に応じて、一般的なパッケージ マネージャーの [Nuget](https://www.nuget.org/packages/Redis-64/) および [Choclatey](https://chocolatey.org/packages/redis-64) を通して署名済みのバイナリを利用できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="99b3d-133">提供された msi を実行してプロンプトに従います。</span><span class="sxs-lookup"><span data-stu-id="99b3d-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="99b3d-134">ファイアウォールのルールを追加するチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="99b3d-135">リスナー サービスは証明書を必要とします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="99b3d-136">信頼された証明機関によって署名された証明書があることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="99b3d-137">ラボでのテスト目的で自己署名証明書を使用するような場合には、「[自己署名証明書の作成](deploy.md#BKMK_SelfCert)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="99b3d-p106">エージェントが (チェーンの検証ではなく) 証明書の拇印の検証を使用することに注意してください。自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。</span><span class="sxs-lookup"><span data-stu-id="99b3d-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="99b3d-140">リスナー サービスのインストール</span><span class="sxs-lookup"><span data-stu-id="99b3d-140">Install the Listener service</span></span>

<span data-ttu-id="99b3d-141">StatsManPerfAgentListener.msi を実行し、次を指定するホスト ・ マシン上のリスナー サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="99b3d-142">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="99b3d-143">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="99b3d-144">**サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="99b3d-145">**サービス ポート:** エージェントと通信するためにリスナーを使用する HTTPS ポート番号です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="99b3d-146">インストール時に、このポート通過を許可するローカルのファイアウォールでは、URL の ACL が作成され、SSL 証明書は、このポートにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="99b3d-147">デフォルトは、8443 です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="99b3d-148">**証明書の拇印:** これは、HTTPS プロトコルを暗号化するために、リスナーで使用する証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="99b3d-149">ネットワーク サービスには、秘密キーへの読み取りアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="99b3d-150">[**選択...**] をクリックして拇印を選びます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="99b3d-151">証明書マネージャーを使用するか、次の PowerShell コマンドを使用して証明書の拇印を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="99b3d-152">**インストール ディレクトリ:** これは、バイナリをインストールするディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="99b3d-153">既定値から、[**参照...** ] ボタンを使用して変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="99b3d-154">**AppData ディレクトリ:** これは、ログ フォルダーとその他のデータを格納するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="99b3d-155">既定値から変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-155">You may change it from the default.</span></span> <span data-ttu-id="99b3d-156">それは削除されませんをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="99b3d-157">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-157">Click **Install**.</span></span>
    
<span data-ttu-id="99b3d-158">インストールを検証するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="99b3d-159">ブラウザーを開き、下に移動https://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="99b3d-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="99b3d-160">既定では、(別のポートを指定済みでない限り) サービス ポートは 8443 です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="99b3d-161">リスナーが適切にインストールされていることを確認するには、次について調べます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="99b3d-162">正常性チェックのページが表示される場合は、リスナーのインストールは正常に完了しています。</span><span class="sxs-lookup"><span data-stu-id="99b3d-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="99b3d-163">KnownServersCount が 1 以上である場合は、Redis への接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="99b3d-164">数秒間経過してから、および少なくとも 1 つのエージェントがインストールされてから、ValuesWritten カウンターの数値が増えていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="99b3d-165">Web サイトのインストール</span><span class="sxs-lookup"><span data-stu-id="99b3d-165">Install the Website</span></span>

<span data-ttu-id="99b3d-166">( [Skype ビジネス サーバーに、リアルタイムの統計情報マネージャー (64 ビット)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)に含まれている) StatsManWebSite.msi を実行して、ホスト ・ マシン上の web サイトをインストールし、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="99b3d-167">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="99b3d-168">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="99b3d-169">**サービス ポート:** Web サイト上でリッスンするポート番号です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="99b3d-170">バインドの IIS マネージャーを使用して後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="99b3d-171">インストール時に、ローカル ファイアウォールによってこのポートが許可されます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="99b3d-172">**インストール ディレクトリ:** これは、バイナリのインストール先となるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="99b3d-173">既定値から、[**参照...** ] ボタンを使用して変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="99b3d-174">**AppData ディレクトリ:** これは、ログ フォルダーとその他のデータを格納するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="99b3d-175">既定値から変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-175">You may change it from the default.</span></span> <span data-ttu-id="99b3d-176">それは削除されませんをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="99b3d-177">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-177">Click **Install**.</span></span>
    
<span data-ttu-id="99b3d-178">Web サイトを表示するには、ブラウザーを開きに移動: http://localhost、webport\>とします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="99b3d-179">状態情報のみを表示、ブラウザーを開きに移動する: http://localhost:\<webport\>/healthcheck/。</span><span class="sxs-lookup"><span data-stu-id="99b3d-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="99b3d-180">既定では、Web ポート番号は 8080 です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="99b3d-181">IIS マネージャーを使用して Web サイトのポートのバインドを変更できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="99b3d-182">Web インストーラーは StatsManWebSiteUsers というローカル セキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="99b3d-183">アカウントをこのセキュリティ グループに追加して Web サイトへのアクセスを付与することができます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="99b3d-184">エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="99b3d-184">Install the Agents</span></span>

<span data-ttu-id="99b3d-185">各 Skype で、StatsManPerfAgent.msi を実行し、次を指定することによって、監視するビジネスのサーバーにエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="99b3d-186">使用許諾契約書の内容を確認して、同意する場合は [**使用許諾契約書に同意します**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="99b3d-187">次のページで、以下の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="99b3d-188">**サービス パスワード:** これはリモート エージェントがリスナー サービスを認証するために使用するパスワードです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="99b3d-189">**サービスの URI:** これは、リスナーが存在する URI です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="99b3d-190">それを使用する必要があります、https://name:portの形式です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="99b3d-191">NETBIOS 名または FQDN を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="99b3d-192">**件名**またはリスナー サービスに証明書の**サブジェクト代替名**としても指定されている名前を使用することができますが、これは要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="99b3d-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="99b3d-193">**サービスの拇印:** これは、リスナーを使用して SSL 証明書の拇印です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="99b3d-194">(自己署名証明書を使用することが可能なため、証明書の完全な検証は行いません。</span><span class="sxs-lookup"><span data-stu-id="99b3d-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="99b3d-195">)</span><span class="sxs-lookup"><span data-stu-id="99b3d-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="99b3d-196">**インストール ディレクトリ:** これは、バイナリをインストールするディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="99b3d-197">既定値から、[**参照...** ] ボタンを使用して変更する場合があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="99b3d-198">**AppData ディレクトリ:** これは、ログ フォルダーと暗号化された password.txt ファイルを保存するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="99b3d-199">ことがあります、ありがとうございます、デフォルトから変更します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-199">You may thanks change it from the default.</span></span> <span data-ttu-id="99b3d-200">それは削除されませんをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="99b3d-201">[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-201">Click **Install**.</span></span>
    
<span data-ttu-id="99b3d-p121">エージェントを多数のコンピューターにインストールしている場合、その操作を無人モードで実行する方が望ましい場合が考えられます。例:  </span><span class="sxs-lookup"><span data-stu-id="99b3d-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="99b3d-204">トポロジのインポート</span><span class="sxs-lookup"><span data-stu-id="99b3d-204">Import the topology</span></span>
<span data-ttu-id="99b3d-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="99b3d-205"></span></span>

<span data-ttu-id="99b3d-206">統計マネージャーのインストールし、実行している場合、インポートする必要がビジネスのサーバー トポロジの Skype ある、その統計マネージャーを知っているサイト、プール、および各サーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="99b3d-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="99b3d-207">ビジネス サーバー トポロジの場合、Skype をインポートするには、 [Get CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps)コマンドレットを使用して、組織で使用されている各プールに関する情報を取得し、統計マネージャーにこの情報をインポートします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="99b3d-208">ビジネス サーバー トポロジの Skype をインポートするのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="99b3d-209">ビジネス サーバーの PowerShell コマンドレットの Skype のあるホスト。</span><span class="sxs-lookup"><span data-stu-id="99b3d-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="99b3d-210">a.</span><span class="sxs-lookup"><span data-stu-id="99b3d-210">a.</span></span> <span data-ttu-id="99b3d-211">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="99b3d-212">b.</span><span class="sxs-lookup"><span data-stu-id="99b3d-212">b.</span></span> <span data-ttu-id="99b3d-213">リスナーを実行しているサーバーに"mypoolinfo.xml"ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="99b3d-214">リスナーを実行するホストで、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="99b3d-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="99b3d-215">a.</span><span class="sxs-lookup"><span data-stu-id="99b3d-215">a.</span></span> <span data-ttu-id="99b3d-216">PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="99b3d-217">b.</span><span class="sxs-lookup"><span data-stu-id="99b3d-217">b.</span></span> <span data-ttu-id="99b3d-218">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="99b3d-219">既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="99b3d-220">どのサーバーが追加および更新されているかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="99b3d-221">次のコマンドで、すべてのオプションを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="99b3d-222">読み込まれた現在のサーバーの情報を表示するには、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="99b3d-223">--ビジネス サーバー トポロジを Exchange Server に、Skype ではないサーバーを監視したい場合たとえば--リスナーを実行しているホスト上の 1 台のサーバーのインポートを実行できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="99b3d-224">単一サーバーのインポートを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="99b3d-225">リスナーがインストールされているディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="99b3d-226">既定値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99b3d-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="99b3d-227">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="99b3d-228">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="99b3d-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="99b3d-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="99b3d-229"></span></span>

<span data-ttu-id="99b3d-230">エージェントを開始できない場合は、次について確認します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="99b3d-231">エージェントが統計情報マネージャーでを登録されているでしょうか。</span><span class="sxs-lookup"><span data-stu-id="99b3d-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="99b3d-p129">	トポロジのインポートの手順に従っていることを確認します。「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="99b3d-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="99b3d-234">このトポロジ内のリストに記述されていないサーバーにエージェントがある場合 (たとえば、SQL AlwaysOn クラスタ内のノード)、「[トポロジのインポート](deploy.md#BKMK_ImportTopology)」にある手順に従ってエージェントを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99b3d-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="99b3d-235">エージェントがリスナーと連絡することができるか</span><span class="sxs-lookup"><span data-stu-id="99b3d-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="99b3d-236">リスナー サービスが実行中であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="99b3d-237">実行中でない場合は、Redis が実行していることを確認して、リスナーの再起動を試行します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="99b3d-238">リスナー サービスには、ポートとポートと、エージェント コンピューターが通信できることを確認ください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="99b3d-239">統計マネージャーがデータを収集していることを確認するには、次のように CSV ファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="99b3d-240">次のコマンドで、カウンターのストレージ名を取得します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="99b3d-241">次のコマンドで指定したカウンターの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="99b3d-242">アプリケーション イベント ログに表示されるすべてのイベントに関する情報は、 [Skype のビジネス サーバーの統計マネージャーのトラブルシューティング](troubleshoot.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="99b3d-243">自己署名証明書の作成</span><span class="sxs-lookup"><span data-stu-id="99b3d-243">Create a self-signed certificate</span></span>
<span data-ttu-id="99b3d-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="99b3d-244"></span></span>

<span data-ttu-id="99b3d-245">Microsoft は、必ず信頼済みの認証局によって署名された証明書を使用することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="99b3d-246">ただし、自己署名証明書をテストの目的で使用する場合は、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="99b3d-247">PowerShell コンソールから、管理者としてログ オンしている状態で、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="99b3d-248">型`certlm.msc`。</span><span class="sxs-lookup"><span data-stu-id="99b3d-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="99b3d-249">これにより、ローカル コンピューターの証明書マネージャーが開きます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="99b3d-250">**個人**に移動して、**証明書**を開きます。</span><span class="sxs-lookup"><span data-stu-id="99b3d-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="99b3d-251">右クリックして**StatsManListener -\>すべてのタスク -\>秘密キーの管理...**</span><span class="sxs-lookup"><span data-stu-id="99b3d-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="99b3d-252">[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="99b3d-253">[**選択するオブジェクト名を入力してください**] ボックスに、「Network Service」と入力します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="99b3d-254">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="99b3d-p132">[**フル コントロール**] で、[**許可**] チェック ボックスをオフにします。(読み取りアクセス権のみが必要です。)</span><span class="sxs-lookup"><span data-stu-id="99b3d-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="99b3d-257">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="99b3d-258">関連情報</span><span class="sxs-lookup"><span data-stu-id="99b3d-258">For more information</span></span>
<span data-ttu-id="99b3d-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="99b3d-259"></span></span>

<span data-ttu-id="99b3d-260">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b3d-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="99b3d-261">Skype 統計マネージャーのビジネス サーバー計画します。</span><span class="sxs-lookup"><span data-stu-id="99b3d-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="99b3d-262">ビジネス サーバーの Skype の統計マネージャーをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="99b3d-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="99b3d-263">ß の[Skype ビジネス サーバーの統計マネージャーのトラブルシューティング](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="99b3d-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>