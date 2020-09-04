---
title: Cloud Connector エディション PSTN サイトの計画
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
description: このトピックでは、効率的で費用効果の高い通話ルーティングを実現するために、Cloud Connector エディションの PSTN サイトを計画する方法について説明します。
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358803"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="4ebfd-103">Cloud Connector エディション PSTN サイトの計画</span><span class="sxs-lookup"><span data-stu-id="4ebfd-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="4ebfd-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4ebfd-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="4ebfd-106">このトピックでは、効率的で費用効果の高い通話ルーティングを実現するために、Cloud Connector エディションの PSTN サイトを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="4ebfd-107">このトピックでは、Cloud Connector の PSTN サイトを計画できるようにするために、Cloud Connector エディションと通話ルーティングについて知っておく必要のある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="4ebfd-108">PSTN サイトは、クラウドコネクタアプライアンスを組み合わせたもので、同じ場所に展開され、共通の PSTN ゲートウェイが接続されています。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="4ebfd-109">このトピックでは、クラウドコネクタサイトトポロジを設定して、サイトに割り当てられているすべてのユーザーについて、最もコスト効率と効果的な方法で受信と送信の両方のルーティングを処理できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="4ebfd-110">Cloud Connector および PSTN サイトの利点の詳細については、「Plan for [Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="4ebfd-111">Cloud Connector PSTN サイトと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="4ebfd-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="4ebfd-112">Cloud Connector PSTN サイトは、不必要な長距離および国内間 tariffs を防止するために作成されたトポロジ構成要素で、送信緊急電話が適切なトランクにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="4ebfd-113">緊急サービスへの通話を含む、通話の費用効果の高い効率的なルーティングを実現するには、PSTN サイトと各サイトへのユーザーの割り当て方法を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="4ebfd-114">Cloud Connector の計画の一環として、オフィスとユーザーの所在地や、PSTN トランクがキャリアから終了する場所について、carrier に連絡することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="4ebfd-115">緊急通話をルーティングする方法を決定するために、配送業者と協力して、その情報を使用して Cloud Connector PSTN サイトを定義し、ユーザーを適切なサイトに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="4ebfd-116">たとえば、PSTN サイトが拡張されたデータセンターで終了するトランクが、そのサイトのユーザーに割り当てられたすべての番号について、受信および送信ルーティングの両方を処理するように構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="4ebfd-117">各 Cloud Connector アプライアンスは、複数の IP ゲートウェイ、IP Pbx、またはセッションボーダーコントローラー (sbc) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="4ebfd-118">ゲートウェイと Pbx は、電話会社のトランク (PRI または SIP トランク) に接続されているため、クラウドコネクタアプライアンスは、着信および発信通話の PSTN トランクに論理的に接続されています。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="4ebfd-119">Cloud Connector とオンプレミスの PSTN 接続を使用して、トランクおよび関連する電話番号をローカルの通信事業者から取得します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="4ebfd-120">企業が大規模な企業の場合は、複数の電話会社が存在することがあります。特に、事業者が複数の市区町村、州、または国を対象としている場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="4ebfd-121">Carrier は電話番号を所有しているため、電話会社は緊急電話の処理を担当します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="4ebfd-122">Skype for Business Online は、サイト内のすべての Cloud Connector アプライアンスを均等に扱っており、同じサイト内の Cloud Connector アプライアンスに対して、発信通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="4ebfd-123">サイト内の各 Cloud Connector は、PSTN トランクの同じセットに交差しています (完全にメッシュ化されています)。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="4ebfd-124">各ユーザーは Cloud Connector PSTN サイトに関連付けられているため、そのユーザーからの発信通話 (通常または緊急) は、ユーザーが関連付けられている PSTN サイト内の Cloud Connector アプライアンスの1つに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="4ebfd-125">Cloud Connector は、接続されている IP ゲートウェイ、IP-PBX、または直接 PSTN トランクに対して静的な通話ルーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="4ebfd-126">Cloud Connector は、接続先 (最小コストルーティング) または発信元 (静的または動的な緊急通話) に基づいて、トランクへの動的ルーティングがまだできません。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="4ebfd-127">通話は番号に関連付けられたトランクからのみ取得できるため、着信呼び出しは問題になりません。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="4ebfd-128">ただし、発信通話は、サイト内の任意の Cloud Connector アプライアンス (およびその Cloud Connector アプライアンスに接続されている PSTN トランク) にアクセスできます。これにより、不要な長距離電話が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="4ebfd-129">さらに、クラウドコネクタの PSTN サイトが異なるエリアコードまたは通信事業者を使用してデータセンター間でストレッチされている場合、緊急通話は行われません。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="4ebfd-130">例</span><span class="sxs-lookup"><span data-stu-id="4ebfd-130">An example</span></span>

<span data-ttu-id="4ebfd-131">次の例は、トランクを PSTN サイトにグループ化する方法と、ユーザーをサイトに割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="4ebfd-132">Contoso 社の場合、以下のことを想定します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="4ebfd-133">次の4人のユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-133">There are four users:</span></span> 
    
  - <span data-ttu-id="4ebfd-134">Redmond ワシントン州のユーザー A (米国)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="4ebfd-135">べレビュー WA のユーザー B (米国)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="4ebfd-136">セントラリア WA のユーザー C (米国)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="4ebfd-137">ポートランドまたは (米国) のユーザー D</span><span class="sxs-lookup"><span data-stu-id="4ebfd-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="4ebfd-138">Carrier A は、電話番号とトランクを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="4ebfd-139">Redmond (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="4ebfd-140">べレビュー (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="4ebfd-141">セントラリア (市外局番 360)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="4ebfd-142">Carrier B は電話番号とトランクを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="4ebfd-143">ポートランド (市外局番 503)</span><span class="sxs-lookup"><span data-stu-id="4ebfd-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="4ebfd-144">Redmond のユーザー A (データセンター A) とべレビュー (データセンター B) のユーザー B が相互に隣接していて、同じ市外局番 (425) に含まれているため、Carrier A は、べレビューのトランクにある Redmond のユーザー A から緊急電話を受けることができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="4ebfd-145">その結果、ユーザー A と B、およびべレビューとレドモンドの Cloud Connector トランクは、次の図に示すように、同じ Cloud Connector PSTN サイトに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="4ebfd-146">あるオフィスのユーザーからの緊急電話は、もう一方のトランクにルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="4ebfd-147">ただし、これが機能することをキャリアに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-147">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN サイトをセットアップする方法](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="4ebfd-149">次の例も考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="4ebfd-150">セントラリアのユーザー C。これは、電話会社 A によって番号が提供されており、他の電話会社からべレビューおよび Redmond 425 の市外局番に入っているユーザーとは異なる市外局番 (360) で提供されています。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="4ebfd-151">そのため、通話が Carrier A から来たとしても、セントラリア area code 360 のキャリアの通話ルーティングソフトウェアは、べレビューエリアコード425のユーザー B からの着信緊急電話を拒否する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="4ebfd-152">この場合、電話会社は、セントラリア PSTN サイト内の Cloud Connector とそれに関連付けられているトランクが距離と市外局番を越えて通話を処理できることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="4ebfd-153">ポートランドのユーザー D は、Carrier B によって提供される番号とトランクを使用しているため、carrier A が所有する電話番号からの緊急電話が必要になる可能性が高くなります。そのため、ユーザー D および Cloud Connector アプライアンスと、ポートランドに関連付けられているトランクは、別の PSTN サイトに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ebfd-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

