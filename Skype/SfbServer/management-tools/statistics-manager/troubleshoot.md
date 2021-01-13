---
title: Skype for Business Server の統計情報マネージャーのトラブルシューティング
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '概要: このトピックでは、Skype for Business Server の Statistics Manager の展開のトラブルシューティングを行います。'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821777"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="f22c0-103">Skype for Business Server の統計情報マネージャーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f22c0-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="f22c0-104">**概要:** Skype for Business Server の Statistics Manager の展開のトラブルシューティングを行う場合は、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22c0-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="f22c0-105">このトピックでは、アプリケーション イベント ログに表示される可能性があるイベントを説明して Statistics Manager の展開をトラブルシューティングする方法と、イベントを修正するために実行する可能性がある適切なアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="f22c0-106">このトピックは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="f22c0-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="f22c0-107">エージェント イベント</span><span class="sxs-lookup"><span data-stu-id="f22c0-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="f22c0-108">リスナー イベント</span><span class="sxs-lookup"><span data-stu-id="f22c0-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="f22c0-109">Web サイトの問題</span><span class="sxs-lookup"><span data-stu-id="f22c0-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="f22c0-110">エージェント イベント</span><span class="sxs-lookup"><span data-stu-id="f22c0-110">Agent events</span></span>
<span data-ttu-id="f22c0-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-111"><a name="BKMK_Agent"> </a></span></span>

- <span data-ttu-id="f22c0-112">**1000** - プロセッサ リミターをセットアップできません (ジョブ オブジェクト) — 不明な理由</span><span class="sxs-lookup"><span data-stu-id="f22c0-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="f22c0-113">**1001** - プロセスに対するプロセス制限は許可されません (おそらく既にジョブ オブジェクト内に存在します)。</span><span class="sxs-lookup"><span data-stu-id="f22c0-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="f22c0-114">エージェントは Windows ジョブ オブジェクト内で実行され、メモリ使用量が自動的に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="f22c0-115">エージェントが起動しない場合、これらのイベント エントリがイベント ログに記録されている場合、ジョブ オブジェクトをサーバー上でインスタンス化できません。</span><span class="sxs-lookup"><span data-stu-id="f22c0-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="f22c0-116">これを回避するには、構成ファイルの値を変更することで、メモリ上限を削除できます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="f22c0-117">"MaxProcessMemoryMB" を検索し、次に示すように値を "0" に変更します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="f22c0-118">この変更を行った場合、エージェントは通常 100 MB のメモリを消費しますが、既定のように強制的に \< 300 MB に制限されません。</span><span class="sxs-lookup"><span data-stu-id="f22c0-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="f22c0-119">この変更を行った場合は、メモリ使用量を監視して、エージェントがホスト マシンで大量のメモリを消費することを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f22c0-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="f22c0-120">**2000** - クライアントの初期化エラー</span><span class="sxs-lookup"><span data-stu-id="f22c0-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="f22c0-121">**2001**- どの送信元 IP 上のサービスにも接続可能</span><span class="sxs-lookup"><span data-stu-id="f22c0-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="f22c0-122">エージェントがリスナー コンピューターに接続できない場合は、次の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="f22c0-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
    1. <span data-ttu-id="f22c0-123">リスナー サービスがリスナー コンピューターで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f22c0-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="f22c0-124">実行されていない場合は、Redis がサーバーで実行されているのを確認し、リスナー サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
        
        <span data-ttu-id="f22c0-125">リスナー コンピューターの Statistics Manager イベント ログを調して、Statistics Manager Listener サービス自体に問題が発生しなかからなか確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
        
    2. <span data-ttu-id="f22c0-126">telnet などの接続ツールを使用して、エージェント コンピューターから適切なポートのリスナーへの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
        
        <span data-ttu-id="f22c0-127">接続されていない場合は、リスナー コンピューターが接続されているネットワークの種類 (プライベート/パブリック/ドメイン) に対して、受信ファイアウォール規則がリスナー コンピューターで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f22c0-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="f22c0-128">リスナー コンピューターがドメインに参加していない場合、ネットワークがパブリックとして一覧表示される可能性があります。その場合、Statistics Manager と一緒にインストールされたファイアウォールルールは既定では適用されません。</span><span class="sxs-lookup"><span data-stu-id="f22c0-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="f22c0-129">**4000** - リスナーからサーバー情報をダウンロードできません (不明な理由)</span><span class="sxs-lookup"><span data-stu-id="f22c0-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="f22c0-130">**4001** - リスナー トポロジにサーバーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="f22c0-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="f22c0-131">このエラーは、サーバーがリスナーに正常に接続しているが、サーバーがリスナーのキャッシュ内のトポロジに追加されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="f22c0-132">解決策のオプション:</span><span class="sxs-lookup"><span data-stu-id="f22c0-132">Resolution options:</span></span>
    
  - <span data-ttu-id="f22c0-133">トポロジをインポートする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f22c0-133">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="f22c0-134">「 [トポロジのインポート」を参照してください](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="f22c0-134">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="f22c0-135">エージェントがトポロジにリストされていないサーバー上にある場合 (たとえば、SQL AlwaysOn クラスター内のノード)、トポロジのインポートの手順に従って手動でエージェントを追加する必要[があります。](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="f22c0-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="f22c0-136">**4002** - リスナーのパスワードが無効です</span><span class="sxs-lookup"><span data-stu-id="f22c0-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="f22c0-137">エージェントが使用を試みる暗号化されたパスワードが、リスナー自体のサービス パスワードと一致しません。</span><span class="sxs-lookup"><span data-stu-id="f22c0-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="f22c0-138">エージェントをアンインストールし、正しいサービス パスワードを使用して再インストールします。</span><span class="sxs-lookup"><span data-stu-id="f22c0-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="f22c0-139">**4003** - 証明書の拇印が一致しません</span><span class="sxs-lookup"><span data-stu-id="f22c0-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="f22c0-140">インストール時にエージェントに与えられた証明書の拇印が、リスナーが現在使用している証明書の拇印と一致しならないので、接続は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="f22c0-141">エージェントをアンインストールし、正しい証明書の拇印を使用して再インストールします。</span><span class="sxs-lookup"><span data-stu-id="f22c0-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="f22c0-142">**4004** - 無効な応答または HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="f22c0-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="f22c0-143">リスナーが予期した状態で応答していない。</span><span class="sxs-lookup"><span data-stu-id="f22c0-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="f22c0-144">接続がプロキシされている場合は、プロキシ構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="f22c0-145">リスナー コンピューターの StatsMan ログで、構成に関する問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="f22c0-146">**4005** - XML を逆シリアル化できない</span><span class="sxs-lookup"><span data-stu-id="f22c0-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="f22c0-147">リスナー サーバー上のサーバー情報が破損しているか、エージェント コンピューターとリスナー コンピューターの間にバージョンの不一致がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f22c0-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="f22c0-148">バージョンが一致し、リスナーのイベント ログに問題が記録されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="f22c0-149">リスナー イベント</span><span class="sxs-lookup"><span data-stu-id="f22c0-149">Listener events</span></span>
<span data-ttu-id="f22c0-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-150"><a name="BKMK_Listener"> </a></span></span>

- <span data-ttu-id="f22c0-151">**10000** - スタートアップ エラー不明な理由 (これらは回復不能であり、サービスは結果として停止/クラッシュします)</span><span class="sxs-lookup"><span data-stu-id="f22c0-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="f22c0-152">**10001** - 構成の問題</span><span class="sxs-lookup"><span data-stu-id="f22c0-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="f22c0-153">通常、このエラーは、[listener_install_location]\PerfAgentListener.exe.config ファイルが手で変更され、アプリケーションが読み取りできない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="f22c0-154">**10002** - HTTP リスナー初期化エラー</span><span class="sxs-lookup"><span data-stu-id="f22c0-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="f22c0-155">このイベントは、通常、インストール中に URL ACL が正しく設定されていないか、SSL 証明書が無効な場合にログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="f22c0-156">構成内の証明書が有効な証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="f22c0-157">インストールされている場合は、「統計マネージャーを展開する」の手順に従ってリスナー [を再インストールします](deploy.md#BKMK_Deploy)。</span><span class="sxs-lookup"><span data-stu-id="f22c0-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="f22c0-158">**10003** - Redis エラー</span><span class="sxs-lookup"><span data-stu-id="f22c0-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="f22c0-159">**10004** - キャッシュ インフラストラクチャの障害</span><span class="sxs-lookup"><span data-stu-id="f22c0-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="f22c0-160">**10007** - 設定 (redis に格納)</span><span class="sxs-lookup"><span data-stu-id="f22c0-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="f22c0-161">リスナーは Redis に接続できないか、キャッシュから整形データを取得する必要が生じ、開始できない。</span><span class="sxs-lookup"><span data-stu-id="f22c0-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="f22c0-162">Redis サービスがサーバーで開始され、適切に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="f22c0-163">**10005** — サーバー情報の取得/解析</span><span class="sxs-lookup"><span data-stu-id="f22c0-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="f22c0-164">Redis キャッシュのトポロジ情報が無効です。</span><span class="sxs-lookup"><span data-stu-id="f22c0-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="f22c0-165">まず、Redis とリスナーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="f22c0-166">エラーが解決しない場合は、「 [トポロジをインポートしてトポロジ](deploy.md#BKMK_ImportTopology) データを再作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22c0-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="f22c0-167">**10100** — Redis PING の停止</span><span class="sxs-lookup"><span data-stu-id="f22c0-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="f22c0-168">**10101** - Redis PING の停止が続く (60 秒ごとに)</span><span class="sxs-lookup"><span data-stu-id="f22c0-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="f22c0-169">**30100** — Redis PING の停止が復元されました</span><span class="sxs-lookup"><span data-stu-id="f22c0-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="f22c0-170">リスナーが Redis に接続できない場合、これらはログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="f22c0-171">Redis が開始され、リスナーと Redis 間のネットワーク接続が使用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="f22c0-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="f22c0-172">**10200** - Redis 書き込み停止</span><span class="sxs-lookup"><span data-stu-id="f22c0-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="f22c0-173">**10201** - Redis 書き込みの停止が継続しました (60 秒ごとに)</span><span class="sxs-lookup"><span data-stu-id="f22c0-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="f22c0-174">**30100** - Redis 書き込みの停止が解決されました</span><span class="sxs-lookup"><span data-stu-id="f22c0-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="f22c0-175">これらは、リスナーが Redis キャッシュに書き込めない場合にログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="f22c0-176">Redis が開始され、リスナーと Redis 間のネットワーク接続が使用可能な場合。</span><span class="sxs-lookup"><span data-stu-id="f22c0-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="f22c0-177">**30000** — 正常に開始されました</span><span class="sxs-lookup"><span data-stu-id="f22c0-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="f22c0-178">リスナーが開始されるたびログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="f22c0-179">**22000** - Statistics Manager エージェントの初期化に成功しました。</span><span class="sxs-lookup"><span data-stu-id="f22c0-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="f22c0-180">**23000** - EventLogQueryManager の初期化に成功しました (初回または失敗後)</span><span class="sxs-lookup"><span data-stu-id="f22c0-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="f22c0-181">**24000** - serverinfo の初期化に成功しました (初回または失敗後)。</span><span class="sxs-lookup"><span data-stu-id="f22c0-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="f22c0-182">**25000** - リスナーが投稿に失敗した後 (または最初に成功した投稿) 後にオンラインに戻る</span><span class="sxs-lookup"><span data-stu-id="f22c0-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="f22c0-183">**5000** — データを投稿するリスナーのオフラインの開始</span><span class="sxs-lookup"><span data-stu-id="f22c0-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="f22c0-184">**5001** - リスナーがまだオフラインで長期続く</span><span class="sxs-lookup"><span data-stu-id="f22c0-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="f22c0-185">これらのイベントは、監視/警告/消去の問題に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="f22c0-186">Web サイトの問題</span><span class="sxs-lookup"><span data-stu-id="f22c0-186">Website issues</span></span>
<span data-ttu-id="f22c0-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-187"><a name="BKMK_Website"> </a></span></span>

- <span data-ttu-id="f22c0-188">Chrome でのログイン プロンプトの繰り返し - これはバージョン 1.1 で解決されたバグでした。</span><span class="sxs-lookup"><span data-stu-id="f22c0-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="f22c0-189">Chrome ブラウザーでログイン プロンプトが繰り返し表示される場合は、最新バージョンの Statistics Manager にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="f22c0-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="f22c0-190">実行している Web サイトのバージョンを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="f22c0-191">エクスプローラーで開きます (既定のディレクトリ)</span><span class="sxs-lookup"><span data-stu-id="f22c0-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="f22c0-192">ビューを右クリックしてStatsManHubWebSite.dllプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="f22c0-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="f22c0-193">[KHI 横] ビューまたは [カウンターの詳細] ビューでコンピューターが見つからない場合は、そのコンピューターがサイトおよびプールのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f22c0-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="f22c0-194">表示されていない場合、これらのビューには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f22c0-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="f22c0-195">トポロジ内のサーバーのサイトとプールの定義については、「トポロジのインポート」を [参照してください](deploy.md#BKMK_ImportTopology)。</span><span class="sxs-lookup"><span data-stu-id="f22c0-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="f22c0-196">製品バージョンが説明の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f22c0-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="f22c0-197">関連情報</span><span class="sxs-lookup"><span data-stu-id="f22c0-197">For more information</span></span>
<span data-ttu-id="f22c0-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="f22c0-198"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="f22c0-199">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f22c0-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="f22c0-200">Skype for Business Server の Statistics Manager の計画</span><span class="sxs-lookup"><span data-stu-id="f22c0-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="f22c0-201">Skype for Business Server の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="f22c0-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="f22c0-202">Skype for Business Server の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="f22c0-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
