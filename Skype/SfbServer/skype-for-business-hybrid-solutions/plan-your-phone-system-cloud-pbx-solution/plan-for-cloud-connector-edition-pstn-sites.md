---
title: Cloud Connector エディション PSTN サイトの計画
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 効率的かつコスト ・ パフォーマンスの通話のルーティングを確認するのには、クラウド コネクタのエディションの PSTN のサイトを計画する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 4bf702314e46e1f8281ac6237dd8a7829900440e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897616"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="0fbd5-103">Cloud Connector エディション PSTN サイトの計画</span><span class="sxs-lookup"><span data-stu-id="0fbd5-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="0fbd5-104">効率的かつコスト ・ パフォーマンスの通話のルーティングを確認するのには、クラウド コネクタのエディションの PSTN のサイトを計画する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="0fbd5-105">このトピックでは、クラウドのコネクタのエディションを知るし、クラウドのコネクタの PSTN のサイトを計画することができますされるようにルーティングを呼び出すに必要なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="0fbd5-106">PSTN のサイトは、クラウドのコネクタのアプライアンスを使用して、共通の PSTN ゲートウェイに接続されていると同じ位置では、展開の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="0fbd5-107">このトピックでは、クラウド コネクタ サイトがほとんどコスト効率的かつ効果的な方法で、サイトに割り当てられているすべてのユーザーの受信と送信の両方のルーティングを処理できることを確認するのには、クラウドのコネクタのサイト トポロジをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="0fbd5-108">クラウド コネクタと、PSTN のサイトの利点については、必ずお読み[ビジネス クラウド コネクタ ・ エディションの Skype を計画](plan-skype-for-business-cloud-connector-edition.md)します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="0fbd5-109">Cloud Connector PSTN サイトと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="0fbd5-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="0fbd5-110">クラウド コネクタ PSTN のサイトには、不要な長距離および国間の関税率を防ぐために、適切なトランクに緊急の発信コールがルーティングされるようにするを作成するトポロジの構成要素があります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="0fbd5-111">コスト効果的かつ効率的な緊急サービスへの呼び出しなどの呼び出しのルーティングを確認するには、PSTN のサイトおよび各サイトにユーザーを割り当てる方法を慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="0fbd5-112">クラウド コネクタの計画の一環として、ユーザー、オフィスが配置されているとキャリアから PSTN トランクを終了する場所について、通信事業者に相談が重要です。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="0fbd5-113">作業する必要がある緊急を呼び出す方法を決定するのには、キャリアがルーティングすることができ、その情報を使用して、クラウド コネクタ PSTN のサイトを定義し、適切なサイトにユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="0fbd5-114">たとえば、PSTN サイトが拡大されますが、データ センターに終了するトランクがそのサイトのユーザーに割り当てられている番号のすべての着信および発信の両方のルーティングを処理するために構成されていることを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="0fbd5-115">各コネクタのクラウド アプライアンスは、いくつかの IP ゲートウェイ、IP Pbx、またはセッション ボーダー コント ローラー (SBCs) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="0fbd5-116">ゲートウェイと Pbx は、電話会社のトランク (PRI または SIP トランク) に接続している、ためクラウド コネクタのアプライアンスは、着信および発信呼び出しの PSTN トランクに論理的に接続されます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="0fbd5-117">クラウド コネクタと、オンプレミスの PSTN への接続では、ローカル キャリアのトランクと、関連付けられている電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="0fbd5-118">お客様のビジネスが大企業の場合は、複数のキャリアが必要があります-お客様のビジネスが 1 つ以上の市区町村、状態、または国をまたがる場合に特に。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="0fbd5-119">キャリアが電話番号を所有するためキャリアは、緊急の呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="0fbd5-120">ビジネス オンラインの Skype では、同様に、サイト内のすべてのコネクタのクラウド アプライアンスを処理しを同じサイト内のコネクタのクラウド アプライアンスに順番に発信コールをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="0fbd5-121">サイトにそれぞれのクラウド コネクタは、PSTN トランクが (完全にメッシュ化) の同じセットに接続されている間。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="0fbd5-122">各ユーザーがクラウドのコネクタの PSTN のサイトに関連付けられているため、通常 (緊急) は、そのユーザーからの送信の呼び出しがユーザーが関連付けられている PSTN のサイトでコネクタのクラウド アプライアンスのいずれかに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="0fbd5-123">クラウド コネクタでは、静的呼び出しは、接続されている IP ゲートウェイ、IP Pbx、SBCs または直接の PSTN トランクにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="0fbd5-124">クラウドのコネクタは、まだトランク (最小コストのルーティング) の保存先に基づくまたは送信元 (静的または動的な緊急通報) を基に動的ルーティングを行うことはありません。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="0fbd5-125">着信呼び出しは、呼び出しできる番号に関連付けられているトランクから来たものであるために、問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="0fbd5-126">送信呼び出しは、サイト (および PSTN トランクは、そのコネクタのクラウド アプライアンスに接続されている拡張機能)、クラウド コネクタ ・ アプライアンスに移動できますただし、不要な市外通話の呼び出しが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="0fbd5-127">さらに、緊急通報は経由しないクラウド コネクタ PSTN のサイトが別の市外局番または通信事業者とのデータ センターをまたぐ場合です。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="0fbd5-128">例</span><span class="sxs-lookup"><span data-stu-id="0fbd5-128">An example</span></span>

<span data-ttu-id="0fbd5-129">次の例では、サイトの PSTN へのトランクをグループ化する方法と、サイトにユーザーを割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="0fbd5-130">Contoso 社の企業は、次を想定しています。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="0fbd5-131">4 人のユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-131">There are four users:</span></span> 
    
  - <span data-ttu-id="0fbd5-132">レドモンド ワシントン州 (アメリカ合衆国) では、ユーザー A</span><span class="sxs-lookup"><span data-stu-id="0fbd5-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="0fbd5-133">ベルビュー ワシントン州 (アメリカ合衆国) では、ユーザー B</span><span class="sxs-lookup"><span data-stu-id="0fbd5-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="0fbd5-134">Centralia のワシントン州 (アメリカ合衆国) では、ユーザー C</span><span class="sxs-lookup"><span data-stu-id="0fbd5-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="0fbd5-135">ポートランド OR (アメリカ合衆国) では、ユーザー D</span><span class="sxs-lookup"><span data-stu-id="0fbd5-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="0fbd5-136">キャリア A には、トランク内の電話番号とが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="0fbd5-137">レドモンド (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="0fbd5-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="0fbd5-138">ベルビュー (市外局番 425)</span><span class="sxs-lookup"><span data-stu-id="0fbd5-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="0fbd5-139">Centralia (市外局番 360)</span><span class="sxs-lookup"><span data-stu-id="0fbd5-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="0fbd5-140">キャリア B には、トランク内の電話番号とが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="0fbd5-141">ポートランド (市外局番 503)</span><span class="sxs-lookup"><span data-stu-id="0fbd5-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="0fbd5-142">レッドモンド (データ センター A) A のユーザーとベルビュー (データ センター B) では、ユーザー B は、互いの横にある郊外のと同じ市外局番 (425) であるためキャリア A はベルビューのトランクにレドモンドでユーザー A から、緊急の呼び出しを実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="0fbd5-143">その結果、ユーザー A と B、およびベルビューおよびレドモンド、クラウド コネクタ トランクできる可能性がありますサイトにある、同じクラウド コネクタ PSTN 次の図に示すように。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="0fbd5-144">もう一方のトランクを 1 つのオフィス内のユーザーからの緊急電話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="0fbd5-145">この機能をキャリアにチェックする必要があります、ただし、します。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-145">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN サイトをセットアップする方法](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="0fbd5-147">同様に次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="0fbd5-148">Centralia の番号は、A のキャリアによって提供される、ユーザー C ドライブでは、2 時間、および別の市外局番 (360)、ベルビューおよびレドモンド 425 市外局番の場合は、他のキャリア A ユーザーから。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="0fbd5-149">したがって、場合でも、着信呼び出しがある A のキャリアから、ベルビュー市外局番 425 では、ユーザー B から発信される通信事業者の呼び出しを受信した緊急時の元に戻すことがあります Centralia 市外局番 360 のルーティング ソフトウェアを呼び出すことが可能です。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="0fbd5-150">ここでクラウドのコネクタと Centralia の PSTN のサイトに関連付けられているそのトランクを処理できる呼び出し距離と市外局番の間で、通信事業者の確認が重要です。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="0fbd5-151">ポートランドでは、ユーザー D がいくつかを使用し、A. 配送業者が所有しているキャリアの B が提供しているため、その可能性はほとんどありませんキャリア B になることの電話番号から緊急の呼び出しをトランクD のユーザーと、クラウド コネクタ アプライアンスとポートランドに関連付けられているトランクは、PSTN の別のサイト内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fbd5-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

