---
title: 緊急通話の計画と管理
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 緊急対応の住所、緊急通話ルーティング、動的緊急通話に関する情報など、緊急通話について説明します。
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031603"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="d1fa9-103">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="d1fa9-103">Manage emergency calling</span></span>

<span data-ttu-id="d1fa9-104">この記事では、緊急通話を管理するために知る必要がある概念について説明します。これには、緊急対応の住所、動的緊急対応の住所、緊急通話ルーティングに関する情報が &mdash; 含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="d1fa9-105">この記事では、次の用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="d1fa9-106">**緊急対応** の住所 - 組織の場所の物理的または番地の住所 &mdash; を公の住所で指定します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="d1fa9-107">たとえば、住所  *12345 North Main Street、Redmond、WA 98052* は、緊急通話を適切なディスパッチ機関にルーティングし、緊急発信者の特定を支援するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="d1fa9-108">**[場所** ] - 通常、フロア番号、ビル番号、航空番号、またはオフィス番号。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="d1fa9-109">場所は、建物内のより正確な場所を提供するために緊急対応の住所に関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="d1fa9-110">緊急対応の住所に関連付けられる場所の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="d1fa9-111">たとえば、組織に複数のビルがある場合は、各ビルの場所情報と各ビル内の各フロアの場所情報を含める必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="d1fa9-112">**緊急対応の** 場所 - 場所は、オプションの場所 &mdash; を持つ市民の住所です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="d1fa9-113">ビジネスに複数の物理的な場所がある場合は、複数の緊急対応の場所が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="d1fa9-114">緊急対応の住所を作成すると、この住所の一意の場所 ID が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="d1fa9-115">たとえば、緊急対応の住所に場所を追加する場合、建物の住所にフロアを追加すると、緊急対応の住所と場所の組み合わせの場所 &mdash; &mdash; ID が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="d1fa9-116">この例では、2 つの場所の IP があります。1 つは、市民のアドレス用です。参加した市民アドレスと関連付けられている場所用の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="d1fa9-117">緊急対応の場所をユーザーまたはサイトに割り当てると、そのユーザーまたはサイトに関連付けられている一意の場所 ID です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="d1fa9-118">**登録済み住所** - 各通話プラン ユーザーに割り当てられる緊急対応の住所。これは、静的緊急対応の住所またはレコードのアドレスと呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="d1fa9-119">(登録済みのアドレスは、ダイレクト ルーティング ユーザーには適用されません)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="d1fa9-120">通話プランのユーザーの緊急対応の住所は、管理センターでTeams作成します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="d1fa9-121">PSTN 接続に 電話システム 通話プランまたは 電話システム ダイレクト ルーティングを使用するかどうかに応じて、緊急通話の管理方法にいくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="d1fa9-122">これらの考慮事項については、この記事全体で説明します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="d1fa9-123">緊急対応の住所の検証</span><span class="sxs-lookup"><span data-stu-id="d1fa9-123">Emergency address validation</span></span>

<span data-ttu-id="d1fa9-124">緊急対応の住所をユーザーまたはネットワーク識別子に割り当てるには、緊急対応の住所が "検証済み" としてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="d1fa9-125">アドレスの検証により、アドレスが正当であり、割り当て後に変更できないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="d1fa9-126">Teams 管理センターのアドレス マップ検索機能を使用して緊急対応の住所を定義すると、その住所は自動的に検証済みとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="d1fa9-127">検証済み緊急対応の住所を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="d1fa9-128">そのため、住所の形式または表現が変更された場合は、更新された形式で新しいアドレスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="d1fa9-129">緊急対応の住所の geo コード</span><span class="sxs-lookup"><span data-stu-id="d1fa9-129">Emergency address geo codes</span></span>

<span data-ttu-id="d1fa9-130">各緊急対応の住所には、地理コード (緯度と経度) を関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="d1fa9-131">これらの geo コードは、動的な場所での緊急通話のルーティングを支援するために、一部の国で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="d1fa9-132">Teams 管理センターのアドレス マップ検索機能を使用して緊急対応の住所を定義した場合、geo コードは自動的に緊急対応の住所に関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="d1fa9-133">PowerShell を使用してアドレスを定義する場合は、geo コードをアドレスに関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="d1fa9-134">ただし、microsoft では、Teams 管理センターのマップ検索機能を使用して、通話プランの緊急対応の住所を作成し、住所の書式設定、検証、適切な geo コードの設定を行う方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="d1fa9-135">緊急対応の場所を動的緊急通話のネットワーク識別子に割り当てるには、緊急対応の住所に適切な geo コードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="d1fa9-136">通話プランに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d1fa9-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="d1fa9-137">地域で通話プランを利用できるかどうかについては、「通話プランの国と地域の利用可 [否」を参照してください](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="d1fa9-138">緊急通話の有効化</span><span class="sxs-lookup"><span data-stu-id="d1fa9-138">Emergency call enablement</span></span>

<span data-ttu-id="d1fa9-139">通話プランの各ユーザーは、緊急通話に対して自動的に有効になります。割り当てられた電話番号に関連付けられている登録済みの緊急対応の住所が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="d1fa9-140">場所を電話番号に関連付けなければならない場合は、国/地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="d1fa9-141">たとえば、米国とカナダでは、ユーザーに番号を割り当てるときに緊急対応の場所が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="d1fa9-142">ヨーロッパ、中東、アフリカ (EMEA) などの他の国では、Microsoft 365 または Office 365 から電話番号を取得する場合、または別のサービス プロバイダーまたは運送業者から電話番号を転送する場合は、緊急対応の場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Microsoft 365 or Office 365, or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="d1fa9-143">動的緊急通話</span><span class="sxs-lookup"><span data-stu-id="d1fa9-143">Dynamic emergency calling</span></span>

<span data-ttu-id="d1fa9-144">Microsoft 通話プランの動的緊急通話は、クライアントの現在の場所に基づいて緊急通話を構成し、ルーティングTeamsします。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="d1fa9-145">適切な公衆安全応答ポイント (PSAP) への自動ルーティングを行う機能、またはセキュリティ デスクの担当者に通知する機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="d1fa9-146">通話プランのユーザーの場合、緊急通話をルーティングする動的な場所は、次のように米国でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="d1fa9-147">(動的緊急通話と直接ルーティングについては、「ダイレクト ルーティングに関する [考慮事項」を参照してください](#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="d1fa9-148">米国通話プランのユーザーの Teams クライアントが米国内で緊急対応の住所を動的に取得した場合、その住所は登録された住所ではなく緊急ルーティングに使用され、そのアドレスのサービス領域の PSAP に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="d1fa9-149">米国通話Teamsユーザーのクライアントが米国内で緊急対応の住所を動的に取得しない場合は、登録された緊急対応の住所を使用して通話の画面とルーティングを行います。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="d1fa9-150">ただし、呼び出し元を適切な PSAP に接続する前に、更新されたアドレスが必要かどうかを判断するために、呼び出しが画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="d1fa9-151">米国では、ネットワーク識別子に割り当てられている緊急対応の場所の一部であり、関連付けられている geo コードを含む、市民の住所を構成 &mdash; する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="d1fa9-152">詳細については、「動的緊急通話の [計画と構成」を参照してください](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="d1fa9-153">緊急通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="d1fa9-153">Emergency call routing</span></span>

<span data-ttu-id="d1fa9-154">通話プランTeamsユーザーが緊急電話番号にダイヤルすると、呼び出しが PSAP にルーティングされる方法は、次の条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="d1fa9-155">緊急対応の住所がクライアントによって動的にTeamsかどうか。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="d1fa9-156">緊急対応の住所が、ユーザーの電話番号に関連付けられている登録済み住所かどうか。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="d1fa9-157">その国の緊急通話ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="d1fa9-158">**米国の場合:**</span><span class="sxs-lookup"><span data-stu-id="d1fa9-158">**In the United States:**</span></span>

  - <span data-ttu-id="d1fa9-159">テナントがTeamsが定義した動的緊急対応の場所にクライアントが存在する場合、そのクライアントからの緊急通話は、その地理的な場所を提供する PSAP に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="d1fa9-160">Teams クライアントがテナント定義の動的緊急対応の場所に存在しない場合、そのクライアントからの緊急通話は、その地理的な場所にサービスを提供する PSAP に通話を転送する前に、呼び出し元の場所を特定するために、国内のコール センターによって画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="d1fa9-161">緊急発信者が緊急対応の場所をスクリーニング センターに更新できない場合、通話は発信者の登録された住所を提供する PSAP に転送されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="d1fa9-162">**カナダ、アイルランド、** 英国では、緊急通話が最初に画面に表示され、通話を適切なディスパッチ センターに接続する前に、ユーザーの現在の場所が決定されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="d1fa9-163">**フランス、ドイツ**、スペインでは、緊急通話は、発信者の場所に関係なく、番号に関連付けられている緊急対応の住所を提供する PSAP に直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="d1fa9-164">**オランダでは、** 発信者の場所に関係なく、緊急通話は番号のローカル エリア コードの PSAP に直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="d1fa9-165">**オーストラリアでは**、緊急対応の住所が構成され、運送業者パートナーによってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="d1fa9-166">**日本では**、緊急通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="d1fa9-167">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-167">For more information, see:</span></span>

- [<span data-ttu-id="d1fa9-168">通話プラン</span><span class="sxs-lookup"><span data-stu-id="d1fa9-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="d1fa9-169">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="d1fa9-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="d1fa9-170">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="d1fa9-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="d1fa9-171">ダイレクト ルーティングに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d1fa9-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="d1fa9-172">地域で通話プランを利用できない場合、または既存の運送業者を維持する場合は、直接ルーティングを [検討してください](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="d1fa9-173">詳細については、「ダイレクト ルーティングの [構成」と「](direct-routing-configure.md) 緊急通話ルーティング [ポリシーの管理」を参照してください](manage-emergency-call-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="d1fa9-174">緊急通話の有効化と構成</span><span class="sxs-lookup"><span data-stu-id="d1fa9-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="d1fa9-175">Teams 緊急通話ルーティング ポリシー (TeamsEmergencyCallRoutingPolicy) を使用して緊急電話番号と関連するルーティング先を定義することで、ダイレクト ルーティング ユーザーの緊急通話ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="d1fa9-176">(登録済みの緊急対応の場所は、直接ルーティング ユーザーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="d1fa9-177">緊急通話ルーティング ポリシーは、直接ルーティング ユーザー アカウントTeamsネットワーク サイト、または両方に割り当て可能です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="d1fa9-178">クライアントがTeamsまたはネットワーク接続を変更すると、Teams は、クライアントが位置するネットワーク サイトの参照を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="d1fa9-179">緊急通話ルーティング ポリシーがサイトに関連付けられている場合は、サイト ポリシーを使用して緊急通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="d1fa9-180">サイトに関連付けられている緊急通話ルーティング ポリシーがない場合、またはクライアントが未定義のサイトに接続されている場合は、ユーザー アカウントに関連付けられている緊急通話ルーティング ポリシーを使用して緊急通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="d1fa9-181">クライアントTeams緊急通話ルーティング ポリシーを取得できない場合、ユーザーは緊急通話を有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="d1fa9-182">動的緊急通話</span><span class="sxs-lookup"><span data-stu-id="d1fa9-182">Dynamic emergency calling</span></span>

<span data-ttu-id="d1fa9-183">Teamsルーティング ユーザー用のクライアントは、動的緊急アドレスを取得できます。これは、呼び出し元の場所に基づいて呼び出しを動的にルーティングするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="d1fa9-184">詳細については、「動的緊急通話の [構成」を参照してください](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="d1fa9-185">緊急通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="d1fa9-185">Emergency call routing</span></span>

<span data-ttu-id="d1fa9-186">緊急通話ルーティング ポリシーは、オンライン PSTN 使用法を参照します。緊急通話を適切な PSTN ゲートウェイに適切にルーティングするには、適切な直接ルーティング構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="d1fa9-187">特に、緊急ダイヤル文字列に OnlineVoiceRoute が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="d1fa9-188">詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="d1fa9-189">(注: Teams クライアントが緊急電話番号の前に "+" 記号を付け、Skype for Business クライアントと同様の方法で 、つまり +911。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="d1fa9-190">この動作は数か月以内に変更され、緊急Teams番号の前に "+" が送信されなくなります。つまり、911)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="d1fa9-191">ダイレクト ルーティング ユーザーの緊急通話を動的にルーティングする機能は、特定の国内の緊急通話ネットワークによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="d1fa9-192">次の 2 つのソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-192">There are two solutions available:</span></span>

- <span data-ttu-id="d1fa9-193">緊急ルーティング サービス プロバイダー (米国のみ)</span><span class="sxs-lookup"><span data-stu-id="d1fa9-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="d1fa9-194">緊急位置情報識別番号 (ELIN) ゲートウェイ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d1fa9-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="d1fa9-195">緊急ルーティング サービス プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d1fa9-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="d1fa9-196">米国には、発信者の場所に基づいて緊急通話を自動的にルーティングできる多数の認定緊急ルーティング サービス プロバイダー (ERSP) があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="d1fa9-197">緊急ルーティング サービス プロバイダーが直接ルーティング展開に統合されている場合、動的に取得された場所を持つ緊急通話は、その場所を提供するパブリック セーフティ応答ポイント (PSAP) に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="d1fa9-198">動的に取得された場所がない緊急通話は、最初に、更新された場所に基づいて適切なディスパッチ センターに通話を接続する前に、ユーザーの現在の場所を決定するために画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="d1fa9-199">詳細については、直接ルーティングの [認定を受けたセッション ボーダー コントローラーに関するページを参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="d1fa9-200">緊急位置情報識別番号 (ELIN) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d1fa9-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="d1fa9-201">セッション ボーダー コントローラー (SBC) には、緊急位置情報識別番号 (ELIN) アプリケーションを含めできます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="d1fa9-202">SBC ELIN アプリケーションが直接ルーティング展開に統合されている場合は、ELIN アプリケーションで緊急対応の住所と関連する電話番号を構成し、それぞれの PSTN の緊急通話データベースに ELIN レコードをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="d1fa9-203">Teams ELIN 識別子を持つ緊急対応の場所は、ELIN アプリケーション内の緊急対応の場所と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="d1fa9-204">動的に取得された場所を含む緊急通話が適切な SBC にルーティングされる場合、ELIN アプリケーションは次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="d1fa9-205">呼び出し元の緊急対応の場所を解析します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="d1fa9-206">ELIN レコードの場所と一致します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="d1fa9-207">緊急発信者番号を ELIN 電話番号に置き換える。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="d1fa9-208">その場所を提供する PSAP に呼び出しをルーティングし、ディスパッチャーはアップロードされた ELIN レコードから場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="d1fa9-209">緊急電話番号にコールバックすると、ELIN アプリケーションは、元の緊急呼び出し元の番号に対して逆の番号置換を行います。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="d1fa9-210">詳細については、直接ルーティングの [認定を受けたセッション ボーダー コントローラーに関するページを参照してください](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="d1fa9-211">セキュリティ デスクの通知</span><span class="sxs-lookup"><span data-stu-id="d1fa9-211">Security desk notification</span></span>

<span data-ttu-id="d1fa9-212">セキュリティ デスク通知は、Microsoft 通話プランと直接ルーティングの両方電話システム利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="d1fa9-213">Teams 緊急通話ポリシー (TeamsEmergencyCallingPolicy) を使用して、緊急通話中に通知を受け取るユーザーと通知方法を構成します。チャットのみ、会議中とミュート状態、またはミュート状態で電話会議を行うがミュート解除機能。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="d1fa9-214">また、緊急通話を呼び出して参加するユーザーまたはグループの外部 PSTN 番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="d1fa9-215">緊急通話ポリシーは、ネットワーク サイトTeams割り当てられたユーザー アカウント、または両方に付与できます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="d1fa9-216">クライアントがTeamsまたはネットワーク接続を変更すると、クライアントTeamsがあるネットワーク サイトの参照が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="d1fa9-217">緊急通話ポリシーがネットワーク サイトに関連付けられている場合は、サイト ポリシーを使用してセキュリティ デスク通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="d1fa9-218">サイトに関連付けられている緊急通話ポリシーがない場合、またはクライアントが未定義のサイトに接続されている場合は、ユーザー アカウントに関連付けられている緊急通話ポリシーを使用して、セキュリティ デスク通知が構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="d1fa9-219">クライアントTeams緊急呼び出しポリシーを取得できない場合、ユーザーはセキュリティ デスク通知を有効にしません。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="d1fa9-220">緊急通話中は、セキュリティ デスクが通話に電話会議を行い、セキュリティ デスク ユーザーのエクスペリエンスは、緊急通話ポリシーに基Teams制御されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="d1fa9-221">各セキュリティ デスク メンバーとグループ チャットが開始され、緊急呼び出し元の場所は重要なメッセージ通知を介して共有されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="d1fa9-222">会議オプションがポリシーの一部として構成されている場合、各セキュリティ デスク ユーザーは会議の一部として追加で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d1fa9-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="d1fa9-223">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d1fa9-223">Related topics</span></span>

- [<span data-ttu-id="d1fa9-224">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="d1fa9-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="d1fa9-225">緊急通話ルーティング ポリシーを管理する </span><span class="sxs-lookup"><span data-stu-id="d1fa9-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="d1fa9-226">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="d1fa9-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="d1fa9-227">ユーザーの緊急対応の場所を割り当てるまたは変更する</span><span class="sxs-lookup"><span data-stu-id="d1fa9-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="d1fa9-228">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="d1fa9-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
