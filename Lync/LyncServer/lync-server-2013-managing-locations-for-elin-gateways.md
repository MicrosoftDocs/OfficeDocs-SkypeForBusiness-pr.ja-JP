---
title: 'Lync Server 2013: ELIN ゲートウェイの場所を管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="0e787-102">Lync Server 2013 での ELIN ゲートウェイの場所の管理</span><span class="sxs-lookup"><span data-stu-id="0e787-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e787-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0e787-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0e787-104">Lync Server でネットワーク内のクライアントの場所を自動的に提供するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e787-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="0e787-105">ネットワーク wiremap を使用して位置情報サービスデータベースを設定し、緊急対応の場所の識別番号 (ELINs) を CompanyName フィールドに含めます。</span><span class="sxs-lookup"><span data-stu-id="0e787-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="0e787-106">場所を、ネットワーク内のクライアントが利用できるように公開します。</span><span class="sxs-lookup"><span data-stu-id="0e787-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="0e787-107">ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0e787-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="0e787-108">これらのタスクの実行方法の詳細については、展開ドキュメントの「 [Lync Server 2013 で場所データベースを構成](lync-server-2013-configure-the-location-database.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e787-109">中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまで、クライアントでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="0e787-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="0e787-110">詳細については、展開ドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からロケーションデータベースを発行</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0e787-111">このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="0e787-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="0e787-112">緊急位置の計画</span><span class="sxs-lookup"><span data-stu-id="0e787-112">Planning Emergency Locations</span></span>

<span data-ttu-id="0e787-113">ELIN ゲートウェイを使用する場合、場所情報サービスデータベースに、都市の住所、建物内の特定の場所、および各場所の少なくとも1つの ELIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="0e787-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="0e787-114">計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e787-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="0e787-115">場所名の計画</span><span class="sxs-lookup"><span data-stu-id="0e787-115">Planning Location Names</span></span>

<span data-ttu-id="0e787-116">建物内の特定の場所を保持する "位置情報サービスの**場所**" フィールドでは、最大20文字 (スペースを含む) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e787-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="0e787-117">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="0e787-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="0e787-p104">緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。</span><span class="sxs-lookup"><span data-stu-id="0e787-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="0e787-121">Lync クライアントが適切な場所を取得したことをユーザーが簡単に確認できる場所識別子。</span><span class="sxs-lookup"><span data-stu-id="0e787-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="0e787-122">Lync クライアントは、[検出された**場所**] フィールドと [**市区町村**] フィールドを自動的に連結し、ヘッダーに表示します。</span><span class="sxs-lookup"><span data-stu-id="0e787-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="0e787-123">適切な方法としては、建物の番地を各場所の識別子 (たとえば、"第1階\<町村番号\>" など) に追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e787-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="0e787-124">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="0e787-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="0e787-125">場所がワイヤレス アクセス ポイントで決定されるために近似値となる場合は、「Near」という単語を追加することができます (たとえば、「Near 1 階 1234」など)。</span><span class="sxs-lookup"><span data-stu-id="0e787-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="0e787-126">ELIN の計画</span><span class="sxs-lookup"><span data-stu-id="0e787-126">Planning ELINs</span></span>

<span data-ttu-id="0e787-p106">建物のスペースをどのように場所に区切るかを決めたら、いくつの ELIN を各場所に割り当てるかを決める必要があります。たとえば、階数やテナント数が多い建物では建物内のエリアごとに別の緊急ゾーンが割り当てられる場合があります。一般的には建物の 1 つの階を 1 つの場所として指定し、さらに 1 つの場所に 1 つ以上の ELIN を割り当てます。ELIN は緊急通報の際に呼び出し元番号として使用されます。ELIN に使用できる電話番号については、各自の PSTN 通信業者にお問い合わせください。次の表には、1 つの住所に含まれる複数の場所の例を示します。</span><span class="sxs-lookup"><span data-stu-id="0e787-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="0e787-133">場所と ELIN の割り当てのサンプル</span><span class="sxs-lookup"><span data-stu-id="0e787-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e787-134">建物内のエリア</span><span class="sxs-lookup"><span data-stu-id="0e787-134">Building Area</span></span></th>
<th><span data-ttu-id="0e787-135">場所</span><span class="sxs-lookup"><span data-stu-id="0e787-135">Location</span></span></th>
<th><span data-ttu-id="0e787-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="0e787-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e787-137">1 階</span><span class="sxs-lookup"><span data-stu-id="0e787-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="0e787-138">1</span><span class="sxs-lookup"><span data-stu-id="0e787-138">1</span></span></p></td>
<td><p><span data-ttu-id="0e787-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="0e787-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e787-140">2 階</span><span class="sxs-lookup"><span data-stu-id="0e787-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="0e787-141">両面</span><span class="sxs-lookup"><span data-stu-id="0e787-141">2</span></span></p></td>
<td><p><span data-ttu-id="0e787-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="0e787-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e787-143">3 階</span><span class="sxs-lookup"><span data-stu-id="0e787-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="0e787-144">3</span><span class="sxs-lookup"><span data-stu-id="0e787-144">3</span></span></p></td>
<td><p><span data-ttu-id="0e787-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="0e787-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e787-146">定義する場所は次の要件を満たすことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="0e787-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="0e787-147">場所ごとのエリアの最大の広さ、および番地ごとの場所の個数について、自治体、および国または地域の規制に準拠していること。</span><span class="sxs-lookup"><span data-stu-id="0e787-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="0e787-148">緊急通報をした人の場所が簡単にわかるように、十分に具体的であること。</span><span class="sxs-lookup"><span data-stu-id="0e787-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="0e787-149">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="0e787-149">Populating the Location Database</span></span>

<span data-ttu-id="0e787-150">場所データベースへのデータの取り込み方法を決める際は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="0e787-151">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="0e787-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="0e787-p107">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="0e787-154">**場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="0e787-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="0e787-155">Lync Server の [Secondary Location Information service] オプションを使ってサードパーティのデータベースに接続すると、オフラインプラットフォームを使用して場所をグループ化して管理できます。</span><span class="sxs-lookup"><span data-stu-id="0e787-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="0e787-156">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="0e787-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="0e787-157">つまり、位置情報サービスは、セカンダリの場所情報サービスからの複数のアドレスを Lync Server クライアントに返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e787-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="0e787-158">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e787-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="0e787-159">位置情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e787-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="0e787-160">詳細について<http://go.microsoft.com/fwlink/p/?linkid=213819>は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="0e787-161">セカンダリ位置情報サービスの展開の詳細については、展開ドキュメントの「 [Lync Server 2013 でセカンダリ場所情報サービスを構成](lync-server-2013-configure-a-secondary-location-information-service.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0e787-162">場所データベースの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で場所データベースを構成する](lync-server-2013-configure-the-location-database.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="0e787-163">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="0e787-163">Maintaining the Location Database</span></span>

<span data-ttu-id="0e787-p110">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0e787-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="0e787-166">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="0e787-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="0e787-p111">場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="0e787-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="0e787-169">**SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**</span><span class="sxs-lookup"><span data-stu-id="0e787-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="0e787-170">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e787-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="0e787-171">SNMP アプリケーションが、データベースに含まれていないシャーシの IP アドレスまたはポート ID を返す場合、位置情報サービスは位置情報をクライアントに返すことができません。</span><span class="sxs-lookup"><span data-stu-id="0e787-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

