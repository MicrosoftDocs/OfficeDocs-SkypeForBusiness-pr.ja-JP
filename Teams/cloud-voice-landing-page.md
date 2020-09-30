---
title: Microsoft Teams の音声
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Microsoft voice solutions の詳細については、「Microsoft 電話システムと PSTN 接続オプション (通話プラン、直接ルーティングなど)」を参照してください。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 513525448112fbb9b2b0bf4beacfec46bfb1d76a
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308361"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="aceb5-103">チームのボイスソリューションを計画する</span><span class="sxs-lookup"><span data-stu-id="aceb5-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="aceb5-104">この記事では、組織に適した Microsoft voice ソリューションを決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="aceb5-105">この記事では、選択したソリューションの実装を可能にするコンテンツのロードマップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span> 

<span data-ttu-id="aceb5-106">通話プランには、最も簡単なソリューション電話システムが必要になることがあり &mdash; ます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-106">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="aceb5-107">これは、次の図に示すように、プライベートな支店交換 (PBX) 機能と公衆交換電話網 (PSTN) への通話を提供する、Microsoft のすべてのクラウドソリューションです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-107">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="aceb5-108">このソリューションを使用すると、Microsoft が PSTN キャリアになります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-108">With this solution, Microsoft is your PSTN carrier.</span></span>

![図1は、通話プランが含まれる電話システムを示しています。](media/msft-voice-solutions-1.png)

<span data-ttu-id="aceb5-110">「はい」を選択すると、通話プランを使用した電話システムは適切な解決策となります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-110">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="aceb5-111">通話プランは、お住まいの地域でご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-111">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="aceb5-112">現在の PSTN キャリアを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-112">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="aceb5-113">PSTN への Microsoft 管理のアクセスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-113">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="aceb5-114">ただし、状況が複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-114">However, your situation might be more complex.</span></span> <span data-ttu-id="aceb5-115">たとえば、通話プランを利用できない場所にオフィスがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-115">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="aceb5-116">または、地理的な場所によって要件が異なる、複数の地域にわたる複雑な展開をサポートする組み合わせソリューションが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-116">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="aceb5-117">Microsoft は、次のソリューションの組み合わせをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-117">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="aceb5-118">通話プラン付きの電話システム</span><span class="sxs-lookup"><span data-stu-id="aceb5-118">Phone System with Calling Plan</span></span>
- <span data-ttu-id="aceb5-119">直接ルーティングを使用する独自の PSTN キャリアを搭載した電話システム</span><span class="sxs-lookup"><span data-stu-id="aceb5-119">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="aceb5-120">直接ルーティングを使用する通話プランと電話システムの両方を使用する組み合わせのソリューション</span><span class="sxs-lookup"><span data-stu-id="aceb5-120">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="aceb5-121">何を読む必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="aceb5-121">What do you need to read?</span></span>

<span data-ttu-id="aceb5-122">**すべてに必須。**</span><span class="sxs-lookup"><span data-stu-id="aceb5-122">**Required for all.**</span></span> <span data-ttu-id="aceb5-123">この記事の一部のセクションは、すべての組織に関連しています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-123">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="aceb5-124">たとえば、すべてのユーザーが電話システムについての情報を読み、公衆交換電話網 (PSTN) に接続するためのオプションについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-124">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="aceb5-125">すべてに必須</span><span class="sxs-lookup"><span data-stu-id="aceb5-125">Required for all</span></span> | <span data-ttu-id="aceb5-126">説明</span><span class="sxs-lookup"><span data-stu-id="aceb5-126">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="aceb5-127">**電話システム**</span><span class="sxs-lookup"><span data-stu-id="aceb5-127">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="aceb5-128">Microsoft Teams で microsoft 365 クラウドの通話コントロールとプライベート支店 Exchange (PBX) 機能を有効にするための microsoft の技術。</span><span class="sxs-lookup"><span data-stu-id="aceb5-128">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="aceb5-129">**公衆交換電話網 (PSTN) 接続オプション**</span><span class="sxs-lookup"><span data-stu-id="aceb5-129">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="aceb5-130">直接の電話会社として Microsoft を使用するか、直接ルーティングを使用して、独自のテレフォニーキャリアを Microsoft Teams に接続するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-130">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="aceb5-131">電話システムと PSTN の接続オプションを組み合わせると、世界中の電話に通話を発信することができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-131">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="aceb5-132">**要件によって異なります。**</span><span class="sxs-lookup"><span data-stu-id="aceb5-132">**Depending on your requirements.**</span></span> <span data-ttu-id="aceb5-133">この記事の一部のセクションは、既存の展開と要件に応じて関連しています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-133">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="aceb5-134">たとえば、場所に基づくルーティングは、有料の通話を許可していない地理的な場所にいるユーザーに対してのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="aceb5-134">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>


| <span data-ttu-id="aceb5-135">要件に応じて</span><span class="sxs-lookup"><span data-stu-id="aceb5-135">Depending on your requirements</span></span> | <span data-ttu-id="aceb5-136">説明</span><span class="sxs-lookup"><span data-stu-id="aceb5-136">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="aceb5-137">**Microsoft からの電話番号**</span><span class="sxs-lookup"><span data-stu-id="aceb5-137">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="aceb5-138">Microsoft から電話番号を取得して管理する方法と、既存の電話番号を Microsoft に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-138">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="aceb5-139">Microsoft 通話プランの電話番号を取得する必要がある場合、既存の電話番号を移行する場合、サービス番号を取得する場合は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-139">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="aceb5-140">**ダイヤルプランと通話ルーティング**</span><span class="sxs-lookup"><span data-stu-id="aceb5-140">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="aceb5-141">ダイヤルした電話番号を別の形式 (通常は164形式) に変換するダイヤルプランを設定および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-141">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="aceb5-142">ダイヤルプランについて理解する必要がある場合、および組織のダイヤルプランを指定する必要がある場合は、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-142">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="aceb5-143">**緊急通話**</span><span class="sxs-lookup"><span data-stu-id="aceb5-143">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="aceb5-144">PSTN 接続オプションに応じて、緊急通話の管理と構成を行う方法につい &mdash; て説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-144">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="aceb5-145">Microsoft 通話プランまたはダイレクトルーティングを使用していて、組織の緊急通話の管理方法を理解する必要がある場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-145">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="aceb5-146">**ダイレクトルーティング用の位置情報に基づくルーティング**</span><span class="sxs-lookup"><span data-stu-id="aceb5-146">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="aceb5-147">場所に基づくルーティング (LBR) を使用して、地理的な場所に基づいて Microsoft Teams ユーザーの有料電話のバイパスを制限する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-147">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="aceb5-148">このセクションは、組織で有料のバイパスが許可されていない場所で直接ルーティングを使用している場合にお読みください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-148">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="aceb5-149">**クラウド音声機能のネットワークトポロジ**</span><span class="sxs-lookup"><span data-stu-id="aceb5-149">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="aceb5-150">組織で、ダイレクトルーティングまたは動的な緊急通話のために位置情報に基づくルーティング (LBR) を展開している場合は、Microsoft Teams でこれらの機能を使用するためにネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-150">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="aceb5-151">ダイレクトルーティング用に LBR を実装している場合、または、通話プランまたは直接ルーティングを使って動的な緊急通話を実装している場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-151">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="aceb5-152">**既存のボイスソリューションを移行する**</span><span class="sxs-lookup"><span data-stu-id="aceb5-152">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="aceb5-153">音声ソリューションを Teams に移行する際に考慮する必要があること。</span><span class="sxs-lookup"><span data-stu-id="aceb5-153">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="aceb5-154">既存のボイスソリューションから Teams に移行する場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-154">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="aceb5-155">この記事では、Microsoft Teams のボイスソリューションに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-155">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="aceb5-156">Skype for Business Online のソリューションはまだ使用できますが (「 [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)」で説明しています)、Skype For business online は2021年7月31日に廃止されることを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="aceb5-156">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="aceb5-157">その日を過ぎると、Skype for Business Online サービスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-157">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="aceb5-158">さらに、 &mdash; skype For Business Server または Cloud Connector Edition と skype For Business Online のどちらを使用しても、オンプレミス環境間の PSTN 接続 &mdash; がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-158">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="aceb5-159">この記事では、Teams voip ソリューションの概要について説明します。また、必要に応じてオンプレミスのテレフォニーネットワークを、直接ルーティングを使用してチームに接続する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-159">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="aceb5-160">電話システム</span><span class="sxs-lookup"><span data-stu-id="aceb5-160">Phone System</span></span>

<span data-ttu-id="aceb5-161">電話システムは、microsoft Teams を使用して Microsoft 365 または Office 365 クラウドの通話コントロールとプライベート支店 Exchange (PBX) 機能を有効にするための Microsoft の技術です。</span><span class="sxs-lookup"><span data-stu-id="aceb5-161">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="aceb5-162">電話システムは、Teams または Skype for Business クライアントと認定されたデバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-162">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="aceb5-163">電話システムを使用すると、既存の PBX システムを、Microsoft 365 または Office 365 から直接配信される一連の機能に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-163">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="aceb5-164">組織内のユーザー間の通話は電話システムの内部で処理され、公衆交換電話網 (PSTN) に流れることは決してありません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-164">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="aceb5-165">これは、地理的にさまざまな場所にいる組織内のユーザー間の通話にも当てはまるため、このような長距離の社内通話にかかるコストが解消されます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-165">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="aceb5-166">この記事では、次の電話システムの主要機能と機能について説明し、検討する必要がある展開の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-166">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="aceb5-167">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="aceb5-167">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="aceb5-168">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="aceb5-168">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="aceb5-169">通話 ID</span><span class="sxs-lookup"><span data-stu-id="aceb5-169">Calling identity</span></span>](#calling-identity)

<span data-ttu-id="aceb5-170">電話システムのすべての機能と、電話システムのセットアップ方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-170">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-171">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="aceb5-171">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="aceb5-172">組織で電話システムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="aceb5-172">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="aceb5-173">電話システムのライセンスを購入して割り当てる方法、電話番号を管理する方法、無料番号の通信クレジットを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-173">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="aceb5-174">サポートされているデバイスを管理する方法については、「Microsoft Teams および[Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[でデバイスを管理](devices/device-management.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-174">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="aceb5-175">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="aceb5-175">Auto attendants and Call queues</span></span>

<span data-ttu-id="aceb5-176">自動応答を使うと、発信者の入力に基づいて着信をルーティングするためのメニューオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-176">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="aceb5-177">通話キューは、発信者の待機領域です。</span><span class="sxs-lookup"><span data-stu-id="aceb5-177">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="aceb5-178">自動応答と通話キューを併用すると、発信者を組織内の適切なユーザーまたは部門に簡単にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-178">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="aceb5-179">自動応答と通話キューの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-179">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-180">Teams の自動応答と通話キューを計画する</span><span class="sxs-lookup"><span data-stu-id="aceb5-180">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="aceb5-181">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="aceb5-181">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="aceb5-182">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="aceb5-182">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="aceb5-183">Contoso のケーススタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="aceb5-183">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="aceb5-184">架空の多国籍企業、Contoso が、ボイスソリューションの自動応答と通話キューを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-184">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="aceb5-185">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="aceb5-185">Cloud Voicemail</span></span>

<span data-ttu-id="aceb5-186">Azure ボイスメールサービスを利用するクラウドボイスメールでは、Exchange メールボックスのみに対するボイスメールのデポジットがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-186">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="aceb5-187">サードパーティのメールシステムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-187">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="aceb5-188">クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-188">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="aceb5-189">会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-189">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="aceb5-190">オンラインのみのユーザーの場合は、電話システムのライセンスが割り当てられた後、クラウドボイスメールが自動的に設定され、ユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-190">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="aceb5-191">Exchange メールボックスを使用している電話システムのユーザーの場合は、追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-191">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="aceb5-192">クラウドボイスメールとその構成の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-192">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-193">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="aceb5-193">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="aceb5-194">組織でボイスメールポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="aceb5-194">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="aceb5-195">通話 ID</span><span class="sxs-lookup"><span data-stu-id="aceb5-195">Calling identity</span></span>

<span data-ttu-id="aceb5-196">既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-196">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="aceb5-197">通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-197">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="aceb5-198">発信者番号認識を構成する方法、または発信者番号を変更またはブロックする方法については、「 [ユーザーに発信者番号を設定](set-the-caller-id-for-a-user.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-198">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="aceb5-199">公衆交換電話のネットワーク接続オプション</span><span class="sxs-lookup"><span data-stu-id="aceb5-199">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="aceb5-200">電話システムには、組織のための包括的な PBX 機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-200">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="aceb5-201">ただし、ユーザーが組織外から電話をかけることができるようにするには、電話システムを公衆交換電話網 (PSTN) に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-201">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="aceb5-202">電話システムを PSTN に接続するには、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-202">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="aceb5-203">[**通話プラン付きの電話システム**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-203">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="aceb5-204">PSTN キャリアとしての Microsoft とのクラウドソリューション。</span><span class="sxs-lookup"><span data-stu-id="aceb5-204">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="aceb5-205">直接ルーティングを使用して、オンプレミス環境を Teams に接続して、[**独自の PSTN キャリアを搭載した電話システム**](#phone-system-with-own-pstn-carrier-with-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-205">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="aceb5-206">また、さまざまなオプションを組み合わせて、複雑な環境のソリューションを設計したり、マルチステップ移行を管理したりできます (詳細については、後で移行する)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-206">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="aceb5-207">通話プラン付きの電話システム</span><span class="sxs-lookup"><span data-stu-id="aceb5-207">Phone System with Calling Plan</span></span> 

<span data-ttu-id="aceb5-208">この記事で既に説明したように、通話プランが含まれる電話システムは、Teams ユーザー向けの Microsoft のクラウド向けのボイスソリューションです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-208">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="aceb5-209">これは、世界中の固定電話と携帯電話への通話を可能にするために、Microsoft 電話システムと公衆交換電話網 (PSTN) を接続する最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-209">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="aceb5-210">このオプションを使用すると、次の図に示すように、Microsoft が組織のプライベートブランチ Exchange (PBX) 機能を利用できるようになり、PSTN キャリアとして機能します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-210">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![図1は、通話プランが含まれる電話システムを示しています。](media/msft-voice-solutions-1a.png)

<span data-ttu-id="aceb5-212">「はい」を選択すると、通話プランを使用した電話システムは適切な解決策となります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-212">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="aceb5-213">通話プランは、お住まいの地域でご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-213">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="aceb5-214">現在の PSTN キャリアを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-214">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="aceb5-215">PSTN への Microsoft 管理のアクセスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-215">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="aceb5-216">次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-216">With this option:</span></span> 

- <span data-ttu-id="aceb5-217">国内または国際通話プランを追加して Microsoft 電話システムを利用すると、世界中の電話に通話を発信できます (ライセンスされているサービスのレベルによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-217">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="aceb5-218">&mdash;通話プランは Microsoft 365 または Office 365 から使用できないため、オンプレミス展開の展開またはメンテナンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-218">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="aceb5-219">注: 必要に応じて、サポートされているセッション境界コントローラー (SBC) と、SBC でサポートされているサードパーティ製の電話機器、およびその他のサードパーティ製の電話機器との相互運用性を実現するために、サポートされているユーザーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-219">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="aceb5-220">このオプションをオンにするには、Microsoft 365 または Office 365 への接続を中断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-220">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="aceb5-221">通話プランの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-221">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-222">どの通話プランが適していますか?</span><span class="sxs-lookup"><span data-stu-id="aceb5-222">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="aceb5-223">通話プランを購入する方法</span><span class="sxs-lookup"><span data-stu-id="aceb5-223">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="aceb5-224">通話プランが利用可能な国と地域</span><span class="sxs-lookup"><span data-stu-id="aceb5-224">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="aceb5-225">通話プランを設定する</span><span class="sxs-lookup"><span data-stu-id="aceb5-225">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="aceb5-226">直接ルーティングを使用する独自の PSTN キャリアを搭載した電話システム</span><span class="sxs-lookup"><span data-stu-id="aceb5-226">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="aceb5-227">このオプションでは、次の図に示すように、直接ルーティングを使用して Microsoft 電話システムをテレフォニーネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-227">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![図2は、ダイレクトルーティングを使用した電話システムを示しています。](media/msft-voice-solutions-2.png)

<span data-ttu-id="aceb5-229">以下の質問に対して [はい] を選択した場合、直接ルーティングを使用する電話システムは適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-229">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="aceb5-230">電話システムで Teams を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="aceb5-230">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="aceb5-231">現在の PSTN キャリアを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-231">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="aceb5-232">通話プランを通じて一部の通話を発信したり、通信事業者を通じてルーティングを組み合わせたりする必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="aceb5-232">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="aceb5-233">サードパーティの Pbx や機器との相互運用には、skype のオーバーヘッドポケットベル、アナログデバイスなど、お客様が対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-233">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="aceb5-234">次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-234">With this option:</span></span>

- <span data-ttu-id="aceb5-235">オンプレミスソフトウェアを追加しなくても、サポートされている SBC を Microsoft 電話システムに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-235">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="aceb5-236">ほぼすべてのテレフォニーキャリアを Microsoft 電話システムと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-236">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="aceb5-237">このオプションの構成と管理を行うことができます。また、お客様の通信事業者またはパートナーによって構成および管理することもできます (お使いの電話会社またはパートナーがこのオプションを提供しているかどうかを尋ねます)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-237">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="aceb5-238">&mdash;サードパーティ PBX、アナログデバイス、Microsoft 電話システムなどのテレフォニー機器の間の相互運用性を構成することができ &mdash; ます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-238">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="aceb5-239">このオプションには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="aceb5-239">This option requires the following:</span></span>

- <span data-ttu-id="aceb5-240">Microsoft 365 または Office 365 への接続を中断します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-240">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="aceb5-241">サポートされている SBC の展開と保守。</span><span class="sxs-lookup"><span data-stu-id="aceb5-241">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="aceb5-242">サードパーティの携帯電話会社との契約。</span><span class="sxs-lookup"><span data-stu-id="aceb5-242">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="aceb5-243">(お客様がサードパーティ PBX、アナログデバイス、または通話システムを使用しているユーザー用のその他のテレフォニー機器への接続を提供するオプションとして展開されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-243">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="aceb5-244">直接ルーティングの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-244">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-245">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="aceb5-245">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="aceb5-246">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="aceb5-246">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="aceb5-247">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="aceb5-247">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="aceb5-248">直接ルーティングで使用するためのボイスルーティングポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="aceb5-248">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="aceb5-249">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="aceb5-249">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="aceb5-250">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="aceb5-250">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="aceb5-251">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="aceb5-251">Phone numbers from Microsoft</span></span>

<span data-ttu-id="aceb5-252">Microsoft には、2種類の電話番号が用意されています。 *加入者* (ユーザー) 番号は、組織内のユーザーに割り当てることができ、 *サービス* 番号は有料および有料サービスの電話番号として利用できます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-252">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="aceb5-253">サービス番号は加入者番号よりも高い同時通話能力を備えており、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-253">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="aceb5-254">次のことを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-254">You will need to decide:</span></span>

- <span data-ttu-id="aceb5-255">Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?</span><span class="sxs-lookup"><span data-stu-id="aceb5-255">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="aceb5-256">どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?</span><span class="sxs-lookup"><span data-stu-id="aceb5-256">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="aceb5-257">どんな方法で既存の電話番号を Teams に移植しますか?</span><span class="sxs-lookup"><span data-stu-id="aceb5-257">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="aceb5-258">組織内の電話番号を管理する方法の詳細については、新しい番号を取得したり、既存の番号を移行したりするなど、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-258">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-259">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="aceb5-259">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="aceb5-260">通話プランに使用される異なる種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="aceb5-260">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="aceb5-261">ユーザー用の電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="aceb5-261">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="aceb5-262">Microsoft Teams に電話番号を転送する</span><span class="sxs-lookup"><span data-stu-id="aceb5-262">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="aceb5-263">ダイヤルプランと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="aceb5-263">Dial plans and call routing</span></span>

<span data-ttu-id="aceb5-264">ダイヤルプランとは、ダイヤルした電話番号を別の形式 (通常は164形式) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-264">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="aceb5-265">次のことを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-265">You will need to decide the following:</span></span> 

- <span data-ttu-id="aceb5-266">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="aceb5-266">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="aceb5-267">カスタマイズされたダイヤルプランが必要なユーザー</span><span class="sxs-lookup"><span data-stu-id="aceb5-267">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="aceb5-268">各ユーザーに割り当てるテナントのダイヤルプランを選択してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-268">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="aceb5-269">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-269">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="aceb5-270">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="aceb5-270">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="aceb5-271">テナントダイヤルプランの計画</span><span class="sxs-lookup"><span data-stu-id="aceb5-271">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="aceb5-272">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="aceb5-272">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="aceb5-273">緊急通話</span><span class="sxs-lookup"><span data-stu-id="aceb5-273">Emergency calling</span></span>

<span data-ttu-id="aceb5-274">緊急通話の構成方法は、PSTN 接続オプション (Microsoft 通話プランまたは直接ルーティング) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-274">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="aceb5-275">Microsoft 通話プランや電話システムのダイレクトルーティングの動的な緊急通話では、チームクライアントの現在の場所に基づいて緊急通話の構成とルーティングを行う機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-275">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="aceb5-276">緊急通話の概念と用語の詳細と、動的な緊急通話の設定方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-276">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-277">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="aceb5-277">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="aceb5-278">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="aceb5-278">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="aceb5-279">Contoso のケーススタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="aceb5-279">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="aceb5-280">架空の多国籍企業 Contoso が組織の緊急通報を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-280">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="aceb5-281">ダイレクトルーティング用の位置情報に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="aceb5-281">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="aceb5-282">一部の国と地域では、公衆交換電話網 (PSTN) プロバイダーを迂回して長距離通話料金を削減することはできません。</span><span class="sxs-lookup"><span data-stu-id="aceb5-282">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="aceb5-283">ダイレクトルーティングの位置情報に基づくルーティングでは、地理的な場所に基づいて、Microsoft Teams ユーザーの有料のバイパスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-283">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="aceb5-284">位置情報に基づくルーティング (LBR) の計画と構成の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-284">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="aceb5-285">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="aceb5-285">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="aceb5-286">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="aceb5-286">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="aceb5-287">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="aceb5-287">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="aceb5-288">Contoso のケーススタディ: 場所に基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="aceb5-288">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="aceb5-289">架空の多国籍企業 Contoso が組織の位置情報に基づくルーティングを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-289">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="aceb5-290">音声機能のネットワークトポロジ</span><span class="sxs-lookup"><span data-stu-id="aceb5-290">Network topology for voice features</span></span>

<span data-ttu-id="aceb5-291">動的な緊急通話または位置ベースのルーティングを直接ルーティングする場合は、Microsoft Teams でこれらの機能を使用するためにネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-291">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="aceb5-292">ネットワークの領域、ネットワークサイト、ネットワークサブネット、および信頼できる IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-292">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="aceb5-293">Microsoft Teams のクラウド音声機能のネットワーク設定-概念と用語</span><span class="sxs-lookup"><span data-stu-id="aceb5-293">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="aceb5-294">Microsoft Teams でクラウド音声機能のネットワークトポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="aceb5-294">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="aceb5-295">既存のボイスソリューションを Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="aceb5-295">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="aceb5-296">チームにアップグレードしている組織の場合、最終的な目標は、すべてのユーザーを Teams Sonly モードに移動することです。</span><span class="sxs-lookup"><span data-stu-id="aceb5-296">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="aceb5-297">Teams での電話システムの使用は、ユーザーが TeamsOnly モードになっている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-297">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="aceb5-298">Teams へのアップグレードに関する基本的な情報が必要な場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-298">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="aceb5-299">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="aceb5-299">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="aceb5-300">アップグレードのフレームワークについて</span><span class="sxs-lookup"><span data-stu-id="aceb5-300">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="aceb5-301">Skype for Business から Teams へのアップグレード (IT 管理者向け)</span><span class="sxs-lookup"><span data-stu-id="aceb5-301">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

<span data-ttu-id="aceb5-302">ボイスソリューションを移行する場合は、teams Sonly モードに移行するときに、次の4つの通話シナリオを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-302">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="aceb5-303">[**Microsoft の通話プランを使用した、Skype For Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="aceb5-303">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="aceb5-304">アップグレードすると、このユーザーには引き続き Microsoft 通話プランが設定されます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-304">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="aceb5-305">Skype for business\*\*のオンプレミスまたはクラウドコネクタエディションによる[オンプレミス音声機能を備えた Skype For business Online のユーザー](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) \*\*。</span><span class="sxs-lookup"><span data-stu-id="aceb5-305">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="aceb5-306">このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-306">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="aceb5-307">**[エンタープライズ voip がオンプレミスの Skype for business のユーザー](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。オンラインに移行し、オンプレミスの PSTN 接続を維持し**ます。</span><span class="sxs-lookup"><span data-stu-id="aceb5-307">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="aceb5-308">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-308">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="aceb5-309">**[エンタープライズ voip がオンプレミスの Skype for business のユーザー](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。オンラインに移行し、Microsoft の通話プランを使用**します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-309">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="aceb5-310">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aceb5-310">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="aceb5-311">&mdash;ハイブリッド接続を設定する必要がある場合や、オンプレミスのボイス機能を使用してユーザーを直接ルーティングする方法について &mdash; は、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aceb5-311">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="aceb5-312">チームにアップグレードするときの PSTN の考慮事項 (IT 管理者向け)</span><span class="sxs-lookup"><span data-stu-id="aceb5-312">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="aceb5-313">Contoso ボイス移行のケーススタディ</span><span class="sxs-lookup"><span data-stu-id="aceb5-313">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="aceb5-314">このケーススタディでは、架空の多国籍企業である Contoso が組織のために Teams のボイスソリューションを実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aceb5-314">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="aceb5-315">次の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aceb5-315">It contains the following articles:</span></span>

  - [<span data-ttu-id="aceb5-316">Teams アップグレード計画</span><span class="sxs-lookup"><span data-stu-id="aceb5-316">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="aceb5-317">電話システムと PSTN の接続オプション</span><span class="sxs-lookup"><span data-stu-id="aceb5-317">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="aceb5-318">位置に基づくルーティングの実装</span><span class="sxs-lookup"><span data-stu-id="aceb5-318">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="aceb5-319">緊急通話</span><span class="sxs-lookup"><span data-stu-id="aceb5-319">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="aceb5-320">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="aceb5-320">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="aceb5-321">電話会議</span><span class="sxs-lookup"><span data-stu-id="aceb5-321">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












