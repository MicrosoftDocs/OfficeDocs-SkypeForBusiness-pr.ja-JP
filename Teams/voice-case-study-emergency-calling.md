---
title: Teams Contoso のケース スタディ
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
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786101"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="96861-103">Contoso のケース スタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="96861-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="96861-104">緊急通話の可用性と緊急通話に関連する用語を理解するために、緊急対応の住所、場所、緊急対応の場所、および登録済み住所 Contoso は、「緊急通話の管理と動的緊急通話の計画と構成」を確認 &mdash; &mdash; [しました](configure-dynamic-emergency-calling.md)。 [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="96861-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="96861-105">このOffice 365プランのユーザーは、緊急通話に対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="96861-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="96861-106">ただし、緊急通話のルーティングに動的な場所を使用できるのは、米国の通話プラン ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="96861-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="96861-107">直接ルーティングの場合、Contoso は、緊急通話をルーティングするために、および場合によってはパートナーの接続に追加の構成が必要なことを学習しました。</span><span class="sxs-lookup"><span data-stu-id="96861-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="96861-108">管理者は、緊急ルーティング サービス プロバイダー (ERSP) (米国) への接続を構成するか、緊急位置情報識別番号 (ELIN) アプリケーションのセッション ボーダー コントローラー (SBC) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96861-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="96861-109">Contoso は、米国および米国外にオフィスを持っています。</span><span class="sxs-lookup"><span data-stu-id="96861-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="96861-110">米国では、Contoso 通話プランのユーザーは、緊急通話のルーティングに動的な場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="96861-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="96861-111">米国外では、Contoso は通話プランを使用する一部のサイトと、直接ルーティングを介して電話システムに接続されている一部のサイトを持っています。</span><span class="sxs-lookup"><span data-stu-id="96861-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="96861-112">緊急通話の使用例</span><span class="sxs-lookup"><span data-stu-id="96861-112">Emergency calling use cases</span></span>

<span data-ttu-id="96861-113">Contoso がシステムに接続する方法を決定電話、Contoso は次の緊急通話の使用例を特定しました。</span><span class="sxs-lookup"><span data-stu-id="96861-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="96861-114">米国の通話プラン ユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="96861-115">米国外の通話プラン ユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="96861-116">ダイレクト ルーティングを介して電話システムに接続するユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="96861-117">米国の通話プラン ユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="96861-118">電話番号を緊急対応の場所に関連付けする必要がある場合の要件があります。</span><span class="sxs-lookup"><span data-stu-id="96861-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="96861-119">これらの要件を理解するために、Contoso は「プランの呼び出し [に関する考慮事項」を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="96861-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="96861-120">Contoso は、これらの要件に基づいて、米国内のユーザーに番号が割り当てられると、場所を電話番号に関連付けすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="96861-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="96861-121">米国外の通話プラン ユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="96861-122">緊急対応の場所に電話番号を関連付けする必要がある場合を理解するために、Contoso は「通話プランに関する考慮事項  [」を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="96861-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="96861-123">Contoso は要件に基づいて、次の条件を決定しました。</span><span class="sxs-lookup"><span data-stu-id="96861-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="96861-124">カナダのユーザーに番号が割り当てられると、その場所と電話番号が関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="96861-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="96861-125">Contoso が緊急対応の場所を割り当てるのは、電話番号が Office 365 から取得された場合、または別のサービス プロバイダーまたは運送業者から番号が転送された場合です。</span><span class="sxs-lookup"><span data-stu-id="96861-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="96861-126">ダイレクト ルーティングを介して電話システムに接続するユーザー</span><span class="sxs-lookup"><span data-stu-id="96861-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="96861-127">この使用例の緊急ルーティングを計画するために、Contoso は直接ルーティングに関 [する考慮事項を確認しました](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="96861-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="96861-128">直接ルーティングユーザーは通話プランのユーザーと同じ方法で緊急通話を受信しないので、Contoso は緊急通話を提供する方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96861-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="96861-129">ダイレクト ルーティングは、緊急ルーティング サービス プロバイダー (ERSP) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="96861-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="96861-130">直接ルーティングには、緊急位置情報識別番号 (ELIN) を含む SBC を含め、SBC を設定できます。</span><span class="sxs-lookup"><span data-stu-id="96861-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="96861-131">緊急ルーティング サービス プロバイダー (ERSP) に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="96861-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="96861-132">緊急ルーティング サービス プロバイダー (ERSP) は、発信者の場所に基づいて緊急通話を自動的にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="96861-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="96861-133">緊急ルーティング サービス プロバイダーが直接ルーティング展開に統合されている場合、動的に取得された場所を持つ緊急通話は、その場所を提供するパブリック セーフティ応答ポイント (PSAP) に自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="96861-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="96861-134">動的に取得された場所がない緊急通話は、最初に、更新された場所に基づいて適切なディスパッチ センターに通話を接続する前に、ユーザーの現在の場所を決定するために画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96861-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="96861-135">ELIN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="96861-135">ELIN considerations</span></span>

<span data-ttu-id="96861-136">SBC ELIN アプリケーションが直接ルーティング展開に統合されている場合は、緊急対応の住所を電話番号に関連付ける追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96861-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="96861-137">Contoso は、緊急位置情報識別番号 (ELIN) アプリケーションを含むセッション ボーダー コントローラーを使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="96861-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="96861-138">セキュリティ デスクの通知</span><span class="sxs-lookup"><span data-stu-id="96861-138">Security desk notification</span></span>

<span data-ttu-id="96861-139">緊急通話が発信された場合にセキュリティ デスクに通知する機能は、Microsoft 通話プランと直接ルーティングの両方電話システム使用できます。</span><span class="sxs-lookup"><span data-stu-id="96861-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="96861-140">Contoso は、セキュリティ デスク通知の詳細を確認して、これがオフィスで構成される必要かどうかを判断しました</span><span class="sxs-lookup"><span data-stu-id="96861-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="96861-141">Contoso は、セキュリティ デスク通知を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="96861-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="96861-142">構成</span><span class="sxs-lookup"><span data-stu-id="96861-142">Configuration</span></span> 

<span data-ttu-id="96861-143">Contoso は、「動的緊急通話を構成 [する」の手順に従って、次の手順を実行](configure-dynamic-emergency-calling.md) しました。</span><span class="sxs-lookup"><span data-stu-id="96861-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="96861-144">緊急対応の住所を割り当てる</span><span class="sxs-lookup"><span data-stu-id="96861-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="96861-145">ネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="96861-145">Configure network settings</span></span> 

- <span data-ttu-id="96861-146">Location Information Service の構成</span><span class="sxs-lookup"><span data-stu-id="96861-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="96861-147">緊急ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="96861-147">Configure emergency policies</span></span> 

- <span data-ttu-id="96861-148">ユーザーとサイトを有効にする</span><span class="sxs-lookup"><span data-stu-id="96861-148">Enable users and sites</span></span> 

- <span data-ttu-id="96861-149">緊急通話をテストする</span><span class="sxs-lookup"><span data-stu-id="96861-149">Test emergency calling</span></span> 

<span data-ttu-id="96861-150">動的緊急通話が構成された後、Contoso は適切なユーザーに場所を割り当てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="96861-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="96861-151">組織の緊急対応の場所を追加、変更、または削除するには、「組織の緊急対応の場所を追加、変更、または削除する」の手順 [に従いました。](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="96861-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="96861-152">建物、フロア、オフィスの場所を作成するために、Contoso は「緊急対応の場所を追加、変更、または削除する」の手順 [に従いました](add-change-remove-emergency-place-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="96861-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="96861-153">緊急対応の場所を割り当てるには、「ユーザーの緊急対応の場所を割り当てるまたは変更する」 [の手順に従いました](assign-change-emergency-location-user.md)。</span><span class="sxs-lookup"><span data-stu-id="96861-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 