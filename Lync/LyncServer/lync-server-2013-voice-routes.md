---
title: 'Lync Server 2013: 音声ルート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e46b4074d41d2ac79dfe63bc99411a7aba72a88c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a><span data-ttu-id="c3db9-102">Lync Server 2013 の音声ルート</span><span class="sxs-lookup"><span data-stu-id="c3db9-102">Voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3db9-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c3db9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c3db9-104">通話ルートは、Lync Server がエンタープライズボイスユーザーによる発信通話をどのように処理するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3db9-104">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="c3db9-105">ユーザーが番号をダイヤルすると、フロントエンドサーバーは、必要に応じてダイヤル文字列を E.i 形式に正規化し、SIP URI と一致させようとします。</span><span class="sxs-lookup"><span data-stu-id="c3db9-105">When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="c3db9-106">一致する SIP URI が見つからない場合は、番号に基づいて発信通話ルーティング ロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-106">If the server cannot make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="c3db9-107">発信通話ルーティング ロジックを定義する最後のステップでは、ダイヤル プランごとの各相手電話番号に対して、個別の名前が付けられた通話ルートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-107">The final step in defining that logic is to create a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="c3db9-108">発信通話ルートを定義する前に、次のステップを実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-108">Before you define outbound call routes, you should complete the following steps:</span></span>

  - <span data-ttu-id="c3db9-109">1 つ以上のトランクの展開</span><span class="sxs-lookup"><span data-stu-id="c3db9-109">Deploy one or more trunks.</span></span>

  - <span data-ttu-id="c3db9-110">必要に応じた、場所、個々のユーザー、および連絡先オブジェクトに対するダイヤル プランの作成</span><span class="sxs-lookup"><span data-stu-id="c3db9-110">Create dial plans as needed for sites, individuals, and Contact objects.</span></span>

  - <span data-ttu-id="c3db9-111">公衆交換電話網 (PSTN) の使用法レコードの作成</span><span class="sxs-lookup"><span data-stu-id="c3db9-111">Create public switched telephone network (PSTN) usage records.</span></span>

<span data-ttu-id="c3db9-p102">さらに、発信通話ルーティングを有効にするには、1 つ以上の音声ポリシーを作成して割り当てる必要があります。このステップは、発信通話ルートを定義する前および定義した後のどちらでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-p102">Additionally, to enable outbound call routing, you must create and assign one or more voice policies. You can do this either before or after you define outbound call routes.</span></span>

<span data-ttu-id="c3db9-114">各ルートごとに、次の項目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-114">For each route, you must specify:</span></span>

  - <span data-ttu-id="c3db9-115">簡単に識別できる名前</span><span class="sxs-lookup"><span data-stu-id="c3db9-115">A name by which the route can be easily identified.</span></span>

  - <span data-ttu-id="c3db9-116">オプションの説明 (名前だけではルートの内容を十分に説明できない場合に使用)</span><span class="sxs-lookup"><span data-stu-id="c3db9-116">An optional description in cases where the name alone may not be sufficient to describe the route.</span></span>

  - <span data-ttu-id="c3db9-117">ルートを適用する対象となる、相手電話番号を識別する正規表現による一致パターンと、一致パターンを適用させない例外</span><span class="sxs-lookup"><span data-stu-id="c3db9-117">The regular expression matching pattern that identifies the destination phone numbers to which the route is applied, along with exceptions to which the matching pattern is not to be applied.</span></span>

  - <span data-ttu-id="c3db9-118">ルートに割り当てる 1 つ以上のトランク</span><span class="sxs-lookup"><span data-stu-id="c3db9-118">One or more trunks that you want to assign to the route.</span></span>

  - <span data-ttu-id="c3db9-119">相手電話番号の正規表現に一致する電話番号を発信するために、ユーザーに必要な PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="c3db9-119">The PSTN usage records that users must have in order to call numbers matching the destination phone number regular expression.</span></span>

<span data-ttu-id="c3db9-120">通話ルートは Lync Server コントロールパネルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-120">You can specify call routes in the Lync Server Control Panel.</span></span> <span data-ttu-id="c3db9-121">これらの通話ルートは、サーバールーティングテーブルに設定されます。これにより、Lync Server で PSTN 宛ての通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-121">These call routes populate the server routing table, which Lync Server uses to route calls that are destined for the PSTN.</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="c3db9-122">M:N トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="c3db9-122">M:N Trunk Support</span></span>

<span data-ttu-id="c3db9-123">Lync Server では、通話を PSTN にルーティングする柔軟性が提供されています。</span><span class="sxs-lookup"><span data-stu-id="c3db9-123">Lync Server provides flexibility in how calls are routed to the PSTN.</span></span> <span data-ttu-id="c3db9-124">ボイス ルートは、特定の音声通話に対して使用できる PSTN へのトランクのセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3db9-124">A voice route specifies a set of trunks to the PSTN that can be used for a particular voice call.</span></span> <span data-ttu-id="c3db9-125">トランクは、仲介サーバーとポート番号を PSTN ゲートウェイとリスニングポート番号と関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-125">A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number.</span></span> <span data-ttu-id="c3db9-126">この論理的な関連付けによって、仲介サーバーが複数のゲートウェイに関連付けられ、同じゲートウェイへの複数の接続が可能になります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-126">This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway.</span></span> <span data-ttu-id="c3db9-127">通話ルートを定義する場合は、そのルートに関連付けられている trunks を指定しますが、そのルートに関連付ける仲介サーバーを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3db9-127">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route.</span></span> <span data-ttu-id="c3db9-128">仲介サーバーと PSTN ゲートウェイ、IP-Pbx、およびセッション境界コントローラー (SBCs) 間の関係を定義して trunks を作成するには、トポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c3db9-128">To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.</span></span>

</div>

<div>

## <a name="least-cost-routing"></a><span data-ttu-id="c3db9-129">最小コスト ルーティング</span><span class="sxs-lookup"><span data-stu-id="c3db9-129">Least-Cost Routing</span></span>

<span data-ttu-id="c3db9-p105">さまざまな番号のルーティング先であるトランクを指定する機能を使用すると、コストが最も低くなるルートを判断し、それに従ってルーティングできます。この機能は、長距離通話料金を最も少なくするために、宛先の番号の場所に最も近いゲートウェイを含むトランクを選択して指定します。たとえば、ニューヨークからローマの番号に発信する場合に、ローマの事務所のゲートウェイを含むトランクまで IP ネットワークを介して通話を中継すると、支払いが必要になるのは市内通話料金だけになります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-p105">The ability to specify the trunks to which various numbers are routed enables you to determine which routes incur the lowest costs and implement them accordingly. The general rule in selecting trunks is to choose the trunk with the closest gateway to the location of the destination number in order to minimize long-distance charges. For example, if you are in New York and calling a number in Rome, you would carry the call over the IP network to the trunk with the gateway in your Rome office, thereby incurring a charge only for a local call.</span></span>

<span data-ttu-id="c3db9-133">使用頻度の低いルーティング方法の例については、次の点を考慮してください。 Fabrikam は、ドイツのユーザーが米国トランクを使って米国の番号をダイヤルできるようにすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="c3db9-133">For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk.</span></span> <span data-ttu-id="c3db9-134">また、Fabrikam は、米国の Lync Server ユーザーからドイツの国または地域へのすべての通話がドイツのゲートウェイで終了するようにシステムを構成することを希望しています。</span><span class="sxs-lookup"><span data-stu-id="c3db9-134">Fabrikam also wants to configure the system so that all calls from U.S. Lync Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany.</span></span> <span data-ttu-id="c3db9-135">たとえば、ドイツからオーストリアへの通話は、米国内からオーストリアへの通話よりも経費が安いためです。</span><span class="sxs-lookup"><span data-stu-id="c3db9-135">This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.</span></span>

</div>

<div>

## <a name="translating-outbound-dial-strings"></a><span data-ttu-id="c3db9-136">発信ダイヤル文字列の変換</span><span class="sxs-lookup"><span data-stu-id="c3db9-136">Translating Outbound Dial Strings</span></span>

<span data-ttu-id="c3db9-137">直前の先行タスクと同様に、Lync Server 2013 では、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列を E-164 形式に正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-137">Lync Server 2013, like its immediate predecessors, requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c3db9-138">ローカルのダイヤル形式で数値を変換する必要があるゲートウェイまたは私的な支店 (Pbx) を使用する trunks の場合、Lync Server 2013 を使用すると、通話先の番号 (つまり要求 URI) を操作する際に役立つ1つまたは複数のルールを作成して、それをルーティングすることができます。トランク.</span><span class="sxs-lookup"><span data-stu-id="c3db9-138">For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Lync Server 2013 enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk.</span></span> <span data-ttu-id="c3db9-139">たとえば、+44 をダイヤル文字列の先頭から削除し、0144 に置き換えるルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-139">For example, you could write a rule to remove +44 from the head of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="c3db9-140">Lync Server 2013 を使用すると、1つ以上のルールを作成して、その番号をトランクにルーティングする前に、通話番号の操作を支援することができます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-140">With Lync Server 2013, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.</span></span>

<span data-ttu-id="c3db9-141">ゲートウェイに接続する trunks を計画するには、ポートペアと仲介サーバーの組み合わせを使用して trunks をグループ化することができます。これにより、必要な翻訳ルールの数と書き込みにかかる時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-141">In planning your trunks that associate gateways:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.</span></span>

</div>

<div>

## <a name="configuring-caller-id"></a><span data-ttu-id="c3db9-142">発信者番号の構成</span><span class="sxs-lookup"><span data-stu-id="c3db9-142">Configuring Caller ID</span></span>

<span data-ttu-id="c3db9-143">Lync Server では、発信通話の発信者番号認識を操作することができます。</span><span class="sxs-lookup"><span data-stu-id="c3db9-143">Lync Server provides a way to manipulate the caller ID for outbound calls.</span></span> <span data-ttu-id="c3db9-144">たとえば、組織で従業員の直通ダイヤルの内線番号をマスクして、一般法人または部署別の番号に置き換える場合は、管理者は Lync Server コントロールパネルを使って発信者番号認識を抑制し、それを指定した代替発信者番号。</span><span class="sxs-lookup"><span data-stu-id="c3db9-144">For example, if an organization wants to mask employees’ direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Lync Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID.</span></span> <span data-ttu-id="c3db9-145">ルーティング ロジックを計画する際は、このオプションが特定の個人、グループ、場所、またはすべての従業員に必要かどうかを検討します。</span><span class="sxs-lookup"><span data-stu-id="c3db9-145">In planning your routing logic, consider which individuals, groups, sites you’ll want this option for—perhaps, even, for all employees.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3db9-p109">PSTN を介して再ルーティングされる通話の場合、元の発信者番号ではなく、一般的な発信者番号が表示されます。これにより、通話の呼び出し先が構成した応答不可設定またはプライバシー設定がバイパスされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-p109">For calls that are rerouted over the PSTN, the generic caller ID will be presented instead of the original caller ID. This can cause the call to bypass Do Not Disturb or privacy settings that the callee may have configured.</span></span>



</div>

</div>

<div>

## <a name="additional-routing-logic"></a><span data-ttu-id="c3db9-148">その他のルーティング ロジック</span><span class="sxs-lookup"><span data-stu-id="c3db9-148">Additional Routing Logic</span></span>

<span data-ttu-id="c3db9-149">発信通話ルートを作成する際には、以下の要因がルーティング ロジックに作用することを認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-149">In creating outbound call routes, you should be aware of the following factors that can affect routing logic:</span></span>

  - <span data-ttu-id="c3db9-150">フェデレーションの境界を越えて通話が確立される場合、URI のドメイン部分を使用して、発信ルーティング ロジックの適用を行うエンタープライズに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c3db9-150">Where a call is established over a federated boundary, the domain portion of the URI is used to route the call over to the enterprise that is responsible for applying the outbound routing logic.</span></span>

  - <span data-ttu-id="c3db9-151">要求 URI のドメイン部分にエンタープライズでサポートされているドメインが含まれていない場合、サーバーの発信ルーティング コンポーネントは通話の処理を行いません。</span><span class="sxs-lookup"><span data-stu-id="c3db9-151">If the domain portion of the request URI does not contain a supported domain for the enterprise, the outbound routing component on the server does not process the call.</span></span>

  - <span data-ttu-id="c3db9-152">ユーザーがエンタープライズ Voip を有効にしていない場合は、必要に応じて、サーバーが他のルーティングロジックを適用します。</span><span class="sxs-lookup"><span data-stu-id="c3db9-152">If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.</span></span>

  - <span data-ttu-id="c3db9-p110">空き回線のないゲートウェイ (すべてのトランク回線が使用中) に通話がルーティングされると、ゲートウェイによって通話が拒否されるため、発信ルーティング コンポーネントは次にコストの低いルートに通話をリダイレクトします。海外の小規模な支店 (たとえば、チューリヒ) に合わせて構成された小規模なゲートウェイが、実際にはスイス宛ての大量の国際通話を処理するような場合があるため、ルーティングには詳細な配慮が必要です。このような追加トラフィックに対応できるようにゲートウェイのサイズを適正に構成していない場合は、スイス宛ての通話がドイツにあるゲートウェイを経由してルーティングされ、多額の通話料金が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3db9-p110">If a call is routed to a gateway that is fully occupied (all trunk lines are busy), the gateway rejects the call and the outbound routing logic redirects the call to the next-least-cost route. Give this careful consideration, because a gateway sized for a small office overseas (for example, Zurich) may actually carry a significant amount of nonlocal traffic for international calls to Switzerland. If the gateway is not correctly sized for this additional traffic, calls to Switzerland may be routed by way of a gateway in Germany, resulting in larger toll charges.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

