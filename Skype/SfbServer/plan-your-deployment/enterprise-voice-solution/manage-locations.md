---
title: ビジネス サーバーの Skype では、SIP トランク サービス プロバイダーの場所を管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: 意思決定の計画に必要な場所情報のデータベース、または ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して、ような外部データベースです。
ms.openlocfilehash: b92d0d13797e50cf4b538b6bd96e304658a7585e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924172"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="62a2a-103">ビジネス サーバーの Skype では、SIP トランク サービス プロバイダーの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="62a2a-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>

<span data-ttu-id="62a2a-104">意思決定の計画に必要な場所情報のデータベース、または ~ 9-1-1 展開のビジネス サーバーのエンタープライズ VoIP の Skype で、SIP トランキング プロバイダーを使用して、ような外部データベースです。</span><span class="sxs-lookup"><span data-stu-id="62a2a-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="62a2a-105">Skype ビジネス サーバーでネットワーク内のクライアントを自動的に検索するように構成するのにはネットワーク wiremap に場所情報サービス データベースを設定し、発行場所、または既に含まれている外部データベースへのリンクする必要があります。正しいマッピングします。</span><span class="sxs-lookup"><span data-stu-id="62a2a-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="62a2a-106">このプロセスの一環として、E9-1-1 サービスのサービス プロバイダーで場所の公的アドレスを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a2a-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="62a2a-107">詳細については、「展開」のドキュメントの「[Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-107">For details, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="62a2a-108">場所情報サービス データベースに、公的アドレスと建物内の特定のアドレスで構成される緊急応答ロケーション (ERL) を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="62a2a-109">建物内の特定の場所で、位置情報サービス**の場所**フィールドには、20 の文字 (スペースを含む) の最大の長さがあります。</span><span class="sxs-lookup"><span data-stu-id="62a2a-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="62a2a-110">この制限された長さの中に、以下を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="62a2a-110">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="62a2a-p103">緊急対応員が公的アドレスにたどり着いたときに特定の場所をすぐに特定するように、緊急電話の発信者の場所を特定するわかりやすい名前。この場所名には建物番号、階数、ウイング名、部屋番号などを含めることができます。従業員にしかわからないニックネームは避けてください。そのようなニックネームになっていると、緊急対応員が間違った場所へ行ってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62a2a-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="62a2a-114">ビジネス クライアントが適切な場所を選択、Skype ユーザーが簡単に理解することを支援する場所の識別子です。</span><span class="sxs-lookup"><span data-stu-id="62a2a-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="62a2a-115">ビジネス クライアント用の Skype は自動的に連結し、ヘッダーで検出された**場所**と**市区町村**フィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="62a2a-116">場所識別子ごとに建物の住所を追加するのにはお勧め (たとえば、"1 階<street number>")。</span><span class="sxs-lookup"><span data-stu-id="62a2a-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="62a2a-117">番地がないと、「1 階」のような一般的な場所 ID は、市内のすべての建物に該当します。</span><span class="sxs-lookup"><span data-stu-id="62a2a-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="62a2a-118">それは、ワイヤレス アクセス ポイントによって決定されるために、場所がおおよそ場合は、 **[付近]** (たとえば、"近くにある 1 階 1234") という単語を追加できます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

> [!NOTE]
> <span data-ttu-id="62a2a-119">ビジネス サーバー管理シェル コマンドを Skype を使用して公開およびプールのローカル ストアにレプリケートされるまでにも、中央の場所データベースに追加する場所はクライアントにご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="62a2a-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="62a2a-120">詳細については、「展開」のドキュメントの「[Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-120">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="62a2a-121">以降のセクションでは、場所データベースへのデータの取り込みおよび管理で考慮する必要がある事項について検討します。</span><span class="sxs-lookup"><span data-stu-id="62a2a-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="62a2a-122">場所データベースの設定</span><span class="sxs-lookup"><span data-stu-id="62a2a-122">Populating the Location Database</span></span>

<span data-ttu-id="62a2a-123">以下の質問は、場所データベースにデータを取り込む方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-123">The following questions can help you determine how to populate the location database.</span></span>

 <span data-ttu-id="62a2a-124">**場所データベースにデータを取り込むためにどんなプロセスを使用するのか。**</span><span class="sxs-lookup"><span data-stu-id="62a2a-124">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="62a2a-p106">データがどこに存在し、そのデータを場所データベースで要求される形式に変換するためにどのようなステップを実行する必要があるのか考慮してください。また、場所を個別に追加するのか、または CSV ファイルを使用して一括追加するのか検討してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="62a2a-127">**場所のマッピング情報が既に格納されているサードパーティのデータベースを定義するのか。**</span><span class="sxs-lookup"><span data-stu-id="62a2a-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="62a2a-128">セカンダリ場所情報サービスのオプションを使用するとサード ・ パーティ製のデータベースに接続するのには、グループ化し、オフラインのプラットフォームを使用して場所を管理できます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="62a2a-129">この方法の利点は、場所をネットワーク ID に関連付けることに加えて、場所をユーザーに関連付けられることです。</span><span class="sxs-lookup"><span data-stu-id="62a2a-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="62a2a-130">つまり、場所情報サービスが、Skype のビジネス クライアントに、セカンダリ場所情報サービスから発信される、複数のアドレスを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="62a2a-131">その後、ユーザーは最適な場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-131">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="62a2a-132">位置情報サービスとの統合、サードパーティのデータベースは、Lync Server の場所要求/応答スキーマに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a2a-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="62a2a-133">詳細については、「 [」[MS E911WS]: E911 サポート プロトコル仕様の Web サービス"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span><span class="sxs-lookup"><span data-stu-id="62a2a-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="62a2a-134">セカンダリ場所情報サービスの展開に関する詳細情報は、展開に関するドキュメントで[Skype ビジネス サーバーでセカンダリ場所情報サービスの構成](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="62a2a-135">場所データベースへのデータの取り込みの詳細については、「展開」のドキュメントの「[Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-135">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="62a2a-136">場所データベースの管理</span><span class="sxs-lookup"><span data-stu-id="62a2a-136">Maintaining the Location Database</span></span>

<span data-ttu-id="62a2a-p109">場所データベースにデータを取り込んだ後は、ネットワーク構成の変更に伴ってデータベースを更新するための手段を講じる必要があります。以下の質問は、場所データベースを管理する方法を決めるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62a2a-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="62a2a-139">**場所データベースをどのような方法で更新するのか。**</span><span class="sxs-lookup"><span data-stu-id="62a2a-139">**How will you update the location database?**</span></span>

<span data-ttu-id="62a2a-p110">場所データベースの更新が必要になる場合としては、WAP の追加、オフィスでの再配線 (別のスイッチ割り当てに変更)、サブネットの拡張など、いくつかのシナリオが考えられます。個々の場所を直接更新するのか、または CSV ファイルを使用してすべての場所の一括更新を実行するのか考慮してください。</span><span class="sxs-lookup"><span data-stu-id="62a2a-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="62a2a-142">**SNMP アプリケーションを使用して、Lync クライアントの MAC アドレスをポートおよびスイッチ ID と照合するのか。**</span><span class="sxs-lookup"><span data-stu-id="62a2a-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="62a2a-143">SNMP アプリケーションを使用する場合は、SNMP アプリケーションと場所データベースの間でスイッチ シャーシおよびポート情報の整合性を維持するための手動のプロセスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a2a-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="62a2a-144">SNMP アプリケーションがデータベースに含まれていないシャーシ IP アドレスまたはポート ID を返す場合は、位置情報サービスは場所をクライアントに返すことができませんできません。</span><span class="sxs-lookup"><span data-stu-id="62a2a-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


