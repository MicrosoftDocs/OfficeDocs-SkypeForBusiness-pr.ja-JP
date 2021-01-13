---
title: Skype for Business Server での場所の決定に使用するネットワーク要素を定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所に発信者をマップするために使用するネットワーク コンポーネントを計画するために必要な決定。
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813637"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="b237f-103">Skype for Business Server での場所の決定に使用するネットワーク要素を定義する</span><span class="sxs-lookup"><span data-stu-id="b237f-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="b237f-104">Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所に発信者をマップするために使用するネットワーク コンポーネントを計画するために必要な決定。</span><span class="sxs-lookup"><span data-stu-id="b237f-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b237f-105">Skype for Business Server インフラストラクチャをセットアップしてクライアントの場所の自動検出をサポートする場合は、発信者を場所にマップするために使用するネットワーク要素を最初に決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="b237f-106">Skype for Business Server では、次のレイヤー 2 およびレイヤー 3 のネットワーク要素を場所に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="b237f-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="b237f-107">ワイヤレス アクセス ポイント (WAP) の BSSID (Basic Service Set Identification) アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="b237f-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="b237f-108">LLDP スイッチ ポート (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="b237f-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="b237f-109">LLDP スイッチ シャーシ ID (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="b237f-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="b237f-110">IP サブネット (レイヤー 3)</span><span class="sxs-lookup"><span data-stu-id="b237f-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="b237f-111">クライアント MAC アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="b237f-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="b237f-112">これらのネットワーク要素は、優先順位の高い順に記されています。</span><span class="sxs-lookup"><span data-stu-id="b237f-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="b237f-113">複数のネットワーク要素を使用してクライアントを見つけできる場合、Skype for Business Server は優先順位を使用して使用するメカニズムを決定します。</span><span class="sxs-lookup"><span data-stu-id="b237f-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="b237f-114">以下のセクションでは、各ネットワーク要素を使用する方法の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="b237f-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b237f-115">ネットワーク要素を使用して発信者を場所にマップする場合、場所情報サービス データベースを最新の状態に維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="b237f-116">ネットワーク要素を追加または変更する場合は (WAP の追加など)、場所データベースの古いエントリを削除して、新しいエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="b237f-117">ワイヤレス アクセス ポイント</span><span class="sxs-lookup"><span data-stu-id="b237f-117">Wireless Access Point</span></span>

<span data-ttu-id="b237f-118">クライアントがワイヤレスでネットワークに接続する場合、場所の要求では WAP の BSSID アドレスを使用してその場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="b237f-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="b237f-119">クライアントがローミングしている場合、示されている WAP が最も近い WAP ではない可能性があります。また、建物の別の階に位置する WAP を選択する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="b237f-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="b237f-120">場所が近似値として表示される場合は、場所の値の先頭に **[Near]** 記述子または **[Closeto] 記述子を追加** します。</span><span class="sxs-lookup"><span data-stu-id="b237f-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="b237f-121">場所に関するこの方法では、各 WAP の BSSID が静的なものであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b237f-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="b237f-122">ただし、WAP ベンダーが動的に割り当てられた BSSID を使用している場合は、WAP から取得した BSSID が変更される可能性があります (WAP 構成の変更後にこの問題が発生する可能性があります)、ワイヤレス クライアントが場所を受け取らない状況で放置される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="b237f-123">このような可能性を回避するには、各 WAP で使用される可能性のあるすべての BSSID アドレスの ERL を場所情報サービス データベースに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="b237f-124">LLDP ポートおよびスイッチ</span><span class="sxs-lookup"><span data-stu-id="b237f-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="b237f-p106">LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) をサポートしている管理されたイーサネット スイッチは、自らの ID とポート情報を LLDP-MED に準拠したクライアントにアドバタイズできます。さらにこうしたクライアントは、デバイスの場所を提供するために場所データベースに対して照会できます。ERL はスイッチ シャーシ ID に対してのみ関連付けることも、ポート レベルにまで詳細に記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="b237f-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b237f-127">Skype for Business Server では、Lync Phone Edition デバイスおよび Skype for Business クライアントの場所を特定するための LLDP-MED の使用がサポートWindows 8。</span><span class="sxs-lookup"><span data-stu-id="b237f-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="b237f-128">スイッチレベルのレイヤー 2 データを使用して、他の有線 PC ベースの Skype for Business Server クライアントの場所を特定する必要がある場合は、クライアント MAC アドレス方式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="b237f-129">Subnet</span><span class="sxs-lookup"><span data-stu-id="b237f-129">Subnet</span></span>

<span data-ttu-id="b237f-130">レイヤー 3 IP サブネットは、クライアントの場所を自動的に検出するために使用できるすべての Skype for Business Server クライアントでサポートされるメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="b237f-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="b237f-131">IP サブネットの使用は有線クライアントを構成および管理する最も簡単な場所特定の方法です。</span><span class="sxs-lookup"><span data-stu-id="b237f-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="b237f-132">ただし、サブネットの使用を決定する前に、以下の質問を参考にして、サブネットの場所の特異性がクライアントを正確に特定するうえで十分に細かいかどうかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="b237f-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="b237f-133">1 つ以上のクライアント サブネットで複数の階をカバーしていますか。</span><span class="sxs-lookup"><span data-stu-id="b237f-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="b237f-134">1 つ以上のサブネットで複数の建物をカバーしていますか。</span><span class="sxs-lookup"><span data-stu-id="b237f-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="b237f-135">どれほどのフロア領域が各クライアント サブネットでカバーされていますか。</span><span class="sxs-lookup"><span data-stu-id="b237f-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="b237f-p109">サブネットでカバーする領域が広すぎる場合は、別のメカニズムを使用したクライアントの特定が必要になることがあります。ただし、たとえ実用的であったとしても、サードパーティによる SNMP ベースのソリューションの費用と複雑さを受け入れるよりは、ERL の場所の特異性に関する要件を満たすように顧客が自らの IP サブネット処理を再編成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b237f-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="b237f-138">クライアント MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="b237f-138">Client MAC Address</span></span>

<span data-ttu-id="b237f-139">クライアント コンピューターの MAC アドレスを使用して発信者を見つけるには、管理されたイーサネット スイッチが必要です。また、これらのスイッチに接続されている (または経由して) Skype for Business クライアントの MAC アドレスを検出できるサードパーティ製の SNMP ソリューションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b237f-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="b237f-140">こうした SNMP ソリューションは、管理されたスイッチの継続的なポーリングによって各ポートに接続されているエンドポイント MAC アドレスの現在のマッピングを取得し、対応するポート ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="b237f-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="b237f-141">場所情報サービスに対する Skype for Business クライアントの要求時に、場所情報サービスは、クライアントの MAC アドレスを使用してサードパーティ アプリケーションに照会し、一致するスイッチ IP アドレスとポート ID を返します。</span><span class="sxs-lookup"><span data-stu-id="b237f-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="b237f-142">場所情報サービスは、この情報を使用して、公開されたレイヤー 2 ワイヤーマップに一致するレコードを照会し、その場所をクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="b237f-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="b237f-143">このオプションを使用する場合は、SNMP アプリケーションと公開されている場所データベースのレコードの間でスイッチ ポート ID の整合が取れていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b237f-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b237f-144">一部のサード パーティ製 SNMP ソリューションでは、アンマネージ アクセス スイッチをサポートできます。Skype for Business クライアントをサービスするスイッチが管理されていないが、管理された配布スイッチに対するアップリンクがある場合、管理スイッチは、アクセス スイッチに接続されているクライアントの MAC アドレスを SNMP アプリケーションに報告できます。</span><span class="sxs-lookup"><span data-stu-id="b237f-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="b237f-145">この情報により、場所情報サービスはユーザーの場所を識別できます。</span><span class="sxs-lookup"><span data-stu-id="b237f-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="b237f-146">ただし、管理されていないスイッチ上のすべてのポートに 1 つの ERL のみを割り当て可能なので、場所の特定性はアクセス スイッチのシャーシ レベルでのみ使用できます。ポート レベルでは割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="b237f-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

