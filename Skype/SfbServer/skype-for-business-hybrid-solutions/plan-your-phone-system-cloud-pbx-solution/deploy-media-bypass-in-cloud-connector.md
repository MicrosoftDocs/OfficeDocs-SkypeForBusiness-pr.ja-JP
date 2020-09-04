---
title: Cloud Connector エディションでのメディアバイパスの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: このトピックでは、Cloud Connector エディションバージョン2.0 以降を使用してメディアバイパスを展開する手順について説明します。
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359313"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="60757-103">Cloud Connector エディションでのメディアバイパスの展開</span><span class="sxs-lookup"><span data-stu-id="60757-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="60757-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="60757-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="60757-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60757-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="60757-106">このトピックでは、Cloud Connector エディションバージョン2.0 以降を使用してメディアバイパスを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="60757-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="60757-107">メディアバイパスを使用すると、クライアントはメディアを公衆交換電話網 (PSTN) の次ホップに直接送信できます。ゲートウェイまたはセッションボーダーコントローラー (SBC) を使用して、Cloud Connector Edition コンポーネントをメディアパスから削除します。</span><span class="sxs-lookup"><span data-stu-id="60757-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="60757-108">[Cloud Connector Edition の「Plan for media バイパス](plan-for-media-bypass-in-cloud-connector-edition.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="60757-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="60757-109">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="60757-109">Enable media bypass</span></span>

<span data-ttu-id="60757-110">メディアバイパスを有効にするには、メディアバイパス web サービスの DNS 名を構成し、テナント構成でメディアバイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="60757-111">メディアバイパス web サービスは、すべての仲介サーバーで自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="60757-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="60757-112">テナント管理者はハイブリッド音声サービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインの名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="60757-113">サービス名は、すべての Cloud Connector アプライアンスと、クライアントの場所に関係なくすべての PSTN サイトで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="60757-114">Web サービスは、ネットワーク内部でのみ利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="60757-115">テナント管理者は内部運用 Active Directory で DNS A レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="60757-116">複雑なマルチサイト環境がある場合は、「 [複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード](deploy-media-bypass-in-cloud-connector.md#Example)」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60757-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="60757-117">DNS レコードは、内部ネットワーククライアントに対してのみ解決する必要があります。外部ネットワーククライアントに対しては解決されません。</span><span class="sxs-lookup"><span data-stu-id="60757-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="60757-118">DNS を構成した後、Skype for Business 管理者の資格情報を使用してリモート PowerShell を使用して、Skype for Business Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="60757-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="60757-119">詳細については、「 [Windows PowerShell 用にコンピューター](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60757-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="60757-120">PowerShell セッションで、次のコマンドを入力してメディアバイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="60757-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="60757-121">メディアバイパスを有効にするには、2段階のプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="60757-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="60757-122">新しい-CsNetworkMedia コマンドレットでは、新しい構成はすぐには保存されません。メモリに設定を作成するだけです。</span><span class="sxs-lookup"><span data-stu-id="60757-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="60757-123">このコマンドレットで作成したオブジェクトは、変数に保存してから、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="60757-124">詳細については、「 [例: 複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード](deploy-media-bypass-in-cloud-connector.md#Example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60757-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="60757-125">オンプレミスとオンラインのコンポーネント間のレプリケーションには最大24時間かかる場合があるため、ユーザーを有効にする前に、必要なコマンドを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="60757-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="60757-126">メディアバイパス設定の確認</span><span class="sxs-lookup"><span data-stu-id="60757-126">Confirm media bypass settings</span></span>

<span data-ttu-id="60757-127">メディアバイパス設定を確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="60757-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="60757-128">テナントプールへのオンラインレプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="60757-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60757-129">オンプレミスレプリケーションを確認するには、Cloud Connector 仲介サーバーに接続し、PowerShell で次のコマンドを実行し、Enabled = True、Always バイパス = True であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60757-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60757-130">クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、もう一度サインインして、クライアントが次のようにサービス URL を受信していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60757-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="60757-131">%Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. を開く</span><span class="sxs-lookup"><span data-stu-id="60757-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="60757-132">Hybridconfigserviceinternalurl を検索し、URL が定義したものと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="60757-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="60757-133">メディアバイパスパラメーターの変更</span><span class="sxs-lookup"><span data-stu-id="60757-133">Change media bypass parameters</span></span>

<span data-ttu-id="60757-134">テナント管理者は、次のコマンドレットを実行することによって、web サービスの DNS 名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="60757-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="60757-135">クライアントは、新しいサービス名を取得して変更を認識するために、サインアウトしてからサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="60757-136">メディアバイパスを一時的に無効にする</span><span class="sxs-lookup"><span data-stu-id="60757-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="60757-137">このシナリオは、トラブルシューティングや保守に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="60757-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="60757-138">サービスを無効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="60757-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="60757-139">変更後は、変更がすべてのクラウドコネクタにレプリケートされるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="60757-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="60757-140">レプリケーションの状態を確認するには、Cloud Connector 仲介サーバーの PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="60757-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="60757-141">変更がレプリケートされると、仲介サーバーの web サービスは、メディアバイパスサービスに対するクライアント要求の拒否を開始します。</span><span class="sxs-lookup"><span data-stu-id="60757-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="60757-142">メディアバイパスを完全に無効にする</span><span class="sxs-lookup"><span data-stu-id="60757-142">Disable media bypass permanently</span></span>

<span data-ttu-id="60757-143">メディアバイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="60757-144">また、管理者は、内部 DNS サーバーからメディアバイパスの web アドレスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60757-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="60757-145">変更後は、すべての Cloud Connector アプライアンスに変更がレプリケートされるまでに少し時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="60757-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="60757-146">例: 複雑なマルチサイト環境でのメディアバイパス web サイトの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="60757-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="60757-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="60757-147"><a name="Example"> </a></span></span>

<span data-ttu-id="60757-148">クライアントは、内部 DNS サーバーからメディアバイパス web サービスの web アドレスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="60757-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="60757-149">Web サービスの名前は、すべての Cloud Connector アプライアンスおよび Cloud Connector PSTN サイトで同じになります。</span><span class="sxs-lookup"><span data-stu-id="60757-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="60757-150">複雑なマルチサイト環境では、地域の場所に基づいたトラフィック管理に Windows 2016 DNS ポリシーを使用することをお勧めします。そのため、ネットワークにローカルな web サービスにクライアントをリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="60757-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="60757-151">Windows 2016 DNS ポリシーの詳細については、「 [プライマリサーバーを使用した地域の場所ベースのトラフィック管理に Dns ポリシーを使用する](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60757-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="60757-152">次に示すのは、地域の場所ベースのトラフィック管理に Windows 2016 DNS ポリシーを使用している複数のサイトを持つ企業の構成例です。</span><span class="sxs-lookup"><span data-stu-id="60757-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="60757-153">バイパスサービスの名前は ' hybridvoice.adatum.biz ' です。</span><span class="sxs-lookup"><span data-stu-id="60757-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="60757-154">アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して展開された4つの Cloud Connector アプライアンスがあります。</span><span class="sxs-lookup"><span data-stu-id="60757-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="60757-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="60757-155">192.168.1.45</span></span>
    
- <span data-ttu-id="60757-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="60757-156">192.168.1.46</span></span>
    
- <span data-ttu-id="60757-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="60757-157">192.168.1.47</span></span>
    
- <span data-ttu-id="60757-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="60757-158">192.168.1.48</span></span>
    
<span data-ttu-id="60757-159">シアトルのサイトには、次の仲介サーバー IP アドレスを使用して展開された3つの Cloud Connector アプライアンスがあります。</span><span class="sxs-lookup"><span data-stu-id="60757-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="60757-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="60757-160">10.10.1.8</span></span>
    
- <span data-ttu-id="60757-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="60757-161">10.10.1.9</span></span>
    
- <span data-ttu-id="60757-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="60757-162">10.10.1.10</span></span>
    
<span data-ttu-id="60757-163">地域の場所に基づいたトラフィック管理を使用して、DNS サーバーを次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="60757-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="60757-164">アムステルダムとシアトルの両方のサブネットの DNS クライアントサブネットを作成します。</span><span class="sxs-lookup"><span data-stu-id="60757-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="60757-165">アムステルダムとシアトルの両方について、adatum.biz の DNS ゾーンスコープを作成します。</span><span class="sxs-lookup"><span data-stu-id="60757-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="60757-166">Dns ゾーンスコープごとに DNS レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="60757-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="60757-167">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="60757-167">Amsterdam</span></span>
    
   - <span data-ttu-id="60757-168">「A;」と入力します。</span><span class="sxs-lookup"><span data-stu-id="60757-168">Type A;</span></span>
    
   - <span data-ttu-id="60757-169">Name: adatum.biz DNS ゾーンの hybridvoice</span><span class="sxs-lookup"><span data-stu-id="60757-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="60757-170">ターゲット: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="60757-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="60757-171">追加の仲介サーバー用の追加レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="60757-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="60757-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="60757-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="60757-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="60757-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="60757-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="60757-174">192.168.1.48</span></span>
    
     <span data-ttu-id="60757-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="60757-175">Seattle</span></span>
    
   - <span data-ttu-id="60757-176">「A」と入力します。</span><span class="sxs-lookup"><span data-stu-id="60757-176">Type A</span></span>
    
   - <span data-ttu-id="60757-177">Name: hybridvoice in adatum.biz DNS zone</span><span class="sxs-lookup"><span data-stu-id="60757-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="60757-178">ターゲット: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="60757-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="60757-179">追加の仲介サーバー用の追加レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="60757-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="60757-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="60757-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="60757-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="60757-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="60757-182">クライアントサブネットを適切なゾーンスコープに接続する DNS ポリシーを作成して、必要な DNS 解決を確保します。</span><span class="sxs-lookup"><span data-stu-id="60757-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="60757-183">この時点で、クライアントは hybridvoice.adatum.biz のアムステルダムサブネットからの DNS クエリを作成すると、192.168.1.45、192.168.1.46、192.168.1.47、192.168.1.48 の各アドレスが返されますが、同じクエリフォームがシアトルになっているクライアントは10.10.1.8、10.10.1.9、10.10.1.10 を返します。</span><span class="sxs-lookup"><span data-stu-id="60757-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="60757-184">CCE アプライアンスが更新された設定を取得していないように見える場合は、アプライアンスがリモート PowerShell 経由でテナントに接続できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="60757-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="60757-185">リモート PowerShell を使用して、CsHybridPSTNAppliance でアプライアンスの状態を確認したり、CCE ホストで PowerShell を使用して、CcApplianceStatus を使用して状態を確認したりできます。</span><span class="sxs-lookup"><span data-stu-id="60757-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="60757-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="60757-186">See also</span></span>
<span data-ttu-id="60757-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="60757-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="60757-188">Cloud Connector エディションでのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="60757-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
