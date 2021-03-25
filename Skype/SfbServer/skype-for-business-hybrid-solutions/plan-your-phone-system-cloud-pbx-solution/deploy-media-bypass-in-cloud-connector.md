---
title: Cloud Connector Edition でのメディア バイパスの展開
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
description: このトピックでは、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを展開する手順について説明します。
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119366"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="16e1f-103">Cloud Connector Edition でのメディア バイパスの展開</span><span class="sxs-lookup"><span data-stu-id="16e1f-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="16e1f-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="16e1f-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="16e1f-106">このトピックでは、Cloud Connector Edition バージョン 2.0 以降でメディア バイパスを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="16e1f-107">メディア バイパスを使用すると、クライアントはパブリック 交換電話網 (PSTN) ネクスト ホップ (ゲートウェイまたはセッション ボーダー コントローラー (SBC)) にメディアを直接送信し、メディア パスから Cloud Connector Edition コンポーネントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="16e1f-108">「Cloud [Connector Edition でメディア バイパスを計画する」も参照してください](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="16e1f-109">メディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="16e1f-109">Enable media bypass</span></span>

<span data-ttu-id="16e1f-110">メディア バイパスを有効にするには、メディア バイパス Web サービスの DNS 名を構成し、テナント構成でメディア バイパスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="16e1f-111">メディア バイパス Web サービスは、すべての仲介サーバーに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="16e1f-112">テナント管理者は、ハイブリッド 音声サービス (サイト) の名前を選択する必要があります。この名前は、ハイブリッド音声用に登録された SIP ドメインからの名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="16e1f-113">サービス名は、クライアントの場所に関係なく、すべてのクラウド コネクタ アプライアンスとすべての PSTN サイトで同じにします。</span><span class="sxs-lookup"><span data-stu-id="16e1f-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="16e1f-114">Web サービスは、ネットワーク上でのみ内部的に利用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="16e1f-115">テナント管理者は、内部実稼働 Active Directory で DNS A レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="16e1f-116">複雑なマルチサイト環境がある場合は、「例: 複雑なマルチサイト環境でのメディア バイパス Web サイト DNS レコード」の例 [を参照してください](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="16e1f-117">DNS レコードは、内部ネットワーク クライアントでのみ解決する必要があります。外部ネットワーク クライアントでは解決されません。</span><span class="sxs-lookup"><span data-stu-id="16e1f-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="16e1f-118">DNS を構成したら、Skype for Business Administrator 資格情報を使用してリモート PowerShell を使用して Skype for Business Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="16e1f-119">詳細については、「コンピューターの[セットアップ」を参照Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="16e1f-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="16e1f-120">PowerShell セッションで、次のコマンドを入力してメディア バイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="16e1f-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="16e1f-121">メディア バイパスの有効化は、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="16e1f-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="16e1f-122">新New-CsNetworkMediaコマンドレットは、新しい構成を直ちに保存しない。メモリ内に設定が作成されるのみです。</span><span class="sxs-lookup"><span data-stu-id="16e1f-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="16e1f-123">このコマンドレットによって作成されたオブジェクトを変数に保存し、ネットワーク構成の MediaBypassSettings プロパティに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="16e1f-124">詳細については、「例: 複雑なマルチサイト環境でのメディア バイパス Web サイト [DNS レコード」を参照してください](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="16e1f-125">オンプレミスコンポーネントとオンライン コンポーネント間のレプリケーションには最大 24 時間かかる場合があります。そのため、ユーザーを有効にする前に必要なコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="16e1f-126">メディア バイパス設定の確認</span><span class="sxs-lookup"><span data-stu-id="16e1f-126">Confirm media bypass settings</span></span>

<span data-ttu-id="16e1f-127">メディア バイパス設定は、次のように確認できます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="16e1f-128">テナント プールへのオンライン レプリケーションを確認するには、リモート PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="16e1f-129">オンプレミスレプリケーションを確認するには、クラウド コネクタ仲介サーバーに接続し、PowerShell で次のコマンドを実行し、Enabled=True と AlwaysBypass=True を確認します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="16e1f-130">クライアント設定を確認するには、Skype for Business クライアントからサインアウトし、サインインし、クライアントがサービス URL を次のように受信したと確認します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="16e1f-131">%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog を開きます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="16e1f-132">hybridconfigserviceinternalurl を検索し、URL が定義した URL と一致する内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="16e1f-133">メディア バイパス パラメーターの変更</span><span class="sxs-lookup"><span data-stu-id="16e1f-133">Change media bypass parameters</span></span>

<span data-ttu-id="16e1f-134">テナント管理者は、次のコマンドレットを実行して Web サービスの DNS 名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="16e1f-135">クライアントは、新しいサービス名を取得し、変更を認識するためにサインアウトしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="16e1f-136">メディア バイパスを一時的に無効にする</span><span class="sxs-lookup"><span data-stu-id="16e1f-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="16e1f-137">このシナリオは、トラブルシューティングやメンテナンスに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="16e1f-138">サービスを無効にするには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="16e1f-139">変更を行った後、変更がすべてのクラウド コネクタにレプリケートされるのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="16e1f-140">レプリケーションの状態を確認するには、クラウド コネクタ 仲介サーバーの PowerShell で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="16e1f-141">変更がレプリケートされた後、仲介サーバー上の Web サービスは、メディア バイパス サービスに対するクライアント要求の拒否を開始します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="16e1f-142">メディア バイパスを完全に無効にする</span><span class="sxs-lookup"><span data-stu-id="16e1f-142">Disable media bypass permanently</span></span>

<span data-ttu-id="16e1f-143">メディア バイパスを完全に無効にするには、テナント管理者が次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="16e1f-144">管理者は、内部 DNS サーバーからメディア バイパス用の Web アドレスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="16e1f-145">変更を行った後、変更がすべての Cloud Connector アプライアンスにレプリケートされるのに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="16e1f-146">例: 複雑な複数サイト環境でのメディア バイパス Web サイト DNS レコード</span><span class="sxs-lookup"><span data-stu-id="16e1f-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="16e1f-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="16e1f-147"><a name="Example"> </a></span></span>

<span data-ttu-id="16e1f-148">クライアントは、内部 DNS サーバーからメディア バイパス Web サービスの Web アドレスを受信します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="16e1f-149">Web サービスの名前は、すべてのクラウド コネクタ アプライアンスとクラウド コネクタ PSTN サイトで同じになります。</span><span class="sxs-lookup"><span data-stu-id="16e1f-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="16e1f-150">複雑なマルチサイト環境では、Geo-Location ベースのトラフィック管理に Windows 2016 DNS ポリシーを使用することをお勧めします。そのため、クライアントはネットワークのローカルである Web サービスにリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="16e1f-151">Windows 2016 DNS ポリシーの詳細については、「Use DNS Policy for Geo-Location ベースのトラフィック管理とプライマリ サーバー」 [を参照してください](/windows-server/networking/dns/deploy/primary-geo-location)。</span><span class="sxs-lookup"><span data-stu-id="16e1f-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="16e1f-152">次に、Windows 2016 DNS ポリシーを使用して複数のサイトを使用する企業の構成例を示Geo-Location示します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="16e1f-153">バイパス サービスの名前は 'hybridvoice.adatum.biz' です。</span><span class="sxs-lookup"><span data-stu-id="16e1f-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="16e1f-154">アムステルダムのサイトには、次の仲介サーバー IP アドレスを使用して 4 つのクラウド コネクタ アプライアンスが展開されています。</span><span class="sxs-lookup"><span data-stu-id="16e1f-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="16e1f-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="16e1f-155">192.168.1.45</span></span>
    
- <span data-ttu-id="16e1f-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="16e1f-156">192.168.1.46</span></span>
    
- <span data-ttu-id="16e1f-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="16e1f-157">192.168.1.47</span></span>
    
- <span data-ttu-id="16e1f-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="16e1f-158">192.168.1.48</span></span>
    
<span data-ttu-id="16e1f-159">シアトルのサイトには、次の仲介サーバー IP アドレスを使用して 3 つのクラウド コネクタ アプライアンスが展開されています。</span><span class="sxs-lookup"><span data-stu-id="16e1f-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="16e1f-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="16e1f-160">10.10.1.8</span></span>
    
- <span data-ttu-id="16e1f-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="16e1f-161">10.10.1.9</span></span>
    
- <span data-ttu-id="16e1f-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="16e1f-162">10.10.1.10</span></span>
    
<span data-ttu-id="16e1f-163">このGeo-Locationベースのトラフィック管理を使用して、DNS サーバーは次のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="16e1f-164">アムステルダムとシアトルの両方のサブネットの DNS クライアント サブネットを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="16e1f-165">アムステルダムとシアトルの両方 adatum.biz DNS ゾーン スコープを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="16e1f-166">各 DNS ゾーン スコープに DNS レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="16e1f-167">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="16e1f-167">Amsterdam</span></span>
    
   - <span data-ttu-id="16e1f-168">タイプ A;</span><span class="sxs-lookup"><span data-stu-id="16e1f-168">Type A;</span></span>
    
   - <span data-ttu-id="16e1f-169">名前 : DNS ゾーンの adatum.biz 設定</span><span class="sxs-lookup"><span data-stu-id="16e1f-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="16e1f-170">ターゲット: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="16e1f-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="16e1f-171">追加の仲介サーバーの追加レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="16e1f-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="16e1f-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="16e1f-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="16e1f-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="16e1f-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="16e1f-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="16e1f-174">192.168.1.48</span></span>
    
     <span data-ttu-id="16e1f-175">シアトル</span><span class="sxs-lookup"><span data-stu-id="16e1f-175">Seattle</span></span>
    
   - <span data-ttu-id="16e1f-176">タイプ A</span><span class="sxs-lookup"><span data-stu-id="16e1f-176">Type A</span></span>
    
   - <span data-ttu-id="16e1f-177">名前 : DNS ゾーン adatum.biz ハイブリッド</span><span class="sxs-lookup"><span data-stu-id="16e1f-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="16e1f-178">ターゲット: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="16e1f-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="16e1f-179">追加の仲介サーバーの追加レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="16e1f-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="16e1f-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="16e1f-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="16e1f-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="16e1f-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="16e1f-182">クライアント サブネットを適切なゾーン スコープに接続する DNS ポリシーを作成して、必要な DNS 解決を確実に行います。</span><span class="sxs-lookup"><span data-stu-id="16e1f-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="16e1f-183">この時点で、アムステルダムのサブネットから dns クエリを実行するクライアントは、hybridvoice.adatum.biz 192.168.1.45 を返します。 192.168.1.46、192.168.1.47、192.168.1.47 アドレス、192.168.1.48 アドレス、同じクエリ フォームを作成するクライアントは、10.10.1.8、10.10.1.9、10.10.1.10 を返します。</span><span class="sxs-lookup"><span data-stu-id="16e1f-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="16e1f-184">CCE アプライアンスが更新された設定を取得していないと思われる場合は、アプライアンスがリモート PowerShell を介してテナントに連絡できるのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="16e1f-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="16e1f-185">リモート PowerShell を使用して、Get-CsHybridPSTNAppliance でアプライアンスの状態を確認したり、CCE ホストで PowerShell を使用して Get-CcApplianceStatus で状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="16e1f-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="16e1f-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="16e1f-186">See also</span></span>
<span data-ttu-id="16e1f-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="16e1f-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="16e1f-188">Cloud Connector エディションでのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="16e1f-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)