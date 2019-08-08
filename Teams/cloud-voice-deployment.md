---
title: Cloud Voice の展開
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: Rowille
description: Microsoft Teams でクラウド音声機能を展開するための実用的なガイダンス。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 476d65ee927fedf285cf66377c58c9f09698b046
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236767"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="561be-103">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="561be-103">Cloud voice deployment</span></span>

<span data-ttu-id="561be-104">Microsoft Teams、Office 365 でのチームワークとコミュニケーションのハブでは、電話会議、通話プランを使った電話システム、およびチーム会議を拡張してビジネス要件を満たすための電話システムのダイレクトルーティング機能を利用できるようになりました。公衆交換電話網 (PSTN) 経由で接続されている外部関係者を対象とした通話エクスペリエンス。</span><span class="sxs-lookup"><span data-stu-id="561be-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing, Phone System with Calling Plans, and Phone System Direct Routing capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>


> [!Tip] 
> <span data-ttu-id="561be-105">電話システムの概要については、次のセッションをご覧ください。 [Microsoft Teams での電話システムの概要](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="561be-105">Watch the following session for an introduction to Phone Systems: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>
 
<span data-ttu-id="561be-106">このページは、Teams 用のクラウド音声の追加機能が時間の経過と共にリリースされるように更新されます。</span><span class="sxs-lookup"><span data-stu-id="561be-106">We’ll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="561be-107">Microsoft Teams での電話会議</span><span class="sxs-lookup"><span data-stu-id="561be-107">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="561be-108">Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="561be-108">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="561be-109">Office 365 の[電話会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)で利用できる機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="561be-109">Here’s what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="561be-110">Microsoft Teams の通話プラン ("通話プラン") を搭載した電話システム</span><span class="sxs-lookup"><span data-stu-id="561be-110">Phone System with Calling Plans (“Calling Plans”) in Microsoft Teams</span></span>

<span data-ttu-id="561be-111">電話システムは、通話ルーティング、ポリシー、ユーザープロビジョニングを管理する機能を提供する Office 365 の機能です。</span><span class="sxs-lookup"><span data-stu-id="561be-111">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="561be-112">これには、電話の通話管理システム、通話ルーティング、通話制御が含まれます。</span><span class="sxs-lookup"><span data-stu-id="561be-112">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="561be-113">通話プランは、電話システム機能のアドオンサービスであり、Teams と Skype for Business Online を通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="561be-113">Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="561be-114">通話プランを使用するには、Skype for Business Online のユーザーが Microsoft Teams で作業する必要があります。</span><span class="sxs-lookup"><span data-stu-id="561be-114">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="561be-115">通話プランを使用すると、ビジネスの相手に主要な電話番号が提供され、組織外で PSTN 経由で電話をかけたり受けたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="561be-115">Calling Plans provide the people in your business with a primary phone number, and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="561be-116">詳細については、「 [Office 365 の電話システムで利用できる機能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)」および「[電話システムと通話プラン](calling-plan-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561be-116">To learn more, read [Here’s what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [Phone System and Calling Plans](calling-plan-landing-page.md)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="561be-117">電話システム直結ルーティング (「ダイレクトルーティング」)</span><span class="sxs-lookup"><span data-stu-id="561be-117">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="561be-118">直接ルーティングは、電話システムの機能と連携することで、組織内のユーザーに PSTN 経由での電話の発信と受信を許可します。 pstn 接続は、サードパーティのサービスプロバイダーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="561be-118">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="561be-119">詳細については、「[プランダイレクトルーティング](direct-routing-plan.md)と[ダイレクトルーティングの構成](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561be-119">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="561be-120">Microsoft Teams での電話会議、通話プラン、直接ルーティングに関する実用的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="561be-120">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="561be-121">この実用的なガイダンスは、Office 365 FastTrack 顧客の旅フレームワークと、3つ&mdash;のフェーズのビジョン、オンボード、およびドライブ値を使って開催されています。</span><span class="sxs-lookup"><span data-stu-id="561be-121">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="561be-122">これは、電話会議、通話プラン、またはダイレクトルーティングの実装の計画、納品、操作を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="561be-122">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="561be-123">構想</span><span class="sxs-lookup"><span data-stu-id="561be-123">Envision</span></span>  |<span data-ttu-id="561be-124">参加</span><span class="sxs-lookup"><span data-stu-id="561be-124">Onboard</span></span>  |<span data-ttu-id="561be-125">価値の創出</span><span class="sxs-lookup"><span data-stu-id="561be-125">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="561be-126">成功を定義する</span><span class="sxs-lookup"><span data-stu-id="561be-126">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="561be-127">サービスの決定を行う</span><span class="sxs-lookup"><span data-stu-id="561be-127">Make my service decisions for</span></span> <br><span data-ttu-id="561be-128">&nbsp;&nbsp;[電話会議](2-envision-make-my-service-decisions-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="561be-128">&nbsp;&nbsp;[Audio Conferencing](2-envision-make-my-service-decisions-audio-conferencing.md),</span></span><br><span data-ttu-id="561be-129">&nbsp;&nbsp;[通話プラン](2-envision-make-my-service-decisions-phone-system.md)または[ダイレクトルーティング](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="561be-129">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="561be-130">環境を評価する</span><span class="sxs-lookup"><span data-stu-id="561be-130">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="561be-131">サービス管理を計画する</span><span class="sxs-lookup"><span data-stu-id="561be-131">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="561be-132">ユーザーエクスペリエンスを計画する</span><span class="sxs-lookup"><span data-stu-id="561be-132">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="561be-133">成功計画を文書化する</span><span class="sxs-lookup"><span data-stu-id="561be-133">Document my success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="561be-134">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="561be-134">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="561be-135">ユーザーを準備する</span><span class="sxs-lookup"><span data-stu-id="561be-135">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="561be-136">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="561be-136">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="561be-137">サービスを運用する</span><span class="sxs-lookup"><span data-stu-id="561be-137">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="561be-138">サービスを強化する</span><span class="sxs-lookup"><span data-stu-id="561be-138">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="561be-139">コンテンツは順序に従って提示されます。また、開始から終了までの間に、エンドツーエンドの展開が利用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="561be-139">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="561be-140">既に展開している場合は、適用可能なコンテンツ領域を参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="561be-140">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="561be-141">この実際的なガイダンスでは、各アクティビティとキーディスカッションの出力例を提供します。</span><span class="sxs-lookup"><span data-stu-id="561be-141">In this practical guidance, we provide example outputs for each activity and key discussion.</span></span> <span data-ttu-id="561be-142">このドキュメント全体の例は、ヒントの吹き出し内に含まれており、テンプレートとして提供されているため、再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="561be-142">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="561be-143">計画プロセスの一部として実行する必要がある情報については、"TBA" (追加) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="561be-143">You’ll see “TBA” (to be added) for information that you need to complete as part of your planning process.</span></span>
