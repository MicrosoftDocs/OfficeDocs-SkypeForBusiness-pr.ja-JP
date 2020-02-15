---
title: 'Lync Server 2013: SIP トランクサービスプロバイダーの場所の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="f8077-102">Lync Server 2013 での SIP トランクサービスプロバイダーの場所の管理</span><span class="sxs-lookup"><span data-stu-id="f8077-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8077-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f8077-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f8077-104">ネットワーク内のクライアントを自動的に検索するように Lync Server を構成するには、場所情報サービスデータベースにネットワークのワイヤマップを設定し、場所を公開するか、または既に正しい内容が含まれている外部データベースにリンクする必要があります。関連付け.</span><span class="sxs-lookup"><span data-stu-id="f8077-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="f8077-105">このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8077-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="f8077-106">詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f8077-107">場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="f8077-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="f8077-108">場所情報サービスの**場所**フィールド (建物内の特定の場所) の最大長は20文字 (スペースを含む) です。</span><span class="sxs-lookup"><span data-stu-id="f8077-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="f8077-109">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="f8077-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="f8077-p103">緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8077-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="f8077-113">Lync クライアントが正しい場所を取得したことを、ユーザーが簡単に判別するのに役立つ場所の ID。</span><span class="sxs-lookup"><span data-stu-id="f8077-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="f8077-114">Lync クライアントは、検出したヘッダ内の [**Location**] フィールドと [**City**] フィールドを自動的に連結し、表示します。</span><span class="sxs-lookup"><span data-stu-id="f8077-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="f8077-115">建物の番地を各場所の識別子 (たとえば、"1 階\<のストリート番号\>") に追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8077-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="f8077-116">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="f8077-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="f8077-117">場所がワイヤレス アクセス ポイントで決定されるために近似となる場合、「Near」という単語を追加することができます。たとえば、「Near 1 階 1234」です。</span><span class="sxs-lookup"><span data-stu-id="f8077-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8077-118">中央の場所のデータベースに追加された場所は、Lync Server 管理シェルコマンドを使用して発行され、プールのローカルストアにレプリケートされるまでクライアントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="f8077-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="f8077-119">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013 からの場所データベースの発行</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="f8077-120">以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。</span><span class="sxs-lookup"><span data-stu-id="f8077-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="f8077-121">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="f8077-121">Populating the Location Database</span></span>

<span data-ttu-id="f8077-122">以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8077-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="f8077-123">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="f8077-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="f8077-p106">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="f8077-126">**場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="f8077-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="f8077-127">Lync Server のセカンダリの場所情報サービスオプションを使用してサードパーティのデータベースに接続することにより、オフラインプラットフォームを使用して場所をグループ化および管理できます。</span><span class="sxs-lookup"><span data-stu-id="f8077-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="f8077-128">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="f8077-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="f8077-129">これは、場所情報サービスが、セカンダリ場所情報サービスから Lync Server クライアントに送信された複数のアドレスを返すことができることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f8077-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="f8077-130">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f8077-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="f8077-131">場所情報サービスと統合するには、サードパーティのデータベースが Lync Server の場所の要求/応答スキーマに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8077-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="f8077-132">詳細については\[、「Ms-e911ws\]: Web Service For E911 Support Protocol Specification」を<http://go.microsoft.com/fwlink/p/?linkid=213819>参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="f8077-133">セカンダリ場所情報サービスの展開の詳細については、「展開」のドキュメントの「 [Configure a Secondary Location information service In Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f8077-134">場所データベースの設定の詳細については、「展開」のドキュメントの「 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="f8077-135">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="f8077-135">Maintaining the Location Database</span></span>

<span data-ttu-id="f8077-p109">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8077-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="f8077-138">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="f8077-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="f8077-p110">場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f8077-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="f8077-141">**SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**</span><span class="sxs-lookup"><span data-stu-id="f8077-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="f8077-142">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8077-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="f8077-143">SNMP アプリケーションがデータベースに含まれていないシャーシの IP アドレスまたはポート ID を返した場合、Location Information service はクライアントに場所を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="f8077-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

