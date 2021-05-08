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
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101033"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="389b4-103">Contoso のケース スタディ: 電話システム</span><span class="sxs-lookup"><span data-stu-id="389b4-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="389b4-104">地理的な場所や他の要因に応じて、Contoso は次のテレフォニー ソリューションを使用してオフィスを持っています。</span><span class="sxs-lookup"><span data-stu-id="389b4-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="389b4-105">サイトの種類 A: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="389b4-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="389b4-106">サイトの種類 B: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="389b4-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="389b4-107">サイトの種類 C: 従来のレガシ Skype for Business エンタープライズ VoIPシステムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="389b4-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="389b4-108">組織全体に Microsoft 電話 System ソリューションを実装するには、Contoso は、電話システム で使用されるサイトの種類ごとに、公衆交換電話網 &mdash; (PSTN) に接続するオプションを決定する &mdash; 必要がありました。</span><span class="sxs-lookup"><span data-stu-id="389b4-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="389b4-109">電話システムプランの使用</span><span class="sxs-lookup"><span data-stu-id="389b4-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="389b4-110">電話システム直接ルーティングを使用して PSTN 通信業者と通信する</span><span class="sxs-lookup"><span data-stu-id="389b4-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="389b4-111">通話プラン電話システム直接ルーティングを使用電話システム PSTN 通信事業者との組み合わせ</span><span class="sxs-lookup"><span data-stu-id="389b4-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="389b4-112">Contoso は、組織に適切なソリューションを決定するために[、Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)テレフォニー ソリューションと Ignite 2019 セッション[Calling in Microsoft Teams。](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="389b4-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="389b4-113">サイトの種類 A: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="389b4-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="389b4-114">Contoso Skype for Business エンタープライズ VoIPハブとスポークとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="389b4-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="389b4-115">PSTN ゲートウェイを維持する中央の場所は、PSTN への接続を国のユーザーに提供Skype for Business エンタープライズ VoIP場所でした。</span><span class="sxs-lookup"><span data-stu-id="389b4-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="389b4-116">多くの場合、これらの衛星オフィスには独自のインターネットエグレスがなかった。</span><span class="sxs-lookup"><span data-stu-id="389b4-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="389b4-117">これらのユーザーの番号は、既存の SBC に接続する SIP トランクに存在しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="389b4-118">既にデプロイされている SBC がダイレクト ルーティングとメディア バイパスの認定を受けたかどうかを確認するために、Contoso は直接ルーティングの認定を受けたセッション ボーダー コントローラーの一覧を [確認しました](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="389b4-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="389b4-119">ユーザーのダイヤル習慣は、ユーザーがピアツーピア オーディオで使用可能な Skype for Business クライアントを持っている場合でも、拡張機能を使用してレガシ テレフォニー システムでユーザーをダイヤルする方法でした。</span><span class="sxs-lookup"><span data-stu-id="389b4-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="389b4-120">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="389b4-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="389b4-121">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-121">Q.</span></span> <span data-ttu-id="389b4-122">オンプレミスデプロイによって提供される機能を保持する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="389b4-123">A.</span><span class="sxs-lookup"><span data-stu-id="389b4-123">A.</span></span> <span data-ttu-id="389b4-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="389b4-124">No</span></span> 

- <span data-ttu-id="389b4-125">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-125">Q.</span></span> <span data-ttu-id="389b4-126">サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="389b4-127">A.</span><span class="sxs-lookup"><span data-stu-id="389b4-127">A.</span></span> <span data-ttu-id="389b4-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="389b4-128">No</span></span> 

- <span data-ttu-id="389b4-129">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-129">Q.</span></span> <span data-ttu-id="389b4-130">現在のサードパーティの運送業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="389b4-131">A.はい (規制対象の国)、いいえ</span><span class="sxs-lookup"><span data-stu-id="389b4-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="389b4-132">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-132">Q.</span></span> <span data-ttu-id="389b4-133">SBC の ROI をデプロイする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="389b4-134">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="389b4-134">A. Yes and No</span></span>  

- <span data-ttu-id="389b4-135">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-135">Q.</span></span> <span data-ttu-id="389b4-136">Microsoft PSTN 通話プランは、このリージョンで利用できますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="389b4-137">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="389b4-137">A. Yes and No</span></span> 

<span data-ttu-id="389b4-138">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="389b4-139">PSTN 通話プランを利用できる地域にあるユーザーを、通話プランで電話システム移動します。</span><span class="sxs-lookup"><span data-stu-id="389b4-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="389b4-140">PSTN 通話プランを利用できる地域に存在しないユーザー、SBC の ROI がまだ満たされていないサイトに位置するユーザー、および直接ルーティングを使用して 電話システム に対するテレフォニー規制がある国に居住しているユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="389b4-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="389b4-141">次の図は、デプロイの初期Skype for Business エンタープライズ VoIPと、この展開が Microsoft 通話プランと直接ルーティングの両方に移行された方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="389b4-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![状態の前と後を示す図](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="389b4-143">サイトの種類 B: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="389b4-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="389b4-144">Contoso には、レガシ テレフォニー システムを利用するオフィスが多数いました。</span><span class="sxs-lookup"><span data-stu-id="389b4-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="389b4-145">E1.64 電話番号を持つユーザーと、内線番号のみを持つユーザーのサブセットがあります。</span><span class="sxs-lookup"><span data-stu-id="389b4-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="389b4-146">これらの番号は、PSTN ゲートウェイへの TDM トランク上に存在します。</span><span class="sxs-lookup"><span data-stu-id="389b4-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="389b4-147">サイト内ダイヤルは、拡張機能の前にあるサイト コードを利用して、通話をルーティングする場所を決定することで構成されました。</span><span class="sxs-lookup"><span data-stu-id="389b4-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="389b4-148">ユーザーのダイヤルの習慣は、内線番号でダイヤルすることでした。</span><span class="sxs-lookup"><span data-stu-id="389b4-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="389b4-149">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="389b4-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="389b4-150">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-150">Q.</span></span> <span data-ttu-id="389b4-151">オンプレミスデプロイによって提供される機能を保持する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="389b4-152">A.</span><span class="sxs-lookup"><span data-stu-id="389b4-152">A.</span></span> <span data-ttu-id="389b4-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="389b4-153">No</span></span> 

- <span data-ttu-id="389b4-154">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-154">Q.</span></span> <span data-ttu-id="389b4-155">サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="389b4-156">A.うん</span><span class="sxs-lookup"><span data-stu-id="389b4-156">A. Yes</span></span>

- <span data-ttu-id="389b4-157">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-157">Q.</span></span> <span data-ttu-id="389b4-158">現在のサードパーティの運送業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="389b4-159">A.違います</span><span class="sxs-lookup"><span data-stu-id="389b4-159">A. No</span></span> 

- <span data-ttu-id="389b4-160">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-160">Q.</span></span> <span data-ttu-id="389b4-161">Microsoft PSTN の通話プランは地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="389b4-162">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="389b4-162">A. Yes and No</span></span> 

<span data-ttu-id="389b4-163">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="389b4-164">PSTN 通話プランを利用できる地域にあるユーザーを、通話プランで電話システム移動します。</span><span class="sxs-lookup"><span data-stu-id="389b4-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="389b4-165">PSTN 通話プランを直接ルーティングで使用できるリージョンに電話システム移動します。</span><span class="sxs-lookup"><span data-stu-id="389b4-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="389b4-166">業務上重要なアナログ デバイスへの PSTN 接続を維持します。</span><span class="sxs-lookup"><span data-stu-id="389b4-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="389b4-167">次の図は、リモート サイトを使用した元のレガシ システムのデプロイと、ローカル メディアの最適化を使用したダイレクト ルーティング デプロイへの移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="389b4-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="389b4-168">**元のレガシ デプロイ**  
 ![状態の前と後を示す図](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="389b4-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="389b4-169">**直接ルーティングを使用したデプロイ**</span><span class="sxs-lookup"><span data-stu-id="389b4-169">**Deployment with Direct Routing**</span></span>

![状態の前と後を示す図](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="389b4-171">サイトの種類 C: 従来のレガシ Skype for Business エンタープライズ VoIPシステムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="389b4-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="389b4-172">Contoso Skype for Business エンタープライズ VoIPの番号は、SIP トランク上に存在し、運送業者から SBC に送信されます。</span><span class="sxs-lookup"><span data-stu-id="389b4-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="389b4-173">従来のテレフォニー システムの番号は、PSTN ゲートウェイへの TDM トランクに存在します。</span><span class="sxs-lookup"><span data-stu-id="389b4-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="389b4-174">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="389b4-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="389b4-175">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-175">Q.</span></span> <span data-ttu-id="389b4-176">オンプレミスデプロイによって提供される機能を保持する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="389b4-177">A.</span><span class="sxs-lookup"><span data-stu-id="389b4-177">A.</span></span> <span data-ttu-id="389b4-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="389b4-178">No</span></span> 

- <span data-ttu-id="389b4-179">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-179">Q.</span></span> <span data-ttu-id="389b4-180">サードパーティの PBX システムや他のテレフォニー機器と相互運用する必要はありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="389b4-181">A.違います</span><span class="sxs-lookup"><span data-stu-id="389b4-181">A. No</span></span> 

- <span data-ttu-id="389b4-182">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-182">Q.</span></span> <span data-ttu-id="389b4-183">現在のサードパーティの運送業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="389b4-184">A.違います</span><span class="sxs-lookup"><span data-stu-id="389b4-184">A. No</span></span> 

- <span data-ttu-id="389b4-185">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-185">Q.</span></span> <span data-ttu-id="389b4-186">SBC の ROI をデプロイする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="389b4-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="389b4-187">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="389b4-187">A. Yes and No</span></span>  

- <span data-ttu-id="389b4-188">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-188">Q.</span></span> <span data-ttu-id="389b4-189">Microsoft の PSTN 通話プランは、この地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="389b4-190">A.違います</span><span class="sxs-lookup"><span data-stu-id="389b4-190">A. No</span></span> 

<span data-ttu-id="389b4-191">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="389b4-192">ダイレクト ルーティングが有効になるレガシ テレフォニー ユーザーの場合、Contoso は、SBC がダイレクト ルーティングの認定を受けたので、TDM トランクから SBC の SIP トランクに番号を移植しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="389b4-193">電話システム に移行するユーザーのサブセットをサポートし、レガシ システムを介したルーティングを継続するために、レガシ テレフォニー システムが SBC の次ホップとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="389b4-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="389b4-194">さらに、ユーザーの行動の変更を促し、サイト間およびサイト内の内線番号のダイヤルに対する依存関係を削除するために、Contoso は、すべての内部呼び出しに Teams を使用するガイダンスを提供しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="389b4-195">次の図は、元のSkype for Business エンタープライズ VoIPレガシ テレフォニー システムのデプロイと、ダイレクト ルーティングを使用した混合デプロイへの移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="389b4-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="389b4-196">**元の混合デプロイ** 
 ![状態の前を示す図](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="389b4-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="389b4-197">**ダイレクト ルーティングを使用した混合デプロイ** 
 ![状態の前を示す図](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="389b4-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="389b4-198">通話プラン</span><span class="sxs-lookup"><span data-stu-id="389b4-198">Calling Plans</span></span>

<span data-ttu-id="389b4-199">通話プランの構成要件を決定するために、Contoso は通話プランのコア デプロイの決定 [を確認しました](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="389b4-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="389b4-200">その結果、次のような決定が行われた。</span><span class="sxs-lookup"><span data-stu-id="389b4-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="389b4-201">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-201">Q.</span></span> <span data-ttu-id="389b4-202">ユーザーは国際電話を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-202">Do my users need international calling?</span></span><br> <span data-ttu-id="389b4-203">A.うん</span><span class="sxs-lookup"><span data-stu-id="389b4-203">A. Yes</span></span> 

- <span data-ttu-id="389b4-204">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-204">Q.</span></span> <span data-ttu-id="389b4-205">ユーザーは、それぞれ直接内向き DID 電話番号を持っていますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="389b4-206">A. 今日ではありません。</span><span class="sxs-lookup"><span data-stu-id="389b4-206">A. Not today.</span></span> <span data-ttu-id="389b4-207">有効になっているすべてのユーザーは DID を受け取る。</span><span class="sxs-lookup"><span data-stu-id="389b4-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="389b4-208">Q.</span><span class="sxs-lookup"><span data-stu-id="389b4-208">Q.</span></span> <span data-ttu-id="389b4-209">発信者 ID のマスクや無効化を行いますか?</span><span class="sxs-lookup"><span data-stu-id="389b4-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="389b4-210">A.ユーザーの呼び出し元 ID は、Contoso のローカル番号にマスクされます。</span><span class="sxs-lookup"><span data-stu-id="389b4-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="389b4-211">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="389b4-211">Direct Routing</span></span>

<span data-ttu-id="389b4-212">Contoso は Ignite に出席し、Office 365システムと直接ルーティングで利用できる機能電話最新の状態を取り入れる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="389b4-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="389b4-213">技術的なリーダーシップとアーキテクトは、Ignite 2019 の間に提供されたガイダンスを使用して、方向を決定しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="389b4-214">使用された主なセッション:</span><span class="sxs-lookup"><span data-stu-id="389b4-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="389b4-215">直接ルーティングを使用して成功Microsoft Teams計画する</span><span class="sxs-lookup"><span data-stu-id="389b4-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="389b4-216">ダイレクト ルーティングの更新</span><span class="sxs-lookup"><span data-stu-id="389b4-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="389b4-217">構成</span><span class="sxs-lookup"><span data-stu-id="389b4-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="389b4-218">通話プラン サイト</span><span class="sxs-lookup"><span data-stu-id="389b4-218">Calling Plans sites</span></span>

<span data-ttu-id="389b4-219">ライセンスを取得し、ユーザーに電話番号を割り当てるには、「通話プランを設定する [」の手順に従いました](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="389b4-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="389b4-220">電話番号を割り当てる必要があるユーザーの数のために、Contoso は PowerShell を使用して電話番号を割り当てすることを決定しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="389b4-221">他の設定に加えて PowerShell を使用して数値を割り当てる方法については &mdash; &mdash; [、「PowerShell の概要」Teams使用しました](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="389b4-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="389b4-222">直接ルーティング サイト</span><span class="sxs-lookup"><span data-stu-id="389b4-222">Direct Routing sites</span></span>

<span data-ttu-id="389b4-223">Contoso のオンプレミスのテレフォニー インフラストラクチャを Microsoft Teams に接続するために、Contoso の管理者はダイレクト ルーティング[](direct-routing-configure.md)の構成に関するページの手順に従い、Microsoft Teams のビデオダイレクト[ルーティング](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)に関するガイダンスを確認しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="389b4-224">Contoso は、認定された SBC ベンダーによる直接ルーティングの展開に関するドキュメントにも言及しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="389b4-225">SBC と Microsoft 電話 System の間で直接ルーティングが構成された後は、Contoso が構成をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b4-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="389b4-226">これを行うには、Contoso の管理者は [、Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)のダイレクト ルーティングの更新セッションで説明した SIP Tester クライアントを使用しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="389b4-227">SIP Tester クライアント スクリプトとドキュメントは、直接ルーティング セッション ボーダー コントローラー接続をテストするために PowerShell スクリプトからダウンロードされています。</span><span class="sxs-lookup"><span data-stu-id="389b4-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="389b4-228">ローカル メディアの最適化</span><span class="sxs-lookup"><span data-stu-id="389b4-228">Local Media Optimization</span></span>

<span data-ttu-id="389b4-229">Contoso は、世界中の異なるリージョンでローカル メディアの最適化を利用する機会を見ていました。</span><span class="sxs-lookup"><span data-stu-id="389b4-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="389b4-230">Contoso でサポートされるシナリオについては、「直接ルーティングのための [ローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="389b4-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="389b4-231">ローカル メディアの最適化の構成は、SBC ベンダーと Microsoft の両方からのガイダンスに従って完了しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="389b4-232">ローカル メディアの最適化の構成手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="389b4-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="389b4-233">ユーザーサイトと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="389b4-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="389b4-234">SBC ベンダーの仕様に従って SBC を構成します。</span><span class="sxs-lookup"><span data-stu-id="389b4-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="389b4-235">ローカル メディアの最適化に使用される各サイトに外部信頼済み IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="389b4-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="389b4-236">ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="389b4-236">Define the network topology</span></span> 

- <span data-ttu-id="389b4-237">仮想ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="389b4-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="389b4-238">モードを決定する: ローカル ユーザーの場合は常にバイパスまたはのみ</span><span class="sxs-lookup"><span data-stu-id="389b4-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="389b4-239">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="389b4-239">Networking considerations</span></span>

<span data-ttu-id="389b4-240">Contoso には多数のユーザーがいましたが、ユーザーがリモートで作業を行う必要があったのは、そのユーザーがユーザーの作業を有効にした後、電話システム。</span><span class="sxs-lookup"><span data-stu-id="389b4-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="389b4-241">ユーザーは VPN を使用して特定の Line of Business アプリケーションにアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="389b4-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="389b4-242">VPN を使用している間、電話システムユーザーは通話品質の低下を経験しました。</span><span class="sxs-lookup"><span data-stu-id="389b4-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="389b4-243">品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。この方法では、内部アプリへの接続が VPN 上に残っている間、Office 365 トラフィックがインターネットを通過する許可を与えました。</span><span class="sxs-lookup"><span data-stu-id="389b4-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="389b4-244">VPN 分割トンネリングを実装するために、Contoso は「VPN 分割トンネリングを実装する」のガイダンス[に従](/office365/enterprise/office-365-vpn-implement-split-tunnel)Office 365。</span><span class="sxs-lookup"><span data-stu-id="389b4-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

