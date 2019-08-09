---
title: 電話システムのダイレクト ルーティング サービスに関する決定を行う - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 直接ルーティング、ライセンス、および必要な決定事項について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d3410616cf3e841ab6689ffd0fea772975b484c
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271437"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="870e3-103">サービスの決定を行う</span><span class="sxs-lookup"><span data-stu-id="870e3-103">Make my service decisions</span></span>

<span data-ttu-id="870e3-104">電話システムによる直接ルーティング ("直接ルーティング") の技術実装を計画するには、定義したビジネス要件を満たすソリューションを実装するために、事前に一連のサービス決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="870e3-105">Teams での通話</span><span class="sxs-lookup"><span data-stu-id="870e3-105">Calling in Teams</span></span>

<span data-ttu-id="870e3-106">Microsoft Teams では、ユーザーは公衆交換電話網 (PSTN) との間で電話をかけたり受けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="870e3-107">ユーザーは、独自の専用電話番号を使用して、Teams クライアントアプリケーションから国内および国際通話 (ボイスメールを含む) を発信および受信できます。</span><span class="sxs-lookup"><span data-stu-id="870e3-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="870e3-108">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="870e3-108">Direct Routing</span></span>

<span data-ttu-id="870e3-109">Lync ユーザーが PSTN 通話を発信および受信できるようにするには、Office 365 の機能である電話システムで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="870e3-110">PSTN への接続を有効にするには、ダイレクトルーティングを使用して、組織内のユーザーに PSTN 経由で組織外の電話を発信および受信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="870e3-111">直接ルーティングを使用すると、PSTN 接続はサードパーティプロバイダーによって提供されるため、PSTN サービスプロバイダーによって提供された既存の PSTN trunks を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="870e3-112">これにより、電話システムが通話プラン (「通話プラン」) を使用できない、または既存の PSTN サービスプロバイダコントラクトを管理する必要がある、または特定のオンプレミスシステムとの相互運用性を備えている展開で、展開することができます。必須。</span><span class="sxs-lookup"><span data-stu-id="870e3-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="870e3-113">直接ルーティングの可用性</span><span class="sxs-lookup"><span data-stu-id="870e3-113">Availability of Direct Routing</span></span>

<span data-ttu-id="870e3-114">直接ルーティングは、Office 365 を利用できるすべての国で利用できます。</span><span class="sxs-lookup"><span data-stu-id="870e3-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="870e3-115">これらの国のリストについては、「[国際可用性](https://products.office.com/business/international-availability)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="870e3-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="870e3-116">組織が電話システム機能を入手できることを確認した後、利用可能な国と地域の一覧に基づいて、電話システムを実装するユーザーの場所またはオフィスのリストをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="870e3-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="870e3-117">また、通話プランを有効にするユーザー、または取得している各場所のダイレクトルーティングを有効にするユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-118">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-118">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-119">電話システムを実装するユーザーの場所またはオフィスを特定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="870e3-120">通話プランを有効にするユーザー、またはお持ちの各場所のダイレクトルーティングを有効にするユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-121">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-121">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-122">電話システム用に有効にするユーザーの場所またはオフィスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="870e3-123">通話プランを有効にするユーザーのリストを作成する、または、持っている場所ごとに直接ルーティングする</span><span class="sxs-lookup"><span data-stu-id="870e3-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="870e3-124">次に示すのは、ダイレクトルーティングサイトの有効化リストの例です。</span><span class="sxs-lookup"><span data-stu-id="870e3-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="870e3-125">**Office**</span><span class="sxs-lookup"><span data-stu-id="870e3-125">**Office**</span></span>                     | <span data-ttu-id="870e3-126">**場所**</span><span class="sxs-lookup"><span data-stu-id="870e3-126">**Location**</span></span>   | <span data-ttu-id="870e3-127">**電話システムサービス**</span><span class="sxs-lookup"><span data-stu-id="870e3-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="870e3-128">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="870e3-128">One Epping Road</span></span>                | <span data-ttu-id="870e3-129">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="870e3-129">Australia</span></span>      | <span data-ttu-id="870e3-130">従来の PSTN サービス</span><span class="sxs-lookup"><span data-stu-id="870e3-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="870e3-131">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="870e3-131">100 Cyberport Road</span></span>             | <span data-ttu-id="870e3-132">香港特別自治区</span><span class="sxs-lookup"><span data-stu-id="870e3-132">Hong Kong SAR</span></span>  | <span data-ttu-id="870e3-133">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="870e3-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="870e3-134">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="870e3-134">One Marina Boulevard</span></span>           | <span data-ttu-id="870e3-135">シンガポール</span><span class="sxs-lookup"><span data-stu-id="870e3-135">Singapore</span></span>      | <span data-ttu-id="870e3-136">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="870e3-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="870e3-137">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="870e3-137">32 London Bridge Street</span></span>        | <span data-ttu-id="870e3-138">イギリス</span><span class="sxs-lookup"><span data-stu-id="870e3-138">United Kingdom</span></span> | <span data-ttu-id="870e3-139">通話プランを使用した電話システム</span><span class="sxs-lookup"><span data-stu-id="870e3-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="870e3-140">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="870e3-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="870e3-141">フランス</span><span class="sxs-lookup"><span data-stu-id="870e3-141">France</span></span>         | <span data-ttu-id="870e3-142">通話プランを使用した電話システム</span><span class="sxs-lookup"><span data-stu-id="870e3-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="870e3-143">電話番号と緊急対応の場所</span><span class="sxs-lookup"><span data-stu-id="870e3-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="870e3-144">電話システムでは、組織内のすべてのユーザーが、固有の直通ダイヤル (電話番号) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="870e3-145">ダイレクトルーティングでは、電話番号と緊急サービスが PSTN サービスプロバイダーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="870e3-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="870e3-146">直接ルーティングを使用すると、ユーザーは PSTN サービスプロバイダーによって提供される独自の電話番号を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="870e3-147">次のテンプレートを使用して、電話番号の詳細を文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="870e3-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="870e3-148">User</span></span> |<span data-ttu-id="870e3-149">電話番号</span><span class="sxs-lookup"><span data-stu-id="870e3-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="870e3-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="870e3-150">Emily Braun</span></span> | <span data-ttu-id="870e3-151">+ 44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="870e3-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="870e3-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="870e3-152">Lidia Holloway</span></span> | <span data-ttu-id="870e3-153">+ 44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="870e3-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="870e3-154">ルイス Lahr</span><span class="sxs-lookup"><span data-stu-id="870e3-154">Louis Lahr</span></span> | <span data-ttu-id="870e3-155">+ 44 23 4567 8921</span><span class="sxs-lookup"><span data-stu-id="870e3-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="870e3-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="870e3-156">Marcel Beauchamp</span></span> | <span data-ttu-id="870e3-157">TBA</span><span class="sxs-lookup"><span data-stu-id="870e3-157">TBA</span></span> |
> |<span data-ttu-id="870e3-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="870e3-158">Rachelle Cormier</span></span> | <span data-ttu-id="870e3-159">TBA</span><span class="sxs-lookup"><span data-stu-id="870e3-159">TBA</span></span> |
> |<span data-ttu-id="870e3-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="870e3-160">Isabell Potvin</span></span> | <span data-ttu-id="870e3-161">TBA</span><span class="sxs-lookup"><span data-stu-id="870e3-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="870e3-162">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="870e3-162">Voicemail</span></span>

<span data-ttu-id="870e3-163">Azure ボイスメールサービスを利用したクラウドボイスメールは、Exchange メールボックスのみを対象としたボイスメールのデポジットをサポートしており、サードパーティのメールシステムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="870e3-163">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="870e3-164">クラウドボイスメールには、既定で組織内のすべてのユーザーに対して有効になるボイスメールの議事録が含まれています。</span><span class="sxs-lookup"><span data-stu-id="870e3-164">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="870e3-165">ビジネスニーズによっては、特定のユーザーまたは組織全体のすべてのユーザーに対してボイスメールを無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="870e3-166">組織でボイスメールの議事録を有効にしておくことを決定した場合は、ボイスメールの書き起こしのマスクを有効にする必要があるかどうかも検討してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="870e3-167">詳細については[、「組織でボイスメールポリシーを設定](set-up-phone-system-voicemail.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="870e3-168">電話システムの実装でのボイスメールの詳細については、「[クラウドボイスメールをセットアップ](set-up-phone-system-voicemail.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-168">For more information about voicemail in a Phone System implementation, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-169">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-169">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-170">直接ルーティングの実装でクラウドボイスメールを有効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-170">Decide whether you’ll enable Cloud Voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="870e3-171">組織全体または特定のユーザーに対して、ボイスメールやボイスメールの書き起こしのプロファニティのマスキングを有効または無効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-172">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-172">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-173">必要に応じて、クラウドボイスメールをサポートする判断ポイントを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-173">If applicable, document the decision points to support Cloud Voicemail.</span></span><li><span data-ttu-id="870e3-174">ボイスメール、ボイスメール、ボイスメールを有効または無効にすることで、特定のユーザーに対してのみプロファニティのマスキングを行うことができます。その場合は、ユーザーのリストを記録します。</span><span class="sxs-lookup"><span data-stu-id="870e3-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="870e3-175">次の表のように、通話プランの実装のクラウドボイスメールの詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="870e3-175">Cloud Voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="870e3-176">**User**</span><span class="sxs-lookup"><span data-stu-id="870e3-176">**User**</span></span>         | <span data-ttu-id="870e3-177">**Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="870e3-177">**Exchange mailbox**</span></span> | <span data-ttu-id="870e3-178">**ボイスメールを有効にしますか?**</span><span class="sxs-lookup"><span data-stu-id="870e3-178">**Enable voicemail?**</span></span> | <span data-ttu-id="870e3-179">**ボイスメールの書き起こし**</span><span class="sxs-lookup"><span data-stu-id="870e3-179">**Voicemail transcription**</span></span> | <span data-ttu-id="870e3-180">**ボイスメールの書き起こしのプロファニティマスク**</span><span class="sxs-lookup"><span data-stu-id="870e3-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="870e3-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="870e3-181">Emily Braun</span></span>      | <span data-ttu-id="870e3-182">オンライン</span><span class="sxs-lookup"><span data-stu-id="870e3-182">Online</span></span>               | <span data-ttu-id="870e3-183">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-183">Yes</span></span>                   | <span data-ttu-id="870e3-184">有効</span><span class="sxs-lookup"><span data-stu-id="870e3-184">Enabled</span></span>                     | <span data-ttu-id="870e3-185">有効</span><span class="sxs-lookup"><span data-stu-id="870e3-185">Enabled</span></span>                                       |
> | <span data-ttu-id="870e3-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="870e3-186">Lidia Holloway</span></span>   | <span data-ttu-id="870e3-187">オンライン</span><span class="sxs-lookup"><span data-stu-id="870e3-187">Online</span></span>               | <span data-ttu-id="870e3-188">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-188">Yes</span></span>                   | <span data-ttu-id="870e3-189">有効</span><span class="sxs-lookup"><span data-stu-id="870e3-189">Enabled</span></span>                     | <span data-ttu-id="870e3-190">無効</span><span class="sxs-lookup"><span data-stu-id="870e3-190">Disabled</span></span>                                      |
> | <span data-ttu-id="870e3-191">ルイス Lahr</span><span class="sxs-lookup"><span data-stu-id="870e3-191">Louis Lahr</span></span>       | <span data-ttu-id="870e3-192">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="870e3-192">On-premises</span></span>          | <span data-ttu-id="870e3-193">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-193">Yes</span></span>                   | <span data-ttu-id="870e3-194">有効</span><span class="sxs-lookup"><span data-stu-id="870e3-194">Enabled</span></span>                     | <span data-ttu-id="870e3-195">有効</span><span class="sxs-lookup"><span data-stu-id="870e3-195">Enabled</span></span>                                       |
> | <span data-ttu-id="870e3-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="870e3-196">Marcel Beauchamp</span></span> | <span data-ttu-id="870e3-197">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="870e3-197">On-premises</span></span>          | <span data-ttu-id="870e3-198">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-198">Yes</span></span>                   | <span data-ttu-id="870e3-199">無効</span><span class="sxs-lookup"><span data-stu-id="870e3-199">Disabled</span></span>                    | <span data-ttu-id="870e3-200">N/A</span><span class="sxs-lookup"><span data-stu-id="870e3-200">N/A</span></span>                                           |
> | <span data-ttu-id="870e3-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="870e3-201">Rachelle Cormier</span></span> | <span data-ttu-id="870e3-202">オンライン</span><span class="sxs-lookup"><span data-stu-id="870e3-202">Online</span></span>               | <span data-ttu-id="870e3-203">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-203">Yes</span></span>                   | <span data-ttu-id="870e3-204">無効</span><span class="sxs-lookup"><span data-stu-id="870e3-204">Disabled</span></span>                    | <span data-ttu-id="870e3-205">N/A</span><span class="sxs-lookup"><span data-stu-id="870e3-205">N/A</span></span>                                           |
> | <span data-ttu-id="870e3-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="870e3-206">Isabell Potvin</span></span>   | <span data-ttu-id="870e3-207">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="870e3-207">On-premises</span></span>          | <span data-ttu-id="870e3-208">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-208">Yes</span></span>                   | <span data-ttu-id="870e3-209">無効</span><span class="sxs-lookup"><span data-stu-id="870e3-209">Disabled</span></span>                    | <span data-ttu-id="870e3-210">N/A</span><span class="sxs-lookup"><span data-stu-id="870e3-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="870e3-211">チームとボイスメールを使用するには、ユーザーが Exchange メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="870e3-212">詳細については[、「Exchange および Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="870e3-213">直接ルーティングのライセンス</span><span class="sxs-lookup"><span data-stu-id="870e3-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="870e3-214">組織で直接ルーティングを使用する予定がある場合は、必要なライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="870e3-215">直接ルーティングのユーザーには、Office 365 で次のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="870e3-216">Microsoft 電話システム</span><span class="sxs-lookup"><span data-stu-id="870e3-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="870e3-217">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="870e3-217">Microsoft Teams</span></span>

-   <span data-ttu-id="870e3-218">電話会議</span><span class="sxs-lookup"><span data-stu-id="870e3-218">Audio Conferencing</span></span>

<span data-ttu-id="870e3-219">電話会議ライセンスは、スケジュールされた会議に外部参加者を追加するために必要です。または、ダイヤルイン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="870e3-220">外部からの参加者がダイヤルアウトされると、電話会議サービスはオンライン通話機能を使用して通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="870e3-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="870e3-221">電話会議ライセンスはオプションであり、電話会議が含まれている Teams 会議を開催するユーザーにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="870e3-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="870e3-222">無料電話会議用の電話番号を提供し、国際電話番号への会議のダイヤルアウトをサポートするには、組織の[通信クレジット](what-are-communications-credits.md)を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="870e3-223">電話会議と電話システムは、Office 365 E3 または E1 のサブスクリプションプランを使用している既存のユーザーのために、アドオンサービスとして個別にライセンスを付与することができます。これらは、Office 365 E5 サブスクリプションプランの一部として既に含まれています。</span><span class="sxs-lookup"><span data-stu-id="870e3-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="870e3-224">また、通話をサードパーティの Pbx にルーティングするときに、プランの呼び出しが有効になっているユーザーに対して直接ルーティングを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="870e3-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="870e3-225">詳しくは、「[ライセンスおよび直接ルーティングのその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="870e3-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-226">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-226">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-227">組織に必要な電話システムのライセンスがない場合は、電話システムのライセンスを取得するかどうかを決定します。既存の Office 365 サブスクリプションをステップアップするか、電話システムアドオンサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="870e3-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="870e3-228">直接ルーティングの実装で通信クレジットが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-229">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-229">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-230">電話システムのライセンスを割り当てる部門、部門、office、ユーザーグループを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="870e3-231">無料電話番号を使用した電話会議が範囲内にある場合は、部門、部門、office、またはユーザーグループを文書化して、通信クレジットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="870e3-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="870e3-232">Office 365 に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="870e3-232">Office 365 considerations</span></span>

<span data-ttu-id="870e3-233">直接ルーティングを有効にするすべてのユーザーは、Office 365 に所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="870e3-234">オンプレミスの Skype for Business Server または Lync Server とのハイブリッド展開の場合、ユーザーを Skype for Business Online に移行した後で、Teams との直接ルーティングを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="870e3-235">直接ルーティングの実装のスコープを持つすべてのユーザーが Teams で有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="870e3-236">Onmicrosoft.com ドメインは\*直接ルーティングでは使用できないため、Office 365 テナントは1つ以上のドメインで有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="870e3-237">ドメインと Office 365 テナントの詳細については、「ドメインに関する[FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-238">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-238">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-239">ダイレクトルーティングをサポートするために、ユーザーを Skype for Business Online に移行する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="870e3-240">チームに対して有効にする必要があるユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-241">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-241">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-242">Skype for Business Online に移行する必要があり、Teams で有効になっているユーザーのリストを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="870e3-243">SBC に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="870e3-243">SBC considerations</span></span>

<span data-ttu-id="870e3-244">ユーザーに対して PSTN 接続を提供するために、直接ルーティングサービスとペアリングする必要がある、認定およびサポートされているセッション境界コントローラー (SBCs) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="870e3-245">認定された SBCs の一覧については、[サポートされているセッション境界コントローラー](direct-routing-plan.md#supported-session-border-controllers-sbcs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="870e3-246">環境、場所の数、音声ルーティングの要件によっては、ユーザーベースをサポートするために複数の SBCs を展開することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="870e3-247">SBC ドメイン名</span><span class="sxs-lookup"><span data-stu-id="870e3-247">SBC domain names</span></span>

<span data-ttu-id="870e3-248">直接ルーティングとペアリングする各 SBC には、一意の DNS 名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="870e3-249">SBC DNS 名は、Office 365 テナントに登録されているドメイン名のいずれかに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="870e3-250">テナントに複数のドメイン名が割り当てられている場合は、SBCs の DNS 名を計画するときに、次のいずれかのドメイン名を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="870e3-251">SBC DNS 名に \*. onmicrosoft.com を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="870e3-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="870e3-252">証明書</span><span class="sxs-lookup"><span data-stu-id="870e3-252">Certificates</span></span>

<span data-ttu-id="870e3-253">直接ルーティングを使用して展開する各 SBC には、サポートされている証明機関の一覧から取得した証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="870e3-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="870e3-254">証明書には、[件名]、[サブジェクトの代替名]、または [共通名] の各フィールドに SBC DNS 名が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="870e3-255">SBCs でのワイルドカード証明書の使用もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="870e3-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="870e3-256">詳細とサポートされている証明機関の一覧については、「 [SBC の信頼できる証明書](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="870e3-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="870e3-257">SBC IP アドレスとポート</span><span class="sxs-lookup"><span data-stu-id="870e3-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="870e3-258">各 SBC は、Office 365 データセンターからアクセスできるパブリック IP アドレスを使って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="870e3-259">また、ネットワークアドレス変換 (NAT) を構成して、Office 365 データセンターに SBCs を公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="870e3-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="870e3-260">SBCs には、通信とメディアのためにクラウドサービスと通信するための双方向接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="870e3-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="870e3-261">シグナリングは*SIP プロキシ*という名前のコンポーネントによって処理され、メディアは*メディアプロセッサ*によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="870e3-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="870e3-262">SIP シグナリングとメディアの各 SBC に特定のポート番号を定義し、これらのポートと関連する IP アドレスへの双方向トラフィックを許可するようにファイアウォールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="870e3-263">詳細については、「 [SIP シグナリング: fqdn](direct-routing-plan.md#sip-signaling-fqdns)および[メディアトラフィック: ポート範囲](direct-routing-plan.md#media-traffic-port-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-263">For more details, see [SIP Signaling: FQDNs](direct-routing-plan.md#sip-signaling-fqdns) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="870e3-264">SBC モデルに基づいて、各 SBC に最大同時セッションの制限を設定することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="870e3-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="870e3-265">この制限により、SBC がそのキャパシティを超えて実行されているときに、通知がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="870e3-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-266">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-266">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-267">SBCs を展開する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="870e3-268">展開を計画している各 SBC の DNS 名を決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="870e3-269">SBC ドメイン名の決定に基づいて、展開内のすべての SBCs をサポートするためにワイルドカード証明書を使用するか、SBC あたりの専用証明書を使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="870e3-270">SBCs の証明書を取得するパブリック証明機関を決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="870e3-271">展開する SBC ごとにパブリック IP アドレスとポートのペアを定義し、パブリック IP アドレスを SBCs に割り当てるか、NAT を使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="870e3-272">各 SBC がサポートまたは処理できる同時セッションの最大数を特定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="870e3-273">メディアバイパスを使用して、どの SBCs を構成するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-274">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-274">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-275">次の例の表を使用して、SBCs に対して行われる各決定を文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="870e3-276">次のテンプレートを使用して、ダイレクトルーティングの展開の SBC の詳細を文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="870e3-277">**SBC DNS 名 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="870e3-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="870e3-278">**SBC のメーカーとモデル**</span><span class="sxs-lookup"><span data-stu-id="870e3-278">**SBC make and model**</span></span> | <span data-ttu-id="870e3-279">**証明書**</span><span class="sxs-lookup"><span data-stu-id="870e3-279">**Certificate**</span></span> | <span data-ttu-id="870e3-280">**場所**</span><span class="sxs-lookup"><span data-stu-id="870e3-280">**Location**</span></span>  | <span data-ttu-id="870e3-281">**IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="870e3-281">**IP address**</span></span> | <span data-ttu-id="870e3-282">**SIP シグナリングポート**</span><span class="sxs-lookup"><span data-stu-id="870e3-282">**SIP signaling port**</span></span> | <span data-ttu-id="870e3-283">**NAT?**</span><span class="sxs-lookup"><span data-stu-id="870e3-283">**NAT?**</span></span> | <span data-ttu-id="870e3-284">**同時セッションの最大数**</span><span class="sxs-lookup"><span data-stu-id="870e3-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="870e3-285">**メディアのバイパスは有効ですか?**</span><span class="sxs-lookup"><span data-stu-id="870e3-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="870e3-286">SBC-Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="870e3-287">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-287">TBD</span></span> | <span data-ttu-id="870e3-288">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-288">\*.contoso.com</span></span> | <span data-ttu-id="870e3-289">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="870e3-289">Amsterdam</span></span> | <span data-ttu-id="870e3-290">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-290">TBD</span></span> | <span data-ttu-id="870e3-291">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-291">TBD</span></span> | <span data-ttu-id="870e3-292">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-292">Yes</span></span> | <span data-ttu-id="870e3-293">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-293">TBD</span></span> | <span data-ttu-id="870e3-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="870e3-294">No</span></span> |
> | <span data-ttu-id="870e3-295">SBC-Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="870e3-296">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-296">TBD</span></span> | <span data-ttu-id="870e3-297">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-297">\*.contoso.com</span></span> | <span data-ttu-id="870e3-298">香港特別自治区</span><span class="sxs-lookup"><span data-stu-id="870e3-298">Hong Kong SAR</span></span> | <span data-ttu-id="870e3-299">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-299">TBD</span></span> | <span data-ttu-id="870e3-300">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-300">TBD</span></span> | <span data-ttu-id="870e3-301">いいえ</span><span class="sxs-lookup"><span data-stu-id="870e3-301">No</span></span> | <span data-ttu-id="870e3-302">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-302">TBD</span></span> | <span data-ttu-id="870e3-303">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-303">Yes</span></span> |
> | <span data-ttu-id="870e3-304">SBC-Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="870e3-305">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-305">TBD</span></span> | <span data-ttu-id="870e3-306">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-306">\*.contoso.com</span></span> | <span data-ttu-id="870e3-307">ヨハネスブルグ</span><span class="sxs-lookup"><span data-stu-id="870e3-307">Johannesburg</span></span> | <span data-ttu-id="870e3-308">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-308">TBD</span></span> | <span data-ttu-id="870e3-309">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-309">TBD</span></span> | <span data-ttu-id="870e3-310">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-310">Yes</span></span> | <span data-ttu-id="870e3-311">TBD</span><span class="sxs-lookup"><span data-stu-id="870e3-311">TBD</span></span> | <span data-ttu-id="870e3-312">はい</span><span class="sxs-lookup"><span data-stu-id="870e3-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="870e3-313">音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="870e3-313">Voice routing</span></span>

<span data-ttu-id="870e3-314">特定の SBCs のダイレクトルーティングの着信をルーティングするように Microsoft 電話システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="870e3-315">ボイスルーティングは、次のように設定できます。</span><span class="sxs-lookup"><span data-stu-id="870e3-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="870e3-316">"番号パターン" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="870e3-316">Called number pattern.</span></span>

-   <span data-ttu-id="870e3-317">"番号パターン" と呼ばれ、通話を発信したユーザー。</span><span class="sxs-lookup"><span data-stu-id="870e3-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="870e3-318">通話ルーティングは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="870e3-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="870e3-319">音声ルーティングポリシー– PSTN 使用のコンテナー。ユーザーまたは複数のユーザーに割り当てることができる</span><span class="sxs-lookup"><span data-stu-id="870e3-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="870e3-320">PSTN 使用状況–ボイスルートと PSTN 使用のコンテナー。異なる音声ルーティングポリシーで共有できる</span><span class="sxs-lookup"><span data-stu-id="870e3-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="870e3-321">ボイスルーティング–番号パターンとオンライン PSTN ゲートウェイのセットによって、通話番号がパターンと一致する通話に使用されます。</span><span class="sxs-lookup"><span data-stu-id="870e3-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="870e3-322">オンライン PSTN ゲートウェイ-SBC では、(PAI) または best コーデックなど、SBC を使用して通話を発信するときに適用される構成も保存されます。音声ルートに追加できます</span><span class="sxs-lookup"><span data-stu-id="870e3-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="870e3-323">直接ルーティングと通話プランを共存させるようにボイスルートを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="870e3-324">この構成では、直接ルーティングを使用して、通話プランで特定の SBCs への一部の通話をルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="870e3-325">SBCs は、*アクティブな\*\*バックアップ*として指定できます。</span><span class="sxs-lookup"><span data-stu-id="870e3-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="870e3-326">つまり、この数値パターンに対してアクティブとして構成されている SBC、または数値パターンと特定のユーザーを使用できない場合、通話はバックアップ SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="870e3-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-327">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-327">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-328">直接ルーティングの実装のために、ユーザーの場所またはオフィスをサポートするために作成する音声ルーティングポリシー、PSTN 使用、および音声ルートを決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-329">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-329">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-330">組織のボイスルーティングポリシー、PSTN 使用、および音声ルートをドキュメント化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="870e3-331">定義するボイスルーティングポリシーごとに割り当てるユーザーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="870e3-332">次のテンプレートを使用して、ダイレクトルーティングの展開用のボイスポリシーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="870e3-333">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="870e3-333">**PSTN usage**</span></span> | <span data-ttu-id="870e3-334">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="870e3-334">**Voice route**</span></span> | <span data-ttu-id="870e3-335">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="870e3-335">**Number pattern**</span></span> | <span data-ttu-id="870e3-336">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="870e3-336">**Priority**</span></span> | <span data-ttu-id="870e3-337">**SBC**</span><span class="sxs-lookup"><span data-stu-id="870e3-337">**SBC**</span></span> | <span data-ttu-id="870e3-338">**説明**</span><span class="sxs-lookup"><span data-stu-id="870e3-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="870e3-339">米国限定</span><span class="sxs-lookup"><span data-stu-id="870e3-339">US only</span></span> | <span data-ttu-id="870e3-340">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="870e3-340">“Redmond 1”</span></span> | <span data-ttu-id="870e3-341">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="870e3-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="870e3-342">1</span><span class="sxs-lookup"><span data-stu-id="870e3-342">1</span></span> | <span data-ttu-id="870e3-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="870e3-344">呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="870e3-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="870e3-345">米国限定</span><span class="sxs-lookup"><span data-stu-id="870e3-345">US only</span></span> | <span data-ttu-id="870e3-346">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="870e3-346">“Redmond 2”</span></span> | <span data-ttu-id="870e3-347">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="870e3-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="870e3-348">2</span><span class="sxs-lookup"><span data-stu-id="870e3-348">2</span></span> | <span data-ttu-id="870e3-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="870e3-350">呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート</span><span class="sxs-lookup"><span data-stu-id="870e3-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="870e3-351">米国限定</span><span class="sxs-lookup"><span data-stu-id="870e3-351">US only</span></span> | <span data-ttu-id="870e3-352">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="870e3-352">"Other +1”</span></span> | <span data-ttu-id="870e3-353">\^\\+ 1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="870e3-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="870e3-354">3</span><span class="sxs-lookup"><span data-stu-id="870e3-354">3</span></span> | <span data-ttu-id="870e3-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="870e3-356">"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="870e3-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="870e3-357">International</span><span class="sxs-lookup"><span data-stu-id="870e3-357">International</span></span> | <span data-ttu-id="870e3-358">International</span><span class="sxs-lookup"><span data-stu-id="870e3-358">International</span></span> | <span data-ttu-id="870e3-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="870e3-359">\\d+</span></span> | <span data-ttu-id="870e3-360">4</span><span class="sxs-lookup"><span data-stu-id="870e3-360">4</span></span> | <span data-ttu-id="870e3-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="870e3-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="870e3-362">任意の番号パターンのルート</span><span class="sxs-lookup"><span data-stu-id="870e3-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="870e3-363">ボイスルーティングポリシーの PSTN 使用は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="870e3-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="870e3-364">通話と相互運用ポリシー</span><span class="sxs-lookup"><span data-stu-id="870e3-364">Calling and Interop policies</span></span>

<span data-ttu-id="870e3-365">直接ルーティングは、Microsoft Teams でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="870e3-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="870e3-366">直接ルーティングによって PSTN 通話を発信または受信するには、Teams での着信通話を確実に受信するために必要なポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="870e3-367">直接ルーティングが有効になっているユーザーは、Skype for Business を使用して直接ルーティング通話を発信または受信できないため、チームクライアントを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="870e3-368">次の2つの方法のいずれかを使用して、チームを優先クライアントとして設定するようにユーザーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="870e3-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="870e3-369">ユーザーをチーム専用モードに構成する</span><span class="sxs-lookup"><span data-stu-id="870e3-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="870e3-370">Teams のスケールのポリシーと TeamsInteropPolicy を割り当てて、優先呼び出しクライアントとしてチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="870e3-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="870e3-371">詳細については、「[ユーザー向けの優先発信クライアントとして Microsoft Teams を設定](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="870e3-372">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="870e3-372">Decision points</span></span>|<ul><li><span data-ttu-id="870e3-373">通話の優先クライアントとしてチームを設定するために使用する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="870e3-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="870e3-374">次のステップ</span><span class="sxs-lookup"><span data-stu-id="870e3-374">Next steps</span></span>|<ul><li><span data-ttu-id="870e3-375">相互運用ポリシーと呼び出しポリシーを使って構成するユーザーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="870e3-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="870e3-376">ユーザーがチーム専用モードに構成されている場合、このユーザーは Skype for Business にサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="870e3-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="870e3-377">チームクライアントで [通話] タブが表示されるようにするには、テナントの組織レベルでプライベート通話を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="870e3-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="870e3-378">プライベートな通話を有効にする方法の詳細については、「 [Microsoft Teams の通話を有効](direct-routing-configure.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="870e3-379">ドキュメントサービスの決定</span><span class="sxs-lookup"><span data-stu-id="870e3-379">Document service decisions</span></span>

<span data-ttu-id="870e3-380">この記事の前のセクションの情報を使用して、サービスの決定を文書化してください。</span><span class="sxs-lookup"><span data-stu-id="870e3-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="870e3-381">一般的に、このドキュメントには次のメインセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="870e3-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="870e3-382">通話プランのサイト有効化リストが表示された電話システム</span><span class="sxs-lookup"><span data-stu-id="870e3-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="870e3-383">ボイスメールの設定の詳細</span><span class="sxs-lookup"><span data-stu-id="870e3-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="870e3-384">電話システムのダイレクトルーティングユーザーのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="870e3-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="870e3-385">SBC 構成の詳細</span><span class="sxs-lookup"><span data-stu-id="870e3-385">SBC configuration details</span></span>

-   <span data-ttu-id="870e3-386">ボイスルーティングポリシーとルーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="870e3-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="870e3-387">相互運用機能と通話ポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="870e3-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
