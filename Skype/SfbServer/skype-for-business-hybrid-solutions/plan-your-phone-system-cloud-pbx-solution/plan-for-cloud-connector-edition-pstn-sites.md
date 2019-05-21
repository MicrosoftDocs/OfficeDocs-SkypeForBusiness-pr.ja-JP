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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: このトピックでは、クラウドコネクタエディションの PSTN サイトを計画して、効率的でコスト効率の高い通話ルーティングを実現する方法について説明します。
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287035"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="037cc-103">Cloud Connector エディション PSTN サイトの計画</span><span class="sxs-lookup"><span data-stu-id="037cc-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="037cc-104">このトピックでは、クラウドコネクタエディションの PSTN サイトを計画して、効率的でコスト効率の高い通話ルーティングを実現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="037cc-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="037cc-105">このトピックでは、Cloud connector のバージョンと通話ルーティングについて知っておく必要があることについて説明します。これにより、クラウドコネクタの PSTN サイトを計画することができます。</span><span class="sxs-lookup"><span data-stu-id="037cc-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="037cc-106">PSTN サイトは、クラウドコネクタアプライアンスの組み合わせであり、同じ場所に展開され、共通の PSTN ゲートウェイが接続されています。</span><span class="sxs-lookup"><span data-stu-id="037cc-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="037cc-107">このトピックでは、クラウドコネクタサイトトポロジを設定して、最もコスト効率と効果的な方法でサイトに割り当てられているすべてのユーザーに対して、受信と送信の両方のルーティングを処理できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="037cc-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="037cc-108">クラウドコネクタと PSTN サイトの利点の詳細については、「 [Skype For Business Cloud Connector のエディションの計画](plan-skype-for-business-cloud-connector-edition.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="037cc-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="037cc-109">Cloud Connector PSTN サイトと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="037cc-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="037cc-110">クラウドコネクタの PSTN サイトは、不必要な長距離および国内間の料金を防ぐために作成されたトポロジ構成要素であり、発信緊急通話が適切なトランクにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="037cc-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="037cc-111">緊急電話サービスへの通話を含む、コスト効率の高い効率的なルーティングを実現するには、PSTN サイトと各サイトへのユーザーの割り当てを慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="037cc-112">クラウドコネクタの計画の一環として、オフィスとユーザーの所在地と PSTN trunks がキャリアから終了する場所について、お客さまの通信業者に相談することが重要です。</span><span class="sxs-lookup"><span data-stu-id="037cc-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="037cc-113">緊急電話をどのようにルーティングできるかを判断するには、配送業者と協力し、その情報を使ってクラウドコネクタ PSTN サイトを定義し、ユーザーを適切なサイトに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="037cc-114">たとえば、PSTN サイトが拡張されているデータセンターで終了する trunks は、そのサイトのユーザーに割り当てられているすべての番号について、受信と送信の両方のルーティングを処理するように構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="037cc-115">各クラウドコネクタアプライアンスは、複数の IP ゲートウェイ、IP Pbx、またはセッション境界コントローラー (SBCs) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="037cc-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="037cc-116">ゲートウェイと Pbx は電気通信 trunks (PRI または SIP trunks) に接続されているため、受信と発信の通話には、クラウドコネクタのアプライアンスは PSTN trunks に論理的に接続されています。</span><span class="sxs-lookup"><span data-stu-id="037cc-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="037cc-117">クラウドコネクタとオンプレミスの PSTN 接続を使うと、ローカルの通信事業者からトランクと関連する電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="037cc-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="037cc-118">企業が大企業の場合は、複数の電話会社が存在する可能性があります。特に、ビジネスが複数の市区町村、州、または国にわたる場合です。</span><span class="sxs-lookup"><span data-stu-id="037cc-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="037cc-119">電話会社が電話番号を所有しているため、電話会社は緊急通話の処理を担当しています。</span><span class="sxs-lookup"><span data-stu-id="037cc-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="037cc-120">Skype for Business Online は、サイト内のすべてのクラウドコネクタのアプライアンスを平等に処理し、同一サイト内のクラウドコネクタアプライアンスに対して、発信通話をローテーション方式でルーティングします。</span><span class="sxs-lookup"><span data-stu-id="037cc-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="037cc-121">サイト内の各クラウドコネクタは、同じ PSTN trunks のセット (完全にメッシュ) に相互接続されています。</span><span class="sxs-lookup"><span data-stu-id="037cc-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="037cc-122">各ユーザーは、クラウドコネクタ PSTN サイトに関連付けられているため、そのユーザー (通常または緊急) からのすべての発信通話は、ユーザーが関連付けられている PSTN サイト内のクラウドコネクタアプライアンスのいずれかに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="037cc-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="037cc-123">クラウドコネクタは、接続されている IP ゲートウェイ、IP Pbx、SBCs、または直接 PSTN trunks への静的な通話ルーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="037cc-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="037cc-124">クラウドコネクタは、発信先に基づくトランクへの動的ルーティングを行うことはできません (コストの最小ルーティングの場合)。または、発信元 (静的または動的な緊急通話) に基づいています。</span><span class="sxs-lookup"><span data-stu-id="037cc-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="037cc-125">通話は、その番号に関連付けられているトランクからのみ発信可能であるため、着信通話は問題になりません。</span><span class="sxs-lookup"><span data-stu-id="037cc-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="037cc-126">ただし、発信通話は、サイト内の任意のクラウドコネクタアプライアンスに移動できます。また、そのクラウドコネクタアプライアンスに接続されている PSTN trunks を使用すると、不要な長距離通話が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="037cc-127">さらに、クラウドコネクタの PSTN サイトが、さまざまな市外局番または携帯電話の複数のデータセンターで拡張されている場合は、緊急通話は実行されません。</span><span class="sxs-lookup"><span data-stu-id="037cc-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="037cc-128">例</span><span class="sxs-lookup"><span data-stu-id="037cc-128">An example</span></span>

<span data-ttu-id="037cc-129">次の例は、trunks を PSTN サイトにグループ化する方法と、サイトにユーザーを割り当てる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="037cc-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="037cc-130">Contoso の会社では、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="037cc-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="037cc-131">次の4人のユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="037cc-131">There are four users:</span></span> 
    
  - <span data-ttu-id="037cc-132">米国レドモンドワシントン州のユーザー A</span><span class="sxs-lookup"><span data-stu-id="037cc-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="037cc-133">恵比寿 WA (米国) のユーザー B</span><span class="sxs-lookup"><span data-stu-id="037cc-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="037cc-134">Centralia WA (USA) のユーザー C</span><span class="sxs-lookup"><span data-stu-id="037cc-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="037cc-135">ユーザー D (ポートランドまたは米国)</span><span class="sxs-lookup"><span data-stu-id="037cc-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="037cc-136">電話会社 A には、次の電話番号と trunks が用意されています。</span><span class="sxs-lookup"><span data-stu-id="037cc-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="037cc-137">レドモンド (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="037cc-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="037cc-138">恵比寿 (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="037cc-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="037cc-139">Centralia (市外局番 360)</span><span class="sxs-lookup"><span data-stu-id="037cc-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="037cc-140">電話会社 B は、次の電話番号と trunks を提供します。</span><span class="sxs-lookup"><span data-stu-id="037cc-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="037cc-141">ポートランド (市外局番 503)</span><span class="sxs-lookup"><span data-stu-id="037cc-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="037cc-142">ユーザー A は、Redmond (データセンター A) とユーザー B (データセンター B) が互いに隣り合っていて、同じ市外局番 (425) であるため、航空会社 A は、恵比寿のトランクで、Redmond のユーザー A から緊急電話を受けることができるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="037cc-143">その結果、ユーザー A と B、および恵比寿とレドモンドのクラウドコネクタ trunks は、次の図に示すように、同じクラウドコネクタ PSTN サイトに存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="037cc-144">1つのオフィスのユーザーからの緊急通話は、trunks にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="037cc-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="037cc-145">ただし、ご利用の電話会社にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="037cc-145">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN サイトをセットアップする方法](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="037cc-147">次の例も参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="037cc-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="037cc-148">Centralia のユーザー C は、電話会社 A によって番号が指定されていますが、2時間のドライブは離れていて、別の市外局番 (360) では、恵比寿とレドモンドの425市外局番のユーザーを他の通信事業者から提供されています。</span><span class="sxs-lookup"><span data-stu-id="037cc-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="037cc-149">そのため、通話が航空会社 A から発信されている場合でも、Centralia 市外局番360の電話会社の通話ルーティングソフトウェアは、恵比寿市外局番425のユーザー B から発信された緊急通話を拒否する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="037cc-150">この場合、通信事業者は、Centralia PSTN サイト内のクラウドコネクタとそれに関連付けられている trunks が、距離と市外局番を介しての通話を処理できることを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="037cc-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="037cc-151">ポートランドのユーザー D は、電話会社 B によって提供される番号とトランクを使用しているため、通信事業者 A が所有している電話番号から緊急電話を受けることはほとんどありません。このため、ポートランドのユーザー D とクラウドコネクタのアプライアンスおよび関連する trunks は、別の PSTN サイトに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="037cc-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

