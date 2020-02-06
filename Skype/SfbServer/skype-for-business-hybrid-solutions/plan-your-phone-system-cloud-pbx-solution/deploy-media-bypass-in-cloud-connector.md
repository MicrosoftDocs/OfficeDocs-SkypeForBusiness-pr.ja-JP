---
title: Cloud Connector エディションでメディア バイパスを展開する
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
description: このトピックでは、クラウドコネクタエディションバージョン2.0 以降でメディアのバイパスを展開する手順について説明します。
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802347"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="49b3d-103">Cloud Connector エディションでメディア バイパスを展開する</span><span class="sxs-lookup"><span data-stu-id="49b3d-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="49b3d-104">このトピックでは、クラウドコネクタエディションバージョン2.0 以降でメディアのバイパスを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="49b3d-105">メディアのバイパスを使用すると、クライアントは、公衆交換電話網 (PSTN) の次ホップ (ゲートウェイまたはセッションボーダーコントローラー (SBC)) にメディアを直接送信し、メディアパスからクラウドコネクタエディションコンポーネントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="49b3d-106">「[クラウドコネクタエディションでのメディアバイパスの計画](plan-for-media-bypass-in-cloud-connector-edition.md)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49b3d-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="49b3d-107">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="49b3d-107">Enable media bypass</span></span>

<span data-ttu-id="49b3d-108">メディアバイパスを有効にするには、メディアバイパス web サービスの DNS 名を構成し、テナント構成でメディアバイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="49b3d-109">メディアバイパスの web サービスは、すべての仲介サーバーで自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="49b3d-110">テナント管理者は、ハイブリッドボイスサービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッドボイスに登録されている SIP ドメインから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="49b3d-111">サービス名は、クライアントの場所に関係なく、すべてのクラウドコネクタのアプライアンスとすべての PSTN サイトで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="49b3d-112">Web サービスは、ネットワーク上でのみ利用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="49b3d-113">テナント管理者は、内部の運用 Active Directory で DNS A レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="49b3d-114">複雑なマルチサイト環境がある場合は、「[複雑なマルチサイト環境での web サイトの DNS レコードのバイパス](deploy-media-bypass-in-cloud-connector.md#Example)」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b3d-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="49b3d-115">DNS レコードは、内部ネットワーククライアントに対してのみ解決されます。外部ネットワーククライアントに対しては解決されません。</span><span class="sxs-lookup"><span data-stu-id="49b3d-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="49b3d-116">DNS を構成したら、Skype for Business 管理者の資格情報で リモート PowerShell を使用して、Skype for Business Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="49b3d-117">詳細については、「 [Windows PowerShell 用にコンピューターをセットアップする](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b3d-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="49b3d-118">PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="49b3d-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="49b3d-119">メディアのバイパスを有効にするには、2つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="49b3d-120">新しい-CsNetworkMedia コマンドレットでは、新しい構成はすぐに保存されません。メモリ内の設定のみを作成します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="49b3d-121">このコマンドレットによって作成されたオブジェクトは、変数に保存してから、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="49b3d-122">詳細については、「[例: 複雑なマルチサイト環境での web サイトの DNS レコードのバイパス](deploy-media-bypass-in-cloud-connector.md#Example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b3d-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="49b3d-123">オンプレミスとオンライン コンポーネント間のレプリケーションには最長で 24 時間かかります。したがって、ユーザーを有効化する前に必要なコマンドを実行しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49b3d-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="49b3d-124">メディア バイパス設定を確認する</span><span class="sxs-lookup"><span data-stu-id="49b3d-124">Confirm media bypass settings</span></span>

<span data-ttu-id="49b3d-125">メディア バイパス設定は次の方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="49b3d-126">テナントプールへのオンラインレプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="49b3d-127">オンプレミスのレプリケーションを確認するには、クラウドコネクタの仲介サーバーに接続し、PowerShell で次のコマンドを実行し、有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="49b3d-128">クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、もう一度サインインして、クライアントが次のようにサービス URL を受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="49b3d-129">%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="49b3d-130">hybridconfigserviceinternalurl を探して、定義した URL とそこに表示されている URL が一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="49b3d-131">メディア バイパス パラメータを変更する</span><span class="sxs-lookup"><span data-stu-id="49b3d-131">Change media bypass parameters</span></span>

<span data-ttu-id="49b3d-132">テナント管理者は、次のコマンドレットを実行して、Web サービスの DNS 名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="49b3d-133">クライアントは、一度サインアウトしてから再びサインインし、新しいサービス名を入手することで、変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="49b3d-134">メディア バイパスを一時的に無効にする</span><span class="sxs-lookup"><span data-stu-id="49b3d-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="49b3d-p106">このシナリオは、トラブルシューティングやメンテナンスで役立ちます。サービスを無効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="49b3d-137">変更後、すべての Cloud Connector にレプリケートされるまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="49b3d-138">レプリケーションの状態を確認するには、クラウドコネクタ仲介サーバー上の PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="49b3d-139">変更がレプリケートされると、仲介サーバーの Web サービスにより、メディア バイパス サービスに対するクライアント要求の拒否が開始されます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="49b3d-140">メディア バイパスを完全に無効にする</span><span class="sxs-lookup"><span data-stu-id="49b3d-140">Disable media bypass permanently</span></span>

<span data-ttu-id="49b3d-141">メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="49b3d-142">さらに、管理者は内部 DNS サーバーからメディア バイパスの Web アドレスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="49b3d-143">変更を行った後は、変更がすべてのクラウドコネクタのアプライアンスに複製されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="49b3d-144">例: 複雑なマルチサイト環境でのメディア バイパス Web サイトの DNS レコード</span><span class="sxs-lookup"><span data-stu-id="49b3d-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="49b3d-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="49b3d-145"><a name="Example"> </a></span></span>

<span data-ttu-id="49b3d-146">クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="49b3d-147">Web サービスの名前は、すべてのクラウドコネクタのアプライアンスとクラウドコネクタの PSTN サイトで同じになります。</span><span class="sxs-lookup"><span data-stu-id="49b3d-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="49b3d-148">複雑なマルチサイト環境では、地理的な場所ベースのトラフィック管理用の Windows 2016 DNS ポリシーを使用して、クライアントのネットワークにおいてローカルな Web サービスにクライアントをリダイレクトできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49b3d-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="49b3d-149">Windows 2016 DNS ポリシーの詳細については、「[プライマリサーバーを使用した地理的な場所に基づくトラフィック管理に DNS ポリシーを使用する](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b3d-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="49b3d-150">地理的な場所ベースのトラフィック管理の Windows 2016 DNS ポリシーを使用して、複数のサイトを持つ会社の構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="49b3d-151">バイパスサービスの名前は ' hybridvoice.adatum.biz ' です。</span><span class="sxs-lookup"><span data-stu-id="49b3d-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="49b3d-152">アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して、4つのクラウドコネクタのアプライアンスが展開されています。</span><span class="sxs-lookup"><span data-stu-id="49b3d-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="49b3d-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="49b3d-153">192.168.1.45</span></span>
    
- <span data-ttu-id="49b3d-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="49b3d-154">192.168.1.46</span></span>
    
- <span data-ttu-id="49b3d-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="49b3d-155">192.168.1.47</span></span>
    
- <span data-ttu-id="49b3d-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="49b3d-156">192.168.1.48</span></span>
    
<span data-ttu-id="49b3d-157">シアトルのサイトには、次の仲介サーバー IP アドレスを使用して展開された、3つのクラウドコネクタのアプライアンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49b3d-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="49b3d-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="49b3d-158">10.10.1.8</span></span>
    
- <span data-ttu-id="49b3d-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="49b3d-159">10.10.1.9</span></span>
    
- <span data-ttu-id="49b3d-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="49b3d-160">10.10.1.10</span></span>
    
<span data-ttu-id="49b3d-161">地理的な場所ベースのトラフィック管理を使用する場合は、次の手順で DNS サーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="49b3d-162">アムステルダムとシアトルのサブネットに対する DNS クライアント サブネットを作成します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="49b3d-163">アムステルダムとシアトルの adatum.biz の DNS ゾーン範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="49b3d-164">それぞれの DNS ゾーン範囲で DNS レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="49b3d-165">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="49b3d-165">Amsterdam</span></span>
    
   - <span data-ttu-id="49b3d-166">タイプ A</span><span class="sxs-lookup"><span data-stu-id="49b3d-166">Type A;</span></span>
    
   - <span data-ttu-id="49b3d-167">名前: adatum.biz DNS ゾーンの hybridvoice</span><span class="sxs-lookup"><span data-stu-id="49b3d-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="49b3d-168">ターゲット: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="49b3d-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="49b3d-169">追加の仲介サーバーについてレコードを作成する</span><span class="sxs-lookup"><span data-stu-id="49b3d-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="49b3d-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="49b3d-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="49b3d-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="49b3d-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="49b3d-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="49b3d-172">192.168.1.48</span></span>
    
     <span data-ttu-id="49b3d-173">調布市調布ヶ丘</span><span class="sxs-lookup"><span data-stu-id="49b3d-173">Seattle</span></span>
    
   - <span data-ttu-id="49b3d-174">タイプ A</span><span class="sxs-lookup"><span data-stu-id="49b3d-174">Type A</span></span>
    
   - <span data-ttu-id="49b3d-175">名前: adatum.biz DNS ゾーンの hybridvoice</span><span class="sxs-lookup"><span data-stu-id="49b3d-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="49b3d-176">ターゲット: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="49b3d-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="49b3d-177">追加の仲介サーバーについてレコードを作成する</span><span class="sxs-lookup"><span data-stu-id="49b3d-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="49b3d-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="49b3d-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="49b3d-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="49b3d-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="49b3d-180">クライアント サブネットを適切なゾーン範囲に接続する DNS ポリシーを作成して、DNS が確実に解決されるようにします。</span><span class="sxs-lookup"><span data-stu-id="49b3d-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="49b3d-181">この時点では、hybridvoice.adatum.biz のアムステルダムのサブネットから DNS クエリーを実行しているクライアントは 192.168.1.45、192.168.1.46、192.168.1.47、192.168.1.48 のアドレスを返します。その一方で、シアトルから同様のクエリーを実行しているクライアントは 10.10.1.8、10.10.1.9、10.10.1.10 を返します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="49b3d-182">CCE アプライアンスが更新された設定になっていないように見える場合は、アプライアンスがリモート PowerShell 経由でテナントに接続できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="49b3d-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="49b3d-183">リモート PowerShell を使用して、CsHybridPSTNAppliance でアプライアンスの状態を確認するか、または CCE ホストの PowerShell を使用して、CcApplianceStatus を使って状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="49b3d-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="49b3d-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="49b3d-184">See also</span></span>
<span data-ttu-id="49b3d-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="49b3d-185"><a name="Example"> </a></span></span>

[<span data-ttu-id="49b3d-186">Cloud Connector エディションでのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="49b3d-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
