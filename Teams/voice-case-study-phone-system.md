---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101033"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="c543b-103">Contoso のケース スタディ: 電話システム</span><span class="sxs-lookup"><span data-stu-id="c543b-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="c543b-104">地理的な場所や他の要因に応じて、Contoso には次のテレフォニー ソリューションを使用するオフィスがあります。</span><span class="sxs-lookup"><span data-stu-id="c543b-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="c543b-105">サイトの種類 A: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="c543b-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="c543b-106">サイトの種類 B: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="c543b-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="c543b-107">サイトの種類 C: Skype for Business エンタープライズ VoIP従来のテレフォニー システムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c543b-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="c543b-108">組織全体に Microsoft Phone System ソリューションを実装するには、Contoso は、公衆交換電話網 &mdash; (PSTN) に接続するために電話システムで使用される次のオプションの中から、サイトの種類ごとに決定する必要がありました &mdash; 。</span><span class="sxs-lookup"><span data-stu-id="c543b-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="c543b-109">通話プラン付き電話システム</span><span class="sxs-lookup"><span data-stu-id="c543b-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="c543b-110">ダイレクト ルーティングを通じて独自の PSTN キャリアを使用する電話システム</span><span class="sxs-lookup"><span data-stu-id="c543b-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="c543b-111">通話プランを使用した電話システムと、ダイレクト ルーティングによる独自の PSTN 通信事業者との電話システムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c543b-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="c543b-112">Contoso は、組織に適切なソリューションを決定するために [、Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) テレフォニー ソリューションと、Microsoft Teams での Ignite 2019 セッションの呼び出 [しを使用しました](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="c543b-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="c543b-113">サイトの種類 A: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="c543b-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="c543b-114">Contoso Skype for Business エンタープライズ VoIPハブと音声として設定されています。</span><span class="sxs-lookup"><span data-stu-id="c543b-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="c543b-115">国の Skype for Business ユーザーに PSTN への接続を提供する地域で PSTN ゲートウェイを維持エンタープライズ VoIP場所がありました。</span><span class="sxs-lookup"><span data-stu-id="c543b-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="c543b-116">多くの場合、これらの衛星オフィスには独自のインターネット出口はなかった。</span><span class="sxs-lookup"><span data-stu-id="c543b-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="c543b-117">これらのユーザーの番号は、既存の SBC に接続する SIP トランクに存在しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="c543b-118">既に展開されている SBC がダイレクト ルーティングとメディア バイパスの認定を受けたかどうかを確認するために、Contoso は直接ルーティングの認定を受けたセッション ボーダー コントローラーのリスト [を確認しました](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="c543b-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="c543b-119">ユーザーのダイヤルの習慣は、ユーザーがピアツーピア音声で利用できる Skype for Business クライアントを使用している場合でも、拡張機能を使用して従来のテレフォニー システムでユーザーをダイヤルする方法でした。</span><span class="sxs-lookup"><span data-stu-id="c543b-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="c543b-120">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="c543b-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c543b-121">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-121">Q.</span></span> <span data-ttu-id="c543b-122">オンプレミス展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c543b-123">A.</span><span class="sxs-lookup"><span data-stu-id="c543b-123">A.</span></span> <span data-ttu-id="c543b-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="c543b-124">No</span></span> 

- <span data-ttu-id="c543b-125">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-125">Q.</span></span> <span data-ttu-id="c543b-126">サードパーティ PBX システムや他のテレフォニー機器と相互運用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="c543b-127">A.</span><span class="sxs-lookup"><span data-stu-id="c543b-127">A.</span></span> <span data-ttu-id="c543b-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="c543b-128">No</span></span> 

- <span data-ttu-id="c543b-129">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-129">Q.</span></span> <span data-ttu-id="c543b-130">現在のサードパーティの通信事業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c543b-131">A.○ (規制対象国) および No</span><span class="sxs-lookup"><span data-stu-id="c543b-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="c543b-132">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-132">Q.</span></span> <span data-ttu-id="c543b-133">SPC の ROI を展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="c543b-134">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="c543b-134">A. Yes and No</span></span>  

- <span data-ttu-id="c543b-135">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-135">Q.</span></span> <span data-ttu-id="c543b-136">Microsoft PSTN 通話プランは、この地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="c543b-137">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="c543b-137">A. Yes and No</span></span> 

<span data-ttu-id="c543b-138">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="c543b-139">PSTN 通話プランが通話プランを含む電話システムで利用できる地域にあるユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="c543b-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="c543b-140">PSTN 通話プランが利用可能な地域に存在しないユーザー、SBC の ROI がまだ満たされていないサイトに存在するユーザー、および直接ルーティングを使用する電話システムに対するテレフォニー規制がある国に住んでいるユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="c543b-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="c543b-141">次の図は、初期の Skype for Business エンタープライズ VoIP展開と、この展開が Microsoft 通話プランと直接ルーティングの両方に移行された方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c543b-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![前と後の状態を示す図](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="c543b-143">サイトの種類 B: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="c543b-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="c543b-144">Contoso には、従来のテレフォニー システムを利用する多くのオフィスがありました。</span><span class="sxs-lookup"><span data-stu-id="c543b-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="c543b-145">E1.64 電話番号を持つユーザーのサブセットと、内線番号のみを持つユーザーがいました。</span><span class="sxs-lookup"><span data-stu-id="c543b-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="c543b-146">これらの番号は、PSTN ゲートウェイへの TDM トランクに存在します。</span><span class="sxs-lookup"><span data-stu-id="c543b-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="c543b-147">サイト内ダイヤルは、通話をルーティングする場所を決定するために、拡張機能の前にあるサイト コードを利用して構成されました。</span><span class="sxs-lookup"><span data-stu-id="c543b-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="c543b-148">ユーザーのダイヤルの習慣は、内線番号でダイヤルすることでした。</span><span class="sxs-lookup"><span data-stu-id="c543b-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="c543b-149">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="c543b-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c543b-150">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-150">Q.</span></span> <span data-ttu-id="c543b-151">オンプレミス展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c543b-152">A.</span><span class="sxs-lookup"><span data-stu-id="c543b-152">A.</span></span> <span data-ttu-id="c543b-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="c543b-153">No</span></span> 

- <span data-ttu-id="c543b-154">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-154">Q.</span></span> <span data-ttu-id="c543b-155">サードパーティ PBX システムや他のテレフォニー機器と相互運用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="c543b-156">A.うん</span><span class="sxs-lookup"><span data-stu-id="c543b-156">A. Yes</span></span>

- <span data-ttu-id="c543b-157">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-157">Q.</span></span> <span data-ttu-id="c543b-158">現在のサードパーティの通信事業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c543b-159">A.違います</span><span class="sxs-lookup"><span data-stu-id="c543b-159">A. No</span></span> 

- <span data-ttu-id="c543b-160">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-160">Q.</span></span> <span data-ttu-id="c543b-161">Microsoft PSTN の通話プランは地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="c543b-162">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="c543b-162">A. Yes and No</span></span> 

<span data-ttu-id="c543b-163">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="c543b-164">PSTN 通話プランが通話プランを含む電話システムで利用できる地域にあるユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="c543b-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="c543b-165">PSTN 通話プランが直接ルーティングされた電話システムで利用できる地域にはないユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="c543b-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="c543b-166">業務上重要なアナログ デバイスへの PSTN 接続を維持します。</span><span class="sxs-lookup"><span data-stu-id="c543b-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="c543b-167">次の図は、リモート サイトを使用した元の従来のシステム展開と、ローカル メディア最適化を使用したダイレクト ルーティング展開への移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="c543b-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="c543b-168">**従来の展開**  
 ![前と後の状態を示す図](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="c543b-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="c543b-169">**直接ルーティングを使用した展開**</span><span class="sxs-lookup"><span data-stu-id="c543b-169">**Deployment with Direct Routing**</span></span>

![前と後の状態を示す図](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="c543b-171">サイトの種類 C: Skype for Business エンタープライズ VoIP従来のテレフォニー システムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c543b-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="c543b-172">Contoso Skype for Business エンタープライズ VoIPの電話番号は、通信事業者から SBC への SIP トランク上に存在します。</span><span class="sxs-lookup"><span data-stu-id="c543b-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="c543b-173">PSTN ゲートウェイへの TDM トランクに存在する従来のテレフォニー システムの番号。</span><span class="sxs-lookup"><span data-stu-id="c543b-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="c543b-174">Contoso は、次の質問に基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="c543b-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="c543b-175">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-175">Q.</span></span> <span data-ttu-id="c543b-176">オンプレミス展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="c543b-177">A.</span><span class="sxs-lookup"><span data-stu-id="c543b-177">A.</span></span> <span data-ttu-id="c543b-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="c543b-178">No</span></span> 

- <span data-ttu-id="c543b-179">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-179">Q.</span></span> <span data-ttu-id="c543b-180">サードパーティ PBX システムや他のテレフォニー機器と相互運用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="c543b-181">A.違います</span><span class="sxs-lookup"><span data-stu-id="c543b-181">A. No</span></span> 

- <span data-ttu-id="c543b-182">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-182">Q.</span></span> <span data-ttu-id="c543b-183">現在のサードパーティの通信事業者を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="c543b-184">A.違います</span><span class="sxs-lookup"><span data-stu-id="c543b-184">A. No</span></span> 

- <span data-ttu-id="c543b-185">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-185">Q.</span></span> <span data-ttu-id="c543b-186">SPC の ROI を展開する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="c543b-187">A.さあ何とも言えません</span><span class="sxs-lookup"><span data-stu-id="c543b-187">A. Yes and No</span></span>  

- <span data-ttu-id="c543b-188">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-188">Q.</span></span> <span data-ttu-id="c543b-189">Microsoft の PSTN 通話プランは、この地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="c543b-190">A.違います</span><span class="sxs-lookup"><span data-stu-id="c543b-190">A. No</span></span> 

<span data-ttu-id="c543b-191">Contoso は、質問に対する回答に基づいて、次の点を決定しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="c543b-192">ダイレクト ルーティングが有効になる従来のテレフォニー ユーザーの場合、Contoso は、SBC がダイレクト ルーティングの認定を受けたので、TDM トランクから SBC の SIP トランクに番号を移植しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="c543b-193">電話システムに移行するユーザーのサブセットをサポートし、従来のシステムを介した継続ルーティングを許可するために、従来のテレフォニー システムは SBC への次のホップとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="c543b-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="c543b-194">さらに、ユーザーの動作の変更を促し、サイト間およびサイト内内の内線ダイヤルへの依存を取り除く方法について、Contoso は、すべての内部呼び出しに Teams を使用するガイダンスを提供しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="c543b-195">次の図は、元の Skype for Business エンタープライズ VoIPおよび従来のテレフォニー システムの展開と、ダイレクト ルーティングを使用した複合展開への移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="c543b-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="c543b-196">**元の複合配置** 
 ![状態の前を示す図](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="c543b-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="c543b-197">**ダイレクト ルーティングを使用した複合展開** 
 ![状態の前を示す図](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="c543b-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="c543b-198">通話プラン</span><span class="sxs-lookup"><span data-stu-id="c543b-198">Calling Plans</span></span>

<span data-ttu-id="c543b-199">通話プランの構成要件を決定するために、Contoso は通話プランの主要な展開決定 [を確認しました](calling-plan-landing-page.md#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="c543b-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="c543b-200">その結果、次のような決定が行われた。</span><span class="sxs-lookup"><span data-stu-id="c543b-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="c543b-201">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-201">Q.</span></span> <span data-ttu-id="c543b-202">ユーザーは国際電話を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-202">Do my users need international calling?</span></span><br> <span data-ttu-id="c543b-203">A.うん</span><span class="sxs-lookup"><span data-stu-id="c543b-203">A. Yes</span></span> 

- <span data-ttu-id="c543b-204">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-204">Q.</span></span> <span data-ttu-id="c543b-205">ユーザーそれぞれに内向き DID 電話番号はありますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="c543b-206">A. 今日ではありません。</span><span class="sxs-lookup"><span data-stu-id="c543b-206">A. Not today.</span></span> <span data-ttu-id="c543b-207">有効になっているすべてのユーザーは DID を受け取る。</span><span class="sxs-lookup"><span data-stu-id="c543b-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="c543b-208">Q.</span><span class="sxs-lookup"><span data-stu-id="c543b-208">Q.</span></span> <span data-ttu-id="c543b-209">発信者 ID のマスクや無効化を行いますか?</span><span class="sxs-lookup"><span data-stu-id="c543b-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="c543b-210">A.ユーザーの発信者番号は Contoso のローカル番号にマスクされます。</span><span class="sxs-lookup"><span data-stu-id="c543b-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="c543b-211">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="c543b-211">Direct Routing</span></span>

<span data-ttu-id="c543b-212">Contoso は Ignite に参加し、電話システムと直接ルーティングでOffice 365 の機能を最新の状態に更新しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="c543b-213">技術的な指導者と設計者は、Ignite 2019 で提供されたガイダンスを使用して方向を決定しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="c543b-214">使用されたキー セッション:</span><span class="sxs-lookup"><span data-stu-id="c543b-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="c543b-215">Microsoft Teams ダイレクト ルーティングを使用して成功を計画する</span><span class="sxs-lookup"><span data-stu-id="c543b-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="c543b-216">ダイレクト ルーティングの更新</span><span class="sxs-lookup"><span data-stu-id="c543b-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="c543b-217">構成</span><span class="sxs-lookup"><span data-stu-id="c543b-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="c543b-218">通話プラン サイト</span><span class="sxs-lookup"><span data-stu-id="c543b-218">Calling Plans sites</span></span>

<span data-ttu-id="c543b-219">ライセンスを取得し、ユーザーに電話番号を割り当てるには、Contoso は「通話プランをセットアップする [」の手順に従いました](set-up-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="c543b-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="c543b-220">電話番号を割り当てる必要があるユーザーの数のため、Contoso は PowerShell を使用して電話番号を割り当てしました。</span><span class="sxs-lookup"><span data-stu-id="c543b-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="c543b-221">他の設定に加えて PowerShell を使用して数値を割り当てる方法については、Contoso が &mdash; &mdash; Teams PowerShell の [概要を使用しました](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c543b-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="c543b-222">ダイレクト ルーティング サイト</span><span class="sxs-lookup"><span data-stu-id="c543b-222">Direct Routing sites</span></span>

<span data-ttu-id="c543b-223">Contoso のオンプレミス テレフォニー インフラストラクチャを Microsoft Teams に接続するために、Contoso の管理者[](direct-routing-configure.md)は「ダイレクト ルーティングを構成する」の手順に従い、ガイダンスを得るビデオの[Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)のダイレクト ルーティングを確認しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="c543b-224">Contoso は、認定された SBC ベンダーによるダイレクト ルーティング展開のドキュメントにも言及しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="c543b-225">SBC と Microsoft Phone System の間で直接ルーティングが構成された後、Contoso が構成をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c543b-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="c543b-226">これを行うには、Contoso 管理者は [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)の直接ルーティング セッションの更新プログラムで説明した SIP テスター クライアントを使用しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="c543b-227">SIP Tester クライアント のスクリプトとドキュメントは、PowerShell スクリプトからダウンロードされ、直接ルーティング セッション ボーダー コントローラー接続をテストしました。</span><span class="sxs-lookup"><span data-stu-id="c543b-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="c543b-228">ローカル メディアの最適化</span><span class="sxs-lookup"><span data-stu-id="c543b-228">Local Media Optimization</span></span>

<span data-ttu-id="c543b-229">Contoso は、世界中の異なる地域でローカル メディア最適化を活用する機会を見ていました。</span><span class="sxs-lookup"><span data-stu-id="c543b-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="c543b-230">Contoso でサポートされるシナリオについては、「直接ルーティング用 [のローカル メディアの最適化」を参照してください](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="c543b-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="c543b-231">ローカル メディアの最適化の構成は、SBC ベンダーと Microsoft の両方のガイダンスに従って完了しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="c543b-232">ローカル メディアの最適化の構成手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c543b-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="c543b-233">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="c543b-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="c543b-234">SBC ベンダーの仕様に従って SBC を構成します。</span><span class="sxs-lookup"><span data-stu-id="c543b-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="c543b-235">ローカル メディアの最適化に使用する各サイトに外部の信頼済み IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="c543b-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="c543b-236">ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="c543b-236">Define the network topology</span></span> 

- <span data-ttu-id="c543b-237">仮想ネットワーク トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="c543b-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="c543b-238">モードを決定する: ローカル ユーザーの場合は常にバイパスまたはのみ</span><span class="sxs-lookup"><span data-stu-id="c543b-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="c543b-239">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c543b-239">Networking considerations</span></span>

<span data-ttu-id="c543b-240">Contoso には、電話システムを有効にした後、リモートで作業する必要があるユーザーが多数いました。</span><span class="sxs-lookup"><span data-stu-id="c543b-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="c543b-241">ユーザーは VPN を使用して特定の Line of Business アプリケーションにアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="c543b-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="c543b-242">VPN を使用している間、電話システムユーザーは通話品質の低下を経験しました。</span><span class="sxs-lookup"><span data-stu-id="c543b-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="c543b-243">品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。この方法では、内部アプリへの接続が VPN 上に残っている間、Office 365 トラフィックがインターネットをトラバースする許可を与えました。</span><span class="sxs-lookup"><span data-stu-id="c543b-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="c543b-244">VPN 分割トンネリングを実装するために、Contoso は [365](/office365/enterprise/office-365-vpn-implement-split-tunnel)用の VPN 分割トンネリングを実装するOffice従いました。</span><span class="sxs-lookup"><span data-stu-id="c543b-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

