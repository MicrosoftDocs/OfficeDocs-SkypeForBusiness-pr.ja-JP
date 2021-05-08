---
title: 音声ソリューションの計画を立Microsoft Teams
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
description: クラウド音声機能のMicrosoft Teams、および組織に対して行うデプロイの決定について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d77e0b1ec6277bfeffd85d6657d14fe810aae96
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102573"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="7a6e4-103">音声ソリューションTeams計画する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="7a6e4-104">この記事は、組織に最適な Microsoft 音声ソリューションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="7a6e4-105">決定したら、この記事では、選択したソリューションを実装できるコンテンツのロードマップを提供します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="7a6e4-106">Skype for Business Server から Teams にアップグレードする全体的な計画の一部として Teams 音声ソリューションを計画する方法のガイダンスについては、「Teams から Skype for Business オンプレミス へのアップグレードに関する[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="7a6e4-107">最も簡単なソリューションを通話 &mdash; プラン電話システム必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="7a6e4-108">これは、次の図に示すように、プライベート ブランチ Exchange (PBX) 機能と公衆交換電話網 (PSTN) への呼び出しを提供する Microsoft のクラウド内すべてソリューションです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="7a6e4-109">このソリューションでは、Microsoft は PSTN 通信事業者です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![図 1 は、通話プラン電話システムを示しています](media/voice-solutions-simple.png)

<span data-ttu-id="7a6e4-111">次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="7a6e4-112">通話プランは、お客様のリージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="7a6e4-113">現在の PSTN 通信事業者を保持する必要はない。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="7a6e4-114">PSTN への Microsoft が管理するアクセスを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="7a6e4-115">ただし、状況は複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-115">However, your situation might be more complex.</span></span> <span data-ttu-id="7a6e4-116">たとえば、通話プランが利用できない場所にオフィスがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="7a6e4-117">または、地理的な場所ごとに異なる要件を持つ、複雑で多国籍のデプロイをサポートする組み合わせソリューションが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="7a6e4-118">Microsoft では、次のソリューションの組み合わせをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="7a6e4-119">電話システムプランの使用</span><span class="sxs-lookup"><span data-stu-id="7a6e4-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="7a6e4-120">電話システムルーティングを使用して独自の PSTN 通信業者と通信する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="7a6e4-121">通話プランと通話プランの両方の電話システム直接ルーティング電話システムを使用する組み合わせソリューション</span><span class="sxs-lookup"><span data-stu-id="7a6e4-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="7a6e4-122">何を読む必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-122">What do you need to read?</span></span>

<span data-ttu-id="7a6e4-123">**すべてのユーザーに必須です。**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-123">**Required for all.**</span></span> <span data-ttu-id="7a6e4-124">この記事のセクションの一部は、すべての組織に関連します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="7a6e4-125">たとえば、すべてのユーザーは、電話システムについて読み、公衆交換電話網 (PSTN) に接続するためのオプションを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="7a6e4-126">すべてのユーザーに必須</span><span class="sxs-lookup"><span data-stu-id="7a6e4-126">Required for all</span></span> | <span data-ttu-id="7a6e4-127">説明</span><span class="sxs-lookup"><span data-stu-id="7a6e4-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="7a6e4-128">**電話システム**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="7a6e4-129">クラウドとクラウドの通話制御とプライベート ブランチ Exchange (PBX) 機能を有効にするための Microsoft Microsoft 365テクノロジMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="7a6e4-130">**公衆交換電話網 (PSTN) 接続オプション**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="7a6e4-131">Microsoft をテレフォニー キャリアとして使用するか、直接ルーティングを使用して独自のテレフォニー Microsoft Teams接続するかの選択。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="7a6e4-132">PSTN 接続電話システムと組み合わせると、ユーザーは世界中で電話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="7a6e4-133">**要件に応じて異なる。**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-133">**Depending on your requirements.**</span></span> <span data-ttu-id="7a6e4-134">この記事のセクションの一部は、既存のデプロイと要件に応じて関連します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="7a6e4-135">たとえば、Location-Basedルーティングは、有料バイパスを許可しない地理的な場所のダイレクト ルーティングのお客様にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="7a6e4-136">次の追加構成の中から、必要な構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-136">Consider which of these additional configurations you might need:</span></span>

![図 2 は、Microsoft からの電話番号、ダイヤル プラン電話通話ルーティングなど、追加の音声コンポーネントを示しています。](media/voice-consider-additional-components.png)

| <span data-ttu-id="7a6e4-138">要件に応じて</span><span class="sxs-lookup"><span data-stu-id="7a6e4-138">Depending on your requirements</span></span> | <span data-ttu-id="7a6e4-139">説明</span><span class="sxs-lookup"><span data-stu-id="7a6e4-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="7a6e4-140">**Microsoft からの電話番号**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="7a6e4-141">Microsoft から電話番号を取得および管理する方法と、既存の番号を Microsoft に転送する方法。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="7a6e4-142">Microsoft 通話プランの電話番号を取得したり、既存の番号を転送したり、サービス番号を取得したりする必要がある場合は、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="7a6e4-143">**ダイヤル プランと通話ルーティング**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="7a6e4-144">ダイヤルされた電話番号を別の形式 (通常は E.164 形式) に変換して通話承認と通話ルーティングを行うダイヤル プランを構成および管理する方法。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="7a6e4-145">ダイヤル プランの詳細と、組織のダイヤル プランを指定する必要があるかどうかを理解する必要がある場合は、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="7a6e4-146">**緊急通話**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="7a6e4-147">PSTN 接続オプションに応じて緊急 &mdash; 通話を管理および構成する方法。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="7a6e4-148">Microsoft 通話プランまたは直接ルーティングを使用し、組織の緊急通話を管理する方法を理解する必要がある場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="7a6e4-149">**直接ルーティングのための場所ベースのルーティング**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="7a6e4-150">ローカル ルーティング (LBR) Location-Basedを使用して、地理的な場所に基づいてユーザーのMicrosoft Teamsバイパスを制限する方法。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="7a6e4-151">組織が有料バイパスを許可しない場所で直接ルーティングを使用している場合は、このセクションをお読みください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="7a6e4-152">**クラウド音声機能のネットワーク トポロジ**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="7a6e4-153">組織が直接ルーティングまたは動的緊急通話用に Location-Based ルーティング (LBR) をデプロイしている場合は、Microsoft Teams でこれらの機能で使用するネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="7a6e4-154">直接ルーティング用に LBR を実装している場合、または通話プランまたは直接ルーティングを使用して動的緊急通話を実装している場合は、このセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="7a6e4-155">**既存の音声ソリューションを移行する**</span><span class="sxs-lookup"><span data-stu-id="7a6e4-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="7a6e4-156">音声ソリューションを音声ソリューションに移行するときに考える必要があるTeams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="7a6e4-157">既存の音声ソリューションから既存の音声ソリューションに移行する場合は、このセクションをTeams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="7a6e4-158">この記事では、音声ソリューションと音声ソリューションについてMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="7a6e4-159">Skype for Business Online のソリューションは引き続き利用できます[(「Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions)テレフォニー ソリューション」で説明)、Skype for Business Online は 2021 年 7 月 31 日に廃止される予定です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="7a6e4-160">その日付が終了するとSkype for Businessオンライン サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="7a6e4-161">さらに、オンプレミス環境間の PSTN 接続は、Skype for Business Server または Cloud Connector Edition と Skype for Business Online の間では &mdash; &mdash; サポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="7a6e4-162">この記事ではTeams音声ソリューションと、必要に応じてオンプレミスのテレフォニー ネットワークを直接ルーティングを使用してTeams接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="7a6e4-163">電話システム</span><span class="sxs-lookup"><span data-stu-id="7a6e4-163">Phone System</span></span>

<span data-ttu-id="7a6e4-164">電話システムは、通話制御とプライベート ブランチ Exchange (PBX) の機能を、Microsoft 365 または Office 365 クラウドと Microsoft Teams で有効にするための Microsoft のテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="7a6e4-165">電話システムは、TeamsクライアントSkype for Business認定デバイスで動作します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="7a6e4-166">電話システムでは、既存の PBX システムを、既存の PBX システムから直接配信された一連の機能にMicrosoft 365またはOffice 365。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="7a6e4-167">組織内のユーザー間の通話は電話システムの内部で処理され、公衆交換電話網 (PSTN) に流れることは決してありません。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7a6e4-168">これは、地理的にさまざまな場所にいる組織内のユーザー間の通話にも当てはまるため、このような長距離の社内通話にかかるコストが解消されます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="7a6e4-169">この記事では、次電話システムの主な機能と、考慮する必要があるデプロイの決定について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="7a6e4-170">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="7a6e4-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="7a6e4-171">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="7a6e4-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="7a6e4-172">通話 ID</span><span class="sxs-lookup"><span data-stu-id="7a6e4-172">Calling identity</span></span>](#calling-identity)

![図 3 は、電話応答と通話クエリ、クラウド ボイスメール、通話 ID が含まれているシステムを示しています](media/phone-system-contains.png)

<span data-ttu-id="7a6e4-174">すべての機能と電話システム設定方法については、次電話システム記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-175">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="7a6e4-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="7a6e4-176">組織内の電話システムの設定</span><span class="sxs-lookup"><span data-stu-id="7a6e4-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="7a6e4-177">無料電話番号のライセンスの購入電話システム割り当て、電話番号の管理、およびコミュニケーション クレジットの設定を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="7a6e4-178">サポートされているデバイスの管理については、「Manage your devices [in Microsoft Teams](devices/device-management.md) and Teams Marketplace 」[を参照してください](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="7a6e4-179">自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="7a6e4-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="7a6e4-180">自動応答を使用すると、呼び出し元の入力に基づいて呼び出しをルーティングするメニュー オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="7a6e4-181">呼び出しキューは、呼び出し元の待機領域です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="7a6e4-182">自動応答と通話キューを組み合わせて使用すると、組織内の適切なユーザーまたは部署に発信者を簡単にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="7a6e4-183">自動応答と通話キューの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-184">自動応答Teamsキューの計画</span><span class="sxs-lookup"><span data-stu-id="7a6e4-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="7a6e4-185">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="7a6e4-186">呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="7a6e4-187">Contoso のケース スタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="7a6e4-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="7a6e4-188">架空の多国籍企業 Contoso が、音声ソリューションの自動応答と通話キューを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="7a6e4-189">クラウド ボイスメール</span><span class="sxs-lookup"><span data-stu-id="7a6e4-189">Cloud Voicemail</span></span>

<span data-ttu-id="7a6e4-190">クラウド ボイスメール Azure ボイスメール サービスを利用する場合、メールボックスへのボイスメールの入金Exchangeサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="7a6e4-191">サード パーティのメール システムはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="7a6e4-192">クラウド ボイスメールでは、組織内のすべてのユーザーに対してボイスメールの文字起こしが既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="7a6e4-193">会社のニーズに応じて、特定のユーザーまたは組織全体の全ユーザーに対してボイスメールの文字起こしを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="7a6e4-194">オンライン ユーザーの場合、ユーザークラウド ボイスメールライセンスが割り当てられた後、ユーザーに対して自動的に設定およびプロビジョニング電話システムされます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="7a6e4-195">メールボックス電話システムユーザー Exchange場合は、追加の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="7a6e4-196">構成とその構成のクラウド ボイスメール、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-197">クラウド ボイスメールのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7a6e4-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="7a6e4-198">組織内のボイスメール ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="7a6e4-199">通話 ID</span><span class="sxs-lookup"><span data-stu-id="7a6e4-199">Calling identity</span></span>

<span data-ttu-id="7a6e4-200">既定で、すべての発信通話は、割り当てられた電話番号を通話 ID (発信者 ID) として使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="7a6e4-201">通話の受信者は、発信者をすばやく特定して、通話を承諾または拒否するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="7a6e4-202">発信者番号の構成または発信者番号の変更またはブロックについては、「ユーザーの発信者番号を設定する」 [を参照してください](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="7a6e4-203">公衆交換電話網接続オプション</span><span class="sxs-lookup"><span data-stu-id="7a6e4-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="7a6e4-204">電話システムは、組織に完全な PBX 機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="7a6e4-205">ただし、ユーザーが組織外で通話を発信するには、PSTN (Public Switched Telephone Network) 電話システムに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7a6e4-206">PSTN 電話システム接続するには、次のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="7a6e4-207">[**電話システム プラン を使用して行います**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="7a6e4-208">MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="7a6e4-209">[**電話システム直接ルーティングを**](#phone-system-with-own-pstn-carrier-with-direct-routing)使用してオンプレミス環境をオンプレミス環境に接続することで、独自の PSTN 通信業者Teams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="7a6e4-210">オプションの組み合わせを選択することもできます。これにより、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりすることもできます (移行の詳細については後で説明します)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="7a6e4-211">電話システムプランの使用</span><span class="sxs-lookup"><span data-stu-id="7a6e4-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="7a6e4-212">この記事で前述したように、電話システムプランを使用する方法は、ユーザーが利用できる Microsoft のクラウド内音声Teamsです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="7a6e4-213">これは、世界中の固定電話Microsoft 電話携帯電話への通話を有効にするための、Microsoft 電話 System を公衆交換電話網 (PSTN) に接続する最も簡単なオプションです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="7a6e4-214">このオプションを使用すると、Microsoft は組織Exchange (PBX) 機能を提供し、次の図に示すように PSTN 通信事業者として機能します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![図 4 は、電話システム、通話キュー、発信者番号など、PSTN 通信事業者としての Microsoft の機能を示しています。](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="7a6e4-216">次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="7a6e4-217">通話プランは、お客様のリージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="7a6e4-218">現在の PSTN 通信事業者を保持する必要はない。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="7a6e4-219">PSTN への Microsoft が管理するアクセスを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="7a6e4-220">このオプションでは、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-220">With this option:</span></span> 

- <span data-ttu-id="7a6e4-221">(ライセンスMicrosoft 電話に応じて) 世界中の電話への通話を可能にする国内通話プランまたは国際通話プランが追加された新しいシステムを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="7a6e4-222">通話プランは、オンプレミスのデプロイやメンテナンスを行う必要はないので、Microsoft 365 &mdash; またはOffice 365。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="7a6e4-223">注: 必要に応じて、サード パーティの PBX、アナログ デバイス、SBC でサポートされているその他のサードパーティのテレフォニー機器との相互運用性を確保するために、サポートされているセッション ボーダー コントローラー (SBC) を直接ルーティング経由で接続できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="7a6e4-224">このオプションを使用するには、接続または接続に中断Microsoft 365接続Office 365。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="7a6e4-225">通話プランの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-226">どの通話プランが適していますか?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="7a6e4-227">通話プランを購入する方法</span><span class="sxs-lookup"><span data-stu-id="7a6e4-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="7a6e4-228">通話プランが利用可能な国と地域</span><span class="sxs-lookup"><span data-stu-id="7a6e4-228">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="7a6e4-229">通話プランを設定する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="7a6e4-230">電話システムルーティングを使用して PSTN 通信業者を使用する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="7a6e4-231">このオプションは、Microsoft 電話に示すように、ダイレクト ルーティングを使用して、システムをテレフォニー ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![図 5 は、直接ルーティング電話システムを示しています](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="7a6e4-233">次の質問に対して 「はい」と回答した場合は、電話システム ルーティングを使用する方法が適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="7a6e4-234">このコマンドを使用してTeamsを電話システム。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="7a6e4-235">現在の PSTN 通信事業者を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="7a6e4-236">通話プランを経由する通話と、運送業者を介した通話を組み合わせ、ルーティングを混在したい場合。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="7a6e4-237">サードパーティの PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="7a6e4-238">このオプションでは、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-238">With this option:</span></span>

- <span data-ttu-id="7a6e4-239">追加のオンプレミス ソフトウェアを必要とせずに、Microsoft 電話 SBC をシステムに接続します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="7a6e4-240">Microsoft 電話 System では、事実上任意のテレフォニー キャリアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="7a6e4-241">このオプションの構成と管理を選択するか、通信事業者またはパートナーが構成および管理できます (運送業者またはパートナーにこのオプションが提供されていないか確認してください)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="7a6e4-242">サード パーティ製 PBX やアナログ デバイスなどのテレフォニー機器と、その他のシステムとの間に相互 &mdash; &mdash; 運用性Microsoft 電話できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="7a6e4-243">このオプションには、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-243">This option requires the following:</span></span>

- <span data-ttu-id="7a6e4-244">接続または接続Microsoft 365接続Office 365。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="7a6e4-245">サポートされている SBC のデプロイと保守。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="7a6e4-246">サード パーティの運送業者との契約。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="7a6e4-247">(サード パーティ製 PBX、アナログ デバイス、その他のテレフォニー機器への接続を提供するオプションとして、通話プランを利用しているユーザーに電話システムしない限り)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="7a6e4-248">ダイレクト ルーティングの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-249">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="7a6e4-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="7a6e4-250">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="7a6e4-251">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="7a6e4-252">ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="7a6e4-253">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="7a6e4-254">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="7a6e4-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="7a6e4-255">Microsoft からの電話番号</span><span class="sxs-lookup"><span data-stu-id="7a6e4-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="7a6e4-256">Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー *(ユーザー* ) 番号と、有料サービス番号と無料サービス番号として利用できるサービス番号の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="7a6e4-257">サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="7a6e4-258">次の条件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-258">You will need to decide:</span></span>

- <span data-ttu-id="7a6e4-259">Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="7a6e4-260">どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="7a6e4-261">どんな方法で既存の電話番号を Teams に移植しますか?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="7a6e4-262">新しい番号の取得や終了番号の転送など、組織内の電話番号の管理の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-263">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="7a6e4-264">通話プランに使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="7a6e4-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="7a6e4-265">ユーザー用の電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="7a6e4-266">電話番号を別の電話番号にMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a6e4-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="7a6e4-267">ダイヤル プランと通話ルーティング</span><span class="sxs-lookup"><span data-stu-id="7a6e4-267">Dial plans and call routing</span></span>

<span data-ttu-id="7a6e4-268">ダイヤル プランは、ダイヤルされた電話番号を通話承認と通話ルーティングの代替形式 (通常は E.164 形式) に変換する正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="7a6e4-269">次の条件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="7a6e4-270">組織はダイヤル プランのカスタマイズを必要としているか?</span><span class="sxs-lookup"><span data-stu-id="7a6e4-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="7a6e4-271">カスタマイズされたダイヤル プランが必要なユーザー</span><span class="sxs-lookup"><span data-stu-id="7a6e4-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="7a6e4-272">どのテナント ダイヤル プランを各ユーザーに割り当てる必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="7a6e4-273">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="7a6e4-274">ダイヤル プランについて</span><span class="sxs-lookup"><span data-stu-id="7a6e4-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="7a6e4-275">テナント ダイヤル プランの計画</span><span class="sxs-lookup"><span data-stu-id="7a6e4-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="7a6e4-276">ダイヤル プランを作成および管理する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="7a6e4-277">緊急通話</span><span class="sxs-lookup"><span data-stu-id="7a6e4-277">Emergency calling</span></span>

<span data-ttu-id="7a6e4-278">緊急通話の構成方法は、PSTN 接続オプション (Microsoft 通話プランまたは直接ルーティング) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="7a6e4-279">Microsoft 通話プランと 電話システム ダイレクト ルーティングの動的緊急通話は、緊急通話を構成してルーティングし、Teams クライアントの現在の場所に基づいてセキュリティ担当者に通知する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="7a6e4-280">緊急通話の概念と用語、および動的緊急通話を構成する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-281">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="7a6e4-282">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="7a6e4-283">Contoso のケース スタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="7a6e4-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="7a6e4-284">架空の多国籍企業 Contoso が組織の緊急呼び出しを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="7a6e4-285">Location-Based ルーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="7a6e4-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="7a6e4-286">国や地域によっては、公衆交換電話網 (PSTN) プロバイダーをバイパスして、遠距離通話コストを削減する方法は違法です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="7a6e4-287">Location-Based ルーティングを使用すると、地理的な場所に基づいて、Microsoft Teamsユーザーの有料バイパスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="7a6e4-288">ルーティング (LBR) を計画および構成する方法のLocation-Based、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-289">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="7a6e4-290">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="7a6e4-291">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="7a6e4-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="7a6e4-292">Contoso のケース スタディ: Location-Based ルーティング</span><span class="sxs-lookup"><span data-stu-id="7a6e4-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="7a6e4-293">架空の多国籍企業 Contoso が、組織に対して Location-Based ルーティングを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="7a6e4-294">音声機能のネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="7a6e4-294">Network topology for voice features</span></span>

<span data-ttu-id="7a6e4-295">動的緊急通話または直接ルーティング用の Location-Based ルーティングをデプロイする場合は、これらの機能で使用するネットワーク設定を構成する必要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="7a6e4-296">ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-297">Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語</span><span class="sxs-lookup"><span data-stu-id="7a6e4-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="7a6e4-298">クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a6e4-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="7a6e4-299">既存の音声ソリューションを既存の音声ソリューションに移行Teams</span><span class="sxs-lookup"><span data-stu-id="7a6e4-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="7a6e4-300">アプリケーションにアップグレードする組織Teams最終的な目標は、すべてのユーザーを TeamsOnly モードに移行する方法です。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="7a6e4-301">ユーザー電話システムでのTeamsは、ユーザーが TeamsOnly モードの場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="7a6e4-302">アプリケーションへのアップグレードに関する基本的な情報が必要なTeams開始します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="7a6e4-303">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="7a6e4-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="7a6e4-304">アップグレードのフレームワークについて</span><span class="sxs-lookup"><span data-stu-id="7a6e4-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="7a6e4-305">IT 管理者向けアップグレード戦略</span><span class="sxs-lookup"><span data-stu-id="7a6e4-305">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="7a6e4-306">音声ソリューションを移行する場合、TeamsOnly モードに移行するときに、次の 4 つの呼び出しシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="7a6e4-307">[**Microsoft 通話プラン をSkype for Business Online のユーザー**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="7a6e4-308">アップグレード後も、このユーザーは引き続き Microsoft 通話プランを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="7a6e4-309">Skype for Business Online のユーザー。オンプレミスまたは Cloud Connector Edition を介してSkype for Business音声 **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)機能を使用します**。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="7a6e4-310">このユーザーの Teams へのアップグレードは、その TeamsOnly ユーザーが確実に PSTN 機能を持てるようにするため、ユーザーのダイレクト ルーティングへの移行に合わせた調整が必要になります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="7a6e4-311">**[を使用Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** オンプレミスのユーザーエンタープライズ VoIP、オンラインに移行し、オンプレミスの PSTN 接続を維持します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="7a6e4-312">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行をそのユーザーのダイレクト ルーティングへの移行に合わせて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="7a6e4-313">**[を使用Skype for Business](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** オンプレミスのユーザーエンタープライズ VoIP、オンラインに移行し、Microsoft 通話プラン を使用します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="7a6e4-314">このユーザーを Teams に移行するには、そのユーザーのオンプレミスの Skype for Business アカウントをクラウドに移行し、移行を A) Microsoft 通話プランへのユーザーの電話番号のポートに合わせて調整するか、B) 利用可能な地域から新しいサブスクライバー番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="7a6e4-315">ハイブリッド接続を設定する必要がある状況や、オンプレミスの音声機能を持つユーザーを直接ルーティングに移行する方法に関する情報など、これらのシナリオごとに音声移行を実装する方法の詳細については、次の記事 &mdash; &mdash; を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="7a6e4-316">IT 管理者向け Teamsアップグレード時の PSTN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="7a6e4-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="7a6e4-317">Contoso 音声移行のケース スタディ</span><span class="sxs-lookup"><span data-stu-id="7a6e4-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="7a6e4-318">このケース スタディでは、架空の多国籍企業 Contoso が、組織に対してTeamsソリューションを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="7a6e4-319">次の記事が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a6e4-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="7a6e4-320">Teamsアップグレード プラン</span><span class="sxs-lookup"><span data-stu-id="7a6e4-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="7a6e4-321">電話システム PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="7a6e4-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="7a6e4-322">場所ベースのルーティングの実装</span><span class="sxs-lookup"><span data-stu-id="7a6e4-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="7a6e4-323">緊急通話</span><span class="sxs-lookup"><span data-stu-id="7a6e4-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="7a6e4-324">自動応答と呼び出しキュー</span><span class="sxs-lookup"><span data-stu-id="7a6e4-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="7a6e4-325">電話会議</span><span class="sxs-lookup"><span data-stu-id="7a6e4-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)