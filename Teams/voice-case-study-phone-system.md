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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786100"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="003e6-103">Contoso のケーススタディ: 電話システム</span><span class="sxs-lookup"><span data-stu-id="003e6-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="003e6-104">地理的な位置情報やその他の要因によっては、Contoso には以下のテレフォニーソリューションが使用されていました。</span><span class="sxs-lookup"><span data-stu-id="003e6-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="003e6-105">サイトの種類 A: Skype for Business のエンタープライズボイス</span><span class="sxs-lookup"><span data-stu-id="003e6-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="003e6-106">サイトの種類 B: 従来の従来のテレフォニーシステム</span><span class="sxs-lookup"><span data-stu-id="003e6-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="003e6-107">サイトの種類 C: Skype for Business のエンタープライズボイスと従来の従来のテレフォニーシステムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="003e6-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="003e6-108">組織全体に対して Microsoft 電話システムソリューションを実装するために、Contoso は各サイトの種類を決定する必要がありました &mdash; &mdash; 。電話システムで公衆交換電話網 (PSTN) に接続するために使用されるオプションは、次のうちのどれですか。</span><span class="sxs-lookup"><span data-stu-id="003e6-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="003e6-109">通話プラン付きの電話システム</span><span class="sxs-lookup"><span data-stu-id="003e6-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="003e6-110">直接ルーティングを通じて独自の PSTN キャリアを搭載した電話システム</span><span class="sxs-lookup"><span data-stu-id="003e6-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="003e6-111">電話システムと通話プランと電話システムの組み合わせ (独自の PSTN キャリアと直接ルーティング経由)</span><span class="sxs-lookup"><span data-stu-id="003e6-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="003e6-112">組織に最適なソリューションを決定するために、Contoso は microsoft の[office](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)で使用されている Ignite 2019 セッション[通話](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)を使用しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="003e6-113">サイトの種類 A: Skype for Business のエンタープライズボイス</span><span class="sxs-lookup"><span data-stu-id="003e6-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="003e6-114">Contoso Skype for Business のエンタープライズボイスはハブとスポークとして設定されました。</span><span class="sxs-lookup"><span data-stu-id="003e6-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="003e6-115">国内の Skype for Business のエンタープライズボイスユーザーに対して PSTN への接続が提供された地域で PSTN ゲートウェイを管理する場所がありました。</span><span class="sxs-lookup"><span data-stu-id="003e6-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="003e6-116">多くの場合、これらのサテライトオフィスには、独自のインターネット出口がありませんでした。</span><span class="sxs-lookup"><span data-stu-id="003e6-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="003e6-117">これらのユーザの番号は、既存の SBC に接続している SIP トランクに属しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="003e6-118">既に展開されている SBC が直接ルーティングとメディアのバイパスを認定しているかどうかを判断するために、Contoso は、[ダイレクトルーティング用に認定されたセッション境界コントローラーのリスト](direct-routing-border-controllers.md)を確認しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="003e6-119">ユーザーのダイヤルの傾向は、ユーザーが Skype for Business クライアントをピアツーピアオーディオで利用できる場合でも、内線番号を使用して、従来のテレフォニーシステムでユーザーをダイヤルすることでした。</span><span class="sxs-lookup"><span data-stu-id="003e6-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="003e6-120">Contoso は以下の質問に基づいて決定しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="003e6-121">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-121">Q.</span></span> <span data-ttu-id="003e6-122">オンプレミスの展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="003e6-123">、.</span><span class="sxs-lookup"><span data-stu-id="003e6-123">A.</span></span> <span data-ttu-id="003e6-124">X</span><span class="sxs-lookup"><span data-stu-id="003e6-124">No</span></span> 

- <span data-ttu-id="003e6-125">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-125">Q.</span></span> <span data-ttu-id="003e6-126">サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="003e6-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="003e6-127">、.</span><span class="sxs-lookup"><span data-stu-id="003e6-127">A.</span></span> <span data-ttu-id="003e6-128">X</span><span class="sxs-lookup"><span data-stu-id="003e6-128">No</span></span> 

- <span data-ttu-id="003e6-129">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-129">Q.</span></span> <span data-ttu-id="003e6-130">現在のサードパーティの携帯電話会社を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="003e6-131">A. ○ (規制対象国) といいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="003e6-132">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-132">Q.</span></span> <span data-ttu-id="003e6-133">SBCs では ROI を導入する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="003e6-134">A. はいといいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-134">A. Yes and No</span></span>  

- <span data-ttu-id="003e6-135">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-135">Q.</span></span> <span data-ttu-id="003e6-136">Microsoft PSTN 通話プランはこの地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="003e6-137">A. はいといいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-137">A. Yes and No</span></span> 

<span data-ttu-id="003e6-138">お客様の質問に対する回答に基づいて、Contoso は以下のことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="003e6-139">通話プランがある電話システムで PSTN 通話プランを利用できる地域に配置されているユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="003e6-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="003e6-140">PSTN 通話プランが利用可能な地域内に存在しないユーザー、SBCs の ROI がまだ満たされているサイト内のユーザー、および直接ルーティングを使用して電話システムに電話をかけている国に居住しているユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="003e6-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="003e6-141">次の図は、最初の Skype for Business のエンタープライズ Voip の展開と、この展開が Microsoft の通話プランと直接ルーティングの両方に移行された方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![前と後の状態を示す図](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="003e6-143">サイトの種類 B: 従来の従来のテレフォニーシステム</span><span class="sxs-lookup"><span data-stu-id="003e6-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="003e6-144">Contoso には、従来のテレフォニーシステムを活用した多くのオフィスがありました。</span><span class="sxs-lookup"><span data-stu-id="003e6-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="003e6-145">他のユーザーには、電子1.64 電話番号が付いているユーザーのサブセットがありましたが、内線番号しかありませんでした。</span><span class="sxs-lookup"><span data-stu-id="003e6-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="003e6-146">これらの番号は、PSTN ゲートウェイに TDM トランクで存在しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="003e6-147">サイト内ダイヤルは、内線番号の前にあるサイトコードを利用して、通話をルーティングする場所を決定して構成されました。</span><span class="sxs-lookup"><span data-stu-id="003e6-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="003e6-148">ユーザーのダイヤルの傾向は内線番号によって発信されました。</span><span class="sxs-lookup"><span data-stu-id="003e6-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="003e6-149">Contoso は以下の質問に基づいて決定しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="003e6-150">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-150">Q.</span></span> <span data-ttu-id="003e6-151">オンプレミスの展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="003e6-152">、.</span><span class="sxs-lookup"><span data-stu-id="003e6-152">A.</span></span> <span data-ttu-id="003e6-153">X</span><span class="sxs-lookup"><span data-stu-id="003e6-153">No</span></span> 

- <span data-ttu-id="003e6-154">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-154">Q.</span></span> <span data-ttu-id="003e6-155">サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="003e6-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="003e6-156">A. はい</span><span class="sxs-lookup"><span data-stu-id="003e6-156">A. Yes</span></span>

- <span data-ttu-id="003e6-157">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-157">Q.</span></span> <span data-ttu-id="003e6-158">現在のサードパーティの携帯電話会社を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="003e6-159">A. いいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-159">A. No</span></span> 

- <span data-ttu-id="003e6-160">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-160">Q.</span></span> <span data-ttu-id="003e6-161">Microsoft PSTN の通話プランは skype の地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="003e6-162">A. はいといいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-162">A. Yes and No</span></span> 

<span data-ttu-id="003e6-163">お客様の質問に対する回答に基づいて、Contoso は以下のことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="003e6-164">通話プランがある電話システムで PSTN 通話プランを利用できる地域に配置されているユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="003e6-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="003e6-165">PSTN 通話プランが電話システムで直接ルーティングされている地域に存在しないユーザーを移動します。</span><span class="sxs-lookup"><span data-stu-id="003e6-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="003e6-166">ビジネス上重要なアナログデバイスへの PSTN 接続を維持します。</span><span class="sxs-lookup"><span data-stu-id="003e6-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="003e6-167">次の図は、リモートサイトを使った元のレガシシステム展開と、ローカルメディア最適化によるダイレクトルーティング展開への移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="003e6-168">**従来の従来の展開**  
 ![前と後の状態を示す図](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="003e6-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="003e6-169">**ダイレクトルーティングを使用した展開**</span><span class="sxs-lookup"><span data-stu-id="003e6-169">**Deployment with Direct Routing**</span></span>

![前と後の状態を示す図](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="003e6-171">サイトの種類 C: Skype for Business のエンタープライズボイスと従来の従来のテレフォニーシステムの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="003e6-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="003e6-172">Contoso Skype for Business のエンタープライズボイスユーザーの電話番号は、電話会社の SBC に対する SIP トランク上に存在します。</span><span class="sxs-lookup"><span data-stu-id="003e6-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="003e6-173">従来のテレフォニーシステムの番号は、PSTN ゲートウェイへの TDM トランクに搭載されています。</span><span class="sxs-lookup"><span data-stu-id="003e6-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="003e6-174">Contoso は以下の質問に基づいて決定しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="003e6-175">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-175">Q.</span></span> <span data-ttu-id="003e6-176">オンプレミスの展開によって提供される機能を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="003e6-177">、.</span><span class="sxs-lookup"><span data-stu-id="003e6-177">A.</span></span> <span data-ttu-id="003e6-178">X</span><span class="sxs-lookup"><span data-stu-id="003e6-178">No</span></span> 

- <span data-ttu-id="003e6-179">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-179">Q.</span></span> <span data-ttu-id="003e6-180">サードパーティ PBX システムやその他のテレフォニー機器との相互運用が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="003e6-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="003e6-181">A. いいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-181">A. No</span></span> 

- <span data-ttu-id="003e6-182">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-182">Q.</span></span> <span data-ttu-id="003e6-183">現在のサードパーティの携帯電話会社を保持する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="003e6-184">A. いいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-184">A. No</span></span> 

- <span data-ttu-id="003e6-185">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-185">Q.</span></span> <span data-ttu-id="003e6-186">SBCs では ROI を導入する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="003e6-187">A. はいといいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-187">A. Yes and No</span></span>  

- <span data-ttu-id="003e6-188">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-188">Q.</span></span> <span data-ttu-id="003e6-189">Microsoft の PSTN 通話プランはこの地域で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="003e6-190">A. いいえ</span><span class="sxs-lookup"><span data-stu-id="003e6-190">A. No</span></span> 

<span data-ttu-id="003e6-191">Contoso は、質問への回答に基づいて、次のことを決定しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="003e6-192">直接ルーティングが有効になる従来のテレフォニーユーザーの場合、Contoso は直接ルーティングの認定を受けているため、TDM トランクからの数を SBC の SIP トランクに移植しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="003e6-193">電話システムに移行するユーザーのサブセットをサポートし、従来のシステムによる継続的なルーティングを可能にするため、従来のテレフォニーシステムは、SBC への次のホップとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="003e6-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="003e6-194">さらに、ユーザーの行動を変更して、サイト内およびサイト間拡張ダイヤルの依存関係を削除することもできます。これには、すべての内部通話に Teams を使用するためのガイダンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="003e6-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="003e6-195">次の図は、元の Skype for Business のエンタープライズボイスと従来のテレフォニーシステムの展開と、ダイレクトルーティングを使用した混在展開への移行を示しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="003e6-196">**元の混在展開** 
 ![以前の状態を示す図](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="003e6-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="003e6-197">**ダイレクトルーティング** 
 ![ による混在展開以前の状態を示す図](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="003e6-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="003e6-198">通話プラン</span><span class="sxs-lookup"><span data-stu-id="003e6-198">Calling Plans</span></span>

<span data-ttu-id="003e6-199">通話プランの構成要件を決定するために、Contoso は、[通話プランのコア展開の決定](calling-plan-landing-page.md#core-deployment-decisions)をレビューしています。</span><span class="sxs-lookup"><span data-stu-id="003e6-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="003e6-200">その結果、決定が行われました。</span><span class="sxs-lookup"><span data-stu-id="003e6-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="003e6-201">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-201">Q.</span></span> <span data-ttu-id="003e6-202">ユーザーは国際電話を利用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-202">Do my users need international calling?</span></span><br> <span data-ttu-id="003e6-203">A. はい</span><span class="sxs-lookup"><span data-stu-id="003e6-203">A. Yes</span></span> 

- <span data-ttu-id="003e6-204">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-204">Q.</span></span> <span data-ttu-id="003e6-205">各ユーザーは、内側に電話番号を直接接続していますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="003e6-206">最新のものではありません。</span><span class="sxs-lookup"><span data-stu-id="003e6-206">A. Not today.</span></span> <span data-ttu-id="003e6-207">すべてのユーザが有効になります。</span><span class="sxs-lookup"><span data-stu-id="003e6-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="003e6-208">Q&a.</span><span class="sxs-lookup"><span data-stu-id="003e6-208">Q.</span></span> <span data-ttu-id="003e6-209">発信者 ID のマスクや無効化を行いますか?</span><span class="sxs-lookup"><span data-stu-id="003e6-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="003e6-210">A. ユーザーの発信者番号は、Contoso の市内番号に対してマスクされます。</span><span class="sxs-lookup"><span data-stu-id="003e6-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="003e6-211">ダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="003e6-211">Direct Routing</span></span>

<span data-ttu-id="003e6-212">Contoso は、電話システムと直接ルーティングで利用可能なものも含め、Office 365 の機能を常に最新の状態に保つことを Ignite しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="003e6-213">技術リーダーと設計者は、Ignite 2019 で提供されているガイダンスを使用して、その方向を決定しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="003e6-214">使用された主なセッション:</span><span class="sxs-lookup"><span data-stu-id="003e6-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="003e6-215">Microsoft Teams のダイレクトルーティングを使用して成功を計画する</span><span class="sxs-lookup"><span data-stu-id="003e6-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="003e6-216">直接ルーティングの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="003e6-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="003e6-217">構成</span><span class="sxs-lookup"><span data-stu-id="003e6-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="003e6-218">通話プランのサイト</span><span class="sxs-lookup"><span data-stu-id="003e6-218">Calling Plans sites</span></span>

<span data-ttu-id="003e6-219">ライセンスを取得して電話番号をユーザーに割り当てるには、Contoso が[通話プランを設定](set-up-calling-plans.md)する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="003e6-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="003e6-220">電話番号を割り当てる必要があるユーザー数のため、Contoso は電話番号を割り当てるために PowerShell を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="003e6-221">他の設定に加えて、PowerShell を使用して数値を割り当てる方法については &mdash; &mdash; 、 [「Teams PowerShell の概要」](teams-powershell-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003e6-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="003e6-222">ダイレクトルーティングサイト</span><span class="sxs-lookup"><span data-stu-id="003e6-222">Direct Routing sites</span></span>

<span data-ttu-id="003e6-223">Contoso のオンプレミスのテレフォニーインフラストラクチャを Microsoft Teams に接続するために、Contoso の管理者は「[ダイレクトルーティングを構成](direct-routing-configure.md)する」の手順に従って、ガイダンスについては[microsoft Teams のビデオダイレクトルーティング](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl)を確認しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="003e6-224">Contoso は、認定された SBC ベンダーによるダイレクトルーティングの展開ドキュメントも参照しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="003e6-225">SBC と Microsoft Phone システムの間で直接ルーティングを構成した後は、Contoso が構成をテストする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="003e6-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="003e6-226">これを行うために、Contoso 管理者は、 [Ignite 2019 でのダイレクトルーティングセッションの更新](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)で説明されている SIP テスタークライアントを使用しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="003e6-227">SIP Tester クライアントスクリプトとドキュメントは、PowerShell スクリプトからダウンロードされ、ダイレクトルーティングセッションの境界コントローラー接続をテストしました。</span><span class="sxs-lookup"><span data-stu-id="003e6-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="003e6-228">ローカルメディアの最適化</span><span class="sxs-lookup"><span data-stu-id="003e6-228">Local Media Optimization</span></span>

<span data-ttu-id="003e6-229">Contoso は、世界中のさまざまな地域でのローカルメディア最適化を活用しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="003e6-230">Contoso でサポートされているシナリオは、[ダイレクトルーティング用のローカルメディア最適化](direct-routing-media-optimization.md)について説明しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="003e6-231">ローカルメディア最適化の構成は、SBC ベンダーと Microsoft の両方のガイダンスに従って完了しました。</span><span class="sxs-lookup"><span data-stu-id="003e6-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="003e6-232">ローカルメディア最適化の構成手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="003e6-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="003e6-233">ユーザーと SBC サイトを構成する</span><span class="sxs-lookup"><span data-stu-id="003e6-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="003e6-234">Sbc ベンダー仕様に従って SBC を構成します。</span><span class="sxs-lookup"><span data-stu-id="003e6-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="003e6-235">ローカルメディア最適化に使用される各サイトに外部の信頼できる IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="003e6-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="003e6-236">ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="003e6-236">Define the network topology</span></span> 

- <span data-ttu-id="003e6-237">仮想ネットワークトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="003e6-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="003e6-238">モードを確認する: 常にローカルユーザーに対してのみバイパスまたは使用する</span><span class="sxs-lookup"><span data-stu-id="003e6-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="003e6-239">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="003e6-239">Networking considerations</span></span>

<span data-ttu-id="003e6-240">Contoso には、電話システムを有効にした後、長期間リモートで作業する必要がある多数のユーザーがいました。</span><span class="sxs-lookup"><span data-stu-id="003e6-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="003e6-241">特定の基幹業務アプリケーションへのアクセスに VPN を使用したユーザー。</span><span class="sxs-lookup"><span data-stu-id="003e6-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="003e6-242">VPN では、電話システムのユーザーが通話品質の低下を経験しています。</span><span class="sxs-lookup"><span data-stu-id="003e6-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="003e6-243">この品質の問題を解決するために、Contoso は VPN 分割トンネリングを実装しました。これにより、内部アプリへの接続が VPN に残っている間も、Office 365 トラフィックがインターネットを通過できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="003e6-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="003e6-244">VPN 分割トンネリングを実装するために、Contoso は、 [Office 365 用に vpn 分割トンネリングを実装するため](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)のガイダンスに従っています。</span><span class="sxs-lookup"><span data-stu-id="003e6-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





