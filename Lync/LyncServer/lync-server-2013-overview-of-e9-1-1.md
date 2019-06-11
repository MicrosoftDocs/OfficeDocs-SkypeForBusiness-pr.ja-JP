---
title: 'Lync Server 2013: E9-1-1 の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="8ad2a-102">Lync Server 2013 の E9-1-1 の概要</span><span class="sxs-lookup"><span data-stu-id="8ad2a-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ad2a-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="8ad2a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="8ad2a-104">Microsoft Lync Server 2013 は、Lync クライアントおよび Lync Phone Edition デバイスからの拡張 9-1-1 (E9) 通話をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="8ad2a-105">Lync Server for E9-1-1 を構成すると、Lync 2013 または Lync Phone Edition から発信された緊急通報の情報が、場所情報サービスデータベースから発信されます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="8ad2a-106">ERLs は、事務所の建物やその他のマルチテナント機能のより正確な場所を特定するのに役立つ、市民 (つまり、番地) とその他の情報で構成されています。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="8ad2a-107">ユーザーが緊急通話を発信すると、Lync Server は、仲介サーバー経由で E9 1-1 サービスプロバイダーに通話の音声を転送します。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="8ad2a-108">E9 サービスプロバイダーは、呼び出し元の都市のアドレスを使って、発信者の位置情報を提供している公共の安全性応答ポイント (PSAP) に呼び出しをルーティングし、さらに、PSAP が呼び出し元の ERL を検索するために使用する緊急サービスクエリキー (ESQK) を送信します。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="8ad2a-109">Lync Server では、E9 サービスプロバイダーへの緊急通話のルーティング方法として、次の2つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="8ad2a-110">対象となる E9-1-1 サービス プロバイダーへのセッション開始プロトコル (SIP) トランク接続</span><span class="sxs-lookup"><span data-stu-id="8ad2a-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="8ad2a-111">公衆交換電話網 (PSTN) ベースの E9-1-1 サービス プロバイダーへの緊急位置識別番号 (ELIN) ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="8ad2a-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="8ad2a-112">SIP トランク E9 サービスプロバイダを使用する場合は、Location Information service データベースに ERLs を追加してから、E9 サービスプロバイダーによって管理されているマスターの住所ガイド (MSAG) に対して場所を検証します。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="8ad2a-113">ロケーション情報を含まない通話、またはロケーションが MSAG で確認されていない通話を受けた場合、E9-1-1 サービス プロバイダーは、可能であれば、発信者のロケーションを口頭で確認する特別な訓練を受けたスタッフがいる、国または地域の緊急通話応答センター (ECRC) に通話をルーティングしてから、適切な PSAP に手動でルーティングします (PSTN への Direct-Inward-Diaing (DID) 番号を顧客に提供している E9-1-1 サービス プロバイダーもあります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="8ad2a-114">この番号は、SIP トランクが何らかの理由で失敗した場合に 9-1-1 通話をルーティングするための代替手段となります)。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="8ad2a-115">Time ディビジョン多重 (TDM) と IP ベースの構内交換 (PBX) 電話とは異なり、Lync のエンドポイントは、非常にモバイルです。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="8ad2a-116">E9 機能を展開すると、発信者がどこにいるかに関係なく、Lync Server によって、発信者の位置情報を提供している PSAP に緊急通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="8ad2a-117">たとえば、本社がワシントン州レドモンドにあるユーザーがカンザス州ウィチタの支社のコンピューターから緊急電話をかけると、SIP トランクまたは PSTN ベースの E9-1-1 サービス プロバイダーは、その通話をレドモンドではなくウィチタの PSAP にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="8ad2a-118">ELIN ゲートウェイを使用している場合は、場所情報サービスデータベースに ERLs も追加しますが、それぞれの場所には ELIN 番号も含めます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="8ad2a-119">ELIN 番号は、緊急通話中の緊急通話番号になります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="8ad2a-120">その後で、使用する PSTN 事業者が ELIN を自動ロケーション識別 (ALI) データベースにアップロードすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ad2a-121">Lync に接続されたアナログデバイスでは、位置情報サービスから、または E9 のサービスプロバイダーへの送信場所に関する情報を受信できません。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="8ad2a-122">SIP トランク E9-1-1 サービス プロバイダー オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="8ad2a-123"><STRONG>従来の PS-ALI オプション</STRONG>&nbsp;&nbsp;&nbsp;アナログ電話が配備され、それぞれのアナログ電話があれば、各サイトにローカルの PSTN ゲートウェイがある場合は、プライベートスイッチを使って直接アナログデバイスの場所をプロビジョニングできます。位置情報の識別 (PS-ALI) サービスプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="8ad2a-124">この場合は、特別な細工をした Lync voice のポリシーを構成して、それらをアナログデバイスの連絡先オブジェクトに割り当てて、ローカルゲートウェイからサイトをサービスする PSTN プロバイダー (ルーティングされるのではなく、ローカルゲートウェイから) に直接通話を発信します。E9-1-1 サービスプロバイダ SIP トランクへの通話。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="8ad2a-125">緊急電話がかかってくると、PSTN トランクに関連付けられている PS-ALI プロバイダーのデータベースが各アナログ電話の DID を物理ロケーションにマッピングし、その場所を PSAP に提供します。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="8ad2a-126">これらのレコードは、電話が異なる ERL に移動するたびに、PS-ALI サービス プロバイダーが更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="8ad2a-127"><STRONG>E9 サービスプロバイダオプション</STRONG>&nbsp;&nbsp;&nbsp;: E9 サービスプロバイダでサポートされている場合は、アナログ電話の dids と、対応する erls を E9 サービスプロバイダに登録することができます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="8ad2a-128">プロバイダーが、PIDF データが含まれていない Lync Server からの通話を受信した場合、プロバイダーは、通話相手の DID 番号に一致するデータベースがあるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="8ad2a-129">データベースから取得した ERL を使うことで、プロバイダーは緊急通話を適切な PSAP に自動的にルーティングすることができます。また、PSAP は、ディスパッチャーが呼び出し元の場所を参照できるようにする、アナログデバイスと ESQK レコードを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="8ad2a-p108">ELIN ゲートウェイ オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、前述の 1 つ目のオプションで説明したように、アナログ機器のロケーションを直接 PS-ALI サービス プロバイダーに対してプロビジョニングすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="8ad2a-131">Lync Server の観点から、E9 プロセスは次の2つのステージに分けることができます。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="8ad2a-132">ステージ 1: 場所の取得</span><span class="sxs-lookup"><span data-stu-id="8ad2a-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="8ad2a-133">ステージ 2: E9-1-1 サービス プロバイダーへの緊急電話のルーティング</span><span class="sxs-lookup"><span data-stu-id="8ad2a-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="8ad2a-134">このセクションでは、これらのステージがどのように動作するのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-134">This section describes how these stages work.</span></span>

<span data-ttu-id="8ad2a-135">クライアントの場所を自動検出するようにインフラストラクチャを構成しようと計画している場合は、まず発信者を場所にマッピングするために使用するネットワーク構成要素を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="8ad2a-136">使用可能なオプションの詳細については、「 [Lync Server 2013 で場所を決定するために使用されるネットワーク要素を定義する](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad2a-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ad2a-137">このセクション中</span><span class="sxs-lookup"><span data-stu-id="8ad2a-137">In This Section</span></span>

  - [<span data-ttu-id="8ad2a-138">Lync Server 2013 での場所の取得</span><span class="sxs-lookup"><span data-stu-id="8ad2a-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="8ad2a-139">Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="8ad2a-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="8ad2a-140">Lync Server 2013 での ELIN ゲートウェイを使用した E9-1-1 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="8ad2a-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

