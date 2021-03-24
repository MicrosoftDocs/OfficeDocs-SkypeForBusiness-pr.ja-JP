---
title: クラウド コネクタ エディション PSTN サイトの計画
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: このトピックでは、効率的でコスト効率の高い通話ルーティングを実現するためにクラウド コネクタ エディション PSTN サイトを計画する方法について説明します。
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096231"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="33ecb-103">クラウド コネクタ エディション PSTN サイトの計画</span><span class="sxs-lookup"><span data-stu-id="33ecb-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="33ecb-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="33ecb-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="33ecb-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="33ecb-106">このトピックでは、効率的でコスト効率の高い通話ルーティングを実現するためにクラウド コネクタ エディション PSTN サイトを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="33ecb-107">このトピックでは、クラウド コネクタ PSTN サイトを計画するために、クラウド コネクタエディションと通話ルーティングについて知る必要がある内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="33ecb-108">PSTN サイトは、クラウド コネクタ アプライアンスの組み合わせで、同じ場所に展開され、共通の PSTN ゲートウェイが接続されています。</span><span class="sxs-lookup"><span data-stu-id="33ecb-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="33ecb-109">このトピックでは、クラウド コネクタ サイト トポロジをセットアップして、可能な限り最もコスト効率が高く効果的な方法でサイトに割り当てられているすべてのユーザーに対して、クラウド コネクタ サイトが受信ルーティングと送信ルーティングの両方を処理できる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="33ecb-110">クラウド コネクタと PSTN サイトの利点の詳細については [、「Plan for Skype for Business Cloud Connector Edition」を参照してください](plan-skype-for-business-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="33ecb-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="33ecb-111">クラウド コネクタ PSTN サイトと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="33ecb-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="33ecb-112">クラウド コネクタ PSTN サイトは、不要な長距離および国間の料金を防止し、発信緊急通話が適切なトランクにルーティングされるのを防ぐために作成されたトポロジ構造です。</span><span class="sxs-lookup"><span data-stu-id="33ecb-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="33ecb-113">緊急サービスへの呼び出しを含む、コスト効率の高い効率的な通話ルーティングを実現するには、PSTN サイトとユーザーが各サイトに割り当てられている方法を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="33ecb-114">クラウド コネクタの計画の一環として、オフィスとユーザーの場所、および PSTN トランクが通信事業者から終了する場所について、通信事業者に相談する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="33ecb-115">通信事業者と一緒に緊急通話のルーティング方法を決定し、その情報を使用してクラウド コネクタ PSTN サイトを定義し、ユーザーを適切なサイトに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="33ecb-116">たとえば、PSTN サイトがストレッチされているデータセンターで終了するトランクが、そのサイトでユーザーに割り当てられたすべての番号の受信ルーティングと送信ルーティングの両方を処理するように構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="33ecb-117">各クラウド コネクタ アプライアンスは、複数の IP ゲートウェイ、IP PBX、またはセッション ボーダー コントローラー (SBC) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="33ecb-118">ゲートウェイと PBX は電話会社のトランク (PRI または SIP トランク) に接続されています。クラウド コネクタ アプライアンスは、着信および発信通話用の PSTN トランクに論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="33ecb-119">クラウド コネクタとオンプレミス PSTN 接続を使用すると、トランクと関連付けられた電話番号をローカルキャリアから取得します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="33ecb-120">ビジネスが大規模な企業の場合は、複数の通信事業者 (特に、複数の都市、州、または国にまたがる場合) が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="33ecb-121">通信事業者が電話番号を所有している場合、通信事業者は緊急電話の処理を担当します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="33ecb-122">Skype for Business Online は、サイト内のすべてのクラウド コネクタ アプライアンスを均等に処理し、同じサイト内のクラウド コネクタ アプライアンスに、ローテーションベースで発信呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="33ecb-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="33ecb-123">サイト内の各クラウド コネクタは、同じ PSTN トランクセット (完全メッシュ) にクロス接続されます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="33ecb-124">各ユーザーはクラウド コネクタ PSTN サイトに関連付けられているため、そのユーザーからの発信呼び出し (通常または緊急) は、ユーザーが関連付けられている PSTN サイトのクラウド コネクタ アプライアンスの 1 つに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="33ecb-125">クラウド コネクタは、接続された IP ゲートウェイ、IP-PBX、SBC、または直接 PSTN トランクへの静的通話ルーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="33ecb-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="33ecb-126">クラウド コネクタは、宛先 (最小コストのルーティング) または発信元 (静的または動的緊急通話) に基づくトランクへの動的ルーティングがまだできません。</span><span class="sxs-lookup"><span data-stu-id="33ecb-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="33ecb-127">着信呼び出しは、番号に関連付けられたトランクからのみ発生するため、問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="33ecb-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="33ecb-128">ただし、発信呼び出しは、サイト内の任意のクラウド コネクタ アプライアンス (および、そのクラウド コネクタ アプライアンスに接続されている PSTN トランクを拡張して) に移動し、望ましくない長距離通話を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="33ecb-129">さらに、クラウド コネクタ PSTN サイトが異なるエリア コードまたは通信事業者を持つデータセンター全体に広がっている場合、緊急通話は通過しません。</span><span class="sxs-lookup"><span data-stu-id="33ecb-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="33ecb-130">例</span><span class="sxs-lookup"><span data-stu-id="33ecb-130">An example</span></span>

<span data-ttu-id="33ecb-131">次の例は、PSTN サイトにトランクをグループ化する方法と、ユーザーをサイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="33ecb-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="33ecb-132">Contoso 社の場合、次の条件を満たします。</span><span class="sxs-lookup"><span data-stu-id="33ecb-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="33ecb-133">ユーザーは 4 人です。</span><span class="sxs-lookup"><span data-stu-id="33ecb-133">There are four users:</span></span> 
    
  - <span data-ttu-id="33ecb-134">Redmond WA のユーザー A (米国)</span><span class="sxs-lookup"><span data-stu-id="33ecb-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="33ecb-135">Bellevue WA のユーザー B (米国)</span><span class="sxs-lookup"><span data-stu-id="33ecb-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="33ecb-136">Centralia WA のユーザー C (米国)</span><span class="sxs-lookup"><span data-stu-id="33ecb-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="33ecb-137">ポートランド OR のユーザー D (米国)</span><span class="sxs-lookup"><span data-stu-id="33ecb-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="33ecb-138">キャリア A は、次の電話番号とトランクを提供します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="33ecb-139">Redmond (市外コード 425)</span><span class="sxs-lookup"><span data-stu-id="33ecb-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="33ecb-140">Bellevue (市域コード 425)</span><span class="sxs-lookup"><span data-stu-id="33ecb-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="33ecb-141">Centralia (市域コード 360)</span><span class="sxs-lookup"><span data-stu-id="33ecb-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="33ecb-142">キャリア B は、次の電話番号とトランクを提供します。</span><span class="sxs-lookup"><span data-stu-id="33ecb-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="33ecb-143">ポートランド (市域コード 503)</span><span class="sxs-lookup"><span data-stu-id="33ecb-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="33ecb-144">Redmond (Data Center A) のユーザー A と Bellevue (Data Center B) のユーザー B が隣り合って同じ市外局コード (425) にあるため、キャリア A はベルビューのトランクで Redmond のユーザー A から緊急通話を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="33ecb-145">したがって、ユーザー A と B、および Bellevue と Redmond のクラウド コネクタ トランクは、次の図に示すように、同じクラウド コネクタ PSTN サイトにある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="33ecb-146">あるオフィスのユーザーからの緊急通話は、もう一方のオフィスのトランクにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="33ecb-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="33ecb-147">ただし、これが機能する場合は、通信事業者に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-147">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN サイトを設定する方法](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="33ecb-149">次の例も考慮してください。</span><span class="sxs-lookup"><span data-stu-id="33ecb-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="33ecb-150">Centralia のユーザー C は、その番号がキャリア A によって提供され、車で 2 時間、ベルビューと Redmond 425 エリア コードの他のキャリア A ユーザーとは別の市外コード (360) です。</span><span class="sxs-lookup"><span data-stu-id="33ecb-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="33ecb-151">したがって、通話がキャリア A から発信されている場合でも、Centralia エリア コード 360 の通信事業者の通話ルーティング ソフトウェアが、ベルビューエリア コード 425 のユーザー B から発信される着信緊急通話を拒否する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="33ecb-152">この場合、通信事業者は、Centralia PSTN サイト内のクラウド コネクタとその関連トランクが、距離とエリア コードを越えて通話を処理できると確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="33ecb-153">ポートランドのユーザー D は、キャリア B が提供する番号とトランクを使用します。そのため、キャリア B がキャリア A が所有する電話番号から緊急電話を受け取る可能性は非常に低い。そのため、ユーザー D とクラウド コネクタ アプライアンス、およびポートランドの関連トランクは、別の PSTN サイトにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33ecb-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
