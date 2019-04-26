---
title: 電話システムのダイレクト ルーティング サービスに関する決定を行う - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: については直接ルーティングでは、ライセンス、および意思決定をする必要があります。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a2371c72f24b19b9e3c4fe836a59cbc800ad1c4
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304718"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="c6898-103">[サービスの決定を行う</span><span class="sxs-lookup"><span data-stu-id="c6898-103">Make my service decisions</span></span>

<span data-ttu-id="c6898-104">電話システム直接ルーティング (「直接ルーティング」) の技術的な実装を計画するには、一連のサービスの決定事前組織のビジネス要件を満たすソリューションを実装する準備が定義されているを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="c6898-105">チームでの通話</span><span class="sxs-lookup"><span data-stu-id="c6898-105">Calling in Teams</span></span>

<span data-ttu-id="c6898-106">マイクロソフト チームは、ユーザーが配置し、その公衆交換電話網 (PSTN) との間に電話を受けます。</span><span class="sxs-lookup"><span data-stu-id="c6898-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="c6898-107">ユーザーは、チームのクライアント アプリケーションを配置すると、国内および国際電話 (ボイスメールを含む) を受信自分専用の電話番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="c6898-108">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="c6898-108">Direct Routing</span></span>

<span data-ttu-id="c6898-109">チームを配置し、PSTN の呼び出しを受信できるユーザー、電話システムでは、Office 365 の機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="c6898-110">PSTN への接続を有効にするには、ことができますルーティングを使用して直接に組織し、PSTN 上で、組織外の電話を受信するのに機能をユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="c6898-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="c6898-111">直接ルーティングでは、PSTN への接続が引き続き PSTN サービス プロバイダーによって提供される、既存の PSTN トランクを使用できるようになり、サードパーティのプロバイダーによって容易にします。</span><span class="sxs-lookup"><span data-stu-id="c6898-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="c6898-112">配置 (「呼び出し計画」) 計画を呼び出すと、電話システムが利用されていない国で、または、既存の PSTN サービス プロバイダー コントラクトを保持する必要や、特定の設置型システムとの相互運用性の導入では、この必須。</span><span class="sxs-lookup"><span data-stu-id="c6898-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="c6898-113">直接ルーティングの可用性</span><span class="sxs-lookup"><span data-stu-id="c6898-113">Availability of Direct Routing</span></span>

<span data-ttu-id="c6898-114">直接ルーティングは、Office 365 が利用可能な任意の国であります。</span><span class="sxs-lookup"><span data-stu-id="c6898-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="c6898-115">これらの国の一覧については、[国際的な可用性](https://products.office.com/business/international-availability)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="c6898-116">組織が電話システムの機能を取得できることを確認するには後に、、ユーザーの所在地、またはオフィスの場所を実装する場合の利用可能な国や地域の一覧を基に、電話システムのリストをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="c6898-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="c6898-117">あるそれぞれの場所の計画を呼び出すか、直接ルーティングを有効にするしようとするユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="c6898-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-118">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-118">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-119">ユーザーの所在地、またはオフィスの電話システムを実装することを識別します。</span><span class="sxs-lookup"><span data-stu-id="c6898-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="c6898-120">ある場合、それぞれの場所の計画を呼び出すか、直接ルーティングを有効にしようとするユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="c6898-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-121">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-121">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-122">ユーザーの所在地、またはオフィスの電話システムを有効にするを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="c6898-123">ある場合、それぞれの場所の計画を呼び出すか、直接ルーティングを有効にしようとするユーザーの一覧を文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="c6898-124">サイト対応の直接ルーティングの一覧の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c6898-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="c6898-125">**Office**</span><span class="sxs-lookup"><span data-stu-id="c6898-125">**Office**</span></span>                     | <span data-ttu-id="c6898-126">**場所**</span><span class="sxs-lookup"><span data-stu-id="c6898-126">**Location**</span></span>   | <span data-ttu-id="c6898-127">**電話システム サービス**</span><span class="sxs-lookup"><span data-stu-id="c6898-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="c6898-128">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="c6898-128">One Epping Road</span></span>                | <span data-ttu-id="c6898-129">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="c6898-129">Australia</span></span>      | <span data-ttu-id="c6898-130">従来の PSTN サービス</span><span class="sxs-lookup"><span data-stu-id="c6898-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="c6898-131">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="c6898-131">100 Cyberport Road</span></span>             | <span data-ttu-id="c6898-132">香港特別自治区</span><span class="sxs-lookup"><span data-stu-id="c6898-132">Hong Kong SAR</span></span>  | <span data-ttu-id="c6898-133">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="c6898-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="c6898-134">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="c6898-134">One Marina Boulevard</span></span>           | <span data-ttu-id="c6898-135">シンガポール</span><span class="sxs-lookup"><span data-stu-id="c6898-135">Singapore</span></span>      | <span data-ttu-id="c6898-136">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="c6898-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="c6898-137">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="c6898-137">32 London Bridge Street</span></span>        | <span data-ttu-id="c6898-138">イギリス</span><span class="sxs-lookup"><span data-stu-id="c6898-138">United Kingdom</span></span> | <span data-ttu-id="c6898-139">通話プランと電話システム</span><span class="sxs-lookup"><span data-stu-id="c6898-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="c6898-140">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="c6898-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="c6898-141">フランス</span><span class="sxs-lookup"><span data-stu-id="c6898-141">France</span></span>         | <span data-ttu-id="c6898-142">通話プランと電話システム</span><span class="sxs-lookup"><span data-stu-id="c6898-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="c6898-143">電話番号と緊急時の場所</span><span class="sxs-lookup"><span data-stu-id="c6898-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="c6898-144">電話システムには、独自の直接内側 (DID) 電話番号をダイヤルして、組織内のすべてのユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="c6898-145">直接ルーティングでは、電話番号と緊急時のサービスは PSTN サービス プロバイダーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="c6898-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="c6898-146">直接ルーティングでは、ユーザーは、PSTN サービス プロバイダーによって提供される、自分の電話番号を使用して続行できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="c6898-147">次のテンプレートを使用すると、電話番号の詳細を文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="c6898-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="c6898-148">User</span></span> |<span data-ttu-id="c6898-149">電話番号</span><span class="sxs-lookup"><span data-stu-id="c6898-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="c6898-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="c6898-150">Emily Braun</span></span> | <span data-ttu-id="c6898-151">+44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="c6898-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="c6898-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="c6898-152">Lidia Holloway</span></span> | <span data-ttu-id="c6898-153">+44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="c6898-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="c6898-154">ルイ Lahr</span><span class="sxs-lookup"><span data-stu-id="c6898-154">Louis Lahr</span></span> | <span data-ttu-id="c6898-155">+44 23 4567 ・ 8921</span><span class="sxs-lookup"><span data-stu-id="c6898-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="c6898-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="c6898-156">Marcel Beauchamp</span></span> | <span data-ttu-id="c6898-157">TBA</span><span class="sxs-lookup"><span data-stu-id="c6898-157">TBA</span></span> |
> |<span data-ttu-id="c6898-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="c6898-158">Rachelle Cormier</span></span> | <span data-ttu-id="c6898-159">TBA</span><span class="sxs-lookup"><span data-stu-id="c6898-159">TBA</span></span> |
> |<span data-ttu-id="c6898-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="c6898-160">Isabell Potvin</span></span> | <span data-ttu-id="c6898-161">TBA</span><span class="sxs-lookup"><span data-stu-id="c6898-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="c6898-162">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="c6898-162">Voicemail</span></span>

<span data-ttu-id="c6898-163">電源は、Azure のボイスメール サービスが、クラウドのボイスメール ボイスメール出金のみの Exchange メールボックスをサポートしている、サード ・ パーティ製の電子メール システムをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="c6898-163">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="c6898-164">クラウドのボイス メールには、組織内のすべてのユーザーに対して既定で有効には、ボイスメールの議事録が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6898-164">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="c6898-165">ビジネス ニーズは、特定のユーザーまたは組織全体のすべてのユーザーのボイスメールの議事録作成を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="c6898-166">ボイスメールの議事録作成を有効にする場合、組織は、ボイスメールの議事録の不適切なマスキングを有効にする必要かどうかについても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="c6898-167">詳細については[、組織内のボイス メール ポリシーの設定](set-up-phone-system-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="c6898-168">電話システムの実装でボイスメールの詳細については、[クラウドのボイス メールの設定](set-up-phone-system-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-168">For more information about voicemail in a Phone System implementation, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-169">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-169">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-170">直接ルーティングの実装では、クラウドのボイスメールを有効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-170">Decide whether you’ll enable Cloud Voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="c6898-171">有効にするまたはボイスメールの議事録と、組織全体または特定のユーザーのボイスメールの議事録不適切なマスキングを無効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-172">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-172">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-173">該当する場合は、クラウドのボイスメールをサポートするための意思決定ポイントを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-173">If applicable, document the decision points to support Cloud Voicemail.</span></span><li><span data-ttu-id="c6898-174">有効にしたり、ボイス メール、ボイスメールの議事録、およびボイスメールの議事録の不適切なマスキング特定のユーザーに対してのみ無効にする場合、は、ユーザーの一覧を文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="c6898-175">クラウドのボイスメールの詳細計画を呼び出す実装は、次の表に示すように文書化することができます。</span><span class="sxs-lookup"><span data-stu-id="c6898-175">Cloud Voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="c6898-176">**User**</span><span class="sxs-lookup"><span data-stu-id="c6898-176">**User**</span></span>         | <span data-ttu-id="c6898-177">**Exchange メールボックス**</span><span class="sxs-lookup"><span data-stu-id="c6898-177">**Exchange mailbox**</span></span> | <span data-ttu-id="c6898-178">**ボイスメールを有効にしますか。**</span><span class="sxs-lookup"><span data-stu-id="c6898-178">**Enable voicemail?**</span></span> | <span data-ttu-id="c6898-179">**ボイスメールの議事録**</span><span class="sxs-lookup"><span data-stu-id="c6898-179">**Voicemail transcription**</span></span> | <span data-ttu-id="c6898-180">**ボイスメールの議事録の不適切なマスキング**</span><span class="sxs-lookup"><span data-stu-id="c6898-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="c6898-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="c6898-181">Emily Braun</span></span>      | <span data-ttu-id="c6898-182">オンライン</span><span class="sxs-lookup"><span data-stu-id="c6898-182">Online</span></span>               | <span data-ttu-id="c6898-183">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-183">Yes</span></span>                   | <span data-ttu-id="c6898-184">有効</span><span class="sxs-lookup"><span data-stu-id="c6898-184">Enabled</span></span>                     | <span data-ttu-id="c6898-185">有効</span><span class="sxs-lookup"><span data-stu-id="c6898-185">Enabled</span></span>                                       |
> | <span data-ttu-id="c6898-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="c6898-186">Lidia Holloway</span></span>   | <span data-ttu-id="c6898-187">オンライン</span><span class="sxs-lookup"><span data-stu-id="c6898-187">Online</span></span>               | <span data-ttu-id="c6898-188">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-188">Yes</span></span>                   | <span data-ttu-id="c6898-189">有効</span><span class="sxs-lookup"><span data-stu-id="c6898-189">Enabled</span></span>                     | <span data-ttu-id="c6898-190">無効</span><span class="sxs-lookup"><span data-stu-id="c6898-190">Disabled</span></span>                                      |
> | <span data-ttu-id="c6898-191">ルイ Lahr</span><span class="sxs-lookup"><span data-stu-id="c6898-191">Louis Lahr</span></span>       | <span data-ttu-id="c6898-192">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="c6898-192">On-premises</span></span>          | <span data-ttu-id="c6898-193">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-193">Yes</span></span>                   | <span data-ttu-id="c6898-194">有効</span><span class="sxs-lookup"><span data-stu-id="c6898-194">Enabled</span></span>                     | <span data-ttu-id="c6898-195">有効</span><span class="sxs-lookup"><span data-stu-id="c6898-195">Enabled</span></span>                                       |
> | <span data-ttu-id="c6898-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="c6898-196">Marcel Beauchamp</span></span> | <span data-ttu-id="c6898-197">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="c6898-197">On-premises</span></span>          | <span data-ttu-id="c6898-198">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-198">Yes</span></span>                   | <span data-ttu-id="c6898-199">無効</span><span class="sxs-lookup"><span data-stu-id="c6898-199">Disabled</span></span>                    | <span data-ttu-id="c6898-200">N/A</span><span class="sxs-lookup"><span data-stu-id="c6898-200">N/A</span></span>                                           |
> | <span data-ttu-id="c6898-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="c6898-201">Rachelle Cormier</span></span> | <span data-ttu-id="c6898-202">オンライン</span><span class="sxs-lookup"><span data-stu-id="c6898-202">Online</span></span>               | <span data-ttu-id="c6898-203">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-203">Yes</span></span>                   | <span data-ttu-id="c6898-204">無効</span><span class="sxs-lookup"><span data-stu-id="c6898-204">Disabled</span></span>                    | <span data-ttu-id="c6898-205">N/A</span><span class="sxs-lookup"><span data-stu-id="c6898-205">N/A</span></span>                                           |
> | <span data-ttu-id="c6898-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="c6898-206">Isabell Potvin</span></span>   | <span data-ttu-id="c6898-207">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="c6898-207">On-premises</span></span>          | <span data-ttu-id="c6898-208">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-208">Yes</span></span>                   | <span data-ttu-id="c6898-209">無効</span><span class="sxs-lookup"><span data-stu-id="c6898-209">Disabled</span></span>                    | <span data-ttu-id="c6898-210">N/A</span><span class="sxs-lookup"><span data-stu-id="c6898-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="c6898-211">チームとボイスメールを使用するには、ユーザーの Exchange メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="c6898-212">詳細については、[どの Exchange と対話するマイクロソフトのチーム](exchange-teams-interact.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="c6898-213">直接ルーティングするためのライセンス</span><span class="sxs-lookup"><span data-stu-id="c6898-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="c6898-214">組織が直接ルーティングを使用しようとすると場合、は、必要なライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="c6898-215">直接ルーティングのユーザーには、次のライセンスの Office 365 に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="c6898-216">マイクロソフトの電話システム</span><span class="sxs-lookup"><span data-stu-id="c6898-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="c6898-217">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6898-217">Microsoft Teams</span></span>

-   <span data-ttu-id="c6898-218">電話会議</span><span class="sxs-lookup"><span data-stu-id="c6898-218">Audio Conferencing</span></span>

<span data-ttu-id="c6898-219">オーディオ会議のライセンスは、それらにダイアル アウトするか、ダイヤルイン番号を提供することでスケジュールされたミーティングの場合は、外部の参加者を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="c6898-220">外部の参加者は、ダイヤルをオーディオ会議サービスはオンラインの呼び出し機能を使用して呼び出しを配置します。</span><span class="sxs-lookup"><span data-stu-id="c6898-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="c6898-221">オーディオ会議のライセンスはオプションであり、人を整理することがチーム電話会議を含む会議のユーザー用にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="c6898-222">無料電話会議ブリッジの電話番号を指定し、会議の国際電話番号にダイアル アウトをサポートするためは、組織の[通信のクレジット](what-are-communications-credits.md)を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="c6898-223">オーディオ会議や電話システムは、Office 365 の E3 または E1 サブスクリプション計画している既存のお客様向けのアドオン サービスとして個別にライセンスことができます。既に Office 365 の E5 のサブスクリプションの計画の一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="c6898-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="c6898-224">また、サード パーティの Pbx に呼び出しをルーティングするときに計画を呼び出すことは有効になっているユーザーの直接ルーティングを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6898-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="c6898-225">詳細については、[使用許諾契約との直接のルーティングには、その他の要件](direct-routing-plan.md#licensing-and-other-requirements)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-226">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-226">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-227">組織には、必要な電話システムのライセンスが割り当てられていない、または電話システムのアドオン サービスを入手することで、既存の Office 365 サブスクリプションをステップ実行して、電話システムのライセンスを習得していただくことがあるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="c6898-228">直接ルーティングを実装するための通信のクレジットする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-229">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-229">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-230">電話システムのライセンスを割り当てる部署、部門、オフィス、またはユーザーのグループを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="c6898-231">フリー ダイヤル番号に電話会議がスコープ内にある場合は、クレジットの通信を有効にします、部門、部門、オフィス、またはユーザー グループを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="c6898-232">Office 365 に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c6898-232">Office 365 considerations</span></span>

<span data-ttu-id="c6898-233">Office 365 に直接ルーティングを有効にするにはすべてのユーザーが所属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="c6898-234">ビジネス サーバーまたは Lync Server のハイブリッド展開での設置型の Skype では、Skype をオンライン ビジネスのチームに直接ルーティングを使用するよう構成する前にユーザーを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="c6898-235">チームに直接ルーティングの実装のスコープ内にあるすべてのユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="c6898-236">Office 365 テナントする必要がありますを有効にする 1 つまたは複数のドメインを持つため、デフォルト\*. onmicrosoft.com ドメインは、直接ルーティングでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c6898-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="c6898-237">ドメインと Office 365 のテナントの詳細については、[ドメインに関する FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-238">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-238">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-239">すべてのユーザーが直接ルーティングをサポートするためにオンライン ビジネスの Skype に移行する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="c6898-240">チームを有効にする必要があるユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="c6898-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-241">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-241">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-242">Skype ビジネスをオンラインに移動し、チームを有効にする必要があるユーザーの一覧を文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="c6898-243">SBC の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c6898-243">SBC considerations</span></span>

<span data-ttu-id="c6898-244">認定およびサポートされているセッション ボーダー コント ローラー (SBCs) は対にして、直接ルーティング サービスをユーザーに PSTN 接続を提供する必要があるを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="c6898-245">認定 SBCs のリストは、[サポートされているセッション ボーダー コント ローラー](direct-routing-plan.md#supported-session-border-controllers-sbcs)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="c6898-246">環境、場所、および音声ルーティングの要件の数に応じて、ユーザー ベースをサポートするために複数の SBCs を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="c6898-247">SBC ドメイン名</span><span class="sxs-lookup"><span data-stu-id="c6898-247">SBC domain names</span></span>

<span data-ttu-id="c6898-248">各 SBC を直接ルーティングをペアにするには、一意の DNS 名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="c6898-249">SBC の DNS 名は、Office 365 テナントに登録されたドメイン名のいずれかをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="c6898-250">テナントに複数のドメイン名が割り当てられている場合ことができますを使用するこれらのドメイン名のいずれか、SBCs の DNS 名を計画するとき。</span><span class="sxs-lookup"><span data-stu-id="c6898-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6898-251">使用 \*. onmicrosoft.com SBC の DNS 名は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="c6898-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="c6898-252">証明書</span><span class="sxs-lookup"><span data-stu-id="c6898-252">Certificates</span></span>

<span data-ttu-id="c6898-253">直接ルーティングを展開する各 SBC には、サポートされている証明機関の一覧から取得した証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="c6898-254">証明書は、件名、件名の代替名、または共通名フィールドに、SBC の DNS 名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="c6898-255">SBCs でワイルドカード証明書の使用もサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6898-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="c6898-256">およびサポートされている証明機関の一覧の詳細については[、SBC の信頼された証明書の公開](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="c6898-257">SBC の IP アドレスとポート</span><span class="sxs-lookup"><span data-stu-id="c6898-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="c6898-258">Office 365 のデータ センターからアクセスできるパブリック IP アドレスを使用して各 SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="c6898-259">ネットワーク アドレス変換 (NAT) が、半角を Office 365 のデータ センターに発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6898-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="c6898-260">SBCs シグナリングとメディアのクラウド サービスとの通信に双方向の接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6898-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="c6898-261">*SIP プロキシ*をという名前のコンポーネントによって処理される、信号およびメディアは、*メディア プロセッサ*によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="c6898-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="c6898-262">SIP シグナリングとメディアの各 SBC の特定のポート番号を定義し、これらのポートと関連付けられた IP アドレスへの双方向のトラフィックを許可するようにファイアウォールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="c6898-263">詳細についてを参照してください[SIP シグナリング: Fqdn およびファイアウォールのポート](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports)および[メディア トラフィック: ポート範囲を](direct-routing-plan.md#media-traffic-port-ranges)。</span><span class="sxs-lookup"><span data-stu-id="c6898-263">For more details, see [SIP Signaling: FQDNs and firewall ports](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="c6898-264">SBC モデルに基づいて、各 SBC の最大同時セッションの制限の設定を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6898-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="c6898-265">容量に近い、SBC の実行中に、その制限と通知のトリガーです。</span><span class="sxs-lookup"><span data-stu-id="c6898-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-266">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-266">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-267">場所 SBCs を配置することを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="c6898-268">展開しようとしている各 SBC の DNS 名を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="c6898-269">SBC ドメイン名の決定に基づき、配置内のすべて SBCs をサポートするためにワイルドカード証明書または SBC あたり専用の証明書を使用することかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="c6898-270">どのパブリック証明機関から、SBCs の証明書を取得しますかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="c6898-271">展開、および、半角英数字にパブリック IP アドレスを割り当てるまたは NAT を使用するかどうかを決定するが、各 SBC のパブリック IP アドレスとポートのペアを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6898-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="c6898-272">各 SBC をサポートする同時セッションの最大数を識別するかを処理できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="c6898-273">SBCs は、メディア バイ パスを使用して構成を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-274">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-274">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-275">各意思決定が行われました、SBCs の次の表を使用して文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="c6898-276">直接ルーティングを展開するための SBC の詳細を文書化するのにには、次のテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6898-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="c6898-277">**SBC の DNS 名 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="c6898-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="c6898-278">**SBC の製造元とモデル**</span><span class="sxs-lookup"><span data-stu-id="c6898-278">**SBC make and model**</span></span> | <span data-ttu-id="c6898-279">**証明書**</span><span class="sxs-lookup"><span data-stu-id="c6898-279">**Certificate**</span></span> | <span data-ttu-id="c6898-280">**場所**</span><span class="sxs-lookup"><span data-stu-id="c6898-280">**Location**</span></span>  | <span data-ttu-id="c6898-281">**IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="c6898-281">**IP address**</span></span> | <span data-ttu-id="c6898-282">**SIP ポートのシグナル**</span><span class="sxs-lookup"><span data-stu-id="c6898-282">**SIP signaling port**</span></span> | <span data-ttu-id="c6898-283">**NAT ですか。**</span><span class="sxs-lookup"><span data-stu-id="c6898-283">**NAT?**</span></span> | <span data-ttu-id="c6898-284">**最大同時セッション数**</span><span class="sxs-lookup"><span data-stu-id="c6898-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="c6898-285">**メディアのバイパスが有効になっているでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="c6898-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="c6898-286">SBC Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="c6898-287">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-287">TBD</span></span> | <span data-ttu-id="c6898-288">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-288">\*.contoso.com</span></span> | <span data-ttu-id="c6898-289">アムステルダム</span><span class="sxs-lookup"><span data-stu-id="c6898-289">Amsterdam</span></span> | <span data-ttu-id="c6898-290">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-290">TBD</span></span> | <span data-ttu-id="c6898-291">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-291">TBD</span></span> | <span data-ttu-id="c6898-292">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-292">Yes</span></span> | <span data-ttu-id="c6898-293">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-293">TBD</span></span> | <span data-ttu-id="c6898-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6898-294">No</span></span> |
> | <span data-ttu-id="c6898-295">SBC Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="c6898-296">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-296">TBD</span></span> | <span data-ttu-id="c6898-297">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-297">\*.contoso.com</span></span> | <span data-ttu-id="c6898-298">香港特別自治区</span><span class="sxs-lookup"><span data-stu-id="c6898-298">Hong Kong SAR</span></span> | <span data-ttu-id="c6898-299">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-299">TBD</span></span> | <span data-ttu-id="c6898-300">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-300">TBD</span></span> | <span data-ttu-id="c6898-301">いいえ</span><span class="sxs-lookup"><span data-stu-id="c6898-301">No</span></span> | <span data-ttu-id="c6898-302">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-302">TBD</span></span> | <span data-ttu-id="c6898-303">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-303">Yes</span></span> |
> | <span data-ttu-id="c6898-304">SBC Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="c6898-305">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-305">TBD</span></span> | <span data-ttu-id="c6898-306">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-306">\*.contoso.com</span></span> | <span data-ttu-id="c6898-307">ヨハネスブルグ</span><span class="sxs-lookup"><span data-stu-id="c6898-307">Johannesburg</span></span> | <span data-ttu-id="c6898-308">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-308">TBD</span></span> | <span data-ttu-id="c6898-309">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-309">TBD</span></span> | <span data-ttu-id="c6898-310">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-310">Yes</span></span> | <span data-ttu-id="c6898-311">TBD</span><span class="sxs-lookup"><span data-stu-id="c6898-311">TBD</span></span> | <span data-ttu-id="c6898-312">はい</span><span class="sxs-lookup"><span data-stu-id="c6898-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="c6898-313">音声ルーティング</span><span class="sxs-lookup"><span data-stu-id="c6898-313">Voice routing</span></span>

<span data-ttu-id="c6898-314">直接ルーティングの特定の半角英数字に呼び出しをルーティングするのにはマイクロソフトの電話システムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="c6898-315">基づくボイス ルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="c6898-316">番号のパターンが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c6898-316">Called number pattern.</span></span>

-   <span data-ttu-id="c6898-317">番号のパターンと呼び出しを行うユーザーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6898-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="c6898-318">通話のルーティングは、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="c6898-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="c6898-319">音声ルーティング ポリシー – PSTN の使用法のためのコンテナーユーザーまたは複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c6898-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="c6898-320">PSTN 使用法: ボイス ルートと PSTN の使用法のためのコンテナー別の音声ルーティング ポリシーで共有することができます。</span><span class="sxs-lookup"><span data-stu-id="c6898-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="c6898-321">ボイス ルート – 番号のパターンと、呼び出し側の番号がパターンと一致する呼び出しに使用するオンラインの PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="c6898-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="c6898-322">オンラインの PSTN ゲートウェイ、SBC、ポインターの呼び出しは、前方の P アサートされた Id (PAI) や優先のコーデックなど、SBC を使用して配置するときに適用されている構成を格納します。ボイス ルートを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c6898-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="c6898-323">直接ルーティングの計画を呼び出すと共存させることは、ボイス ルートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="c6898-324">その構成によって、いくつかの特定の半角英数字に呼び出しを直接ルーティングを使用してルーティングすることを計画を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c6898-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="c6898-325">SBCs は、*アクティブ*と*バックアップ*として指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="c6898-326">番号のパターンが、SBC のアクティブな状態で構成されている場合、つまり、番号のパターンと特定のユーザーまたは -いない利用可能な呼び出しにルーティングされますバックアップ SBC。</span><span class="sxs-lookup"><span data-stu-id="c6898-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-327">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-327">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-328">音声ポリシー、PSTN 使用法、およびボイス ルートを作成するをサポート ユーザーの所在地、または直接ルーティングの実装のスコープ内のオフィスにルーティングを決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-329">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-329">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-330">音声ルーティング ポリシー、PSTN 使用法、および組織のボイス ルートを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="c6898-331">各音声ルーティング ポリシーを定義するために割り当てられるユーザーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="c6898-332">直接ルーティングを展開するための音声ポリシーを文書化するのにには、次のテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6898-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="c6898-333">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="c6898-333">**PSTN usage**</span></span> | <span data-ttu-id="c6898-334">**ボイス ルート**</span><span class="sxs-lookup"><span data-stu-id="c6898-334">**Voice route**</span></span> | <span data-ttu-id="c6898-335">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="c6898-335">**Number pattern**</span></span> | <span data-ttu-id="c6898-336">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="c6898-336">**Priority**</span></span> | <span data-ttu-id="c6898-337">**SBC**</span><span class="sxs-lookup"><span data-stu-id="c6898-337">**SBC**</span></span> | <span data-ttu-id="c6898-338">**説明**</span><span class="sxs-lookup"><span data-stu-id="c6898-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="c6898-339">米国のみ</span><span class="sxs-lookup"><span data-stu-id="c6898-339">US only</span></span> | <span data-ttu-id="c6898-340">「Redmond 1」</span><span class="sxs-lookup"><span data-stu-id="c6898-340">“Redmond 1”</span></span> | <span data-ttu-id="c6898-341">\^\\+1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="c6898-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="c6898-342">1</span><span class="sxs-lookup"><span data-stu-id="c6898-342">1</span></span> | <span data-ttu-id="c6898-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="c6898-344">+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号の有効な工順</span><span class="sxs-lookup"><span data-stu-id="c6898-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="c6898-345">米国のみ</span><span class="sxs-lookup"><span data-stu-id="c6898-345">US only</span></span> | <span data-ttu-id="c6898-346">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="c6898-346">“Redmond 2”</span></span> | <span data-ttu-id="c6898-347">\^\\+1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="c6898-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="c6898-348">2</span><span class="sxs-lookup"><span data-stu-id="c6898-348">2</span></span> | <span data-ttu-id="c6898-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="c6898-350">+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号のバックアップ ルート</span><span class="sxs-lookup"><span data-stu-id="c6898-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="c6898-351">米国のみ</span><span class="sxs-lookup"><span data-stu-id="c6898-351">US only</span></span> | <span data-ttu-id="c6898-352">「その他の +1」</span><span class="sxs-lookup"><span data-stu-id="c6898-352">"Other +1”</span></span> | <span data-ttu-id="c6898-353">\^\\+1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="c6898-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="c6898-354">3</span><span class="sxs-lookup"><span data-stu-id="c6898-354">3</span></span> | <span data-ttu-id="c6898-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="c6898-356">呼ばれる数字の +1 XXX XXX の XX XX (+1 425 XXX XX XX +1 206 XXX XX XX 以外) をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c6898-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="c6898-357">International</span><span class="sxs-lookup"><span data-stu-id="c6898-357">International</span></span> | <span data-ttu-id="c6898-358">International</span><span class="sxs-lookup"><span data-stu-id="c6898-358">International</span></span> | <span data-ttu-id="c6898-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="c6898-359">\\d+</span></span> | <span data-ttu-id="c6898-360">4</span><span class="sxs-lookup"><span data-stu-id="c6898-360">4</span></span> | <span data-ttu-id="c6898-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6898-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="c6898-362">任意の番号のパターンのルート</span><span class="sxs-lookup"><span data-stu-id="c6898-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="c6898-363">音声ルーティング ポリシーの PSTN 使用法を適用、およびその他の方法が評価されることはありません最初の使用で一致が見つかった場合。</span><span class="sxs-lookup"><span data-stu-id="c6898-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="c6898-364">通話との相互運用機能のポリシー</span><span class="sxs-lookup"><span data-stu-id="c6898-364">Calling and Interop policies</span></span>

<span data-ttu-id="c6898-365">直接ルーティングは、マイクロソフトのチームでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c6898-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="c6898-366">開始、または直接ルーティングでは、PSTN の呼び出しを受信、チームでの着信呼び出しが受信されるように必要なポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6898-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c6898-367">開始、または受信できません直接ルーティングを有効にするユーザー、ビジネスの Skype を使用して、ルーティングの呼び出しを送信し、したがってする必要がありますチーム クライアントを展開します。</span><span class="sxs-lookup"><span data-stu-id="c6898-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="c6898-368">次の 2 つの方法のいずれかによって、優先するクライアントの呼び出しとしてチームを設定するのには、ユーザーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c6898-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="c6898-369">チーム専用のモードのユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6898-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="c6898-370">優先呼び出し側のクライアントとして、TeamsCallingPolicy と、TeamsInteropPolicy を割り当てることによってチームを構成します。</span><span class="sxs-lookup"><span data-stu-id="c6898-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="c6898-371">詳細については、[マイクロソフトのチームを優先設定は、ユーザーのクライアントを呼び出す](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="c6898-372">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="c6898-372">Decision points</span></span>|<ul><li><span data-ttu-id="c6898-373">チームに推奨されるクライアントの呼び出しの設定に使用する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c6898-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="c6898-374">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c6898-374">Next steps</span></span>|<ul><li><span data-ttu-id="c6898-375">相互運用機能と通話のポリシーを構成するユーザーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="c6898-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="c6898-376">チーム専用のモードのユーザーを構成する場合は、このユーザーは不要になったビジネスの Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c6898-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="c6898-377">チーム クライアントの [通話] タブを参照してください、ユーザーを表示するには、有効にするプライベート テナントの組織レベルで呼び出すこと。</span><span class="sxs-lookup"><span data-stu-id="c6898-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="c6898-378">秘密の呼び出しを有効にする方法の詳細については、[マイクロソフトのチームの呼び出しを有効にする](direct-routing-configure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6898-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="c6898-379">ドキュメント サービスに関する意思決定</span><span class="sxs-lookup"><span data-stu-id="c6898-379">Document service decisions</span></span>

<span data-ttu-id="c6898-380">この資料の前のセクションからの情報を使用して、決定事項をサービスします。</span><span class="sxs-lookup"><span data-stu-id="c6898-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="c6898-381">一般に、このドキュメントは次の主要なセクションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6898-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="c6898-382">プランの呼び出しサイトの有効化] ボックスの一覧で電話システム</span><span class="sxs-lookup"><span data-stu-id="c6898-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="c6898-383">ボイス メール構成の詳細</span><span class="sxs-lookup"><span data-stu-id="c6898-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="c6898-384">ユーザーの電話システムの直接のルーティング用のライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="c6898-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="c6898-385">SBC の構成の詳細</span><span class="sxs-lookup"><span data-stu-id="c6898-385">SBC configuration details</span></span>

-   <span data-ttu-id="c6898-386">音声ポリシーをルーティングとルーティングの詳細します。</span><span class="sxs-lookup"><span data-stu-id="c6898-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="c6898-387">相互運用機能や呼び出し元のポリシーの詳細</span><span class="sxs-lookup"><span data-stu-id="c6898-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
