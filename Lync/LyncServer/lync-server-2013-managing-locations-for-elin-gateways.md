---
title: 'Lync Server 2013: ELIN ゲートウェイの場所の管理'
description: 'Lync Server 2013: ELIN ゲートウェイの場所を管理する。'
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
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557483"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="90c57-103">Lync Server 2013 での ELIN ゲートウェイの場所の管理</span><span class="sxs-lookup"><span data-stu-id="90c57-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90c57-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="90c57-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="90c57-105">Lync Server でネットワーク内のクライアントの場所を自動的に提供するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c57-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="90c57-106">場所情報サービスデータベースにネットワーク wiremap を設定し、緊急位置識別番号 (ELINs) を CompanyName フィールドに含めます。</span><span class="sxs-lookup"><span data-stu-id="90c57-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="90c57-107">場所を、ネットワーク内のクライアントが利用できるように公開します。</span><span class="sxs-lookup"><span data-stu-id="90c57-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="90c57-108">ELIN を、公衆交換電話網 (PSTN) 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="90c57-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="90c57-109">これらのタスクを実行する方法の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90c57-110">中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して公開され、プールのローカルストアにレプリケートされるまでクライアントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="90c57-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="90c57-111">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からの場所データベースの発行</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="90c57-112">このセクションでは、場所データベースの更新および保守の計画を立てるときに考慮する必要のある事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="90c57-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="90c57-113">緊急位置の計画</span><span class="sxs-lookup"><span data-stu-id="90c57-113">Planning Emergency Locations</span></span>

<span data-ttu-id="90c57-114">ELIN ゲートウェイを使用する場合は、場所情報サービスデータベースに、都市の住所、建物内の特定の場所、および場所ごとに少なくとも1つの ELIN を設定します。</span><span class="sxs-lookup"><span data-stu-id="90c57-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="90c57-115">計画段階で、場所にどのように名前を付けるのか、どのように ELIN を割り当てるのかを決定しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90c57-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="90c57-116">場所名の計画</span><span class="sxs-lookup"><span data-stu-id="90c57-116">Planning Location Names</span></span>

<span data-ttu-id="90c57-117">場所情報サービスの **場所** フィールドは、建物内の特定の位置を保持します。最大長は20文字 (スペースを含む) です。</span><span class="sxs-lookup"><span data-stu-id="90c57-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="90c57-118">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="90c57-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="90c57-p104">緊急対応員が特定の住所に到着したときに緊急通報をした人の場所がすぐにわかるように、場所を具体的に特定するわかりやすい名前。この場所名には、建物の番号、階数、翼棟名、部屋番号などを含めます。従業員にしかわからないような呼称は避けます。緊急対応員がわからなければ、彼らは正しい場所に行くことができません。</span><span class="sxs-lookup"><span data-stu-id="90c57-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="90c57-122">Lync クライアントが正しい場所を取得したことを、ユーザーが簡単に判別するのに役立つ場所の ID。</span><span class="sxs-lookup"><span data-stu-id="90c57-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="90c57-123">Lync クライアントは、検出したヘッダ内の [**Location**] フィールドと [**City**] フィールドを自動的に連結し、表示します。</span><span class="sxs-lookup"><span data-stu-id="90c57-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="90c57-124">建物の番地を各場所の識別子 (たとえば、"1 階") に追加することをお勧め \<street number\> します。</span><span class="sxs-lookup"><span data-stu-id="90c57-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="90c57-125">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="90c57-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="90c57-126">場所がワイヤレス アクセス ポイントで決定されるために近似値となる場合は、「Near」という単語を追加することができます (たとえば、「Near 1 階 1234」など)。</span><span class="sxs-lookup"><span data-stu-id="90c57-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="90c57-127">ELIN の計画</span><span class="sxs-lookup"><span data-stu-id="90c57-127">Planning ELINs</span></span>

<span data-ttu-id="90c57-p106">建物のスペースをどのように場所に区切るかを決めたら、いくつの ELIN を各場所に割り当てるかを決める必要があります。たとえば、階数やテナント数が多い建物では建物内のエリアごとに別の緊急ゾーンが割り当てられる場合があります。一般的には建物の 1 つの階を 1 つの場所として指定し、さらに 1 つの場所に 1 つ以上の ELIN を割り当てます。ELIN は緊急通報の際に呼び出し元番号として使用されます。ELIN に使用できる電話番号については、各自の PSTN 通信業者にお問い合わせください。次の表には、1 つの住所に含まれる複数の場所の例を示します。</span><span class="sxs-lookup"><span data-stu-id="90c57-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="90c57-134">場所と ELIN の割り当てのサンプル</span><span class="sxs-lookup"><span data-stu-id="90c57-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="90c57-135">建物内のエリア</span><span class="sxs-lookup"><span data-stu-id="90c57-135">Building Area</span></span></th>
<th><span data-ttu-id="90c57-136">場所</span><span class="sxs-lookup"><span data-stu-id="90c57-136">Location</span></span></th>
<th><span data-ttu-id="90c57-137">ELIN</span><span class="sxs-lookup"><span data-stu-id="90c57-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90c57-138">1 階</span><span class="sxs-lookup"><span data-stu-id="90c57-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="90c57-139">1-d</span><span class="sxs-lookup"><span data-stu-id="90c57-139">1</span></span></p></td>
<td><p><span data-ttu-id="90c57-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="90c57-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90c57-141">2 階</span><span class="sxs-lookup"><span data-stu-id="90c57-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="90c57-142">pbm-2</span><span class="sxs-lookup"><span data-stu-id="90c57-142">2</span></span></p></td>
<td><p><span data-ttu-id="90c57-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="90c57-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90c57-144">3 階</span><span class="sxs-lookup"><span data-stu-id="90c57-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="90c57-145">1/3</span><span class="sxs-lookup"><span data-stu-id="90c57-145">3</span></span></p></td>
<td><p><span data-ttu-id="90c57-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="90c57-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="90c57-147">定義する場所は次の要件を満たすことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="90c57-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="90c57-148">場所ごとのエリアの最大の広さ、および番地ごとの場所の個数について、自治体、および国または地域の規制に準拠していること。</span><span class="sxs-lookup"><span data-stu-id="90c57-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="90c57-149">緊急通報をした人の場所が簡単にわかるように、十分に具体的であること。</span><span class="sxs-lookup"><span data-stu-id="90c57-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="90c57-150">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="90c57-150">Populating the Location Database</span></span>

<span data-ttu-id="90c57-151">場所データベースへのデータの取り込み方法を決める際は、以下の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="90c57-152">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="90c57-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="90c57-p107">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="90c57-155">**場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="90c57-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="90c57-156">Lync Server のセカンダリの場所情報サービスオプションを使用してサードパーティのデータベースに接続することにより、オフラインプラットフォームを使用して場所をグループ化および管理できます。</span><span class="sxs-lookup"><span data-stu-id="90c57-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="90c57-157">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="90c57-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="90c57-158">これは、場所情報サービスが、セカンダリ場所情報サービスから Lync Server クライアントに送信された複数のアドレスを返すことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="90c57-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="90c57-159">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="90c57-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="90c57-160">場所情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所の要求/応答スキーマに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c57-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="90c57-161">詳細については、「」を参照してください <https://go.microsoft.com/fwlink/p/?linkid=213819> 。</span><span class="sxs-lookup"><span data-stu-id="90c57-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="90c57-162">セカンダリ場所情報サービスの展開の詳細については、「展開」のドキュメントの「 [Configure a Secondary Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="90c57-163">場所データベースの設定の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="90c57-164">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="90c57-164">Maintaining the Location Database</span></span>

<span data-ttu-id="90c57-p110">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c57-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="90c57-167">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="90c57-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="90c57-p111">場所データベースの更新が必要になる場合としては、ワイヤレス アクセス ポイント (WAP) の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="90c57-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="90c57-170">**SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**</span><span class="sxs-lookup"><span data-stu-id="90c57-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="90c57-171">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c57-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="90c57-172">SNMP アプリケーションがデータベースに含まれていないシャーシの IP アドレスまたはポート ID を返した場合、Location Information service はクライアントに場所を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="90c57-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

