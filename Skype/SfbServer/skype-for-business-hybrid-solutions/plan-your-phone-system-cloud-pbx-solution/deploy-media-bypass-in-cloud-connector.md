---
title: Cloud Connector エディションでメディア バイパスを展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: クラウド コネクタ版 version 2.0 以降でメディアをバイパスを展開する手順については、このトピックを参照してください。
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="7f85b-103">Cloud Connector エディションでメディア バイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="7f85b-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="7f85b-104">クラウド コネクタ版 version 2.0 以降でメディアをバイパスを展開する手順については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f85b-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="7f85b-105">メディア バイ パスにより、公衆交換電話網 (PSTN) の次のホップに直接メディアを送信するクライアント-ゲートウェイまたはセッション ボーダー コント ローラー (SBC)-メディアのパスからクラウドのコネクタのエディションのコンポーネントを削除するとします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="7f85b-106">[クラウド コネクタのエディションで使用しないメディアの計画](plan-for-media-bypass-in-cloud-connector-edition.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f85b-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="7f85b-107">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="7f85b-107">Enable media bypass</span></span>

<span data-ttu-id="7f85b-108">メディア バイパスを有効にするには、メディア バイパス Web サービスの DNS 名を設定し、テナント構成でメディア バイパスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="7f85b-109">メディア バイパス Web サービスはそれぞれの仲介サーバーに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="7f85b-110">テナント管理者はハイブリッド音声サービス (サイト) の名前を指定する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインの名前を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="7f85b-111">サービス名は、クラウドのコネクタのすべてのアプライアンスやクライアントの場所に関係なくすべての PSTN のサイト間で同じをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="7f85b-112">この Web サービスはネットワーク内部のみで利用可能です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="7f85b-113">テナント管理者は内部実働の Active Directory で DNS A レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="7f85b-114">複雑な複数サイト環境を使っている場合の例を参照してください。[の使用例: メディアが複雑な複数サイトの環境で web サイトの DNS レコードを使用しない](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="7f85b-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="7f85b-115">DNS レコードは、内部ネットワーク クライアントについてのみ解決します。外部ネットワーク クライアントについては解決しません。</span><span class="sxs-lookup"><span data-stu-id="7f85b-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="7f85b-116">DNS を構成したら、Skype for Business 管理者の資格情報で リモート PowerShell を使用して、Skype for Business Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="7f85b-117">詳細については、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f85b-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="7f85b-118">PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7f85b-119">メディア バイパスの有効化は 2 つのプロセスで行います。</span><span class="sxs-lookup"><span data-stu-id="7f85b-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="7f85b-120">New-CsNetworkMedia コマンドレットでは、新しい構成がすぐに保存されません。メモリ内に設定が作成されるだけです。</span><span class="sxs-lookup"><span data-stu-id="7f85b-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="7f85b-121">このコマンドレットで作成したオブジェクトを変数として保存し、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="7f85b-122">詳細についてを参照してください[の使用例: メディアが複雑な複数サイトの環境で web サイトの DNS レコードを使用しない](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="7f85b-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="7f85b-123">設置とオンラインのコンポーネント間のレプリケーションで、ユーザーを有効にする前に必要なコマンドを実行することをお勧めします、最大 24 時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="7f85b-124">メディア バイパス設定を確認する</span><span class="sxs-lookup"><span data-stu-id="7f85b-124">Confirm media bypass settings</span></span>

<span data-ttu-id="7f85b-125">メディア バイパス設定は次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="7f85b-126">テナント プールにオンライン ・ レプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="7f85b-127">設置型のレプリケーションを確認して、クラウドのコネクタの仲介サーバーに接続、PowerShell で次のコマンドを実行、ことを確認するその Enabled = True と AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="7f85b-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7f85b-128">クライアント設定を確認するには、ビジネス クライアント用の Skype からサインアウトにもう一度サインインし、クライアントが、サービスの URL を次のように受け取ることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="7f85b-129">%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="7f85b-130">Hybridconfigserviceinternalurl を検索し、定義した URL に一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="7f85b-131">メディア バイパス パラメータを変更する</span><span class="sxs-lookup"><span data-stu-id="7f85b-131">Change media bypass parameters</span></span>

<span data-ttu-id="7f85b-132">テナント管理者は、次のコマンドレットを実行して、Web サービスの DNS 名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="7f85b-133">クライアントは、一度サインアウトしてから再びサインインし、新しいサービス名を入手することで、変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="7f85b-134">メディア バイパスを一時的に無効にする</span><span class="sxs-lookup"><span data-stu-id="7f85b-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="7f85b-p106">このシナリオは、トラブルシューティングやメンテナンスで役立ちます。サービスを無効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="7f85b-137">変更後、すべての Cloud Connector にレプリケートされるまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="7f85b-138">レプリケーションの状態を確認するには、クラウド コネクタの仲介サーバーに、PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="7f85b-139">変更がレプリケートされると、仲介サーバーの Web サービスにより、メディア バイパス サービスに対するクライアント要求の拒否が開始されます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="7f85b-140">メディア バイパスを完全に無効にする</span><span class="sxs-lookup"><span data-stu-id="7f85b-140">Disable media bypass permanently</span></span>

<span data-ttu-id="7f85b-141">メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="7f85b-142">さらに、管理者は内部 DNS サーバーからメディア バイパスの Web アドレスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="7f85b-143">変更を加えたら、クラウドのコネクタのすべてのアプライアンスをレプリケートする変更の時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="7f85b-144">例: 複雑なマルチサイト環境でのメディア バイパス Web サイトの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="7f85b-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="7f85b-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7f85b-145"></span></span>

<span data-ttu-id="7f85b-146">クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="7f85b-147">Web サービスの名前は同じにするすべてのコネクタのクラウド アプライアンスおよびクラウド コネクタ PSTN のサイト。</span><span class="sxs-lookup"><span data-stu-id="7f85b-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="7f85b-148">複雑なマルチサイト環境では、地理的な場所ベースのトラフィック管理用の Windows 2016 DNS ポリシーを使用して、クライアントのネットワークにおいてローカルな Web サービスにクライアントをリダイレクトできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="7f85b-149">Windows 2016 DNS ポリシーの詳細については、[地理的な場所ベースのトラフィックの管理のプライマリ サーバーの DNS ポリシーの使用](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f85b-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="7f85b-150">地理的な場所ベースのトラフィック管理の Windows 2016 DNS ポリシーを使用して、複数のサイトを持つ会社の構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="7f85b-151">使用しないサービスの名前は、'hybridvoice.adatum.biz' です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="7f85b-152">アムステルダムのサイトには、4 つのクラウド コネクタ アプライアンスを次のような仲介サーバーの IP アドレスで展開があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7f85b-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7f85b-153">192.168.1.45</span></span>
    
- <span data-ttu-id="7f85b-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7f85b-154">192.168.1.46</span></span>
    
- <span data-ttu-id="7f85b-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7f85b-155">192.168.1.47</span></span>
    
- <span data-ttu-id="7f85b-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7f85b-156">192.168.1.48</span></span>
    
<span data-ttu-id="7f85b-157">シアトルのサイトには、次の 3 つのクラウド コネクタ アプライアンスを次のような仲介サーバーの IP アドレスで展開があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="7f85b-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7f85b-158">10.10.1.8</span></span>
    
- <span data-ttu-id="7f85b-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7f85b-159">10.10.1.9</span></span>
    
- <span data-ttu-id="7f85b-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7f85b-160">10.10.1.10</span></span>
    
<span data-ttu-id="7f85b-161">地理的な場所ベースのトラフィック管理を使用する場合は、次の手順で DNS サーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="7f85b-162">アムステルダムとシアトルのサブネットに対する DNS クライアント サブネットを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="7f85b-163">アムステルダムとシアトルの adatum.biz の DNS ゾーン範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="7f85b-164">それぞれの DNS ゾーン範囲で DNS レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="7f85b-165">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="7f85b-165">Amsterdam</span></span>
    
  - <span data-ttu-id="7f85b-166">タイプ A</span><span class="sxs-lookup"><span data-stu-id="7f85b-166">Type A;</span></span>
    
  - <span data-ttu-id="7f85b-167">名前: adatum.biz DNS ゾーンの hybridvoice</span><span class="sxs-lookup"><span data-stu-id="7f85b-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7f85b-168">ターゲット: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="7f85b-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="7f85b-169">追加の仲介サーバーについてレコードを作成する</span><span class="sxs-lookup"><span data-stu-id="7f85b-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7f85b-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="7f85b-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="7f85b-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="7f85b-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="7f85b-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="7f85b-172">192.168.1.48</span></span>
    
    <span data-ttu-id="7f85b-173">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="7f85b-173">Seattle</span></span>
    
  - <span data-ttu-id="7f85b-174">タイプ A</span><span class="sxs-lookup"><span data-stu-id="7f85b-174">Type A</span></span>
    
  - <span data-ttu-id="7f85b-175">名前: adatum.biz DNS ゾーンの hybridvoice</span><span class="sxs-lookup"><span data-stu-id="7f85b-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="7f85b-176">ターゲット: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="7f85b-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="7f85b-177">追加の仲介サーバーについてレコードを作成する</span><span class="sxs-lookup"><span data-stu-id="7f85b-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="7f85b-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="7f85b-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="7f85b-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="7f85b-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="7f85b-180">クライアント サブネットを適切なゾーン範囲に接続する DNS ポリシーを作成して、DNS が確実に解決されるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="7f85b-181">この時点では、hybridvoice.adatum.biz のアムステルダムのサブネットから DNS クエリーを実行しているクライアントは 192.168.1.45、192.168.1.46、192.168.1.47、192.168.1.48 のアドレスを返します。その一方で、シアトルから同様のクエリーを実行しているクライアントは 10.10.1.8、10.10.1.9、10.10.1.10 を返します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f85b-182">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-182">See also</span></span>
<span data-ttu-id="7f85b-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="7f85b-183"></span></span>

#### 

[<span data-ttu-id="7f85b-184">クラウド コネクタのエディションでのメディア バイ パスを計画します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)

