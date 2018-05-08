---
title: Skype for Business Server 2015 での ELIN ゲートウェイの場所の管理
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 意思決定の計画に必要な場所情報のデータベース、または ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype で、ELIN ゲートウェイを使用して、ような外部データベースです。
ms.openlocfilehash: c89f09af2011d316485094f9fc817580b56d1d81
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server-2015"></a><span data-ttu-id="55b54-103">Skype for Business Server 2015 での ELIN ゲートウェイの場所の管理</span><span class="sxs-lookup"><span data-stu-id="55b54-103">Manage locations for ELIN gateways in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="55b54-104">意思決定の計画に必要な場所情報のデータベース、または ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype で、ELIN ゲートウェイを使用して、ような外部データベースです。</span><span class="sxs-lookup"><span data-stu-id="55b54-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using ELIN gateways, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="55b54-105">ビジネス サーバーの Skype が自動的にネットワーク内のクライアントの場所を提供するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b54-105">To have Skype for Business Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span> 
  
- <span data-ttu-id="55b54-106">場所情報サービス データベース、ネットワークの wiremap に設定し、緊急位置識別番号 (ELINs) は、[得意先名] フィールドにします。</span><span class="sxs-lookup"><span data-stu-id="55b54-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>
    
- <span data-ttu-id="55b54-107">場所を、ネットワーク内のクライアントが利用できるように公開します。</span><span class="sxs-lookup"><span data-stu-id="55b54-107">Publish the locations so that they are available for clients in your network.</span></span>
    
- <span data-ttu-id="55b54-108">ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="55b54-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>
    
<span data-ttu-id="55b54-109">これらのタスクを実行する方法の詳細については、展開に関するドキュメントの[場所データベースの構成](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-109">For details about how to perform these tasks, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55b54-110">ビジネス サーバー管理シェル コマンドを Skype を使用して公開されているプールのローカル ストアにレプリケートされるまでにも、中央の場所データベースに追加する場所はクライアントにご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="55b54-110">Locations added to the central location database are not available to the client until they have been published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="55b54-111">詳細については、展開に関するドキュメントの[場所のデータベースのパブリッシュ](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-111">For details, see [Publishing the Location Database](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>
  
<span data-ttu-id="55b54-112">このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="55b54-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>
  
## <a name="planning-emergency-locations"></a><span data-ttu-id="55b54-113">緊急位置の計画</span><span class="sxs-lookup"><span data-stu-id="55b54-113">Planning Emergency Locations</span></span>

<span data-ttu-id="55b54-114">ELIN ゲートウェイを使用する場合は、都市の住所、建物内の特定の場所および場所ごとに少なくとも 1 つの ELIN を場所情報サービス データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="55b54-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="55b54-115">計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="55b54-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>
  
### <a name="planning-location-names"></a><span data-ttu-id="55b54-116">場所名の計画</span><span class="sxs-lookup"><span data-stu-id="55b54-116">Planning Location Names</span></span>

<span data-ttu-id="55b54-117">建物内の特定の場所を保持するには、位置情報サービス**の場所**フィールドには、20 の文字 (スペースを含む) の最大の長さがあります。</span><span class="sxs-lookup"><span data-stu-id="55b54-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="55b54-118">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="55b54-118">Within that limited length, try to include the following:</span></span>
  
- <span data-ttu-id="55b54-p104">緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。</span><span class="sxs-lookup"><span data-stu-id="55b54-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>
    
- <span data-ttu-id="55b54-122">クライアントが正しい場所を取得したことを、ユーザーが簡単に判別するのに役立つ場所の ID。</span><span class="sxs-lookup"><span data-stu-id="55b54-122">A location identifier that helps users to easily see that their client picked up the correct location.</span></span> <span data-ttu-id="55b54-123">ビジネス クライアント用の Skype は自動的に連結し、ヘッダーで検出された**場所**と**市区町村**フィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55b54-123">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="55b54-124">場所識別子ごとに建物の住所を追加するのにはお勧め (たとえば、"1 階<street number>")。</span><span class="sxs-lookup"><span data-stu-id="55b54-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="55b54-125">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="55b54-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>
    
- <span data-ttu-id="55b54-126">場所は、それは、ワイヤレス アクセス ポイントによって決定されるため概算値は、場合は、 **[近く]** (たとえば、"近くにある 1 階 1234") という単語を追加します。</span><span class="sxs-lookup"><span data-stu-id="55b54-126">If the location is approximate because it's determined by a wireless access point, you may want to add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>
    
### <a name="planning-elins"></a><span data-ttu-id="55b54-127">ELIN の計画</span><span class="sxs-lookup"><span data-stu-id="55b54-127">Planning ELINs</span></span>

<span data-ttu-id="55b54-p106">建物のスペースをどのように場所に区切るかを決めたら、いくつの ELIN を各場所に割り当てるかを決める必要があります。たとえば、階数やテナント数が多い建物では建物内のエリアごとに別の緊急ゾーンが割り当てられる場合があります。一般的には建物の 1 つの階を 1 つの場所として指定し、さらに 1 つの場所に 1 つ以上の ELIN を割り当てます。ELIN は緊急通報の際に呼び出し元番号として使用されます。ELIN に使用できる電話番号については、各自の PSTN 通信業者にお問い合わせください。次の表には、1 つの住所に含まれる複数の場所の例を示します。</span><span class="sxs-lookup"><span data-stu-id="55b54-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>
  
<span data-ttu-id="55b54-134">**サンプルの場所と ELIN の割り当て**</span><span class="sxs-lookup"><span data-stu-id="55b54-134">**Sample Location and ELIN Assignments**</span></span>

|<span data-ttu-id="55b54-135">**領域の構築**</span><span class="sxs-lookup"><span data-stu-id="55b54-135">**Building Area**</span></span>|<span data-ttu-id="55b54-136">**場所**</span><span class="sxs-lookup"><span data-stu-id="55b54-136">**Location**</span></span>|<span data-ttu-id="55b54-137">**ELIN**</span><span class="sxs-lookup"><span data-stu-id="55b54-137">**ELIN**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="55b54-138">1 階</span><span class="sxs-lookup"><span data-stu-id="55b54-138">First floor</span></span>  <br/> |<span data-ttu-id="55b54-139">1</span><span class="sxs-lookup"><span data-stu-id="55b54-139">1</span></span>  <br/> |<span data-ttu-id="55b54-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="55b54-140">425-555-0100</span></span>  <br/> |
|<span data-ttu-id="55b54-141">2 階</span><span class="sxs-lookup"><span data-stu-id="55b54-141">Second floor</span></span>  <br/> |<span data-ttu-id="55b54-142">2</span><span class="sxs-lookup"><span data-stu-id="55b54-142">2</span></span>  <br/> |<span data-ttu-id="55b54-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="55b54-143">425-555-0111</span></span>  <br/> |
|<span data-ttu-id="55b54-144">3 階</span><span class="sxs-lookup"><span data-stu-id="55b54-144">Third floor</span></span>  <br/> |<span data-ttu-id="55b54-145">3</span><span class="sxs-lookup"><span data-stu-id="55b54-145">3</span></span>  <br/> |<span data-ttu-id="55b54-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="55b54-146">425-555-0123</span></span>  <br/> |
   
<span data-ttu-id="55b54-147">定義する場所は次の要件を満たすことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="55b54-147">The locations you define should meet the following requirements:</span></span>
  
- <span data-ttu-id="55b54-148">場所ごとのエリアの最大の広さ、および番地ごとの場所の個数について、自治体、および国または地域の規制に準拠していること。</span><span class="sxs-lookup"><span data-stu-id="55b54-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>
    
- <span data-ttu-id="55b54-149">緊急通報をした人の場所が簡単にわかるように、十分に具体的であること。</span><span class="sxs-lookup"><span data-stu-id="55b54-149">Are specific enough to make it easy to locate the emergency caller.</span></span>
    
## <a name="populating-the-location-database"></a><span data-ttu-id="55b54-150">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="55b54-150">Populating the Location Database</span></span>

<span data-ttu-id="55b54-151">場所データベースへのデータの取り込み方法を決める際は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-151">The following questions will help you determine how to will populate the location database.</span></span>
  
 <span data-ttu-id="55b54-152">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="55b54-152">**What process will you use to populate the location database?**</span></span>
  
<span data-ttu-id="55b54-p107">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>
  
 <span data-ttu-id="55b54-155">**場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="55b54-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>
  
<span data-ttu-id="55b54-156">セカンダリ場所情報サービスのオプションを使用するとサード ・ パーティ製のデータベースに接続するのには、グループ化し、オフラインのプラットフォームを使用して場所を管理できます。</span><span class="sxs-lookup"><span data-stu-id="55b54-156">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="55b54-157">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="55b54-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="55b54-158">つまり、場所情報サービスが、Skype のビジネス クライアントに、セカンダリ場所情報サービスから発信される、複数のアドレスを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="55b54-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="55b54-159">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="55b54-159">The user can then choose the most appropriate location.</span></span> 
  
<span data-ttu-id="55b54-160">位置情報サービスとの統合、サードパーティのデータベースはビジネス サーバーの場所の要求/応答スキーマの Skype に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b54-160">To integrate with the Location Information service, the third-party database must follow the Skype for Business Server Location Request/Response schema.</span></span> <span data-ttu-id="55b54-161">詳細については、 [E911 サポート プロトコル用の Web サービス](https://go.microsoft.com/fwlink/p/?linkid=213819)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-161">For details, see [Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="55b54-162">セカンダリ場所情報サービスの展開に関する詳細情報は、展開に関するドキュメントで[ビジネス サーバー 2015 の Skype でのセカンダリ場所情報サービスの構成](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="55b54-163">場所データベースの設定についての詳細は、展開に関するドキュメントの[場所データベースの構成](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-163">For details about populating the location database, see [Configure the Location Database](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>
  
## <a name="maintaining-the-location-database"></a><span data-ttu-id="55b54-164">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="55b54-164">Maintaining the Location Database</span></span>

<span data-ttu-id="55b54-p110">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55b54-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>
  
 <span data-ttu-id="55b54-167">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="55b54-167">**How will you update the location database?**</span></span>
  
<span data-ttu-id="55b54-p111">場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="55b54-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>
  
 <span data-ttu-id="55b54-170">**Skype ビジネス クライアントの MAC アドレスをポートに一致し、識別子をスイッチに SNMP アプリケーションを使用するか。**</span><span class="sxs-lookup"><span data-stu-id="55b54-170">**Will you use an SNMP application to match Skype for Business client MAC addresses to port and switch identifiers?**</span></span>
  
<span data-ttu-id="55b54-171">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b54-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="55b54-172">SNMP アプリケーションがデータベースに含まれていないシャーシ IP アドレスまたはポート ID を返す場合は、位置情報サービスは場所をクライアントに返すことができませんできません。</span><span class="sxs-lookup"><span data-stu-id="55b54-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>
  

