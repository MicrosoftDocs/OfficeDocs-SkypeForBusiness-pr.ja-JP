---
title: チームボイスの Contoso のケーススタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786101"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="57bb8-103">Contoso のケーススタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="57bb8-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="57bb8-104">緊急通話の利用可否、緊急通報の &mdash; 緊急対応の住所、場所、緊急対応の場所、および登録済みの住所については、「緊急通話の管理」と「緊急 &mdash; 通報の[計画と設定](configure-dynamic-emergency-calling.md)」を確認してください。 [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="57bb8-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="57bb8-105">Office 365 では、通話プランのユーザーは緊急通話に対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="57bb8-106">ただし、アメリカ国内の通話プランのユーザーのみが、緊急通話のルーティングに動的な場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="57bb8-107">直接ルーティングの場合、Contoso は緊急通話をルーティングするために追加の構成が必要であるということを伝えましたが、パートナー接続の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="57bb8-108">管理者は、緊急ルーティングサービスプロバイダ (ERSP) (米国) への接続を構成するか、緊急対応の位置情報識別番号 (ELIN) アプリケーションのセッションボーダーコントローラー (SBC) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="57bb8-109">Contoso には米国と米国外の支社があります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="57bb8-110">米国では、Contoso 通話プランのユーザーは、緊急通話のルーティングに動的な場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="57bb8-111">米国外では、Contoso には、通話プランと、電話システムに接続されたいくつかのサイトを、直接ルーティング経由で使用しているサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="57bb8-112">緊急通話の使用例</span><span class="sxs-lookup"><span data-stu-id="57bb8-112">Emergency calling use cases</span></span>

<span data-ttu-id="57bb8-113">Contoso が電話システムに接続する方法を決定したら、Contoso は次の緊急通話のユースケースを特定しました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="57bb8-114">米国の通話プランユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="57bb8-115">米国外への通話プランユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="57bb8-116">直接ルーティングを介して電話システムに接続しているユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="57bb8-117">米国の通話プランユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="57bb8-118">緊急対応の場所に電話番号を関連付ける必要がある場合は、条件があります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="57bb8-119">これらの要件について理解するために、Contoso は[通話プランの考慮事項について](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)検討しています。</span><span class="sxs-lookup"><span data-stu-id="57bb8-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="57bb8-120">これらの要件に基づき、Contoso は、米国のユーザーに番号が割り当てられたときに、その場所を電話番号に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="57bb8-121">米国外への通話プランユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="57bb8-122">緊急対応の場所に電話番号が関連付けられている必要があるタイミングを理解するために、Contoso は[通話プランの考慮事項につい](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)て検討しています。</span><span class="sxs-lookup"><span data-stu-id="57bb8-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="57bb8-123">Contoso は要件に基づいて、次のことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="57bb8-124">Contoso は、カナダのユーザーに番号が割り当てられたときに、その場所を電話番号に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="57bb8-125">Contoso は、電話番号が Office 365 から取得された場合、または別のサービスプロバイダーまたは携帯電話会社から電話番号が移行された場合に、緊急対応の場所を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="57bb8-126">直接ルーティングを介して電話システムに接続しているユーザー</span><span class="sxs-lookup"><span data-stu-id="57bb8-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="57bb8-127">このユースケースで緊急ルーティングを計画するには、Contoso が[直接ルーティングの考慮事項](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)を確認します。</span><span class="sxs-lookup"><span data-stu-id="57bb8-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="57bb8-128">直接ルーティングユーザーは、プランのユーザーと同じ方法で緊急電話を受けることはできないため、Contoso は緊急通話の提供方法を決定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="57bb8-129">ダイレクトルーティングは、緊急ルーティングサービスプロバイダ (ERSP) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="57bb8-130">直接ルーティングには、緊急対応の場所識別番号 (ELIN) を含む SBC も含まれています。</span><span class="sxs-lookup"><span data-stu-id="57bb8-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="57bb8-131">緊急ルーティングサービスプロバイダ (ERSP) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="57bb8-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="57bb8-132">緊急ルーティングサービスプロバイダ (ERSPs) では、発信者の場所に基づいて緊急通話が自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="57bb8-133">緊急ルーティングサービスプロバイダーが、ダイレクトルーティングの展開に統合されている場合は、動的に取得した場所での緊急通話は、その場所を提供する公共の安全な応答ポイント (PSAP) に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="57bb8-134">動的に取得した場所のない緊急通話は、更新された場所に基づいて適切なディスパッチセンターに通話を接続する前に、ユーザーの現在の位置を特定するために最初にスクリーニングされます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="57bb8-135">ELIN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="57bb8-135">ELIN considerations</span></span>

<span data-ttu-id="57bb8-136">SBC ELIN アプリケーションがダイレクトルーティング展開に統合されている場合は、緊急対応の住所を電話番号に関連付けるために、追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57bb8-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="57bb8-137">Contoso は、緊急対応の場所識別番号 (ELIN) アプリケーションを含むセッション境界コントローラーの使用を決定しました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="57bb8-138">セキュリティデスクの通知</span><span class="sxs-lookup"><span data-stu-id="57bb8-138">Security desk notification</span></span>

<span data-ttu-id="57bb8-139">緊急通話が行われたときに、セキュリティデスクに通知する機能は、Microsoft の通話プランと電話システムによる直接ルーティングの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="57bb8-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="57bb8-140">Contoso はセキュリティデスク通知の詳細を確認して、オフィスでこれを構成する必要があるかどうかを判断しました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="57bb8-141">Contoso はセキュリティデスクの通知を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="57bb8-142">構成</span><span class="sxs-lookup"><span data-stu-id="57bb8-142">Configuration</span></span> 

<span data-ttu-id="57bb8-143">Contoso は以下の手順に従って、[[動的な緊急通話の構成](configure-dynamic-emergency-calling.md):</span><span class="sxs-lookup"><span data-stu-id="57bb8-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="57bb8-144">緊急対応の住所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="57bb8-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="57bb8-145">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="57bb8-145">Configure network settings</span></span> 

- <span data-ttu-id="57bb8-146">位置情報サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="57bb8-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="57bb8-147">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="57bb8-147">Configure emergency policies</span></span> 

- <span data-ttu-id="57bb8-148">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="57bb8-148">Enable users and sites</span></span> 

- <span data-ttu-id="57bb8-149">緊急通話のテスト</span><span class="sxs-lookup"><span data-stu-id="57bb8-149">Test emergency calling</span></span> 

<span data-ttu-id="57bb8-150">動的な緊急通話が構成されると、Contoso はその場所を適切なユーザーに割り当てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="57bb8-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="57bb8-151">組織の緊急対応の場所を追加、変更、または削除するには、「[組織の緊急対応の場所を追加、変更、または削除](add-change-remove-emergency-location-organization.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="57bb8-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="57bb8-152">建物、床、オフィスの場所を作成するために、Contoso は[緊急対応の場所を追加、変更、または削除](add-change-remove-emergency-place-organization.md)する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="57bb8-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="57bb8-153">緊急対応の場所を割り当てるには、「[ユーザーの緊急対応の場所を割り当てまたは変更](assign-change-emergency-location-user.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="57bb8-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 