---
title: Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: 意思決定されるネットワーク ・ コンポーネントを計画するために必要なビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 の配置の場所に呼び出し元のマップに使用します。
ms.openlocfilehash: 4cab36efdf0f4bcfbf3834e9c077558610655e3a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206579"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a><span data-ttu-id="21df9-103">Skype ビジネス サーバーの場所を決定するためのネットワーク要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="21df9-103">Define the network elements used to determine location in Skype for Business Server</span></span>
 
<span data-ttu-id="21df9-104">意思決定されるネットワーク ・ コンポーネントを計画するために必要なビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 の配置の場所に呼び出し元のマップに使用します。</span><span class="sxs-lookup"><span data-stu-id="21df9-104">Decisions necessary for planning which network components you will use to map callers to locations for E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="21df9-105">最初ネットワークを決定する必要がある場合は、Skype は、クライアントの自動位置検出をサポートするためにビジネスのサーバー インフラストラクチャのセットアップは、要素を使用して呼び出し元の場所にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="21df9-105">If you are setting up your Skype for Business Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="21df9-106">ビジネス サーバーの Skype は、場所を使用した次のレイヤー 2 およびレイヤー 3 のネットワーク要素を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="21df9-106">In Skype for Business Server, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>
  
- <span data-ttu-id="21df9-107">ワイヤレス アクセス ポイント (WAP) の BSSID (Basic Service Set Identification) アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="21df9-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>
    
- <span data-ttu-id="21df9-108">LLDP スイッチ ポート (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="21df9-108">LLDP switch port (Layer 2)</span></span>
    
- <span data-ttu-id="21df9-109">LLDP スイッチ シャーシ ID (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="21df9-109">LLDP switch chassis IDs (Layer 2)</span></span>
    
- <span data-ttu-id="21df9-110">IP サブネット (レイヤー 3)</span><span class="sxs-lookup"><span data-stu-id="21df9-110">IP subnets (Layer 3)</span></span>
    
- <span data-ttu-id="21df9-111">クライアント MAC アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="21df9-111">Client MAC addresses (Layer 2)</span></span>
    
<span data-ttu-id="21df9-112">これらのネットワーク要素は、優先順位の高い順に記されています。</span><span class="sxs-lookup"><span data-stu-id="21df9-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="21df9-113">クライアントを検索できるようにするには、複数のネットワーク要素を使用して、Skype のビジネス サーバーはどのメカニズムを使用するのにを決定するのにの優先順位を使用します。</span><span class="sxs-lookup"><span data-stu-id="21df9-113">If a client can be located by using more than one network element, Skype for Business Server uses the order of precedence to determine which mechanism to use.</span></span> 
  
<span data-ttu-id="21df9-114">以下のセクションでは、各ネットワーク要素を使用する方法の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="21df9-114">The following sections provide more details for using each network element.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="21df9-115">ネットワーク要素を使用して、呼び出し元の場所にマップするのには、ことが最も重要であることを最新の位置情報サービスのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="21df9-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="21df9-116">ネットワーク要素を追加または変更する場合は (WAP の追加など)、場所データベースの古いエントリを削除して、新しいエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21df9-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span> 
  
## <a name="wireless-access-point"></a><span data-ttu-id="21df9-117">ワイヤレス アクセス ポイント</span><span class="sxs-lookup"><span data-stu-id="21df9-117">Wireless Access Point</span></span>

<span data-ttu-id="21df9-118">クライアントがワイヤレスでネットワークに接続する場合、場所の要求では WAP の BSSID アドレスを使用してその場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="21df9-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="21df9-119">クライアントを移動すると、示されている WAP に最も近いもの、できない場合があります、その建物の異なるフロアにある WAP を選択することも。</span><span class="sxs-lookup"><span data-stu-id="21df9-119">If the client is roaming, the WAP indicated may not be the closest one, and it's even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="21df9-120">場所が概算であることを示す、 **[近く]** 、または **[閉じる]** の記述子を使用して場所の値を先頭に追加できます。</span><span class="sxs-lookup"><span data-stu-id="21df9-120">To indicate that the location is approximate, you can prepend the location value with a **[Near]** or **[Closeto]** descriptor.</span></span>
  
<span data-ttu-id="21df9-121">場所に関するこの方法では、各 WAP の BSSID が静的なものであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="21df9-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="21df9-122">ただし、WAP の製造元に問い合わせては、動的に割り当てられた Bssid を使用する場合 WAP から取得される BSSID を変更 (これは、WAP の構成の変更の発生後)、およびワイヤレス クライアントのままになって、場所を受け取っていない場合。</span><span class="sxs-lookup"><span data-stu-id="21df9-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don't receive a location.</span></span> <span data-ttu-id="21df9-123">この可能性を防ぐためには、各 WAP で使用される、使用可能なすべての BSSID アドレスの ERLs に場所情報サービス データベースを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21df9-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span> 
  
## <a name="lldp-ports-and-switches"></a><span data-ttu-id="21df9-124">LLDP ポートおよびスイッチ</span><span class="sxs-lookup"><span data-stu-id="21df9-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="21df9-p106">LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) をサポートしている管理されたイーサネット スイッチは、自らの ID とポート情報を LLDP-MED に準拠したクライアントにアドバタイズできます。さらにこうしたクライアントは、デバイスの場所を提供するために場所データベースに対して照会できます。ERL はスイッチ シャーシ ID に対してのみ関連付けることも、ポート レベルにまで詳細に記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="21df9-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21df9-127">ビジネス サーバーの Skype では、LLDP-(中) を使用して Windows 8 で実行されているビジネス クライアント用の Lync の電話のエディションのデバイスと Skype のだけ場所を決定するためサポートしています。</span><span class="sxs-lookup"><span data-stu-id="21df9-127">Skype for Business Server supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Skype for Business clients running on Windows 8.</span></span> <span data-ttu-id="21df9-128">スイッチ ・ レベルのレイヤー 2 のデータを使用してビジネス サーバーのクライアントの他の有線の PC ベースの Skype の場所を確認する場合は、クライアントの MAC アドレスのメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21df9-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Skype for Business Server clients, you need to use the client MAC address method.</span></span> 
  
## <a name="subnet"></a><span data-ttu-id="21df9-129">サブネット</span><span class="sxs-lookup"><span data-stu-id="21df9-129">Subnet</span></span>

<span data-ttu-id="21df9-130">レイヤー 3 の IP サブネットは、クライアントの場所を自動的に検出するために使用できるビジネス サーバーのクライアントのすべての Skype でサポートされているメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="21df9-130">Layer 3 IP subnets provide a mechanism supported by all Skype for Business Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="21df9-131">IP サブネットの使用は有線クライアントを構成および管理する最も簡単な場所特定の方法です。</span><span class="sxs-lookup"><span data-stu-id="21df9-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="21df9-132">ただし、サブネットの使用を決定する前に、以下の質問を参考にして、サブネットの場所の特異性がクライアントを正確に特定するうえで十分に細かいかどうかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="21df9-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>
  
- <span data-ttu-id="21df9-133">1 つ以上のクライアント サブネットで複数の階をカバーしていますか?</span><span class="sxs-lookup"><span data-stu-id="21df9-133">Do one or more client subnets cover multiple floors?</span></span>
    
- <span data-ttu-id="21df9-134">1 つ以上のサブネットで複数の建物をカバーしていますか?</span><span class="sxs-lookup"><span data-stu-id="21df9-134">Do one or more subnets cover more than one building?</span></span>
    
- <span data-ttu-id="21df9-135">どれほどのフロア領域が各クライアント サブネットでカバーされていますか?</span><span class="sxs-lookup"><span data-stu-id="21df9-135">How much floor space is covered by each client subnet?</span></span>
    
<span data-ttu-id="21df9-p109">サブネットでカバーする領域が広すぎる場合は、別のメカニズムを使用したクライアントの特定が必要になることがあります。ただし、たとえ実用的であったとしても、サードパーティによる SNMP ベースのソリューションの費用と複雑さを受け入れるよりは、ERL の場所の特異性に関する要件を満たすように顧客が自らの IP サブネット処理を再編成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21df9-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>
  
## <a name="client-mac-address"></a><span data-ttu-id="21df9-138">クライアント MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="21df9-138">Client MAC Address</span></span>

<span data-ttu-id="21df9-139">呼び出し元を検索するのにはクライアント コンピューターの MAC アドレスを使用する必要があります管理されたイーサネット スイッチ、およびビジネスのクライアントまたは接続されている () の Skype の MAC アドレスを検出することができるサードパーティ製の SNMP ソリューションを展開する必要がありますこれらのスイッチです。</span><span class="sxs-lookup"><span data-stu-id="21df9-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Skype for Business clients connected to (or through) those switches.</span></span> <span data-ttu-id="21df9-140">こうした SNMP ソリューションは、管理されたスイッチの継続的なポーリングによって各ポートに接続されているエンドポイント MAC アドレスの現在のマッピングを取得し、対応するポート ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="21df9-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="21df9-141">ビジネス クライアントの要求を場所情報サービスの Skype、時に場所情報サービスはクライアントの MAC アドレスを使用してサード パーティ製アプリケーションに対してクエリを実行し、対応するスイッチの IP アドレスとポートの Id を返します。</span><span class="sxs-lookup"><span data-stu-id="21df9-141">During a Skype for Business client's request to the Location Information service, the Location Information service queries the third-party application by using the client's MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="21df9-142">場所情報サービスは、発行済みのレイヤー 2 wiremap の一致するレコードのクエリを実行するのにはこの情報を使用してし、場所をクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="21df9-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="21df9-143">このオプションを使用する場合は、SNMP アプリケーションと公開されている場所データベースのレコードの間でスイッチ ポート ID の整合が取れていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="21df9-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21df9-144">いくつかサードパーティ製の SNMP ソリューションで使用できるアンマネージ アクセス スイッチです。場合は、Skype のビジネスのクライアントを実行するスイッチでは、管理対象ではありませんが、配布の管理スイッチにアップリンクには、管理対象のスイッチ レポートを返すことを SNMP アプリケーション アクセス スイッチに接続されているクライアントの MAC アドレスです。</span><span class="sxs-lookup"><span data-stu-id="21df9-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Skype for Business client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="21df9-145">この情報は、ユーザーの場所を特定の位置情報サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21df9-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="21df9-146">ただし、場所の特異性は、ポート レベルではなく、アクセス スイッチのシャーシのレベルでのみ使用可能なため、アンマネージ スイッチの全ポートに ERL は 1 つのみを代入することができます。</span><span class="sxs-lookup"><span data-stu-id="21df9-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span> 
  

