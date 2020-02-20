---
title: 'Lync Server 2013: ELIN ゲートウェイを使用した E9-1-1 通話のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e2e3bf94175f2f0ec3f4f7528cc969fe19529c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="52564-102">Lync Server 2013 の ELIN ゲートウェイを使用した E9-1-1 通話のルーティング</span><span class="sxs-lookup"><span data-stu-id="52564-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52564-103">_**トピックの最終更新日:** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="52564-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="52564-104">統合コミュニケーション相互運用プログラムの一部のパートナーは、正規の E9-1-1 サービス プロバイダーへの SIP トランク接続の代替としての機能を果たすことができる、緊急位置識別番号 (ELIN) 対応の正規のゲートウェイを提供しています。</span><span class="sxs-lookup"><span data-stu-id="52564-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="52564-105">ELIN ゲートウェイは、公衆交換電話網 (PSTN) ベースの E9-1-1 サービスへの ISDN 接続 または Centralized Automatic Message Accounting (CAMA) 接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="52564-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="52564-106">ELIN ゲートウェイとそのドキュメントへのリンクを提供するパートナーの詳細に[https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425)ついては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52564-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="52564-107">E9-1-1 サービスプロバイダーへの SIP トランク接続と同様に、ELIN ゲートウェイも、発信者が最も適切な公共の安全応答ポイント (PSAP) に緊急通話をルーティングする手段を提供します。ただし、これらのゲートウェイは、場所の識別子として ELIN を使用します。</span><span class="sxs-lookup"><span data-stu-id="52564-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="52564-108">組織内の各緊急対応の場所 (ERL) に ELINs を定義します (詳細については、「 [Lync Server 2013 で ELIN ゲートウェイの場所を管理](lync-server-2013-managing-locations-for-elin-gateways.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="52564-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="52564-109">緊急電話で ELIN ゲートウェイを使用する場合は、SIP トランク接続に使用するのと同じ Lync Server E9-1-1 インフラストラクチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="52564-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="52564-110">つまり、場所情報サービスデータベースによって Lync Server クライアントへの場所が提供され、場所のポリシーによって機能が有効になり、ルーティングが定義されます。</span><span class="sxs-lookup"><span data-stu-id="52564-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="52564-111">ただし、ELIN ゲートウェイを使用する場合は、場所情報サービスデータベースに ELINs を追加し、それを PSTN キャリアが自動場所識別 (ALI) データベースにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="52564-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="52564-112">Lync クライアントが場所情報サービスから場所を取得すると、その場所には ELIN が含まれます。</span><span class="sxs-lookup"><span data-stu-id="52564-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="52564-113">緊急通話時、ELIN ゲートウェイに送信される場所に ELIN が含まれています。</span><span class="sxs-lookup"><span data-stu-id="52564-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="52564-114">ELIN ゲートウェイが通話を緊急通話と認識すると、発信者の番号を ELIN に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="52564-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="52564-115">そして、ELIN を発信番号として、通話が PSTN にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="52564-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="52564-116">PSTN E9-1-1 プロバイダーでは、主要道路住所案内 (MSAG) データベースのコンパニオン データベースである ALI データベース内で ELIN を検索します。</span><span class="sxs-lookup"><span data-stu-id="52564-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="52564-117">ALI 検索に基づいて最適な PSAP に通話が送られ、ALI 検索に基づいて発信者の場所に最初の対応員が送られます。</span><span class="sxs-lookup"><span data-stu-id="52564-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="52564-118">発信番号は、コールバック用に、事前に定義された時間だけ、ELIN ゲートウェイ上にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="52564-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="52564-119">コールバック時には、PSAP が ELIN ゲートウェイにアクセスすると、そこで ELIN が発信者の Direct Inward Dialing (DID) 番号に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="52564-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="52564-120">ELIN ゲートウェイは、組織のネットワーク内からの緊急通話のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="52564-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="52564-121">ネットワーク外からの緊急通話はサポートしません。</span><span class="sxs-lookup"><span data-stu-id="52564-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52564-122">緊急通話での SIP トランク接続の使用の詳細については、「 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by Using Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52564-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="52564-123">次の図は、ELIN ゲートウェイを使用する場合に、Lync Server から PSAP への緊急通話のルーティング方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="52564-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="52564-124">**ELIN ゲートウェイを使用する場合の E9-1-1 通話のルーティング**</span><span class="sxs-lookup"><span data-stu-id="52564-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="52564-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="52564-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="52564-126">場所、発信者のコールバック番号、および (オプションで) 通知 URL と会議のコールバック番号を含む SIP INVITE が Lync Server にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="52564-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="52564-127">Lync Server は、緊急電話番号と一致し、(該当する場所のポリシーで定義されている**PSTN 使用法**の値に基づいて) 仲介サーバーに通話をルーティングし、そこから ELIN ゲートウェイに転送します。</span><span class="sxs-lookup"><span data-stu-id="52564-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="52564-128">ELIN ゲートウェイは、ISDN または CAMA トランク経由で PSTN に通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="52564-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="52564-p106">PSTN は通話を緊急通話と見なし、ネットワーク内で選択された E9-1-1 ルーターに通話をルーティングします。E9-1-1 ルーターは、ALI データベースで発信者の番号を検索して地理的な場所を取得します。E9-1-1 ルーターは、ALI データベースから取得した場所情報に基づいて最適な PSAP に通話を送信します。</span><span class="sxs-lookup"><span data-stu-id="52564-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="52564-132">通知の場所のポリシーを構成した場合は、1つまたは複数の組織のセキュリティ担当者に対して、特別な Lync 緊急通知インスタントメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="52564-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="52564-133">このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。</span><span class="sxs-lookup"><span data-stu-id="52564-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="52564-p108">通話が途中で終了した場合、PSAP は ELIN を使用して発信者に直接連絡します。ELIN ゲートウェイは、ELIN を発信者の DID に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="52564-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

