---
title: PSTN 接続オプション
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: 通話 (PSTN Teams) オプションと、組織に対して行う決定の詳細について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354519"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="dbf21-103">PSTN 接続オプション</span><span class="sxs-lookup"><span data-stu-id="dbf21-103">PSTN connectivity options</span></span>

<span data-ttu-id="dbf21-104">Microsoft は、お客様の組織Exchangeプライベート ブランチ サービス (PBX) 機能を提供電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="dbf21-105">ただし、ユーザーが組織外で通話を発信するには、PSTN (Public Switched Telephone Network) 電話システムに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="dbf21-106">この記事では、PSTN 接続オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="dbf21-107">Microsoft 音声ソリューションの詳細については、「音声ソリューションを計画する」を電話システム詳細については、「音声ソリューションを計画するTeams[参照してください](cloud-voice-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="dbf21-108">PSTN 電話システム接続するには、次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="dbf21-109">[**通話プラン**](#phone-system-with-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="dbf21-110">MICROSOFT を PSTN 通信事業者として使用する、クラウド内のすべてソリューション。</span><span class="sxs-lookup"><span data-stu-id="dbf21-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="dbf21-111">[**ダイレクト ルーティング**](#phone-system-with-direct-routing): セッション ボーダー コントローラー (SBC) を接続して、独自の PSTN 通信業者を使用電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="dbf21-112">[**オペレーター Connect、**](#phone-system-with-operator-connect)現在パブリック プレビューでのみ **使用できます。**</span><span class="sxs-lookup"><span data-stu-id="dbf21-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="dbf21-113">オペレーター サービスConnect、既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合は、PSTN 通話とセッション ボーダー コントローラー (SBC) を管理できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="dbf21-114">オプションの組み合わせを選択して、複雑な環境向けソリューションを設計したり、複数ステップの移行を管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="dbf21-115">選択したオプションは、一部の機能の構成方法電話システム注意してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="dbf21-116">詳細については、この記事の [後半の「構成に関](#configuration-considerations) する考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="dbf21-117">電話システムプランの使用</span><span class="sxs-lookup"><span data-stu-id="dbf21-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="dbf21-118">電話システムプランを使用する方法は、ユーザーをサポートする Microsoft のクラウド内音声Teamsです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="dbf21-119">これは、PSTN に接続する最も電話システムオプションです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="dbf21-120">このオプションを使用すると、次の図に示すように、Microsoft は PSTN 通信事業者として機能します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![図 1 は、通話プラン電話システムを示しています](media/voice-solutions-simple.png)

<span data-ttu-id="dbf21-122">次に対して 「はい」と答える場合は、電話システムプランを使用する方法が適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="dbf21-123">通話プランは、お客様のリージョンで利用できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="dbf21-124">現在の PSTN 通信事業者を保持する必要はない。</span><span class="sxs-lookup"><span data-stu-id="dbf21-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="dbf21-125">PSTN への Microsoft が管理するアクセスを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="dbf21-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="dbf21-126">このオプションでは、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-126">With this option:</span></span> 

- <span data-ttu-id="dbf21-127">(ライセンスMicrosoft 電話に応じて) 世界中の電話への通話を可能にする国内通話プランまたは国際通話プランが追加された新しいシステムを利用できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="dbf21-128">通話プランは、オンプレミスのデプロイまたはメンテナンスを必要と &mdash; Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dbf21-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="dbf21-129">注: 必要に応じて、サード パーティの PBX、アナログ デバイス、SBC でサポートされているその他のサードパーティのテレフォニー機器との相互運用性を確保するために、サポートされているセッション ボーダー コントローラー (SBC) を直接ルーティング経由で接続できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="dbf21-130">このオプションを使用するには、アプリケーションへの接続が中断Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dbf21-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="dbf21-131">通話プランの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="dbf21-132">どの通話プランが適していますか?</span><span class="sxs-lookup"><span data-stu-id="dbf21-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="dbf21-133">通話プランを購入する方法</span><span class="sxs-lookup"><span data-stu-id="dbf21-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="dbf21-134">通話プランが利用可能な国と地域</span><span class="sxs-lookup"><span data-stu-id="dbf21-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="dbf21-135">通話プランを設定する</span><span class="sxs-lookup"><span data-stu-id="dbf21-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="dbf21-136">電話システムルーティングの使用</span><span class="sxs-lookup"><span data-stu-id="dbf21-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="dbf21-137">このオプションは、電話システムに示すように、ダイレクト ルーティングを使用して、ネットワークをテレフォニー ネットワークに接続します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![図 5 は、直接ルーティング電話システムを示しています](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="dbf21-139">次の質問に対して 「はい」と回答した場合は、電話システム ルーティングを使用する方法が適切なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="dbf21-140">このコマンドを使用してTeamsを電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="dbf21-141">現在の PSTN 通信事業者を保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="dbf21-142">通話プランを経由する通話と、運送業者を介した通話を組み合わせ、ルーティングを混在したい場合。</span><span class="sxs-lookup"><span data-stu-id="dbf21-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="dbf21-143">サードパーティの PBX や、オーバーヘッド ページ、アナログ デバイスなどの機器と相互運用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="dbf21-144">このオプションでは、次のオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-144">With this option:</span></span>

- <span data-ttu-id="dbf21-145">サポートされている独自のセッション ボーダー コントローラー (SBC) を、追加の電話システムソフトウェアを必要とせずに、ネットワーク に接続します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="dbf21-146">事実上、任意のテレフォニー キャリアを使用して、電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="dbf21-147">このオプションの構成と管理を選択するか、通信事業者またはパートナーが構成および管理できます (運送業者またはパートナーにこのオプションが提供されていないか確認してください)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="dbf21-148">サードパーティの PBX やアナログ デバイスなどのテレフォニー機器とデバイス間の相互運用性を &mdash; &mdash; 電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="dbf21-149">このオプションには、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbf21-149">This option requires the following:</span></span>

- <span data-ttu-id="dbf21-150">ネットワークへの接続が中断Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dbf21-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="dbf21-151">サポートされている SBC のデプロイと保守。</span><span class="sxs-lookup"><span data-stu-id="dbf21-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="dbf21-152">サード パーティの運送業者との契約。</span><span class="sxs-lookup"><span data-stu-id="dbf21-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="dbf21-153">(サード パーティ製 PBX、アナログ デバイス、その他のテレフォニー機器への接続を提供するオプションとして、通話プランを利用しているユーザーに電話システムしない限り)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="dbf21-154">ダイレクト ルーティングの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="dbf21-155">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="dbf21-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="dbf21-156">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="dbf21-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="dbf21-157">ダイレクト ルーティングで使用する音声ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="dbf21-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="dbf21-158">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="dbf21-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="dbf21-159">ダイレクト ルーティングに対応する認定済みセッション ボーダー コントローラーのリスト</span><span class="sxs-lookup"><span data-stu-id="dbf21-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="dbf21-160">電話システム 演算子を使用Connect</span><span class="sxs-lookup"><span data-stu-id="dbf21-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="dbf21-161">オペレーター Connect では、現在パブリック プレビュー中です。既存の通信事業者が Microsoft Operator Connect プログラムに参加している場合は、PSTN 通話を Teams に持ち込むサービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="dbf21-162">通信事業者が PSTN 通話サービスとセッション ボーダー コントローラー (SBC) を管理し、ハードウェアの購入と管理を節約できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="dbf21-163">オペレーター Connectは、次の場合に組織に適切なソリューションになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="dbf21-164">Microsoft 通話プランは、地理的な場所では利用できません。</span><span class="sxs-lookup"><span data-stu-id="dbf21-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="dbf21-165">お好みの運送業者は、Microsoft Operator Connectです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="dbf21-166">通話を有効にする新しい通信事業者を探Teams。</span><span class="sxs-lookup"><span data-stu-id="dbf21-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="dbf21-167">Operator Connect の利点と要件、およびこのプログラムに参加している通信事業者の一覧については、「プラン オペレーターサービス」を[Connect。](operator-connect-plan.md)</span><span class="sxs-lookup"><span data-stu-id="dbf21-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="dbf21-168">オペレーター アカウントを構成する方法の詳細についてはConnectを構成する[」をConnect。](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="dbf21-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="dbf21-169">構成に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="dbf21-169">Configuration considerations</span></span>

<span data-ttu-id="dbf21-170">選択電話システム PSTN 接続オプションに関係なく、ほとんどの機能は同じです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="dbf21-171">たとえば、未応答の通話と転送設定、通話転送、保留のカスタム音楽、コール パーク、共有回線、音声アプリはすべて使用できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="dbf21-172">すべての機能の完全な電話システムについては、次[の](here-s-what-you-get-with-phone-system.md)ページを参照電話システム。</span><span class="sxs-lookup"><span data-stu-id="dbf21-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="dbf21-173">ただし、特定の機能の構成方法に影響を与える機能には、いくつかの電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="dbf21-174">たとえば、ダイレクト ルーティングでは、通話ルーティングを構成するための追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbf21-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="dbf21-175">別の例として、ダイレクト ルーティングは場所ベースのルーティング (LBR) を提供します。そのため、許可されていない特定の地理的な場所で有料バイパスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="dbf21-176">電話番号の管理</span><span class="sxs-lookup"><span data-stu-id="dbf21-176">Phone number management</span></span>

<span data-ttu-id="dbf21-177">Microsoft には、組織内のユーザーに割り当て可能なサブスクライバー (ユーザー) 番号と、有料サービス番号と無料サービス番号として利用できるサービス番号の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="dbf21-178">サービス番号は、サブスクライバー番号よりも高い同時通話容量を持ち、電話会議、自動応答、通話キューなどのサービスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="dbf21-179">次の条件を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-179">You will need to decide:</span></span>

- <span data-ttu-id="dbf21-180">Microsoft からの新しい電話番号が必要なのはどのユーザー ロケーションですか?</span><span class="sxs-lookup"><span data-stu-id="dbf21-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="dbf21-181">どの種類の電話番号が必要ですか (サブスクライバーまたはサービス)?</span><span class="sxs-lookup"><span data-stu-id="dbf21-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="dbf21-182">どんな方法で既存の電話番号を Teams に移植しますか?</span><span class="sxs-lookup"><span data-stu-id="dbf21-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="dbf21-183">電話番号を取得および管理する方法は、PSTN 接続オプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="dbf21-184">通話プランの電話番号の管理については、「組織の電話番号を管理 [する」を参照してください](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="dbf21-185">ダイレクト ルーティングの電話番号の管理については、「電話番号を構成し、エンタープライズ音声とボイスメールを有効 [にする」を参照してください](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="dbf21-186">オペレーター アカウントを使用して電話番号を管理する方法についてはConnect演算子を使用して電話番号を[設定する」をConnect。](operator-connect-configure.md#set-up-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="dbf21-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="dbf21-187">通話ルーティングとダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="dbf21-187">Call routing and dial plans</span></span>

<span data-ttu-id="dbf21-188">通話ルーティングの構成方法は、PSTN 接続オプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="dbf21-189">通話プランの場合、通話ルーティングの大部分は Microsoft 通話プラン インフラストラクチャによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="dbf21-190">ユーザー ダイヤル プランは、通話承認と通話ルーティングの番号変換の目的で構成します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="dbf21-191">詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="dbf21-192">ダイレクト ルーティングの場合は、音声ルートを指定し、ユーザーに音声ルーティング ポリシーを割り当て、通話ルーティングを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="dbf21-193">番号変換のダイヤル プランをトランク レベルで構成して、セッション ボーダー コントローラー (SBC) との相互運用性を確保できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="dbf21-194">詳細については、「ダイレクト ルーティングの音声ルーティング[の構成」、音声ルーティング](direct-routing-voice-routing.md)[ポリシー](manage-voice-routing-policies.md)の管理、電話番号の翻訳に関[するページを参照してください](direct-routing-translate-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="dbf21-195">オペレーター サービスConnect、ほとんどの通話ルーティングは通信事業者によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="dbf21-196">ユーザー ダイヤル プランは、通話承認と通話ルーティングの番号変換の目的で構成します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="dbf21-197">詳細については、「ダイヤル プラン [とは」を参照してください](what-are-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="dbf21-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="dbf21-198">Location-Based ルーティングの詳細</span><span class="sxs-lookup"><span data-stu-id="dbf21-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="dbf21-199">一部の国や地域では、PSTN 通信事業者をバイパスして、遠距離通話コストを削減する方法は違法です。</span><span class="sxs-lookup"><span data-stu-id="dbf21-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="dbf21-200">Location-Based ルーティング (LBR) を使用すると、地理的な場所に基づいて、ユーザーのTeamsバイパスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="dbf21-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="dbf21-201">LBR を計画および構成する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="dbf21-202">ダイレクト ルーティングの場所に基づくルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="dbf21-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="dbf21-203">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="dbf21-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="dbf21-204">ダイレクト ルーティングの場所に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="dbf21-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="dbf21-205">Contoso のケース スタディ: Location-Based ルーティング</span><span class="sxs-lookup"><span data-stu-id="dbf21-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="dbf21-206">架空の多国籍企業 Contoso が、組織に対して Location-Based ルーティングを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="dbf21-207">緊急通話</span><span class="sxs-lookup"><span data-stu-id="dbf21-207">Emergency calling</span></span>

<span data-ttu-id="dbf21-208">緊急通話の構成方法は、PSTN 接続オプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="dbf21-209">通話プランの場合、各ユーザーは自動的に緊急通話を有効にし、割り当てられた電話番号に関連付けられている登録済みの緊急対応の住所を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="dbf21-210">動的緊急通話 (クライアントの場所に基Teams) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbf21-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="dbf21-211">直接ルーティングの場合は、Teams 緊急通話ルーティング ポリシー (TeamsEmergencyCallRoutingPolicy) を使用して緊急電話番号と関連するルーティング先を定義することで、ユーザーの緊急通話ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf21-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="dbf21-212">登録済みの緊急対応の場所は、ダイレクト ルーティング ユーザーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dbf21-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="dbf21-213">動的緊急通話の場合は、緊急通話をルーティングし、場合によってはパートナーの接続用に追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbf21-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="dbf21-214">オペレーター Connectでは、各ユーザーは緊急通話を自動的に有効にし、割り当てられた電話番号に関連付けられた登録済みの緊急対応の住所を持っている必要がありますが、設定できるのは運送業者パートナーのみです。</span><span class="sxs-lookup"><span data-stu-id="dbf21-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="dbf21-215">動的緊急通話 (クライアントの場所に基Teams) がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dbf21-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="dbf21-216">緊急通話の概念と用語、および緊急通話と動的緊急通話を構成する方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="dbf21-217">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="dbf21-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="dbf21-218">動的な緊急通話を計画して構成する</span><span class="sxs-lookup"><span data-stu-id="dbf21-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="dbf21-219">緊急通話ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="dbf21-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="dbf21-220">ダイレクト ルーティングの緊急通話ルーティング ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="dbf21-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="dbf21-221">Contoso のケース スタディ: 緊急通話</span><span class="sxs-lookup"><span data-stu-id="dbf21-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="dbf21-222">架空の多国籍企業 Contoso が組織の緊急呼び出しを実装した方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbf21-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="dbf21-223">音声機能のネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="dbf21-223">Network topology for voice features</span></span>

<span data-ttu-id="dbf21-224">動的緊急通話または直接ルーティング用の Location-Based ルーティングをデプロイする場合は、これらの機能で使用するネットワーク設定を構成する必要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="dbf21-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="dbf21-225">ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスのネットワーク設定を構成する方法については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbf21-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="dbf21-226">Microsoft Teams のクラウド音声機能のネットワーク設定 - 概念と用語</span><span class="sxs-lookup"><span data-stu-id="dbf21-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="dbf21-227">クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbf21-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



