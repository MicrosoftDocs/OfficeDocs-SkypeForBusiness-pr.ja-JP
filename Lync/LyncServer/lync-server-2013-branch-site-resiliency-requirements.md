---
title: 'Lync Server 2013: ブランチ サイトの復元要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f146f2c358e6eb6718aa60f8a51106430e6a4a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a><span data-ttu-id="85ee8-102">Lync Server 2013 のブランチ サイトの復元要件</span><span class="sxs-lookup"><span data-stu-id="85ee8-102">Branch-site resiliency requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ee8-103">_**最終更新日:** 2014-02-25_</span><span class="sxs-lookup"><span data-stu-id="85ee8-103">_**Topic Last Modified:** 2014-02-25_</span></span>

<span data-ttu-id="85ee8-104">このトピックでは、ブランチ サイトの復元およびボイス メールの存続性に対するユーザーの準備と、関連するハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-104">This topic will help you to prepare users for branch-site resiliency and voice mail survivability, and also specifies the relevant hardware and software requirements.</span></span>

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a><span data-ttu-id="85ee8-105">ブランチ サイトの復元に対するブランチ サイトのユーザーの準備</span><span class="sxs-lookup"><span data-stu-id="85ee8-105">Preparing Branch Users for Branch-Site Resiliency</span></span>

<span data-ttu-id="85ee8-106">ユーザーのレジストラープールを Survivable Branch Appliance (SBA) または Survivable Branch Server として設定することにより、ブランチサイトの回復力を持つユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-106">Prepare users for branch-site resiliency by setting their Registrar pool as the Survivable Branch Appliance (SBA) or Survivable Branch Server.</span></span>

<div>

## <a name="registrar-assignments-for-branch-users"></a><span data-ttu-id="85ee8-107">ブランチ ユーザーのレジストラーへの割り当て</span><span class="sxs-lookup"><span data-stu-id="85ee8-107">Registrar Assignments for Branch Users</span></span>

<span data-ttu-id="85ee8-108">どのブランチサイトの復元ソリューションを選んでも、プライマリレジストラーを各ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-108">Regardless of which branch-site resiliency solution you choose, you will need to assign a primary Registrar to each user.</span></span> <span data-ttu-id="85ee8-109">ブランチサイトユーザーは、レジストラーが Survivable Branch Appliance、Survivable Branch Server、またはスタンドアロンの Lync Server 2013 Standard または Enterprise Edition サーバーのどちらに存在するかに関係なく、常にブランチサイトのレジストラーに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-109">Branch site users should always register with the Registrar at the branch site, regardless of whether that Registrar resides in the Survivable Branch Appliance, Survivable Branch Server, or stand-alone Lync Server 2013 Standard or Enterprise Edition server.</span></span> <span data-ttu-id="85ee8-110">クライアントがレジストラープールを検出できるように、ドメインネームシステム (DNS) サービス (SRV) リソースレコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="85ee8-110">A domain name system (DNS) service (SRV) resource record is required so that a client can discover its Registrar pool.</span></span> <span data-ttu-id="85ee8-111">Survivable Branch アプライアンスが使用できなくなった場合は、ブランチサイトクライアントでバックアップレジストラーが自動的に検出されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-111">If the Survivable Branch Appliance becomes unavailable, this is how branch site clients will automatically discover the backup Registrar.</span></span>

<span data-ttu-id="85ee8-112">ブランチサイトに DNS サーバーがない場合は、次の2つの方法で、Survivable Branch Appliance または Survivable Branch Server の検出を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-112">If a branch site does not have a DNS server, there are two alternative ways to configure discovery of the Survivable Branch Appliance or Survivable Branch Server:</span></span>

  - <span data-ttu-id="85ee8-113">Survivable Branch Appliance または Survivable Branch Server の完全修飾ドメイン名 (FQDN) をポイントするように、ブランチサイトの動的ホスト構成プロトコル (DHCP) サーバー上の DHCP オプション120を構成します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-113">Configure DHCP option 120 on the branch site’s Dynamic Host Configuration Protocol (DHCP) server to point to the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="85ee8-114">DHCP 120 クエリに応答するように、Survivable Branch Appliance または Survivable Branch Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-114">Configure the Survivable Branch Appliance or Survivable Branch Server to respond to DHCP 120 queries.</span></span>

</div>

<div>

## <a name="voice-routing-for-branch-users"></a><span data-ttu-id="85ee8-115">ブランチ ユーザーの音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="85ee8-115">Voice Routing for Branch Users</span></span>

<span data-ttu-id="85ee8-116">ブランチサイトのユーザーに対して、個別のユーザーレベルのボイスメールインターネットプロトコル (VoIP) ポリシーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-116">We recommend that you create a separate user-level Voice over Internet Protocol (VoIP) policy for users in a branch site.</span></span> <span data-ttu-id="85ee8-117">このポリシーには、Survivable Branch Appliance またはブランチサーバーゲートウェイを使用するプライマリルートと、セントラルサイトで公衆交換電話網 (PSTN) ゲートウェイを使用するトランクを使用する1つ以上のバックアップルートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-117">This policy should include a primary route that uses the Survivable Branch Appliance or branch server gateway, and one or more backup routes that use a trunk with a public switched telephone network (PSTN) gateway at the central site.</span></span> <span data-ttu-id="85ee8-118">プライマリルートを使用できない場合は、1つ以上のセントラルサイトゲートウェイを使用するバックアップルートが代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-118">If the primary route is unavailable, the backup route that uses one or more central site gateways is used instead.</span></span> <span data-ttu-id="85ee8-119">この方法では、ユーザーが登録されている場所に関係なく、ブランチサイトレジストラーまたはセントラルサイトのバックアップレジストラープールで、ユーザーの VoIP ポリシーが常に有効になります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-119">This way, regardless of where a user is registered—on the branch site Registrar or the backup Registrar pool at the central site—the user’s VoIP policy is always in effect.</span></span> <span data-ttu-id="85ee8-120">これは、フェールオーバーシナリオの重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="85ee8-120">This is an important consideration for failover scenarios.</span></span> <span data-ttu-id="85ee8-121">たとえば、Survivable Branch Appliance の名前を変更する必要がある場合、または Survivable Branch アプライアンスを再構成してセントラルサイトのバックアップレジストラープールに接続する必要がある場合は、その期間、ブランチサイトユーザーをセントラルサイトに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-121">For example, if you need to rename the Survivable Branch Appliance or reconfigure the Survivable Branch Appliance to connect to a backup Registrar pool at the central site, then you must move branch site users to the central site for the duration.</span></span> <span data-ttu-id="85ee8-122">(Survivable Branch アプライアンスの名前の変更または再構成の詳細については、「[付録 B: 展開ドキュメントの Lync Server 2013 で Survivable Branch appliance を管理](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)する」を参照してください。)このようなユーザーが、ユーザーレベルの VoIP ポリシーまたはユーザーレベルのダイヤルプランを持っていない場合は、ユーザーが別のサイトに移動すると、ブランチサイトのサイトレベルの VoIP ポリシーとダイヤルプランの代わりに、セントラルサイトのサイトレベルの VoIP ポリシーとサイトレベルのダイヤルプランが既定でユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-122">(For details about renaming or reconfiguring a Survivable Branch Appliance, see [Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in the Deployment documentation.) If those users do not have user-level VoIP policies or user-level dial plans, when the users are moved to another site, the site-level VoIP policies and site-level dial plans of the central site apply to the users by default, instead of the branch site site-level VoIP policies and dial plans,.</span></span> <span data-ttu-id="85ee8-123">このシナリオでは、バックアップレジストラープールで使用されるサイトレベルの VoIP ポリシーやサイトレベルのダイヤルプランもブランチサイトユーザーに適用できる場合を除き、その呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-123">In this scenario, unless the site-level VoIP policies and site-level dial plans used by the backup Registrar pool can also apply to the branch site users, their calls will fail.</span></span> <span data-ttu-id="85ee8-124">たとえば、日本に配置されている支店のユーザーが Redmond のセントラルサイトに移動した場合、すべての7桁の通話に + 1425 を付加する正規化ルールが適用されているダイヤルプランでは、これらのユーザーへの通話を適切に翻訳できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-124">For example, if users from a branch site located in Japan are moved to a central site in Redmond, then a dial plan with normalization rules that prepend +1425 to all 7-digit calls is unlikely to appropriately translate calls for those users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85ee8-125">ブランチ オフィスのバックアップ ルートを作成するときは、ブランチ オフィスのユーザー ポリシーに 2 つの PSTN 電話使用法レコードを追加し、各電話使用法レコードに個別のルートを割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-125">When you create a branch office backup route, we recommend that you add two PSTN phone usage records to the branch office user policy and assign separate routes to each one.</span></span> <span data-ttu-id="85ee8-126">第1または第1のルートでは、Survivable Branch Appliance (SBA) またはブランチサーバーに関連付けられているゲートウェイに直接通話を発信できます。2番目の (バックアップ) ルートは、中央サイトのゲートウェイに直接通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-126">The first, or primary, route would direct calls to the gateway associated with the Survivable Branch Appliance (SBA) or branch server; the second, or backup, route would direct calls to the gateway at the central site.</span></span> <span data-ttu-id="85ee8-127">SBA またはブランチ サーバーは通話を振り分けるときに、最初の PSTN 使用法レコードに割り当てられたすべてのルートを試みてから、2 番目の使用法レコードのルートを試みます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-127">In directing calls, the SBA or branch server will attempt all routes assigned to the first PSTN usage record before attempting the second usage record.</span></span>



</div>

<span data-ttu-id="85ee8-128">Survivable Branch Appliance サイトのブランチゲートウェイまたは Windows コンポーネントが利用できない場合 (たとえば、Survivable Branch Appliance またはブランチの場合など) に、ブランチサイトユーザーへの着信通話がそれらのユーザーに届くようにするために役立ちます。ゲートウェイはメンテナンスのために停止していました)、ゲートウェイでフェールオーバールートを作成します (または、直接内向きダイヤル (DID) プロバイダーと協力して、中央サイトのバックアップレジストラープールに着信通話をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-128">To help ensure that inbound calls to branch site users will reach those users when the branch gateway or the Windows component of the Survivable Branch Appliance site is unavailable (which would happen, for example, if the Survivable Branch Appliance or branch gateway were down for maintenance), create a failover route on the gateway (or work with your Direct Inward Dialing (DID) provider) to redirect incoming calls to the backup Registrar pool at the central site.</span></span> <span data-ttu-id="85ee8-129">通話は、そこから WAN リンク経由でブランチ ユーザーにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-129">From there, the calls will be routed over the WAN link to branch users.</span></span> <span data-ttu-id="85ee8-130">ルートによって番号が PSTN ゲートウェイまたは他のトランク ピアの受け付け済み電話番号方式に準拠するように変換されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-130">Be sure that the route translates numbers to comply with the PSTN gateway or other trunk peer’s accepted phone number formats.</span></span> <span data-ttu-id="85ee8-131">フェールオーバールートの作成の詳細については、「 [Lync Server 2013 でのフェールオーバールートの構成](lync-server-2013-configuring-a-failover-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-131">For details about creating a failover route, see [Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md).</span></span> <span data-ttu-id="85ee8-132">また、ブランチ サイトのゲートウェイに関連付けられたトランクにサービスレベルのダイヤル プランを作成して着信通話を正規化します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-132">Also create service-level dial plans for the trunk associated with the gateway at the branch site to normalize incoming calls.</span></span> <span data-ttu-id="85ee8-133">ブランチサイトに2つの Survivable Branch アプライアンスがある場合は、それぞれについて、それぞれのサービスレベルのプランが必要な場合を除き、両方のサイトレベルのダイヤルプランを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-133">If you have two Survivable Branch Appliances at a branch site, you can create a site-level dial plan for both unless a separate service-level plan for each is necessary.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85ee8-134">プレゼンス、会議、またはフェールオーバーの実行を中央サイトに頼っているすべてのブランチ サイトのユーザーによる中央サイトのリソース消費に対応するには、各ブランチ サイトのユーザーを、中央サイトに登録されたユーザーとしてみなすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-134">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as if the user were registered with the central site.</span></span> <span data-ttu-id="85ee8-135">現時点では、Survivable Branch Appliance に登録されているユーザーを含む、ブランチサイトユーザーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-135">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>



</div>

<span data-ttu-id="85ee8-136">なお、ユーザー レベルのダイヤル プランと音声ポリシーを作成してから、ブランチ サイトのユーザーに割り当てることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-136">We also recommend that you create a user-level dial plan and voice policy, and then assign it to branch site users.</span></span> <span data-ttu-id="85ee8-137">詳細については、「 [Lync server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」および「展開ドキュメントの[lync server 2013 でブランチユーザー用に VoIP ルーティングポリシーを作成](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-137">For details, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) and [Create the VoIP routing policy for branch users in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in the Deployment documentation.</span></span>

<div>

## <a name="routing-extension-numbers"></a><span data-ttu-id="85ee8-138">内線番号のルーティング</span><span class="sxs-lookup"><span data-stu-id="85ee8-138">Routing Extension Numbers</span></span>

<span data-ttu-id="85ee8-139">ブランチサイトユーザーのダイヤルプランと音声ポリシーを準備する場合は、Msrtcsip-userenabled true line (または Line URI) 属性で使用される文字列と数値の書式に一致する正規化ルールと翻訳ルールを含めるようにしてください。そのため、Lync 2013 の通話がブランチ間で有効になります。サイトユーザーとセントラルサイトユーザーは正しくルーティングされます。特に、WAN リンクが利用できないため、PSTN 経由で通話を再ルーティングする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="85ee8-139">When preparing dial plans and voice policies for branch site users, be sure to include normalization rules and translation rules that match the strings and number format used in the msRTCSIP-line (or Line URI) attribute, so that Lync 2013 calls enabled between branch site users and central site users will be routed correctly—particularly when calls must be rerouted over the PSTN because the WAN link is unavailable.</span></span> <span data-ttu-id="85ee8-140">また、電話番号だけではなく、内線番号を含むダイヤル番号には特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-140">Additionally, there are special considerations for dialed numbers that include extension numbers, rather just phone numbers.</span></span>

<span data-ttu-id="85ee8-p108">内線番号を単独で含むか、E.164 準拠の電話番号に追加して含むかにかかわらず、内線番号を含む回線 URI を照合する正規化ルールと変換ルールには要件が追加されます。このセクションでは、いくつかのシナリオ例を挙げて、内線番号を含む回線 URI の通話をルーティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p108">Normalization rules and translations rules that match Line URIs that contain an extension number, whether exclusively or in addition to a full E.164 phone number, have additional requirements. This section describes several example scenarios to route calls for Line URIs with an extension number.</span></span>

<span data-ttu-id="85ee8-p109">組織で個々のユーザーに Direct Inward Dial (DID) 電話番号を構成しないで、各ユーザーの回線 URI を内線番号のみで構成している場合、内部ユーザーは、内線番号のみをダイヤルして通話できます。\*\* ただし、ブランチ サイトのユーザーから、内線番号が一致する中央サイトのユーザーへの通話に適用できる正規化ルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p109">If your organization does not have Direct Inward Dial (DID) phone numbers configured for individual users and the Line URI of each user is configured with *only* an extension number, internal users can call one another by dialing only an extension number. However, you must configure normalization rules that can apply to calls from a branch site user to a central site user, that match the extension numbers.</span></span>

<span data-ttu-id="85ee8-p110">ブランチ サイトのユーザーと中央サイトのユーザーの間で WAN リンクを使用できる場合、ブランチ サイトのユーザーから中央サイトのユーザーへの通話は PSTN 経由でルーティングされないため、マッチング正規化ルールで番号を変換する必要はありません。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p110">In a scenario where the WAN link between a branch site and a central site is available, calls from branch site users to central site users do not require the matching normalization rule to translate the number because the call is not routed over the PSTN. For example:</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85ee8-147">ルール名</span><span class="sxs-lookup"><span data-stu-id="85ee8-147">Rule name</span></span></th>
<th><span data-ttu-id="85ee8-148">説明</span><span class="sxs-lookup"><span data-stu-id="85ee8-148">Description</span></span></th>
<th><span data-ttu-id="85ee8-149">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="85ee8-149">Number pattern</span></span></th>
<th><span data-ttu-id="85ee8-150">変換</span><span class="sxs-lookup"><span data-stu-id="85ee8-150">Translation</span></span></th>
<th><span data-ttu-id="85ee8-151">例</span><span class="sxs-lookup"><span data-stu-id="85ee8-151">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85ee8-152">5digitExtensions</span><span class="sxs-lookup"><span data-stu-id="85ee8-152">5digitExtensions</span></span></p></td>
<td><p><span data-ttu-id="85ee8-153">5 桁の番号を変換しません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-153">Does not translate 5-digit numbers</span></span></p></td>
<td><p><span data-ttu-id="85ee8-154">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="85ee8-154">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="85ee8-155">$1</span><span class="sxs-lookup"><span data-stu-id="85ee8-155">$1</span></span></p></td>
<td><p><span data-ttu-id="85ee8-156">10001 は変換されません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-156">10001 is not translated</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85ee8-p111">また、ブランチ サイトと中央サイトの間で WAN リンクを使用できない場合や、ブランチ サイトからの通話を PSTN 経由でルーティングする必要がある場合などのシナリオの内線番号に対応する必要もあります。WAN の停止時に、ブランチ サイトのユーザーが、中央サイトのユーザーの内線番号のみをダイヤルして中央サイトのユーザーと通話する場合は、中央サイトのユーザーの完全な電話番号を追加する発信変換ルールが必要です。ユーザーの回線 URI に、組織の完全な電話番号とユーザーの一意の内線番号 (ユーザーの一意の完全な電話番号ではなく) が含まれている場合は、組織の完全な電話番号を追加する発信変換ルールが必要です。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p111">You must also accommodate extension numbers for specific scenarios, such as when the WAN link between a branch site and central site is unavailable and a call from a branch site must be routed over the PSTN. During a WAN outage, if a branch site user calls a central site user only by dialing the central site user’s extension, you must have an outbound translation rule that adds the central site user’s full phone number. If a user’s Line URI contains your organization’s full phone number and the user’s unique extension number instead of a full phone number that is unique to the user, then you must have an outbound translation rule that adds your organization’s full phone number instead. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85ee8-161">説明</span><span class="sxs-lookup"><span data-stu-id="85ee8-161">Description</span></span></th>
<th><span data-ttu-id="85ee8-162">一致パターン</span><span class="sxs-lookup"><span data-stu-id="85ee8-162">Matching pattern</span></span></th>
<th><span data-ttu-id="85ee8-163">変換</span><span class="sxs-lookup"><span data-stu-id="85ee8-163">Translation</span></span></th>
<th><span data-ttu-id="85ee8-164">例</span><span class="sxs-lookup"><span data-stu-id="85ee8-164">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85ee8-165">5 桁の番号をユーザーの電話番号と内線番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-165">Translates 5-digit numbers to a user’s phone number and extension</span></span></p></td>
<td><p><span data-ttu-id="85ee8-166">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="85ee8-166">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="85ee8-167">+14255550123;ext=$1</span><span class="sxs-lookup"><span data-stu-id="85ee8-167">+14255550123;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="85ee8-168">10001 は +14255550123;ext=10001 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-168">10001 is translated to +14255550123;ext=10001</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ee8-169">5 桁の番号を組織の電話番号とユーザーの内線番号に変換します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-169">Translates 5-digit numbers to your organization’s phone number and a user’s extension</span></span></p></td>
<td><p><span data-ttu-id="85ee8-170">^ (\d{5}) $</span><span class="sxs-lookup"><span data-stu-id="85ee8-170">^(\d{5})$</span></span></p></td>
<td><p><span data-ttu-id="85ee8-171">+14255550100;ext=$1</span><span class="sxs-lookup"><span data-stu-id="85ee8-171">+14255550100;ext=$1</span></span></p></td>
<td><p><span data-ttu-id="85ee8-172">10001 は +14255550100;ext=10001 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-172">10001 is translated to +14255550100;ext=10001</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85ee8-p112">このシナリオで、PSTN への再ルーティングを処理するトランク ピアが、内線番号をサポートしていない場合は、発信変換ルールによって内線番号を削除する必要もあります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p112">In this scenario, if the trunk peer that handles rerouting to the PSTN does not support extension numbers, then the outbound translation rule must also remove the extension number. For example:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85ee8-175">説明</span><span class="sxs-lookup"><span data-stu-id="85ee8-175">Description</span></span></th>
<th><span data-ttu-id="85ee8-176">一致パターン</span><span class="sxs-lookup"><span data-stu-id="85ee8-176">Matching pattern</span></span></th>
<th><span data-ttu-id="85ee8-177">変換</span><span class="sxs-lookup"><span data-stu-id="85ee8-177">Translation</span></span></th>
<th><span data-ttu-id="85ee8-178">例</span><span class="sxs-lookup"><span data-stu-id="85ee8-178">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85ee8-179">内線番号付きの電話番号から内線番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-179">Removes extension from phone numbers with extensions</span></span></p></td>
<td><p><span data-ttu-id="85ee8-180">^\+(\d *); ext = (\d*) $</span><span class="sxs-lookup"><span data-stu-id="85ee8-180">^\+(\d *);ext=(\d*)$</span></span></p></td>
<td><p><span data-ttu-id="85ee8-181">+$1</span><span class="sxs-lookup"><span data-stu-id="85ee8-181">+$1</span></span></p></td>
<td><p><span data-ttu-id="85ee8-182">+14255550123;ext=10001 は +14255550123 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-182">+14255550123;ext=10001 is translated to +14255550123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="85ee8-p113">WAN リンクが使用できるかどうかにかかわらず、組織で個々のユーザーに DID 番号を構成しないで、ユーザーの回線 URI に組織の電話番号とユーザーの一意の内線番号を含める場合は、組織の電話番号の回線 URI を、ブランチ サイトのトランク ピアまたは PSTN ゲートウェイから到達可能な番号で構成する必要があります。また、組織の電話番号の回線 URI に独自の一意の内線番号を含めて、その番号に通話をルーティングする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-p113">Whether or not a WAN link is available, if your organization does not have DID numbers configured for individual users and the Line URI for a user contains your organization’s phone number and the user’s unique extension number, then you must configure your organization’s phone number Line URI with a number that is reachable by the trunk peer or PSTN gateway at the branch site. You must also configure your organization’s phone number Line URI to include its own unique extension for calls to be routed to that number.</span></span>

<span data-ttu-id="85ee8-185">サイト間の WAN リンクが利用できない場合の中央サイトユーザーからブランチサイトユーザーへの通話について詳しくは、このトピックの後半の「ボイスメールの Survivability の準備」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-185">For details about calls from a central site user to a branch site user when the WAN link between the sites is unavailable, see "Preparing for Voice Mail Survivability" later in this topic.</span></span> <span data-ttu-id="85ee8-186">その他のサンプルルールなど、ダイヤルプランと正規化ルールの詳細については、展開ドキュメントの「会議の計画と lync [server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)」を参照して[2013](lync-server-2013-dial-plans-and-normalization-rules.md)ください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-186">For details about dial plans and normalization rules, including other sample rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation and [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in the Deployment documentation.</span></span> <span data-ttu-id="85ee8-187">送信翻訳ルールの詳細については、「計画ドキュメントの「 [Lync server 2013 の翻訳ルール](lync-server-2013-translation-rules.md)」および「展開ドキュメントの[lync server 2013 での翻訳ルールの定義](lync-server-2013-defining-translation-rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-187">For details about outbound translation rules, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md) in the Planning documentation and [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a><span data-ttu-id="85ee8-188">ボイス メールの存続性の準備</span><span class="sxs-lookup"><span data-stu-id="85ee8-188">Preparing for Voice Mail Survivability</span></span>

<span data-ttu-id="85ee8-189">通常、Exchange ユニファイドメッセージング (UM) は、ブランチサイトではなくセントラルサイトにのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-189">Exchange Unified Messaging (UM) is usually installed only at a central site and not at branch sites.</span></span> <span data-ttu-id="85ee8-190">ブランチ サイトと中央サイトの間で WAN リンクを使用できない場合でも、発信者がボイス メール メッセージを残すことをできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-190">A caller should be able to leave a voice mail message, even if the WAN link between branch site and central site is unavailable.</span></span> <span data-ttu-id="85ee8-191">結果として、ブランチサイトユーザーのボイスメールを提供する Exchange UM 自動応答の電話番号の行 URI を構成するには、そのボイスメールに適用される音声ポリシー、ダイヤルプラン、正規化ルールに加えて、特別な考慮事項が必要です。単位.</span><span class="sxs-lookup"><span data-stu-id="85ee8-191">As a result, configuring the Line URI for the Exchange UM Auto Attendant phone number that provides voice mail for branch site users requires special considerations, in addition to the voice policy, dial plan, and normalization rules applicable to that voice mail number.</span></span>

<span data-ttu-id="85ee8-192">Survivable Branch アプライアンス (SBAs) と Survivable ブランチサーバーは、WAN の停止中に支店のユーザー向けにボイスメール survivability を提供します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-192">Survivable Branch Appliances (SBAs) and Survivable Branch Servers provide voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="85ee8-193">特に、Survivable Branch Appliance または Survivable Branch Server を使用していて、WAN が利用できなくなった場合、SBA または Survivable ブランチサーバーは、PSTN 経由で、不在着信した通話を中央サイトの Exchange UM に再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-193">Specifically, if you are using a Survivable Branch Appliance or Survivable Branch Server and the WAN becomes unavailable, the SBA or Survivable Branch Server reroutes unanswered calls over the PSTN to Exchange UM at the central site.</span></span> <span data-ttu-id="85ee8-194">SBA または Survivable ブランチサーバーでは、ユーザーは、WAN の停止中に PSTN 経由でボイスメールメッセージを受信することもできます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-194">With a SBA or Survivable Branch Server, users can also retrieve voice mail messages through the PSTN during a WAN outage.</span></span> <span data-ttu-id="85ee8-195">最後に、WAN の停止中に、Survivable Branch Appliance または Survivable Branch Server は、不在着信通知をキューに置いて、WAN が復元されたときにそれらを Exchange UM サーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-195">Finally, during a WAN outage the Survivable Branch Appliance or Survivable Branch Server queues missed-call notifications and then uploads them to the Exchange UM server when the WAN is restored.</span></span> <span data-ttu-id="85ee8-196">ボイスメールの再ルーティングが確実に復元されるようにするには、セントラルサイトプールの FQDN と、エッジサーバーの FQDN のエントリを、Survivable Branch Server 上の hosts ファイルに追加してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-196">To help ensure that voice mail rerouting is resilient, be sure that you add an entry for the central site pool’s FQDN and an entry for the Edge Server FQDN to the hosts file on the Survivable Branch Server.</span></span> <span data-ttu-id="85ee8-197">そうしないと、ブランチサイトに DNS サーバーがない場合に、DNS 解決がタイムアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-197">Otherwise, DNS resolution can time out if you do not have a DNS server at the branch site.</span></span>

<span data-ttu-id="85ee8-198">ブランチ サイトのユーザーに対してボイス メールの存続性を構成するには、次のような構成が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-198">We recommend the following configurations for voice mail survivability for branch site users:</span></span>

  - <span data-ttu-id="85ee8-199">Microsoft Exchange 管理者は、Exchange UM 自動応答 (AA) でメッセージのみを受け入れるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-199">An Microsoft Exchange administrator should configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span> <span data-ttu-id="85ee8-200">この構成により、ユーザーへの転送やオペレーターへの転送など、その他の一般的な機能がすべて無効になり、自動応答 (AA) をメッセージの受け取りのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-200">This configuration disables all other generic functionality, such as transfer to a user or transfer to an operator, and limits the AA to only accepting messages.</span></span> <span data-ttu-id="85ee8-201">または、Exchange の管理者は、汎用の自動応答 (AA) を使ったり、自動応答 (AA) をカスタマイズしたりして、通話をオペレーターへルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-201">Alternatively, the Exchange administrator can use a generic AA or an AA customized to route the call to an operator.</span></span>

  - <span data-ttu-id="85ee8-202">Lync Server の管理者は、AA の電話番号を取得し、Survivable Branch Appliance またはブランチサーバーのボイスメールの再ルーティング設定で、その電話番号を**exchange um 自動応答**番号として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-202">The Lync Server administrator should take the AA phone number and use that phone number as the **exchange um auto attendant** number in the voice mail rerouting settings for the Survivable Branch Appliance or branch server.</span></span>

  - <span data-ttu-id="85ee8-203">Lync Server の管理者は、Exchange UM サブスクライバーアクセス用の電話番号を取得し、Survivable Branch Appliance または Survivable ブランチサーバーのボイスメール再ルーティング設定で、**サブスクライバーのアクセス**番号としてその番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-203">The Lync Server administrator should get the Exchange UM subscriber access phone number and use that number as the **subscriber access** number in the voice mail rerouting settings for the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="85ee8-204">Lync Server 管理者は、WAN の停止中にボイスメールへのアクセスを必要とするすべての支店ユーザーと関連付けられるダイヤルプランが1つだけであるように、Exchange UM を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-204">The Lync Server administrator should configure Exchange UM so that only one dial plan is associated with all branch users who need access to voice mail during a WAN outage.</span></span>

  - <span data-ttu-id="85ee8-205">WAN リンクを使用できない場合、ブランチ サイトのユーザーとの通話をユーザーの Exchange ユニファイド メッセージング (UM) ボイス メールボックスにルーティングできます。ただし、これは、その通話に適用される音声ポリシーに、内線番号を含まない一意のボイス メール電話番号が指定されている場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-205">When the WAN link is unavailable, calls to branch site users can be routed to the user’s Exchange Unified Messaging (UM) voice mailbox, but only if the voice policy applied to the call specifies a voice mail phone number that is unique and does not include an extension number.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a><span data-ttu-id="85ee8-206">ブランチ サイトの復元のハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="85ee8-206">Hardware and Software Requirements for Branch-Site Resiliency</span></span>

<span data-ttu-id="85ee8-207">ハードウェアおよびソフトウェア要件は、復元ソリューションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-207">The hardware and software requirements vary, depending on your resiliency solution.</span></span>

<div>

## <a name="requirements-for-survivable-branch-appliances"></a><span data-ttu-id="85ee8-208">存続可能ブランチ アプライアンスの要件</span><span class="sxs-lookup"><span data-stu-id="85ee8-208">Requirements for Survivable Branch Appliances</span></span>

<span data-ttu-id="85ee8-209">Survivable Branch アプライアンスには、必要なハードウェアとソフトウェアが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="85ee8-209">Required hardware and software is built into the Survivable Branch Appliance.</span></span> <span data-ttu-id="85ee8-210">ただし、各ブランチサイトでクライアントの IP アドレスを取得するために DHCP サーバーを展開することもお勧めします。そうしないと、DHCP リースの有効期限が切れると、クライアントに IP 接続ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-210">However, we also recommend that each branch site deploy a DHCP server to obtain client IP addresses; otherwise, when the DHCP lease expires, clients will not have IP connectivity.</span></span>

<span data-ttu-id="85ee8-211">エンタープライズ DNS サーバーがセントラルサイトのみにある場合、ブランチサイトユーザーは、WAN の停止中にそれらのサーバーに接続できず、DNS SRV (service (SRV) リソースレコード) を使用する Lync Server discovery は失敗します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-211">If the enterprise DNS servers are located only in central sites, branch site users will be unable to connect to them during a WAN outage, and therefore Lync Server discovery that uses DNS SRV (service (SRV) resource record) will fail.</span></span> <span data-ttu-id="85ee8-212">WAN の停止時に迅速に再ルーティングされるように、ブランチ サイトで DNS レコードをキャッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-212">To assure prompt rerouting during a WAN outage, DNS records must be cached at the branch site.</span></span> <span data-ttu-id="85ee8-213">ブランチのルーターが DNS キャッシュをサポートする場合は、DNS キャッシュを有効にします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-213">If the branch router supports it, turn on DNS caching.</span></span> <span data-ttu-id="85ee8-214">または、ブランチに DNS サーバーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-214">Or, you can deploy a DNS server at the branch.</span></span> <span data-ttu-id="85ee8-215">これは、スタンドアロンサーバーでも、DNS 機能をサポートする Survivable Branch アプライアンスのバージョンでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-215">This can be a stand-alone server or a version of the Survivable Branch Appliance that supports DNS capabilities.</span></span> <span data-ttu-id="85ee8-216">詳細については、Survivable Branch Appliance プロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-216">For details, contact your Survivable Branch Appliance provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85ee8-217">ブランチサイトにドメインコントローラーが存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-217">It is not necessary to have a domain controller at a branch site.</span></span> <span data-ttu-id="85ee8-218">Survivable Branch アプライアンスは、サインイン時にクライアントの証明書要求に応じてクライアントを送信する特別な証明書を使ってクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-218">The Survivable Branch Appliance authenticates clients by using a special certificate that it sends the client in response to the client’s certificate request when it signs in.</span></span>



</div>

<span data-ttu-id="85ee8-219">Lync クライアントは、DHCP オプション 120 (SIP レジストラーオプション) を使って Lync サーバーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-219">Lync clients can discover the Lync Server by using DHCP Option 120 (SIP Registrar Option).</span></span> <span data-ttu-id="85ee8-220">これは、次の 2 つのいずれかの方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="85ee8-220">This can be configured in one of two ways:</span></span>

  - <span data-ttu-id="85ee8-221">Survivable Branch Appliance または Survivable Branch Server で、レジストラーの FQDN を返す DHCP 120 クエリに応答するように、ブランチサイトで DHCP サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-221">Configure the DHCP server at the branch site to reply to DHCP 120 queries, which return the FQDN of the Registrar on the Survivable Branch Appliance or Survivable Branch Server.</span></span>

  - <span data-ttu-id="85ee8-222">Lync Server DHCP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="85ee8-222">Turn on Lync Server DHCP.</span></span> <span data-ttu-id="85ee8-223">この設定を有効にすると、Lync Server レジストラーは DHCP オプション120クエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="85ee8-223">When this is turned on, the Lync Server Registrar responds to DHCP Option 120 queries.</span></span> <span data-ttu-id="85ee8-224">レジストラーは、DHCP オプション 120 以外の DHCP クエリには応答しません。</span><span class="sxs-lookup"><span data-stu-id="85ee8-224">Note that the Registrar does not respond to any DHCP queries other than DHCP Options 120.</span></span>

<span data-ttu-id="85ee8-225">また、より大きなブランチ サイトで複数のサブネットがある場合は、DHCP オプション 120 のクエリが DHCP サーバー (構成 1) またはレジストラー (構成 2) に転送されるように、DHCP リレー エージェントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-225">Additionally, for larger branch sites that have multiple subnets, DHCP relay agents should be enabled to forward DHCP Option 120 queries to the DHCP Server (configuration 1) or to the Registrar (configuration 2).</span></span>

<span data-ttu-id="85ee8-226">最後に、ブランチサイトユーザーはエンタープライズ Voip 用に構成し、適切なユニファイドコミュニケーションエンドポイントを使用してプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ee8-226">Finally, branch site users must be configured for Enterprise Voice and provisioned with an appropriate unified communications endpoint.</span></span>

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a><span data-ttu-id="85ee8-227">存続可能ブランチ サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="85ee8-227">Requirements for Survivable Branch Servers</span></span>

<span data-ttu-id="85ee8-228">Survivable ブランチサーバーの要件は、フロントエンドサーバーの要件と同じです。</span><span class="sxs-lookup"><span data-stu-id="85ee8-228">The requirements for Survivable Branch Servers are the same as the requirements for a Front End Server.</span></span> <span data-ttu-id="85ee8-229">詳細については、計画ドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-229">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a><span data-ttu-id="85ee8-230">フルスケールの Lync Server ブランチサイト展開の要件</span><span class="sxs-lookup"><span data-stu-id="85ee8-230">Requirements for Full-Scale Lync Server Branch-Site Deployments</span></span>

<span data-ttu-id="85ee8-231">詳細については、計画ドキュメントで「 [Lync Server 2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ee8-231">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

