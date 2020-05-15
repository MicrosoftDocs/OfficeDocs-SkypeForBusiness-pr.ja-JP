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
description: 緊急電話、緊急通話のルーティング、動的な緊急通話に関する情報など、緊急通話について説明します。
ms.openlocfilehash: 8c2de31aa81ac36338560c9b75d5c7ef27e460f8
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232548"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="9f153-103">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="9f153-103">Manage emergency calling</span></span>

<span data-ttu-id="9f153-104">この記事では、緊急通話の管理について知っておく必要がある概念について説明します。これには、緊急対応の住所、動的な緊急対応の住所、緊急通話のルーティングに関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="9f153-104">This article describes concepts you'll need to know to manage emergency calling--it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="9f153-105">この記事では、次の用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f153-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="9f153-106">**緊急対応の住所**-都市の住所。組織の事業所の所在地の住所。</span><span class="sxs-lookup"><span data-stu-id="9f153-106">**Emergency Address** - A civic address--the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="9f153-107">たとえば、住所*12345 北米、レドモンド、98052ワシントンの住所*は、適切なディスパッチ機関に緊急通報をルーティングするために使用され、緊急通報を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9f153-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="9f153-108">**配置**-通常はフロア、建物、翼、またはオフィス番号。</span><span class="sxs-lookup"><span data-stu-id="9f153-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="9f153-109">場所は、建物内の正確な位置情報を得るために、緊急対応の住所と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9f153-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="9f153-110">緊急対応の住所には、無制限の数の場所を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="9f153-111">たとえば、組織が複数の建物を持っている場合は、各建物の位置情報と各建物内のフロアごとに情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="9f153-112">**緊急**対応の場所-場所は、任意の場所に配置された都市の住所です。</span><span class="sxs-lookup"><span data-stu-id="9f153-112">**Emergency Location** - A location is a civic address--with an optional place.</span></span> <span data-ttu-id="9f153-113">事業所が複数ある場合は、複数の緊急対応の場所が必要となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="9f153-114">緊急対応の住所を作成すると、この住所の固有の場所 ID が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="9f153-115">緊急対応の住所に場所を追加した場合 (たとえば、建物の住所に床を追加した場合)、緊急対応の住所と場所を組み合わせて、場所 ID が作成されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-115">If you add a place to an emergency address--for example, if you add a floor to a building address--a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="9f153-116">この例では、2つの場所 Id があります。1つは都市の住所です。これは、結合された都市の住所と関連付けられた場所の1つです。</span><span class="sxs-lookup"><span data-stu-id="9f153-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="9f153-117">緊急対応の場所をユーザーまたはサイトに割り当てると、そのユーザーやサイトに関連付けられた一意の場所 ID になります。</span><span class="sxs-lookup"><span data-stu-id="9f153-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="9f153-118">**登録住所**-各通話プランのユーザーに割り当てられている緊急対応の住所です。静的な緊急対応の住所またはレコードのアドレスと呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f153-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="9f153-119">(登録済みアドレスは、ダイレクトルーティングユーザーには適用されません。)</span><span class="sxs-lookup"><span data-stu-id="9f153-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="9f153-120">Teams 管理センターを使用して、プランユーザーを呼び出すための緊急対応の住所を作成します。</span><span class="sxs-lookup"><span data-stu-id="9f153-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="9f153-121">緊急通話の管理方法には、電話システムの通話プランを使用するか、PSTN 接続に電話システムの直接ルーティングを使うかによって、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9f153-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="9f153-122">これらの考慮事項については、この記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="9f153-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="9f153-123">緊急対応の住所の検証</span><span class="sxs-lookup"><span data-stu-id="9f153-123">Emergency address validation</span></span>

<span data-ttu-id="9f153-124">ユーザーまたはネットワーク識別子に緊急対応の住所を割り当てるには、緊急対応の住所が "検証済み" としてマークされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="9f153-125">住所の検証では、アドレスが正当であり、割り当て後に変更できないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="9f153-126">Teams 管理センターの住所マップ検索機能を使用して、緊急対応の住所を定義した場合、住所は自動的に検証済みとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="9f153-127">検証された緊急対応の住所を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f153-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="9f153-128">そのため、住所の書式または表現が変更された場合は、更新後の形式で新しい住所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="9f153-129">緊急対応の住所の地理コード</span><span class="sxs-lookup"><span data-stu-id="9f153-129">Emergency address geo codes</span></span>

<span data-ttu-id="9f153-130">各緊急対応の住所には、geo コード (緯度と経度) を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="9f153-131">これらの geo コードは、動的な場所で緊急通話をルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="9f153-132">Teams 管理センターの住所マップ検索機能を使用して、緊急対応の住所を定義した場合、geo のコードは緊急対応の住所に自動的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9f153-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="9f153-133">また、PowerShell を使用して住所を定義した場合は、geo コードをアドレスに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="9f153-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="9f153-134">ただし、Microsoft では、Teams 管理センターのマップ検索機能を使用して、通話プランの緊急対応の住所を作成することをお勧めします。これにより、住所の書式設定、検証、適切な geo コードの設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="9f153-135">緊急通話のために緊急対応の場所をネットワーク識別子に割り当てるには、緊急対応の住所に適切な geo コードが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="9f153-136">プランの通話に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9f153-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="9f153-137">お住まいの地域で通話プランが利用可能かどうかを確認するには、「[国と地域](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)の連絡プラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="9f153-138">緊急通話の有効化</span><span class="sxs-lookup"><span data-stu-id="9f153-138">Emergency call enablement</span></span>

<span data-ttu-id="9f153-139">通話プランの各ユーザは、緊急通話のために自動的に有効になり、登録された緊急対応の住所が割り当てられた電話番号に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="9f153-140">所在地が電話番号に関連付けられている必要がある場合は、国/地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f153-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="9f153-141">米国とカナダでは、たとえば、電話番号がユーザーに割り当てられている場合は、緊急対応の場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f153-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="9f153-142">ヨーロッパ、中東、アフリカ (EMEA) など、その他の国については、Office 365 から電話番号を取得する場合、または別のサービスプロバイダーまたは携帯電話会社から電話番号を移行する場合に、緊急対応の場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f153-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="9f153-143">動的な緊急通話</span><span class="sxs-lookup"><span data-stu-id="9f153-143">Dynamic emergency calling</span></span>

<span data-ttu-id="9f153-144">Microsoft 通話プランの動的な緊急通話には、Teams クライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="9f153-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="9f153-145">適切な公開安全性の応答ポイント (PSAP) に自動的にルーティングするか、またはセキュリティデスクの担当者に通知する機能は、Teams ユーザーの使用国によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f153-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="9f153-146">プランユーザのために、緊急通報の動的な場所は、次のように米国でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9f153-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="9f153-147">(動的な緊急通話と直接ルーティングの詳細については、「[直接ルーティングの考慮事項](#considerations-for-direct-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="9f153-148">米国の通話プランのユーザー向けの Teams クライアントで、米国内で緊急対応の住所が動的に取得される場合、その住所は登録アドレスではなく緊急ルーティングに使用され、住所のサービス領域の PSAP に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="9f153-149">米国の通話プランユーザーのチームクライアントで、米国内の緊急対応の住所が動的に取得されない場合は、登録された緊急対応の住所を使って、通話の画面を表示してルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="9f153-150">ただし、発信者を適切な PSAP に接続する前に、更新されたアドレスが必要かどうかを判断するために、通話がスクリーンされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="9f153-151">米国の場合は、ネットワーク識別子に割り当てられている緊急対応の場所の一部である都市の住所を構成し、関連する geo コードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="9f153-152">詳細については、「[動的な緊急通話を計画して構成する](configure-dynamic-emergency-calling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="9f153-153">緊急通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="9f153-153">Emergency call routing</span></span>

<span data-ttu-id="9f153-154">チーム呼び出しプランのユーザーが緊急電話番号をダイヤルする場合、通話が PSAP にルーティングされる方法は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f153-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="9f153-155">緊急対応の住所が Teams クライアントによって動的に決定されるかどうか。</span><span class="sxs-lookup"><span data-stu-id="9f153-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="9f153-156">緊急対応の住所が、ユーザーの電話番号に関連付けられている登録住所であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="9f153-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="9f153-157">その国の緊急通話ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="9f153-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="9f153-158">**米国の場合:**</span><span class="sxs-lookup"><span data-stu-id="9f153-158">**In the United States:**</span></span>

  - <span data-ttu-id="9f153-159">チームクライアントがテナントで定義された動的な緊急対応の場所にある場合、そのクライアントからの緊急通話は、その地理的な場所を提供する PSAP に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="9f153-160">チームクライアントがテナントで定義された動的な緊急対応の場所に配置されていない場合、そのクライアントからの緊急通報は、その地理的な場所を提供する PSAP に通話を転送する前に、発信者の場所を特定するために、国のコールセンターによって選別されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="9f153-161">緊急通報によって、緊急対応の場所を審査センターに更新できない場合、通話は、発信者の登録アドレスを提供する PSAP に転送されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="9f153-162">**カナダ、アイルランド、英国で**は、通話を適切なディスパッチセンターに接続する前に、ユーザーの現在の場所を特定するために、緊急通話が最初にスクリーンされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="9f153-163">**フランス、ドイツ、およびスペインで**は、発信者の所在地に関係なく、電話番号に関連付けられている緊急対応の住所を提供する psap に直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="9f153-164">**オランダで**は、発信者の場所に関係なく、緊急通話は、番号のローカル市外局番に対して直接 psap にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="9f153-165">**オーストラリアで**は、緊急対応の住所が構成され、キャリアパートナーによってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="9f153-166">**日本で**は、緊急通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f153-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="9f153-167">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-167">For more information, see:</span></span>

- [<span data-ttu-id="9f153-168">通話プラン</span><span class="sxs-lookup"><span data-stu-id="9f153-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="9f153-169">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="9f153-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="9f153-170">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="9f153-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="9f153-171">直接ルーティングの考慮事項</span><span class="sxs-lookup"><span data-stu-id="9f153-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="9f153-172">通話プランがお住まいの地域で利用できない場合、または既存の電話会社を維持したい場合は、[ダイレクトルーティング](direct-routing-landing-page.md)を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="9f153-173">詳細については、「[ダイレクトルーティングを構成](direct-routing-configure.md)し、[緊急通話ルーティングポリシーを管理](manage-emergency-call-routing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="9f153-174">緊急通話の有効化と構成</span><span class="sxs-lookup"><span data-stu-id="9f153-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="9f153-175">TeamsEmergencyCallRoutingPolicy を使用して、緊急電話番号とそれに関連付けられたルーティング先を定義することで、直接ルーティングユーザー用の緊急通話ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-175">You must define emergency calling policies for Direct Routing users by using the TeamsEmergencyCallRoutingPolicy to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="9f153-176">(ダイレクトルーティングユーザーの場合、登録されている緊急対応の場所はサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="9f153-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="9f153-177">TeamsEmergencyCallRoutingPolicy は、チームのダイレクトルーティングユーザーアカウント、ネットワークサイト、またはその両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-177">You can assign a TeamsEmergencyCallRoutingPolicy to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="9f153-178">Teams クライアントがネットワーク接続を開始または変更すると、チームは次のように、クライアントが配置されているネットワークサイトの参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f153-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="9f153-179">TeamsEmergencyCallRoutingPolicy がサイトに関連付けられている場合は、サイトポリシーを使って緊急通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f153-179">If a TeamsEmergencyCallRoutingPolicy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="9f153-180">サイトに関連付けられている TeamsEmergencyCallRoutingPolicy がない場合、または未定義のサイトでクライアントが接続されている場合は、ユーザーアカウントに関連付けられた TeamsEmergencyCallRoutingPolicy を使って緊急通話を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f153-180">If there is no TeamsEmergencyCallRoutingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallRoutingPolicy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="9f153-181">チームクライアントが TeamsEmergencyCallRoutingPolicy を取得できない場合、ユーザーは緊急通話に対応していません。</span><span class="sxs-lookup"><span data-stu-id="9f153-181">If the Teams client is unable to obtain an TeamsEmergencyCallRoutingPolicy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="9f153-182">動的な緊急通話</span><span class="sxs-lookup"><span data-stu-id="9f153-182">Dynamic emergency calling</span></span>

<span data-ttu-id="9f153-183">ダイレクトルーティングユーザーのチームクライアントは、動的な緊急対応のアドレスを取得できます。これは、呼び出し元の場所に基づいて、着信を動的にルーティングするために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="9f153-184">詳細については、「[動的な緊急通話を構成する](configure-dynamic-emergency-calling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="9f153-185">緊急通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="9f153-185">Emergency call routing</span></span>

<span data-ttu-id="9f153-186">TeamsEmergencyCallRoutingPolicy は、オンライン PSTN の使用状況を参照します。適切な PSTN ゲートウェイに緊急通話を正しくルーティングするには、適切なダイレクトルーティング構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f153-186">The TeamsEmergencyCallRoutingPolicy references an online PSTN Usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="9f153-187">特に、緊急ダイヤルの文字列の OnlineVoiceRoute があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="9f153-188">詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f153-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="9f153-189">(注: チームクライアントは、Skype for Business クライアント (+ 911) と同様の方法で、緊急電話番号の前に「+」記号を付加します。</span><span class="sxs-lookup"><span data-stu-id="9f153-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="9f153-190">この動作は数か月以内に変更されるため、Teams の緊急通話では、番号の前に "+" が送信されなくなります。つまり、911。)</span><span class="sxs-lookup"><span data-stu-id="9f153-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="9f153-191">直接ルーティングユーザのために、緊急通話を動的にルーティングする機能は、特定の国の緊急通報ネットワークによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f153-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="9f153-192">次の2つの解決策があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-192">There are two solutions available:</span></span>

- <span data-ttu-id="9f153-193">緊急ルーティングサービスプロバイダー (米国のみ)</span><span class="sxs-lookup"><span data-stu-id="9f153-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="9f153-194">緊急対応の場所識別番号 (ELIN) ゲートウェイアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9f153-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="9f153-195">緊急ルーティングサービスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="9f153-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="9f153-196">米国には、発信者の所在地に基づいて緊急通話を自動的にルーティングできる、多数の認定された緊急ルーティングサービスプロバイダー (ERSPs) があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="9f153-197">緊急ルーティングサービスプロバイダーが、ダイレクトルーティングの展開に統合されている場合は、動的に取得した場所での緊急通話は、その場所を提供する公共の安全な応答ポイント (PSAP) に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="9f153-198">動的に取得した場所のない緊急通話は、更新された場所に基づいて適切なディスパッチセンターに通話を接続する前に、ユーザーの現在の位置を特定するために最初にスクリーニングされます。</span><span class="sxs-lookup"><span data-stu-id="9f153-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="9f153-199">詳しくは、「[直接ルーティング用に認定済みのセッション境界コントローラー](direct-routing-border-controllers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f153-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="9f153-200">緊急対応の場所識別番号 (ELIN) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9f153-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="9f153-201">セッション境界コントローラー (SBCs) には、緊急対応の場所識別番号 (ELIN) アプリケーションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="9f153-202">SBC ELIN アプリケーションがダイレクトルーティングの展開に統合されている場合は、ELIN アプリケーションで緊急対応の住所と関連する電話番号を設定し、その ELIN レコードをそれぞれの PSTN の緊急通話用データベースにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="9f153-203">ELIN 識別子を持つ Teams 緊急対応の場所は、ELIN アプリケーション内で一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="9f153-204">動的に取得した場所を使用する緊急通話が適切な SBC (ELIN アプリケーション) に転送されると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f153-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="9f153-205">発信者の緊急対応の場所を解析します。</span><span class="sxs-lookup"><span data-stu-id="9f153-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="9f153-206">場所を ELIN レコードと一致させる。</span><span class="sxs-lookup"><span data-stu-id="9f153-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="9f153-207">緊急電話の発信者の番号を ELIN の電話番号に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9f153-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="9f153-208">その場所を提供する PSAP に呼び出しをルーティングした後、ディスパッチャーは、アップロードされた ELIN レコードから場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f153-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="9f153-209">緊急電話番号にコールバックすると、ELIN アプリケーションでは、元の緊急通報の代わりとして呼び出された番号の代替が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="9f153-210">詳しくは、「[直接ルーティング用に認定済みのセッション境界コントローラー](direct-routing-border-controllers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f153-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="9f153-211">セキュリティデスクの通知</span><span class="sxs-lookup"><span data-stu-id="9f153-211">Security desk notification</span></span>

<span data-ttu-id="9f153-212">セキュリティデスクの通知は、Microsoft の通話プランと電話システムによる直接ルーティングの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="9f153-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="9f153-213">TeamsEmergencyCallingPolicy を使用して、緊急通話中に通知を受けるユーザーと、そのユーザーに通知を送信する方法を構成します。これには、チャットのみ、conferenced インとミュート、または conferenced とミュートにかかわらず、ミュートを解除する機能があります。</span><span class="sxs-lookup"><span data-stu-id="9f153-213">You use the TeamsEmergencyCallingPolicy to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="9f153-214">ユーザーまたはグループの外部 PSTN 番号を指定して、通話を発信したり、緊急通話に参加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9f153-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="9f153-215">TeamsEmergencyCallingPolicy は、Teams のユーザーアカウントに付与したり、ネットワークサイトまたはその両方に割り当てたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f153-215">A TeamsEmergencyCallingPolicy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="9f153-216">Teams クライアントがネットワーク接続を開始または変更すると、チームはクライアントが配置されているネットワークサイトの参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f153-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="9f153-217">TeamsEmergencyCallingPolicy がネットワークサイトに関連付けられている場合は、サイトポリシーを使ってセキュリティデスクの通知を構成します。</span><span class="sxs-lookup"><span data-stu-id="9f153-217">If a TeamsEmergencyCallingPolicy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="9f153-218">サイトに関連付けられている TeamsEmergencyCallingPolicy がない場合、または未定義のサイトでクライアントが接続されている場合は、ユーザーアカウントに関連付けられている TeamsEmergencyCallingPolicy がセキュリティデスクの通知を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-218">If there is no TeamsEmergencyCallingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallingPolicy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="9f153-219">チームクライアントが TeamsEmergencyCallingPolicy を取得できない場合、そのユーザーはセキュリティデスクの通知を有効にしていません。</span><span class="sxs-lookup"><span data-stu-id="9f153-219">If the Teams client is unable to obtain an TeamsEmergencyCallingPolicy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="9f153-220">緊急通話のときに、セキュリティデスクは、TeamsEmergencyCallingPolicy に基づいて、通話に conferenced され、セキュリティデスクユーザーのエクスペリエンスが制御されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the TeamsEmergencyCallingPolicy.</span></span> <span data-ttu-id="9f153-221">各セキュリティデスクメンバーのグループチャットが開始され、緊急通報の場所が重要なメッセージ通知で共有されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="9f153-222">会議オプションがポリシーの一部として構成されている場合、各セキュリティデスクユーザーは、会議の一部として追加されます。</span><span class="sxs-lookup"><span data-stu-id="9f153-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="9f153-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f153-223">Related topics</span></span>

- [<span data-ttu-id="9f153-224">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="9f153-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="9f153-225">緊急通話ルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="9f153-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="9f153-226">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="9f153-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="9f153-227">ユーザーの緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="9f153-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="9f153-228">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="9f153-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
