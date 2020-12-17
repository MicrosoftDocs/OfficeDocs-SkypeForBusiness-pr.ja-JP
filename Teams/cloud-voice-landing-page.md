---
title: Microsoft Teams で音声ソリューションを計画する
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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Microsoft Teams クラウド音声機能と、組織に対して行う展開決定の詳細について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16a2aea0d367c720cf36c8010670a34472ab43a
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701335"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="07e60-103">Teams 音声ソリューションを計画する</span><span class="sxs-lookup"><span data-stu-id="07e60-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="07e60-104">この記事では、組織に最適な Microsoft 音声ソリューションを決定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="07e60-105">決定したら、この記事では、選択したソリューションを実装できるコンテンツのロードマップを提供します。</span><span class="sxs-lookup"><span data-stu-id="07e60-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="07e60-106">Skype for Business Server から Teams にアップグレードする全体的な計画の一部として Teams 音声ソリューションを計画する方法については、オンプレミスの [Skype for Business](upgrade-to-Teams-on-prem-pstn-considerations.md)から Teams にアップグレードする場合の PSTN に関する考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-Teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="07e60-107">最も簡単なソリューションの電話システム &mdash; と通話プランが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="07e60-108">これは、次の図に示すように、プライベート ブランチ交換 (PBX) 機能と公衆交換電話網 (PSTN) への通話を提供する、Microsoft のクラウド内すべてソリューションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="07e60-109">このソリューションを使用すると、Microsoft が PSTN 通信事業者になります。</span><span class="sxs-lookup"><span data-stu-id="07e60-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![図 1 は、通話プランを使用した電話システムを示しています](media/voice-solutions-simple.png)

<span data-ttu-id="07e60-111">「はい」と答える場合は、通話プラン付き電話システムが適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="07e60-112">通話プランは、お客様の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="07e60-113">現在の PSTN 通信事業者を保持する必要はない。</span><span class="sxs-lookup"><span data-stu-id="07e60-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="07e60-114">PSTN への Microsoft が管理するアクセスを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="07e60-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="07e60-115">ただし、状況は複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-115">However, your situation might be more complex.</span></span> <span data-ttu-id="07e60-116">たとえば、通話プランが利用できない場所にオフィスがある場合などです。</span><span class="sxs-lookup"><span data-stu-id="07e60-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="07e60-117">または、地理的な場所ごとに要件が異なる複雑な多国籍展開をサポートする複合ソリューションが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="07e60-118">Microsoft では、次のソリューションの組み合わせをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="07e60-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="07e60-119">通話プラン付き電話システム</span><span class="sxs-lookup"><span data-stu-id="07e60-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="07e60-120">ダイレクト ルーティングを使用した独自の PSTN 通信事業者を使用した電話システム</span><span class="sxs-lookup"><span data-stu-id="07e60-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="07e60-121">通話プラン付き電話システムと直接ルーティング付き電話システムの両方を使用する組み合わせソリューション</span><span class="sxs-lookup"><span data-stu-id="07e60-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="07e60-122">何を読む必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="07e60-122">What do you need to read?</span></span>

<span data-ttu-id="07e60-123">**すべてのユーザーに必要です。**</span><span class="sxs-lookup"><span data-stu-id="07e60-123">**Required for all.**</span></span> <span data-ttu-id="07e60-124">この記事の一部のセクションは、すべての組織に関係します。</span><span class="sxs-lookup"><span data-stu-id="07e60-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="07e60-125">たとえば、すべてのユーザーが電話システムについて理解し、公衆交換電話網 (PSTN) に接続するためのオプションについて理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="07e60-126">すべてのユーザーに必須</span><span class="sxs-lookup"><span data-stu-id="07e60-126">Required for all</span></span> | <span data-ttu-id="07e60-127">説明</span><span class="sxs-lookup"><span data-stu-id="07e60-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="07e60-128">**電話システム**</span><span class="sxs-lookup"><span data-stu-id="07e60-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="07e60-129">Microsoft Teams を使用して Microsoft 365 クラウドで通話制御とプライベート ブランチ交換 (PBX) 機能を有効にする Microsoft のテクノロジ。</span><span class="sxs-lookup"><span data-stu-id="07e60-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="07e60-130">**公衆交換電話網 (PSTN) 接続オプション**</span><span class="sxs-lookup"><span data-stu-id="07e60-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="07e60-131">Microsoft をテレフォニー通信事業者として使用するか、ダイレクト ルーティングを使用して独自のテレフォニー通信事業者を Microsoft Teams に接続するかの選択。</span><span class="sxs-lookup"><span data-stu-id="07e60-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="07e60-132">電話システムと組み合わせると、PSTN 接続オプションにより、ユーザーは世界中に電話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="07e60-133">**要件に応じて異なる。**</span><span class="sxs-lookup"><span data-stu-id="07e60-133">**Depending on your requirements.**</span></span> <span data-ttu-id="07e60-134">この記事の一部のセクションは、既存の展開と要件に応じて関連します。</span><span class="sxs-lookup"><span data-stu-id="07e60-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="07e60-135">たとえば、ルートLocation-Basedは、有料バイパスを許可していない地理的な場所にあるダイレクト ルーティングのお客様にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="07e60-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="07e60-136">次の追加構成が必要な場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-136">Consider which of these additional configurations you might need:</span></span>

![図 2 は、Microsoft の電話番号、ダイヤル プラン、通話ルーティングなどの追加の音声コンポーネントを示しています。](media/voice-consider-additional-components.png)

| <span data-ttu-id="07e60-138">要件に応じて</span><span class="sxs-lookup"><span data-stu-id="07e60-138">Depending on your requirements</span></span> | <span data-ttu-id="07e60-139">説明</span><span class="sxs-lookup"><span data-stu-id="07e60-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="07e60-140">**Microsoft からの電話番号**</span><span class="sxs-lookup"><span data-stu-id="07e60-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="07e60-141">Microsoft から電話番号を取得して管理する方法と、既存の番号を Microsoft に転送する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="07e60-142">Microsoft 通話プランの電話番号の取得、既存の番号の転送、サービス番号の取得が必要な場合は、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="07e60-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="07e60-143">**ダイヤル プランと通話ルーティング**</span><span class="sxs-lookup"><span data-stu-id="07e60-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="07e60-144">ダイヤルされた電話番号を通話承認および通話ルーティング用の別の形式 (通常は E.164 形式) に変換するダイヤル プランを構成および管理する方法。</span><span class="sxs-lookup"><span data-stu-id="07e60-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="07e60-145">ダイヤル プランの詳細と、組織のダイヤル プランを指定する必要があるかどうかを理解する必要がある場合は、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="07e60-146">**緊急通話**</span><span class="sxs-lookup"><span data-stu-id="07e60-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="07e60-147">PSTN 接続オプションに応じて緊急 &mdash; 通話を管理および構成する方法。</span><span class="sxs-lookup"><span data-stu-id="07e60-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="07e60-148">Microsoft 通話プランまたは直接ルーティングを使用し、組織の緊急通話を管理する方法を理解する必要がある場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="07e60-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="07e60-149">**直接ルーティングの場所に基づくルーティング**</span><span class="sxs-lookup"><span data-stu-id="07e60-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="07e60-150">LBR (Location-Basedルーティング) を使用して、地理的な場所に基づいて Microsoft Teams ユーザーの有料バイパスを制限する方法。</span><span class="sxs-lookup"><span data-stu-id="07e60-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="07e60-151">組織が有料バイパスを許可していない場所で直接ルーティングを使用している場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="07e60-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="07e60-152">**クラウド音声機能のネットワーク トポロジ**</span><span class="sxs-lookup"><span data-stu-id="07e60-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="07e60-153">組織が直接ルーティングまたは動的緊急通話用の Location-Based ルーティング (LBR) を展開している場合は、Microsoft Teams でこれらの機能で使用するネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="07e60-154">直接ルーティング用の LBR を実装している場合、または通話プランまたはダイレクト ルーティングを使用して動的緊急通話を実装している場合は、このセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="07e60-155">**既存の音声ソリューションを移行する**</span><span class="sxs-lookup"><span data-stu-id="07e60-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="07e60-156">音声ソリューションを Teams に移行するときに考える必要があるもの。</span><span class="sxs-lookup"><span data-stu-id="07e60-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="07e60-157">既存の音声ソリューションから Teams に移行する場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="07e60-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="07e60-158">この記事では、Microsoft Teams の音声ソリューションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="07e60-159">Skype for Business Online のソリューションは引き続き利用できます [(Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)テレフォニー ソリューションの説明に従って)、Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。</span><span class="sxs-lookup"><span data-stu-id="07e60-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="07e60-160">この日付を終了すると、Skype for Business Online サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="07e60-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="07e60-161">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続は &mdash; &mdash; サポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="07e60-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="07e60-162">この記事では、Teams 音声ソリューションと、必要に応じて直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="07e60-163">電話システム</span><span class="sxs-lookup"><span data-stu-id="07e60-163">Phone System</span></span>

<span data-ttu-id="07e60-164">電話システムは、Microsoft Teams を使用して Microsoft 365 または Office 365 クラウドの通話制御とプライベート ブランチ交換 (PBX) 機能を有効にする Microsoft のテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="07e60-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="07e60-165">電話システムは、Teams または Skype for Business クライアントおよび認定デバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="07e60-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="07e60-166">電話システムでは、既存の PBX システムを、Microsoft 365 または Office 365 から直接提供される一連の機能に置き換える機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="07e60-167">組織内のユーザー間の通話は電話システムの内部で処理され、公衆交換電話網 (PSTN) に流れることは決してありません。</span><span class="sxs-lookup"><span data-stu-id="07e60-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="07e60-168">これは、地理的にさまざまな場所にいる組織内のユーザー間の通話にも当てはまるため、このような長距離の社内通話にかかるコストが解消されます。</span><span class="sxs-lookup"><span data-stu-id="07e60-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="07e60-169">この記事では、次の電話システムの主な機能と、検討する必要がある展開の決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="07e60-170">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="07e60-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="07e60-171">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="07e60-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="07e60-172">通話 ID</span><span class="sxs-lookup"><span data-stu-id="07e60-172">Calling identity</span></span>](#calling-identity)

![図 3 に示す電話システムには、自動応答と通話クエリ、クラウド ボイスメール、通話 ID が含まれている](media/phone-system-contains.png)

<span data-ttu-id="07e60-174">電話システムのすべての機能と電話システムのセットアップ方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="07e60-175">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="07e60-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="07e60-176">組織で電話システムをセットアップする</span><span class="sxs-lookup"><span data-stu-id="07e60-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="07e60-177">電話システム ライセンスの購入と割り当て、電話番号の管理、無料電話番号のコミュニケーション クレジットの設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="07e60-178">サポートされているデバイスの管理の詳細については [、「Microsoft Teams](devices/device-management.md) と Teams Marketplace でデバイスを管理する」 [を参照してください](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="07e60-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="07e60-179">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="07e60-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="07e60-180">自動応答では、発信者の入力に基づいて通話をルーティングするメニュー オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="07e60-181">通話キューは、呼び出し元の待機領域です。</span><span class="sxs-lookup"><span data-stu-id="07e60-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="07e60-182">自動応答と通話キューを組み合わせて使用すると、発信者を組織内の適切な人物または部門に簡単にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="07e60-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="07e60-183">自動応答と通話キューの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="07e60-184">Teams の自動応答と通話キューを計画する</span><span class="sxs-lookup"><span data-stu-id="07e60-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="07e60-185">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="07e60-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="07e60-186">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="07e60-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="07e60-187">Contoso のケース スタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="07e60-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="07e60-188">架空の多国籍企業 Contoso が、音声ソリューションの自動応答と通話キューを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="07e60-189">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="07e60-189">Cloud Voicemail</span></span>

<span data-ttu-id="07e60-190">Azure ボイスメール サービスを利用したクラウド ボイスメールは、Exchange メールボックスへのボイスメール の入金のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="07e60-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="07e60-191">サードパーティのメール システムはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07e60-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="07e60-192">クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="07e60-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="07e60-193">会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07e60-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="07e60-194">オンラインユーザーの場合、ユーザーに電話システム ライセンスが割り当てられると、クラウド ボイスメールが自動的にセットアップされ、プロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="07e60-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="07e60-195">Exchange メールボックスを持つ電話システム ユーザーの場合は、追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="07e60-196">クラウド ボイスメールとその構成の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="07e60-197">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="07e60-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="07e60-198">組織内のボイスメール ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="07e60-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="07e60-199">通話 ID</span><span class="sxs-lookup"><span data-stu-id="07e60-199">Calling identity</span></span>

<span data-ttu-id="07e60-200">既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。</span><span class="sxs-lookup"><span data-stu-id="07e60-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="07e60-201">通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="07e60-202">発信者番号の設定、または発信者番号の変更またはブロックについては、「ユーザーの発信者番号を設定する」 [を参照してください](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="07e60-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="07e60-203">公衆交換電話網接続オプション</span><span class="sxs-lookup"><span data-stu-id="07e60-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="07e60-204">電話システムは、組織に完全な PBX 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="07e60-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="07e60-205">ただし、ユーザーが組織外に通話を発信するには、電話システムを公衆交換電話網 (PSTN) に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="07e60-206">電話システムを PSTN に接続するには、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="07e60-207">[**通話プランが設定された電話システム**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="07e60-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="07e60-208">MICROSOFT を PSTN キャリアとして使用するクラウド内のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="07e60-209">[**直接ルーティングを使用してオンプレミス環境**](#phone-system-with-own-pstn-carrier-with-direct-routing) を Teams に接続することで、独自の PSTN キャリアを備える電話システム。</span><span class="sxs-lookup"><span data-stu-id="07e60-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="07e60-210">オプションの組み合わせを選ぶと、複雑な環境のソリューションを設計したり、複数ステップの移行を管理したりすることもできます (後で移行する方法の詳細)。</span><span class="sxs-lookup"><span data-stu-id="07e60-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="07e60-211">通話プラン付き電話システム</span><span class="sxs-lookup"><span data-stu-id="07e60-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="07e60-212">この記事で前述したように、通話プラン付き電話システムは、Teams ユーザー向け Microsoft のクラウド内音声ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="07e60-213">これは、Microsoft 電話システムを公衆交換電話網 (PSTN) に接続して、世界中の固定電話や携帯電話への通話を有効にする最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="07e60-214">このオプションを使用すると、Microsoft は組織にプライベート ブランチ交換 (PBX) 機能を提供し、次の図に示すように PSTN キャリアとして機能します。</span><span class="sxs-lookup"><span data-stu-id="07e60-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![図 4 は、自動応答、通話キュー、発信者番号などの電話システム、PSTN 通信事業者としての Microsoft を示しています。](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="07e60-216">「はい」と答える場合は、通話プラン付き電話システムが適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="07e60-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="07e60-217">通話プランは、お客様の地域で利用できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="07e60-218">現在の PSTN 通信事業者を保持する必要はない。</span><span class="sxs-lookup"><span data-stu-id="07e60-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="07e60-219">PSTN への Microsoft が管理するアクセスを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="07e60-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="07e60-220">このオプションを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="07e60-220">With this option:</span></span> 

- <span data-ttu-id="07e60-221">Microsoft Phone System に国内通話プランまたは国際通話プランが追加され、世界中の電話への通話が可能になります (ライセンスされるサービスのレベルによって異なる)。</span><span class="sxs-lookup"><span data-stu-id="07e60-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="07e60-222">通話プランは Microsoft 365 または Office 365 から運用されます。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="07e60-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="07e60-223">注: 必要に応じて、サードパーティ PBX、アナログ デバイス、SBC でサポートされているその他のサードパーティテレフォニー機器との相互運用性を確保するために、サポートされているセッション ボーダー コントローラー (SBC) をダイレクト ルーティングを通じて接続することができます。</span><span class="sxs-lookup"><span data-stu-id="07e60-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="07e60-224">このオプションを使用するには、Microsoft 365 または Office 365 への接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="07e60-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="07e60-225">通話プランの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="07e60-226">どの通話プランが適していますか?</span><span class="sxs-lookup"><span data-stu-id="07e60-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="07e60-227">通話プランを購入する方法</span><span class="sxs-lookup"><span data-stu-id="07e60-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="07e60-228">通話プランが利用可能な国と地域</span><span class="sxs-lookup"><span data-stu-id="07e60-228">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="07e60-229">通話プランを設定する</span><span class="sxs-lookup"><span data-stu-id="07e60-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="07e60-230">ダイレクト ルーティングを使用した独自の PSTN 通信事業者を使用した電話システム</span><span class="sxs-lookup"><span data-stu-id="07e60-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="07e60-231">このオプションは、次の図に示すように、直接ルーティングを使用して Microsoft Phone System をテレフォニー ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="07e60-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![図 5 は、ダイレクト ルーティングを使用した電話システムを示しています](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="07e60-233">次の質問に「はい」と回答した場合、直接ルーティングを使用した電話システムが適切なソリューションになります。</span><span class="sxs-lookup"><span data-stu-id="07e60-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="07e60-234">電話システムで Teams を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="07e60-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="07e60-235">現在の PSTN 通信事業者を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="07e60-236">一部の通話は通話プランを経由し、一部は通信事業者を経由して、ルーティングを混在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="07e60-237">サードパーティの PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="07e60-238">このオプションを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="07e60-238">With this option:</span></span>

- <span data-ttu-id="07e60-239">追加のオンプレミス ソフトウェアを必要とせずに、サポートされている独自の SBC を Microsoft Phone System に接続します。</span><span class="sxs-lookup"><span data-stu-id="07e60-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="07e60-240">Microsoft Phone System では、事実上すべてのテレフォニー通信事業者を使用できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="07e60-241">このオプションを構成および管理するか、または通信事業者またはパートナーが構成および管理することができます (通信事業者またはパートナーにこのオプションが提供されていないか確認してください)。</span><span class="sxs-lookup"><span data-stu-id="07e60-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="07e60-242">サードパーティ製 PBX やアナログ デバイスなどのテレフォニー機器と Microsoft Phone System 間の相互運用性 &mdash; &mdash; を構成できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="07e60-243">このオプションには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="07e60-243">This option requires the following:</span></span>

- <span data-ttu-id="07e60-244">Microsoft 365 または Office 365 への接続。</span><span class="sxs-lookup"><span data-stu-id="07e60-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="07e60-245">サポートされている SBC の展開と保守。</span><span class="sxs-lookup"><span data-stu-id="07e60-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="07e60-246">サードパーティの通信事業者との契約。</span><span class="sxs-lookup"><span data-stu-id="07e60-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="07e60-247">(サードパーティ製 PBX、アナログ デバイス、その他のテレフォニー機器への接続を、通話プランを使用して電話システムを使用しているユーザーに提供するオプションとして展開されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="07e60-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="07e60-248">ダイレクト ルーティングの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="07e60-249">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="07e60-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="07e60-250">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="07e60-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="07e60-251">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="07e60-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="07e60-252">ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="07e60-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="07e60-253">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="07e60-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="07e60-254">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="07e60-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="07e60-255">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="07e60-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="07e60-256">Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー *(ユーザー* ) 番号と、有料および無料のサービス番号として利用可能なサービス番号という 2 種類の電話番号があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="07e60-257">サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="07e60-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="07e60-258">次の条件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-258">You will need to decide:</span></span>

- <span data-ttu-id="07e60-259">Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?</span><span class="sxs-lookup"><span data-stu-id="07e60-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="07e60-260">どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?</span><span class="sxs-lookup"><span data-stu-id="07e60-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="07e60-261">どんな方法で既存の電話番号を Teams に移植しますか?</span><span class="sxs-lookup"><span data-stu-id="07e60-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="07e60-262">新しい番号の取得や退出番号の移行など、組織内の電話番号の管理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="07e60-263">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="07e60-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="07e60-264">通話プランに使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="07e60-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="07e60-265">ユーザー用の電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="07e60-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="07e60-266">Microsoft Teams に電話番号を転送する</span><span class="sxs-lookup"><span data-stu-id="07e60-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="07e60-267">ダイヤル プランと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="07e60-267">Dial plans and call routing</span></span>

<span data-ttu-id="07e60-268">ダイヤル プランは、ダイヤルされた電話番号を通話承認および通話ルーティング用の別の形式 (通常は E.164 形式) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="07e60-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="07e60-269">次を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="07e60-270">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="07e60-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="07e60-271">カスタマイズされたダイヤル プランが必要なユーザー</span><span class="sxs-lookup"><span data-stu-id="07e60-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="07e60-272">各ユーザーに割り当てるテナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="07e60-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="07e60-273">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="07e60-274">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="07e60-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="07e60-275">テナント ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="07e60-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="07e60-276">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="07e60-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="07e60-277">緊急通話</span><span class="sxs-lookup"><span data-stu-id="07e60-277">Emergency calling</span></span>

<span data-ttu-id="07e60-278">緊急通話の構成方法は、PSTN 接続オプション (Microsoft 通話プランまたは直接ルーティング) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="07e60-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="07e60-279">Microsoft 通話プランと電話システムダイレクト ルーティングの動的緊急通話は、Teams クライアントの現在の場所に基づいて緊急通話を構成およびルーティングし、セキュリティ担当者に通知する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="07e60-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="07e60-280">緊急通話の概念と用語、および動的緊急通話を構成する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="07e60-281">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="07e60-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="07e60-282">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="07e60-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="07e60-283">Contoso のケース スタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="07e60-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="07e60-284">架空の多国籍企業 Contoso 社が、組織の緊急通話を実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="07e60-285">Location-Based ルーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="07e60-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="07e60-286">国や地域によっては、公衆交換電話網 (PSTN) プロバイダーをバイパスして、長距離通話コストを削減する方法は違法です。</span><span class="sxs-lookup"><span data-stu-id="07e60-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="07e60-287">Location-Basedルーティングを使用すると、地理的な場所に基づいて、Microsoft Teams ユーザーの有料バイパスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="07e60-288">ルーティング (LBR) を計画および構成するLocation-Basedについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="07e60-289">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="07e60-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="07e60-290">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="07e60-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="07e60-291">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="07e60-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="07e60-292">Contoso のケース スタディ: Location-Based ルーティング</span><span class="sxs-lookup"><span data-stu-id="07e60-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="07e60-293">架空の多国籍企業 Contoso が組織のルーティングを実装Location-Basedについて説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="07e60-294">音声機能のネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="07e60-294">Network topology for voice features</span></span>

<span data-ttu-id="07e60-295">動的緊急通話または直接ルーティング用の Location-Based を展開する場合は、Microsoft Teams のこれらの機能で使用するネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="07e60-296">ネットワーク領域、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="07e60-297">Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語</span><span class="sxs-lookup"><span data-stu-id="07e60-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="07e60-298">Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する</span><span class="sxs-lookup"><span data-stu-id="07e60-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="07e60-299">既存の音声ソリューションを Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="07e60-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="07e60-300">Teams にアップグレードする組織の最終的な目標は、すべてのユーザーを TeamsOnly モードに移行する方法です。</span><span class="sxs-lookup"><span data-stu-id="07e60-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="07e60-301">Teams での電話システムの使用は、ユーザーが TeamsOnly モードの場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="07e60-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="07e60-302">Teams へのアップグレードに関する基本的な情報が必要な場合は、次の操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="07e60-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="07e60-303">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="07e60-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="07e60-304">アップグレードのフレームワークについて</span><span class="sxs-lookup"><span data-stu-id="07e60-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="07e60-305">Skype for Business から Teams にアップグレードする ( IT 管理者向け)</span><span class="sxs-lookup"><span data-stu-id="07e60-305">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

<span data-ttu-id="07e60-306">音声ソリューションを移行する場合、TeamsOnly モードに移行するときに、次の 4 つの呼び出しシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="07e60-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="07e60-307">[**Microsoft 通話プランを使用した Skype for Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="07e60-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="07e60-308">アップグレード後も、このユーザーは引き続き Microsoft 通話プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="07e60-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="07e60-309">**[Skype for Business Online のユーザー](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)**。オンプレミスの Skype for Business または Cloud Connector エディションを介したオンプレミスの音声機能。</span><span class="sxs-lookup"><span data-stu-id="07e60-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="07e60-310">このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。</span><span class="sxs-lookup"><span data-stu-id="07e60-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="07e60-311">**[オンプレミスの Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** でオンラインに移行し、エンタープライズ VoIP PSTN 接続を維持するユーザー。</span><span class="sxs-lookup"><span data-stu-id="07e60-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="07e60-312">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="07e60-313">**[Skype for Business オンプレミス](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** に エンタープライズ VoIP を持つユーザー。オンラインに移行し、Microsoft 通話プランを使用します。</span><span class="sxs-lookup"><span data-stu-id="07e60-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="07e60-314">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="07e60-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="07e60-315">ハイブリッド接続をセットアップする必要がある場合や、オンプレミスの音声機能を持つユーザーを直接ルーティングに移行する方法など、これらのシナリオごとに音声移行を実装する方法の詳細については、次の記事を &mdash; &mdash; 参照してください。</span><span class="sxs-lookup"><span data-stu-id="07e60-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="07e60-316">TEAMS にアップグレードする場合の PSTN に関する考慮事項 ( IT 管理者向け)</span><span class="sxs-lookup"><span data-stu-id="07e60-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="07e60-317">Contoso 音声移行のケース スタディ</span><span class="sxs-lookup"><span data-stu-id="07e60-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="07e60-318">このケース スタディでは、架空の多国籍企業 Contoso が、組織に Teams 音声ソリューションを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07e60-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="07e60-319">次の記事が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07e60-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="07e60-320">Teams アップグレード プラン</span><span class="sxs-lookup"><span data-stu-id="07e60-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="07e60-321">電話システムと PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="07e60-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="07e60-322">場所ベースのルーティングの実装</span><span class="sxs-lookup"><span data-stu-id="07e60-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="07e60-323">緊急通話</span><span class="sxs-lookup"><span data-stu-id="07e60-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="07e60-324">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="07e60-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="07e60-325">電話会議</span><span class="sxs-lookup"><span data-stu-id="07e60-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












