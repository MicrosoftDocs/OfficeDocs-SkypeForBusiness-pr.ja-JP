---
title: Skype for Business Server の Statistics Manager のトラブルシューティング
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: '概要: Skype for Business Server の統計マネージャーの展開のトラブルシューティングを行うには、このトピックを参照してください。'
ms.openlocfilehash: 7d9ea061453998f2df01cd2ec31e792600697ee1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992514"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="a6024-103">Skype for Business Server の Statistics Manager のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a6024-103">Troubleshoot Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="a6024-104">**概要:** このトピックを読むと、Skype for Business Server の統計マネージャーの展開のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6024-104">**Summary:** Read this topic to troubleshoot your deployment of Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="a6024-105">このトピックでは、アプリケーションイベントログに表示される可能性のあるイベントと、イベントを解決するために実行できる適切な操作について説明して、統計マネージャーの展開のトラブルシューティングを行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6024-105">This topic describes how to troubleshoot your Statistics Manager deployment by describing events you might see in the application event log, and appropriate actions you might take to rectify the event.</span></span> <span data-ttu-id="a6024-106">このトピックには、次のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="a6024-106">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="a6024-107">エージェント イベント</span><span class="sxs-lookup"><span data-stu-id="a6024-107">Agent events</span></span>](troubleshoot.md#BKMK_Agent)
    
- [<span data-ttu-id="a6024-108">リスナー イベント</span><span class="sxs-lookup"><span data-stu-id="a6024-108">Listener events</span></span>](troubleshoot.md#BKMK_Listener)
    
- [<span data-ttu-id="a6024-109">Web サイトの問題</span><span class="sxs-lookup"><span data-stu-id="a6024-109">Website issues</span></span>](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a><span data-ttu-id="a6024-110">エージェント イベント</span><span class="sxs-lookup"><span data-stu-id="a6024-110">Agent events</span></span>
<span data-ttu-id="a6024-111"><a name="BKMK_Agent"> </a></span><span class="sxs-lookup"><span data-stu-id="a6024-111"></span></span>

- <span data-ttu-id="a6024-112">**1000** - プロセッサー制限をセットアップできない (ジョブ オブジェクト) - 原因不明</span><span class="sxs-lookup"><span data-stu-id="a6024-112">**1000** — Unable to setup processor limiter (Job Object) — Unknown reason</span></span>
    
- <span data-ttu-id="a6024-113">**1001** : プロセスの制限はプロセスで許可されていません (既にジョブオブジェクト内に存在する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="a6024-113">**1001** — Process limiting isn't allowed on the process (probably already inside a Job Object)</span></span>
    
    <span data-ttu-id="a6024-114">エージェントは Windows のジョブ オブジェクト内部で実行され、自動でエージェントの使用するメモリ容量を制限します。</span><span class="sxs-lookup"><span data-stu-id="a6024-114">The Agent runs inside of a Windows Job Object to automatically limit its memory footprint.</span></span> <span data-ttu-id="a6024-115">エージェントが開始しておらず、このジョブ オブジェクトのイベント エントリがイベント ログに存在する場合、このジョブ オブジェクトをサーバー上でインスタンス化できません。</span><span class="sxs-lookup"><span data-stu-id="a6024-115">If the agent will not start and these event entries are present in the event log, the Job Object is not able to be instantiated on the server.</span></span> <span data-ttu-id="a6024-116">これを回避するには、設定ファイルで値を変更してメモリの上限を外してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-116">To work around this, the upper memory limit can be removed by changing a value in the config file:</span></span>
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    <span data-ttu-id="a6024-117">"MaxProcessMemoryMB" を検索し、次のように値を "0" に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6024-117">Search for "MaxProcessMemoryMB" and change the value to "0" as shown:</span></span>
    
  ```console
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > <span data-ttu-id="a6024-118">この変更が加えられた場合、通常、エージェント\<は 100 mb のメモリを消費しますが、既定では 300 mb に制限されません。</span><span class="sxs-lookup"><span data-stu-id="a6024-118">If this change is made, the Agent will generally still consume \< 100 MB of memory, however it will not be forcefully limited to 300 MB as is the default.</span></span> <span data-ttu-id="a6024-119">この変更を行った場合、メモリの使用状況を注意深く監視しそのエージェントがホスト マシンで大容量のメモリを消費しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6024-119">If this change is made, we recommend closely monitoring memory usage to ensure the Agent does not consume a large amount of memory on its host machine.</span></span> 
  
- <span data-ttu-id="a6024-120">**2000** - クライアントの初期化に失敗しました</span><span class="sxs-lookup"><span data-stu-id="a6024-120">**2000** — Client initialization failure</span></span>
    
- <span data-ttu-id="a6024-121">**2001** - このサービスと接続されているソース IP はありません</span><span class="sxs-lookup"><span data-stu-id="a6024-121">**2001**— No connection could be made to the service on any source IP</span></span>
    
    <span data-ttu-id="a6024-122">エージェントがリスナーのコンピューターと接続できない場合、以下を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-122">If the Agent cannot connect to the Listener computer, check the following:</span></span>
    
1. <span data-ttu-id="a6024-123">リスナー サービスがリスナーのコンピューターで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-123">Ensure the Listener service is running on the Listener computer.</span></span> <span data-ttu-id="a6024-124">実行されていない場合は、サーバーで Redis が実行していることを確認してからリスナー サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a6024-124">If not, ensure Redis is running on that server and then restart the Listener service.</span></span>
    
    <span data-ttu-id="a6024-125">リスナーコンピューターの統計情報マネージャーイベントログを確認して、統計情報マネージャーのリスナーサービス自体に問題がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-125">Check the Statistics Manager event log on the Listener computer to ensure there are no issues with the Statistics Manager Listener service itself.</span></span>
    
2. <span data-ttu-id="a6024-126">telnet などの接続ツールを使用して、エージェントのコンピューターから適切なポートのリスナーへの接続性を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-126">Use a connectivity tool such as telnet to verify connectivity from the Agent computer to the Listener on the correct port.</span></span>
    
    <span data-ttu-id="a6024-127">接続されていない場合は、リスナーのコンピューターでのファイアウォールの受信ルールで、リスナーのコンピューターが接続されているネットワークのタイプ (プライベート/パブリック/ドメイン) が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-127">If not, make sure the incoming firewall rule is enabled on the Listener computer for the network type that the Listener computer is connected to (private/public/domain).</span></span> <span data-ttu-id="a6024-128">リスナーコンピューターがドメインに参加していない場合は、ネットワークが公開されている可能性があります。その場合、Statistics Manager を使用してインストールされたファイアウォール規則は既定では適用されません。</span><span class="sxs-lookup"><span data-stu-id="a6024-128">If the Listener computer is not joined to a domain, the network may be listed as public and in that case the firewall rules installed with Statistics Manager will not apply by default.</span></span>
    
- <span data-ttu-id="a6024-129">**4000** - リスナーからのサーバー情報のダウンロードに失敗しました (理由不明)</span><span class="sxs-lookup"><span data-stu-id="a6024-129">**4000** — Failure to download Server Info from Listener (unknown reason)</span></span>
    
  - <span data-ttu-id="a6024-130">**4001** - リスナーのトポロジでサーバーが見つかりませんでした</span><span class="sxs-lookup"><span data-stu-id="a6024-130">**4001** — Server Not Found in Listener Topology</span></span>
    
    <span data-ttu-id="a6024-131">このエラーは、サーバーがリスナーに正常に接続しているにもかかわらず、リスナーのキャッシュのトポロジにサーバーが追加されなかった場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a6024-131">This error will occur if the server is successfully connecting to the Listener, but the server was not added to the topology in the Listener's cache.</span></span> <span data-ttu-id="a6024-132">解決策の選択肢には、以下のものがあります。</span><span class="sxs-lookup"><span data-stu-id="a6024-132">Resolution options:</span></span>
    
  - <span data-ttu-id="a6024-p107">	トポロジのインポートの手順に従っていることを確認します。「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="a6024-p107">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span> 
    
  - <span data-ttu-id="a6024-135">このトポロジ内のリストに記述されていないサーバーにエージェントがある場合 (たとえば、SQL AlwaysOn クラスタ内のノード)、「[トポロジのインポート](deploy.md#BKMK_ImportTopology)」にある手順に従ってエージェントを手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6024-135">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="a6024-136">**4002** - 無効なリスナー パスワード</span><span class="sxs-lookup"><span data-stu-id="a6024-136">**4002** — Invalid Listener Password</span></span>
    
    <span data-ttu-id="a6024-137">エージェントが使用しようとした暗号化されたパスワードが、リスナー自体のサービス パスワードと一致しません。</span><span class="sxs-lookup"><span data-stu-id="a6024-137">The encrypted password that the agent is attempting to use does not match the service password on the Listener itself.</span></span> <span data-ttu-id="a6024-138">エージェントをアンインストールし、正しいサービス パスワードを使用して再度インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="a6024-138">Uninstall the Agent and re-install it using the correct service password.</span></span>
    
  - <span data-ttu-id="a6024-139">**4003** - 証明書の拇印の不一致</span><span class="sxs-lookup"><span data-stu-id="a6024-139">**4003** — Certificate Thumbprint Mismatch</span></span>
    
    <span data-ttu-id="a6024-140">インストール時にエージェントに指定された証明書の拇印が、リスナーが現在使用している証明書の拇印と一致しないため、接続が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="a6024-140">The certificate thumbprint given to the Agent at install time does not match the thumbprint on the certificate the Listener is currently using and therefore the connection will be refused.</span></span> <span data-ttu-id="a6024-141">エージェントをアンインストールし、正しい証明書の拇印を使って再インストールします。</span><span class="sxs-lookup"><span data-stu-id="a6024-141">Uninstall the Agent and re-install it using the correct certificate thumbprint.</span></span>
    
  - <span data-ttu-id="a6024-142">**4004** - 無効な応答または無効な HttpStatusCode</span><span class="sxs-lookup"><span data-stu-id="a6024-142">**4004** — Invalid Response or HttpStatusCode</span></span>
    
    <span data-ttu-id="a6024-143">リスナーの応答が、期待した状態ではありません。  </span><span class="sxs-lookup"><span data-stu-id="a6024-143">The Listener is not responding with an expected status.</span></span> 
    
  - <span data-ttu-id="a6024-144">接続がプロキシ化されている場合、プロキシ設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-144">If the connection is proxied, check the proxy configuration.</span></span>
    
  - <span data-ttu-id="a6024-145">リスナーコンピューターの StatsMan ログで、構成の問題について確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-145">Check the Listener computer's StatsMan log for issues with its configuration.</span></span>
    
  - <span data-ttu-id="a6024-146">**4005** - XML のシリアル化解除ができませんでした</span><span class="sxs-lookup"><span data-stu-id="a6024-146">**4005** — Couldn't de-serialize the XML</span></span>
    
    <span data-ttu-id="a6024-147">リスナー サーバー上の情報が破損しているか、エージェント コンピューターとリスナー コンピューターの間でバージョンの不一致があります。</span><span class="sxs-lookup"><span data-stu-id="a6024-147">The server info on the Listener server is corrupt or there may be a version mismatch between the Agent and the Listener computers.</span></span> <span data-ttu-id="a6024-148">バージョンが一致しているか確認し、リスナーのイベント ログで問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-148">Ensure the versions match and check the Listener event log for issues.</span></span>
    
## <a name="listener-events"></a><span data-ttu-id="a6024-149">リスナー イベント</span><span class="sxs-lookup"><span data-stu-id="a6024-149">Listener events</span></span>
<span data-ttu-id="a6024-150"><a name="BKMK_Listener"> </a></span><span class="sxs-lookup"><span data-stu-id="a6024-150"></span></span>

- <span data-ttu-id="a6024-151">**10000** - 不明な原因で起動に失敗しました (回復不能な障害があるため、サービスは停止またはクラッシュします)</span><span class="sxs-lookup"><span data-stu-id="a6024-151">**10000** — Startup failure Unknown reason (these are unrecoverable and the service will stop/crash as a result)</span></span>
    
  - <span data-ttu-id="a6024-152">**10001** - 構成の問題</span><span class="sxs-lookup"><span data-stu-id="a6024-152">**10001** — Configuration problem</span></span>
    
    <span data-ttu-id="a6024-153">この問題は通常、[listener_install_location]\PerfAgentListener.exe 構成ファイルを手動で変更したために、アプリケーションから読み取れなくなったことが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="a6024-153">Generally this will occur when the [listener_install_location]\PerfAgentListener.exe.config file has been modified by hand and cannot be read by the application.</span></span>
    
  - <span data-ttu-id="a6024-154">**10002** - HTTP リスナー初期化エラー</span><span class="sxs-lookup"><span data-stu-id="a6024-154">**10002** — HTTP Listener initialization error</span></span>
    
    <span data-ttu-id="a6024-155">このイベントは通常、インストール時に URL ACL が適切に設定されていないか、または SSL 証明書が無効な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a6024-155">This event will generally be logged when the URL ACL has not been set properly during installation or the SSL Cert is invalid.</span></span> <span data-ttu-id="a6024-156">使用中の設定にある証明書が有効であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-156">Ensure the certificate in your configuration is valid.</span></span> <span data-ttu-id="a6024-157">有効な場合は、「[Deploy Statistics Manager (英語)](deploy.md#BKMK_Deploy)」の指示に従ってリスナーを再度インストールします。</span><span class="sxs-lookup"><span data-stu-id="a6024-157">If it is, reinstall the Listener according to the instructions in [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span></span>
    
  - <span data-ttu-id="a6024-158">**10003** - Redis エラー</span><span class="sxs-lookup"><span data-stu-id="a6024-158">**10003** — Redis failure</span></span>
    
  - <span data-ttu-id="a6024-159">**10004** - キャッシュ インフラストラクチャーのエラー</span><span class="sxs-lookup"><span data-stu-id="a6024-159">**10004** — Caching infrastructure failure</span></span>
    
  - <span data-ttu-id="a6024-160">**10007** - 設定 (redis に保存)</span><span class="sxs-lookup"><span data-stu-id="a6024-160">**10007** — Settings (stored in redis)</span></span>
    
    <span data-ttu-id="a6024-161">リスナーが Redis に連絡できないか、適切に書式化されたデータをキャッシュから取得できないか、クラウドを開始できません。</span><span class="sxs-lookup"><span data-stu-id="a6024-161">The Listener could not contact Redis or retrieve well-formed data from the cache and could not start.</span></span> <span data-ttu-id="a6024-162">Redis サービスが開始されていて、サーバーが適切に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-162">Ensure the Redis service is started and configured properly on the server.</span></span>
    
  - <span data-ttu-id="a6024-163">**10005** - サーバー情報の取得中または解析中です</span><span class="sxs-lookup"><span data-stu-id="a6024-163">**10005** — Server info retrieval/parsing</span></span>
    
    <span data-ttu-id="a6024-164">Redis キャッシュ内のトポロジ情報が無効です。</span><span class="sxs-lookup"><span data-stu-id="a6024-164">The topology information in the Redis cache is invalid.</span></span> <span data-ttu-id="a6024-165">まず、Redis とリスナーを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="a6024-165">First, attempt to restart Redis and the Listener.</span></span> <span data-ttu-id="a6024-166">解決しない場合は、「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照して、トポロジ データを再度作成します。</span><span class="sxs-lookup"><span data-stu-id="a6024-166">If the error persists, see [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.</span></span>
    
- <span data-ttu-id="a6024-167">**10100** - Redis PING が停止しました</span><span class="sxs-lookup"><span data-stu-id="a6024-167">**10100** — Redis PING outage</span></span>
    
  - <span data-ttu-id="a6024-168">**10101** - Redis PING の停止を継続します (60 秒毎)</span><span class="sxs-lookup"><span data-stu-id="a6024-168">**10101** — Redis PING continued outage (every 60 seconds)</span></span>
    
  - <span data-ttu-id="a6024-169">**30100** - Redis PING の停止から復元しました</span><span class="sxs-lookup"><span data-stu-id="a6024-169">**30100** — Redis PING outage restored</span></span>
    
    <span data-ttu-id="a6024-170">これらのイベントは、リスナーが Redis に接続できない場合にログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a6024-170">These will be logged when the Listener cannot connect to Redis.</span></span> <span data-ttu-id="a6024-171">Redis が開始していること、およびリスナーと Redis 間の接続が使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-171">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="a6024-172">**10200** - Redis の書き込みが停止しました</span><span class="sxs-lookup"><span data-stu-id="a6024-172">**10200** — Redis Write outage</span></span>
    
  - <span data-ttu-id="a6024-173">**10201** - Redis の書き込みの停止を継続します (60 秒毎)</span><span class="sxs-lookup"><span data-stu-id="a6024-173">**10201** — Redis Write outage continued (every 60 seconds)</span></span>
    
  - <span data-ttu-id="a6024-174">**30100** - Redis の書き込みが解決しました</span><span class="sxs-lookup"><span data-stu-id="a6024-174">**30100** — Redis Write outage resolved</span></span>
    
    <span data-ttu-id="a6024-175">これらのイベントは、リスナーが Redis キャッシュへの書き込みに失敗したときにログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a6024-175">These will be logged when the Listener cannot write to the Redis cache.</span></span> <span data-ttu-id="a6024-176">Redis が開始していること、およびリスナーと Redis 間の接続が使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-176">Ensure Redis is started and network connectivity between the Listener and Redis is available.</span></span>
    
- <span data-ttu-id="a6024-177">**30000** - 正常に開始しました</span><span class="sxs-lookup"><span data-stu-id="a6024-177">**30000** — Successfully started</span></span>
    
    <span data-ttu-id="a6024-178">リスナーが開始するたびにログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a6024-178">Logged each time the Listener is started.</span></span>
    
- <span data-ttu-id="a6024-179">**22000** : 統計マネージャーエージェントの初期化に成功しました。</span><span class="sxs-lookup"><span data-stu-id="a6024-179">**22000** — Initialization of Statistics Manager Agent succeeded.</span></span>
    
- <span data-ttu-id="a6024-180">**23000** - EventLogQueryManager の初期化に成功しました (最初、その後は失敗した場合)</span><span class="sxs-lookup"><span data-stu-id="a6024-180">**23000** — Initialization of EventLogQueryManager succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="a6024-181">**24000** - サーバー情報の初期化に成功しました (最初、その後は失敗した場合)</span><span class="sxs-lookup"><span data-stu-id="a6024-181">**24000** — Initialization of serverinfo succeeded (first time or after failing)</span></span>
    
- <span data-ttu-id="a6024-182">**25000** - リスナーが投稿に失敗した後、オンラインに復帰しました (または、最初に成功した投稿)</span><span class="sxs-lookup"><span data-stu-id="a6024-182">**25000** — Listener is back online after failing to post (or first successful post)</span></span>
    
- <span data-ttu-id="a6024-183">**5000** - データを投稿するためオフラインのリスナーを開始します</span><span class="sxs-lookup"><span data-stu-id="a6024-183">**5000** — Start of listener offline for posting data</span></span>
    
- <span data-ttu-id="a6024-184">**5001** - リスナーは拡張された期間中さらにオフラインになります</span><span class="sxs-lookup"><span data-stu-id="a6024-184">**5001** — Listener is still offline for an extended period</span></span>
    
    <span data-ttu-id="a6024-185">これらのイベントは、監視/警告/問題の消去で有用です。</span><span class="sxs-lookup"><span data-stu-id="a6024-185">These events can be useful for monitoring/alerting/clearing issues.</span></span>
    
## <a name="website-issues"></a><span data-ttu-id="a6024-186">Web サイトの問題</span><span class="sxs-lookup"><span data-stu-id="a6024-186">Website issues</span></span>
<span data-ttu-id="a6024-187"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="a6024-187"></span></span>

- <span data-ttu-id="a6024-188">Chrome で繰り返しログインプロンプトが表示されました。これは、バージョン1.1 で解決されたバグです。</span><span class="sxs-lookup"><span data-stu-id="a6024-188">Repetitive login prompts in Chrome - this was a bug that has been resolved in version 1.1.</span></span> <span data-ttu-id="a6024-189">Chrome ブラウザーでログインプロンプトが繰り返し表示される場合は、最新バージョンの統計情報マネージャーにアップグレードしたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-189">Be sure you have upgraded to the latest version of Statistics Manager if you are seeing repeated login prompts in the Chrome browser.</span></span> <span data-ttu-id="a6024-190">実行中の Web サイトのバージョンを確認するには、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-190">To verify the version of the website you are running:</span></span>
    
  - <span data-ttu-id="a6024-191">	エクスプローラーで、デフォルトディレクトリを開きます</span><span class="sxs-lookup"><span data-stu-id="a6024-191">In File Explorer, open (default directory)</span></span>
    
  - <span data-ttu-id="a6024-192">StatsManHubWebSite.dll を右クリックし、このファイルのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="a6024-192">Right click on StatsManHubWebSite.dll and view its properties.</span></span>
    
  - <span data-ttu-id="a6024-193">[KHI 横方向] ビューまたは [カウンター詳細] ビューでコンピューターが見つからない場合、コンピューターがサイトまたはプールのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6024-193">If a computer cannot be found in the KHI Landscape view or the Counter Details view, make sure it is a member of a Site and a Pool.</span></span> <span data-ttu-id="a6024-194">メンバーでない場合は、これらのビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6024-194">If it is not, it will not appear in those views.</span></span> <span data-ttu-id="a6024-195">トポロジでのサーバーに対するサイトおよびプールの定義の詳細については、「[Import the topology (英語)](deploy.md#BKMK_ImportTopology)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-195">For information about defining a site and pool for a server in the topology, see [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
  - <span data-ttu-id="a6024-196">製品のバージョンは [説明] の詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6024-196">The product version will be shown in the Description details.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="a6024-197">関連情報</span><span class="sxs-lookup"><span data-stu-id="a6024-197">For more information</span></span>
<span data-ttu-id="a6024-198"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="a6024-198"></span></span>

<span data-ttu-id="a6024-199">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6024-199">For more information, see the following:</span></span>
  
- [<span data-ttu-id="a6024-200">Skype for Business Server の Statistics Manager の計画</span><span class="sxs-lookup"><span data-stu-id="a6024-200">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="a6024-201">Skype for Business Server の Statistics Manager の展開</span><span class="sxs-lookup"><span data-stu-id="a6024-201">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="a6024-202">Skype for Business Server の Statistics Manager のアップグレード</span><span class="sxs-lookup"><span data-stu-id="a6024-202">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
