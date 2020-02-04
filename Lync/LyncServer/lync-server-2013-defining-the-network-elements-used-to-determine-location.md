---
title: 'Lync Server 2013: 場所を決定するために使用するネットワーク要素を定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d71d222fd6784c32ecf0228fff2f33188d2afae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="586cc-102">Lync Server 2013 での場所の決定に使用するネットワーク要素の定義</span><span class="sxs-lookup"><span data-stu-id="586cc-102">Defining the network elements used to determine location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="586cc-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="586cc-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="586cc-104">クライアントの自動検出をサポートするように Lync Server インフラストラクチャをセットアップする場合、まず、発信者を場所にマップするために使用するネットワーク要素を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-104">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="586cc-105">Lync Server 2013 では、次のレイヤー2とレイヤー3のネットワーク要素を場所と関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="586cc-105">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="586cc-106">ワイヤレス アクセス ポイント (WAP) の BSSID (Basic Service Set Identification) アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="586cc-106">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="586cc-107">LLDP スイッチ ポート (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="586cc-107">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="586cc-108">LLDP スイッチ シャーシ ID (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="586cc-108">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="586cc-109">IP サブネット (レイヤー 3)</span><span class="sxs-lookup"><span data-stu-id="586cc-109">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="586cc-110">クライアント MAC アドレス (レイヤー 2)</span><span class="sxs-lookup"><span data-stu-id="586cc-110">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="586cc-111">これらのネットワーク要素は、優先順位の高い順に記されています。</span><span class="sxs-lookup"><span data-stu-id="586cc-111">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="586cc-112">複数のネットワーク要素を使用してクライアントを配置できる場合、Lync Server は優先順位に従って、どのメカニズムを使うかを決定します。</span><span class="sxs-lookup"><span data-stu-id="586cc-112">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="586cc-113">以下のセクションでは、各ネットワーク要素を使用する方法の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="586cc-113">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="586cc-114">ネットワーク要素を使って発信者を場所にマップする場合は、位置情報サービスデータベースを最新の状態に維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="586cc-114">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="586cc-115">ネットワーク要素を追加または変更する場合は (WAP の追加など)、場所データベースの古いエントリを削除して、新しいエントリを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-115">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="586cc-116">ワイヤレス アクセス ポイント</span><span class="sxs-lookup"><span data-stu-id="586cc-116">Wireless Access Point</span></span>

<span data-ttu-id="586cc-117">クライアントがワイヤレスでネットワークに接続する場合、場所の要求では WAP の BSSID アドレスを使用してその場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="586cc-117">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="586cc-118">クライアントがローミングしている場合は、示される WAP が最も近いものではない可能性があり、建物の別の階の WAP が選択される可能性さえあります。</span><span class="sxs-lookup"><span data-stu-id="586cc-118">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="586cc-119">場所がおおよその場所であることを示すには、場所の値の前に Near または Close to という記述子を追加します。</span><span class="sxs-lookup"><span data-stu-id="586cc-119">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="586cc-120">場所に関するこの方法では、各 WAP の BSSID が静的なものであることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="586cc-120">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="586cc-121">ただし、動的に割り当てられた BSSID を WAP ベンダーが使用している場合は、WAP から取得された BSSID が変化する可能性があり (こうした変化は WAP 構成の変更に引き続いて発生します)、ワイヤレス クライアントは場所の情報を受け取れない状況で放置される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-121">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="586cc-122">このような可能性を避けるために、各 WAP で使用されるすべての BSSID アドレスについて、場所情報サービスデータベースに ERLs を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-122">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="586cc-123">LLDP ポートおよびスイッチ</span><span class="sxs-lookup"><span data-stu-id="586cc-123">LLDP Ports and Switches</span></span>

<span data-ttu-id="586cc-p106">LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) をサポートしている管理されたイーサネット スイッチは、自らの ID とポート情報を LLDP-MED に準拠したクライアントにアドバタイズできます。さらにこうしたクライアントは、デバイスの場所を提供するために場所データベースに対して照会できます。ERL はスイッチ シャーシ ID に対してのみ関連付けることも、ポート レベルにまで詳細に記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="586cc-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="586cc-126">Lync Server 2013 は、Windows 8 で実行されている Lync Phone Edition デバイスと Lync 2013 のみを特定するために LLDP を使用しています。</span><span class="sxs-lookup"><span data-stu-id="586cc-126">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="586cc-127">他の有線 PC ベースの Lync クライアントの場所を特定するために、スイッチレベルレイヤー2のデータを使用する必要がある場合は、クライアントの MAC アドレス方式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-127">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="586cc-128">サブネット</span><span class="sxs-lookup"><span data-stu-id="586cc-128">Subnet</span></span>

<span data-ttu-id="586cc-129">レイヤー 3 IP サブネットは、すべての Lync Server クライアントでサポートされているメカニズムを提供します。これを使用すると、クライアントの場所を自動的に検出できます。</span><span class="sxs-lookup"><span data-stu-id="586cc-129">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="586cc-130">IP サブネットの使用は有線クライアントを構成および管理する最も簡単な場所特定の方法です。</span><span class="sxs-lookup"><span data-stu-id="586cc-130">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="586cc-131">ただし、サブネットの使用を決定する前に、以下の質問を参考にして、サブネットの場所の特異性がクライアントを正確に特定するうえで十分に細かいかどうかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="586cc-131">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="586cc-132">1 つ以上のクライアント サブネットで複数の階をカバーしていますか?</span><span class="sxs-lookup"><span data-stu-id="586cc-132">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="586cc-133">1 つ以上のサブネットで複数の建物をカバーしていますか?</span><span class="sxs-lookup"><span data-stu-id="586cc-133">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="586cc-134">どれほどのフロア領域が各クライアント サブネットでカバーされていますか?</span><span class="sxs-lookup"><span data-stu-id="586cc-134">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="586cc-p109">サブネットでカバーする領域が広すぎる場合は、別のメカニズムを使用したクライアントの特定が必要になることがあります。ただし、たとえ実用的であったとしても、サードパーティによる SNMP ベースのソリューションの費用と複雑さを受け入れるよりは、ERL の場所の特異性に関する要件を満たすように顧客が自らの IP サブネット処理を再編成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="586cc-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="586cc-137">クライアント MAC アドレス</span><span class="sxs-lookup"><span data-stu-id="586cc-137">Client MAC Address</span></span>

<span data-ttu-id="586cc-138">クライアントコンピューターの MAC アドレスを使って発信者を検索するには、管理されたイーサネットスイッチが必要です。また、これらのスイッチを接続 (または経由) している Lync クライアントの MAC アドレスを検出できるサードパーティの SNMP ソリューションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586cc-138">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="586cc-139">こうした SNMP ソリューションは、管理されたスイッチの継続的なポーリングによって各ポートに接続されているエンドポイント MAC アドレスの現在のマッピングを取得し、対応するポート ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="586cc-139">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="586cc-140">Lync クライアントの位置情報サービスへの要求中に、位置情報サービスは、クライアントの MAC アドレスを使ってサードパーティアプリケーションを照会し、一致するスイッチ IP アドレスとポート Id を返します。</span><span class="sxs-lookup"><span data-stu-id="586cc-140">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="586cc-141">位置情報サービスでは、この情報を使って、発行されたレイヤー 2 wiremap に一致するレコードを照会し、その場所をクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="586cc-141">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="586cc-142">このオプションを使用する場合は、SNMP アプリケーションと公開されている場所データベースのレコードの間でスイッチ ポート ID の整合が取れていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="586cc-142">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="586cc-143">一部のサードパーティの SNMP ソリューションは、非管理対象のアクセススイッチをサポートしています。Lync クライアントをサービスするスイッチが管理されておらず、マネージ配布スイッチへのリンクが設定されている場合、管理対象スイッチは、アクセススイッチに接続されているクライアントの MAC アドレスを SNMP アプリケーションに報告することができます。</span><span class="sxs-lookup"><span data-stu-id="586cc-143">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="586cc-144">この情報によって、位置情報サービスがユーザーの場所を特定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="586cc-144">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="586cc-145">ただし、アンマネージスイッチのすべてのポートに1つの ERL のみを割り当てることができます。そのため、目的の場所は、ポートレベルではなく、アクセススイッチのシャーシレベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="586cc-145">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

