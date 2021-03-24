---
title: Skype for Business Server の SIP トランク サービス プロバイダーの場所を管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用した E9-1-1 展開の場所情報データベースまたは同様の外部データベースを計画するために必要な決定。
ms.openlocfilehash: b175c2cc3d0ed02a124a365787c8cb5d7cd37d10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101443"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="01ac2-103">Skype for Business Server の SIP トランク サービス プロバイダーの場所を管理する</span><span class="sxs-lookup"><span data-stu-id="01ac2-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>

<span data-ttu-id="01ac2-104">Skype for Business Server エンタープライズ VoIP で、SIP トランキング プロバイダーを使用した E9-1-1 展開の場所情報データベースまたは同様の外部データベースを計画するために必要な決定。</span><span class="sxs-lookup"><span data-stu-id="01ac2-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="01ac2-105">ネットワーク内のクライアントを自動的に検索する Skype for Business Server を構成するには、場所情報サービス データベースにネットワーク ワイヤーマップを設定して場所を公開するか、または正しいマッピングが既に含まれている外部データベースへのリンクを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="01ac2-106">このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="01ac2-107">詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-107">For details, see [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in the Deployment documentation.</span></span>

<span data-ttu-id="01ac2-108">場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="01ac2-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="01ac2-109">建物内の特定 **の** 場所である [位置情報サービスの場所] フィールドの最大長は 20 文字 (スペースを含む) です。</span><span class="sxs-lookup"><span data-stu-id="01ac2-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="01ac2-110">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="01ac2-110">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="01ac2-p103">緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="01ac2-114">ユーザーが Skype for Business クライアントが正しい場所を選んだのをユーザーが簡単に確認するのに役立つ場所識別子。</span><span class="sxs-lookup"><span data-stu-id="01ac2-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="01ac2-115">Skype for Business クライアントは、検出された Locationフィールドと **City** フィールドをヘッダーに自動的に連結して表示します。</span><span class="sxs-lookup"><span data-stu-id="01ac2-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="01ac2-116">建物の住所を各場所識別子 (たとえば"1st Floor") に追加する方法をお使 <street number> いください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="01ac2-117">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="01ac2-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="01ac2-118">場所がワイヤレス アクセス ポイントによって決まるので近似値の場合は **、[Near]** という単語を追加できます (たとえば、「Near 1st Floor 1234」)。</span><span class="sxs-lookup"><span data-stu-id="01ac2-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

> [!NOTE]
> <span data-ttu-id="01ac2-119">中央の場所データベースに追加された場所は、Skype for Business Server 管理シェル コマンドを使用して発行され、プールのローカル ストアにレプリケートされるまで、クライアントが使用できません。</span><span class="sxs-lookup"><span data-stu-id="01ac2-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="01ac2-120">詳細については、「展開」のドキュメントの「[Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-120">For details, see [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) in the Deployment documentation.</span></span>

<span data-ttu-id="01ac2-121">以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。</span><span class="sxs-lookup"><span data-stu-id="01ac2-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="01ac2-122">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="01ac2-122">Populating the Location Database</span></span>

<span data-ttu-id="01ac2-123">以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01ac2-123">The following questions can help you determine how to populate the location database.</span></span>

 <span data-ttu-id="01ac2-124">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="01ac2-124">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="01ac2-p106">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="01ac2-127">**場所のマッピング情報がすでに格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="01ac2-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="01ac2-128">[セカンダリ位置情報サービス] オプションを使用してサードパーティ データベースに接続すると、オフライン プラットフォームを使用して場所をグループ化および管理できます。</span><span class="sxs-lookup"><span data-stu-id="01ac2-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="01ac2-129">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="01ac2-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="01ac2-130">つまり、位置情報サービスは、セカンダリ 位置情報サービスから Skype for Business クライアントに複数のアドレスを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="01ac2-131">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="01ac2-131">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="01ac2-132">位置情報サービスと統合するには、サード パーティのデータベースが Lync Server の場所要求/応答スキーマに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="01ac2-133">詳細については  [、「[MS-E911WS]: E911](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd)サポート プロトコル仕様の Web サービス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd).</span></span> <span data-ttu-id="01ac2-134">セカンダリ位置情報サービスの展開の詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) でセカンダリ位置情報サービスを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="01ac2-135">場所データベースへのデータの取り込みの詳細については、「展開」のドキュメントの「[Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-135">For details about populating the location database, see [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="01ac2-136">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="01ac2-136">Maintaining the Location Database</span></span>

<span data-ttu-id="01ac2-p109">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01ac2-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="01ac2-139">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="01ac2-139">**How will you update the location database?**</span></span>

<span data-ttu-id="01ac2-p110">場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="01ac2-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="01ac2-142">**SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**</span><span class="sxs-lookup"><span data-stu-id="01ac2-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="01ac2-143">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01ac2-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="01ac2-144">SNMP アプリケーションがデータベースに含まれていないシャーシ IP アドレスまたはポート ID を返す場合、場所情報サービスはクライアントに場所を返す事ができません。</span><span class="sxs-lookup"><span data-stu-id="01ac2-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>