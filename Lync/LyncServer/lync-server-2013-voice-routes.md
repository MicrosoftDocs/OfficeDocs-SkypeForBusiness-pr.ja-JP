---
title: 'Lync Server 2013: 音声ルート'
description: 'Lync Server 2013: 音声ルート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f3c548890c6d2a8c16808eebd9dd50e3ed2715
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554053"
---
# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="1f823-103">Lync Server 2013 の音声ルート</span><span class="sxs-lookup"><span data-stu-id="1f823-103">Voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f823-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1f823-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1f823-105">通話ルートは、Lync Server がエンタープライズ Voip ユーザーによって送信される発信呼び出しを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f823-105">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="1f823-106">ユーザーが番号をダイヤルすると、フロントエンドサーバーは、必要に応じてダイヤル文字列を e.164 形式に正規化し、SIP URI との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="1f823-106">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="1f823-107">サーバーが一致させることができない場合は、その数に基づいて発信呼び出しのルーティングロジックを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f823-107">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="1f823-108">ロジックを定義する最後の手順では、各ダイヤルプランに記載されている宛先電話番号のセットごとに個別の名前付き通話ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f823-108">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="1f823-109">発信通話ルートを定義する前に、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-109">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="1f823-110">1つ以上のトランクを展開します。</span><span class="sxs-lookup"><span data-stu-id="1f823-110">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="1f823-111">必要に応じて、サイト、個人、および連絡先オブジェクトに対するダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f823-111">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="1f823-112">公衆交換電話網 (PSTN) 使用法レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f823-112">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="1f823-113">さらに、発信通話ルーティングを有効にするには、1つ以上の音声ポリシーを作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-113">Additionally, to enable outbound call routing, you must create and assign one or more voice policies.</span></span> <span data-ttu-id="1f823-114">これは、発信通話ルートを定義する前または後のどちらでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1f823-114">You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="1f823-115">ルートごとに、以下を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-115">For each route, you must specify:</span></span>

  - <span data-ttu-id="1f823-116">ルートを簡単に識別できる名前。</span><span class="sxs-lookup"><span data-stu-id="1f823-116">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="1f823-117">省略可能な説明。これは、名前だけではルートを記述するのに十分ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-117">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="1f823-118">ルートが適用される宛先の電話番号を識別する正規表現一致パターンと、一致パターンを適用しない例外を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f823-118">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="1f823-119">ルートに割り当てる1つ以上のトランク。</span><span class="sxs-lookup"><span data-stu-id="1f823-119">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="1f823-120">ユーザーが宛先電話番号正規表現に一致する番号を呼び出すために必要な PSTN 使用法レコード。</span><span class="sxs-lookup"><span data-stu-id="1f823-120">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="1f823-121">通話ルートは、Lync Server コントロールパネルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="1f823-121">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="1f823-122">これらの通話ルートにより、Lync Server が PSTN 宛ての通話をルーティングするために使用するサーバールーティングテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1f823-122">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="1f823-123">M:N トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="1f823-123">M:N Trunk Support</span></span>

<span data-ttu-id="1f823-124">Lync Server は、通話を PSTN にルーティングする方法を柔軟に提供します。</span><span class="sxs-lookup"><span data-stu-id="1f823-124">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="1f823-125">音声ルートは、特定の音声呼び出しで使用できる PSTN へのトランクのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f823-125">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="1f823-126">トランクは、仲介サーバーとポート番号を PSTN ゲートウェイとリスニングポート番号に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1f823-126">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="1f823-127">この論理関連付けにより、仲介サーバーを複数のゲートウェイに関連付け、同じゲートウェイに複数の接続を確立できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1f823-127">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="1f823-128">通話ルートを定義するときは、そのルートに関連付けられているトランクを指定しますが、そのルートに関連付けられている仲介サーバーを指定することはありません。</span><span class="sxs-lookup"><span data-stu-id="1f823-128">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="1f823-129">仲介サーバーと PSTN ゲートウェイ、IP-PBX、およびセッションボーダーコントローラー (sbc) 間の関係を定義してトランクを作成するには、トポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f823-129">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="1f823-130">Least-Cost ルーティング</span><span class="sxs-lookup"><span data-stu-id="1f823-130">Least-Cost Routing</span></span>

<span data-ttu-id="1f823-131">さまざまな番号をルーティングするためのトランクを指定する機能を使用すると、コストが最も低いルートを特定し、それに応じてそれらを実装できます。</span><span class="sxs-lookup"><span data-stu-id="1f823-131">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly.</span></span> <span data-ttu-id="1f823-132">トランクを選択する際の一般的な規則は、長距離料金を最小限に抑えるために、宛先番号の場所に最も近いゲートウェイを持つトランクを選択することです。</span><span class="sxs-lookup"><span data-stu-id="1f823-132">The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges.</span></span> <span data-ttu-id="1f823-133">たとえば、ニューヨークで、ローマで番号を呼び出す場合は、IP ネットワークを介して、ローマ支社のゲートウェイを使用してトランクに電話をかけることにより、ローカル呼び出しに対してのみ課金を行います。</span><span class="sxs-lookup"><span data-stu-id="1f823-133">For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="1f823-134">最小コストのルーティングを使用する方法の例については、次の点を考慮してください。 Fabrikam は、ドイツユーザーが米国トランクを使用して米国番号をダイヤルできるようにすることを決定します。</span><span class="sxs-lookup"><span data-stu-id="1f823-134">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="1f823-135">Fabrikam は、米国 Lync Server ユーザーからドイツおよび隣接する国/地域へのすべての通話を、ドイツのゲートウェイを使用してトランクで終了するようにシステムを構成することも必要としています。</span><span class="sxs-lookup"><span data-stu-id="1f823-135">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="1f823-136">たとえば、ドイツからオーストリアへの通話は、米国内からオーストリアへの通話に比べて安価であるため、このルーティングによってコストが節約されます。</span><span class="sxs-lookup"><span data-stu-id="1f823-136">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="1f823-137">送信ダイヤル文字列の変換</span><span class="sxs-lookup"><span data-stu-id="1f823-137">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="1f823-138">Lync Server 2013 は、直前の先行タスクと同様に、逆引き番号参照 (RNL) を実行するためにすべてのダイヤル文字列を e.164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-138">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="1f823-139">ローカルのダイヤル形式で数値を変換する必要があるゲートウェイまたは構内交換機 (Pbx) を使用するトランクでは、Lync Server 2013 で、呼び出し先の番号 (つまり、要求 URI) をトランクにルーティングする前に操作する際に役立つ1つまたは複数のルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f823-139">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="1f823-140">たとえば、ダイヤル文字列の先頭から + 44 を削除して、それを0144に置き換えるルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1f823-140">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="1f823-141">Lync Server 2013 では、1つまたは複数のルールを作成して、発信番号をトランクにルーティングする前に操作することができます。</span><span class="sxs-lookup"><span data-stu-id="1f823-141">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="1f823-142">ゲートウェイを仲介サーバー: ポートのペアと共に使用するトランクを計画する際には、類似したローカルダイヤル要件を持つトランクをグループ化し、必要な変換ルールの数を減らして、それらの書き込みにかかる時間を短縮することが有用な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-142">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="1f823-143">発信者番号の構成</span><span class="sxs-lookup"><span data-stu-id="1f823-143">Configuring Caller ID</span></span>

<span data-ttu-id="1f823-144">Lync Server は、発信通話の発信者番号を操作する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1f823-144">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="1f823-145">たとえば、組織で従業員の直接ダイヤル内線番号をマスクして、それを汎用の企業または部署の番号に置き換える場合は、管理者は Lync Server コントロールパネルを使用して発信者番号を非表示にし、指定された代替呼び出し ID で置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="1f823-145">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="1f823-146">ルーティングロジックの計画では、すべての従業員に対して、このオプションを使用する個人、グループ、およびサイトを検討します。</span><span class="sxs-lookup"><span data-stu-id="1f823-146">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f823-147">PSTN 経由で再ルーティングされる通話の場合、元の発信者番号ではなく、汎用の発信者番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f823-147">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID.</span></span> <span data-ttu-id="1f823-148">これにより、呼び出し先が構成した応答不可またはプライバシー設定がバイパスされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-148">This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="1f823-149">その他のルーティングロジック</span><span class="sxs-lookup"><span data-stu-id="1f823-149">Additional Routing Logic</span></span>

<span data-ttu-id="1f823-150">発信通話ルートを作成する際には、ルーティングロジックに影響する可能性がある次の要因に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f823-150">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="1f823-151">フェデレーション境界を介して呼び出しが確立された場合、URI のドメイン部分を使用して、発信ルーティングロジックの適用を行うエンタープライズに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="1f823-151">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="1f823-152">要求 URI のドメイン部分に、エンタープライズに対してサポートされているドメインが含まれていない場合、サーバー上の送信ルーティングコンポーネントは通話を処理しません。</span><span class="sxs-lookup"><span data-stu-id="1f823-152">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="1f823-153">ユーザーがエンタープライズ Voip に対して有効になっていない場合、サーバーは必要に応じて他のルーティングロジックを適用します。</span><span class="sxs-lookup"><span data-stu-id="1f823-153">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="1f823-154">通話が完全に占有されているゲートウェイにルーティングされると (すべてのトランク回線がビジー状態になります)、ゲートウェイは通話を拒否し、発信ルーティングロジックは通話を次の最低コストのルートにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="1f823-154">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route.</span></span> <span data-ttu-id="1f823-155">この点を考慮してください。海外に小規模なオフィス (Zurich フルタなど) のゲートウェイを使用すると、実際にはスイスの国際通話に対して、かなり多くの非ローカルトラフィックが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1f823-155">Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland.</span></span> <span data-ttu-id="1f823-156">ゲートウェイがこの追加トラフィックに適したサイズになっていない場合、スイスへの通話はドイツのゲートウェイを経由してルーティングされる可能性があり、費用が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="1f823-156">If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

