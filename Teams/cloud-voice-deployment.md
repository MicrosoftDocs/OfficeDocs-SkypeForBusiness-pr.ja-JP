---
title: Cloud Voice の展開
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: MyAdvisor
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9bf4d920ba8ce8e25d663a9bab1769f80d693a77
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892367"
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="d9ee0-103">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="d9ee0-103">Cloud voice deployment</span></span>

<span data-ttu-id="d9ee0-104">Office 365 でのチームワークおよび通信のためのハブである Microsoft Teams は、公衆交換電話網 (PSTN) を経由して接続される外部パーティを含めるように Teams の会議および通話のエクスペリエンスを拡大することによって追加のビジネス要件にも適合する、電話会議と通話プランが設定された電話システムの機能を提供するようになりました。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="d9ee0-105">このページの内容は、Teams の Cloud Voice の追加機能がリリースされるたびに更新されます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="d9ee0-106">Microsoft Teams での電話会議</span><span class="sxs-lookup"><span data-stu-id="d9ee0-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="d9ee0-107">Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="d9ee0-108">Office 365 の[電話会議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365)で利用できる機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-108">Here's what you get with [Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-in-office-365) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-calling-plans-in-microsoft-teams"></a><span data-ttu-id="d9ee0-109">Microsoft Teams の通話プラン (「通話プラン」) が設定された電話システム</span><span class="sxs-lookup"><span data-stu-id="d9ee0-109">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="d9ee0-110">電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="d9ee0-111">この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="d9ee0-112">通話プランは、Teams と Skype for Business Online を介して提供される電話システム機能用のアドオン サービスです。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="d9ee0-113">通話プランでは、対象ユーザーは Microsoft Teams で機能するために Skype for Business Online に所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-113">Calling Plans requires that the user in question be homed in Skype for Business Online to work in Microsoft Teams.</span></span> <span data-ttu-id="d9ee0-114">通話プランを利用することで、ビジネス ユーザーは代表電話番号を入手でき、公衆交換電話網 (PSTN) を介して組織外での通話の受信と発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-114">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="d9ee0-115">詳細については、「[Office 365 での電話システムで利用できる機能](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system)」と「[Office 365 の通話プランについて](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-115">To learn more, read [Here's what you get with Phone System in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) and [What are Calling Plans in Office 365?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)</span></span>


## <a name="phone-system-direct-routing-direct-routing"></a><span data-ttu-id="d9ee0-116">電話システムのダイレクト ルーティング (「ダイレクト ルーティング」)</span><span class="sxs-lookup"><span data-stu-id="d9ee0-116">Phone System Direct Routing (“Direct Routing”)</span></span>

<span data-ttu-id="d9ee0-117">ダイレクト ルーティングは、電話システムの機能と連動して、組織内のユーザーが PSTN を介して組織外での通話を発信および受信できる機能を提供します。この場合、PSTN 接続はサード パーティのサービス プロバイダーを介して提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-117">Direct Routing works with the Phone System feature to give people in your organization the ability make and receive phone calls outside of the organization over the PSTN, where PSTN connectivity is provided via third-party service providers.</span></span>

<span data-ttu-id="d9ee0-118">詳細については、「[ダイレクト ルーティングを計画する](direct-routing-plan.md)」と「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-118">To learn more, read [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="practical-guidance-for-audio-conferencing-calling-plans-and-direct-routing-in-microsoft-teams"></a><span data-ttu-id="d9ee0-119">Microsoft Teams での電話会議、通話プラン、ダイレクト ルーティングの実践的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="d9ee0-119">Practical guidance for Audio Conferencing, Calling Plans, and Direct Routing in Microsoft Teams</span></span>

<span data-ttu-id="d9ee0-120">この実践的なガイダンスは、Office 365 FastTrack カスタマーの移行フレームワークと、&mdash;構想、参加、価値の創出という 3 つのフェーズを使用して編成されています。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-120">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="d9ee0-121">電話会議、通話プラン、またはダイレクト ルーティングの実装を正常に行うための計画、提供、運営を支援することを意図した内容になっています。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-121">It’s intended to help you plan, deliver, and operate a successful Audio Conferencing, Calling Plans, or Direct Routing implementation.</span></span>

> [!div class="mx-tableFixed"]
> |<span data-ttu-id="d9ee0-122">構想</span><span class="sxs-lookup"><span data-stu-id="d9ee0-122">Envision</span></span>  |<span data-ttu-id="d9ee0-123">参加</span><span class="sxs-lookup"><span data-stu-id="d9ee0-123">Onboard</span></span>  |<span data-ttu-id="d9ee0-124">価値の創出</span><span class="sxs-lookup"><span data-stu-id="d9ee0-124">Drive Value</span></span>  |
> |---------|---------|---------|
> |[<span data-ttu-id="d9ee0-125">成功を定義する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-125">Define my success</span></span>](1-envision-define-my-success-cloud-voice.md) <br> <span data-ttu-id="d9ee0-126">サービスの決定を行う対象</span><span class="sxs-lookup"><span data-stu-id="d9ee0-126">Make my service decisions for</span></span> <br><span data-ttu-id="d9ee0-127">&nbsp;&nbsp;[電話会議](2-envision-make-my-service-decisions-audio-conferencing.md)、</span><span class="sxs-lookup"><span data-stu-id="d9ee0-127">Audio Conferencing</span></span><br><span data-ttu-id="d9ee0-128">&nbsp;&nbsp;[通話プラン](2-envision-make-my-service-decisions-phone-system.md)、または[ダイレクト ルーティング](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="d9ee0-128">&nbsp;&nbsp;[Calling Plans](2-envision-make-my-service-decisions-phone-system.md), or [Direct Routing](2-envision-make-my-service-decisions-direct-routing.md)</span></span> <br> [<span data-ttu-id="d9ee0-129">環境を評価する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-129">Evaluate my environment</span></span>](3-envision-evaluate-my-environment.md) <br> [<span data-ttu-id="d9ee0-130">サービス管理を計画する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-130">Plan my service management</span></span>](4-envision-plan-my-service-management.md) <br> [<span data-ttu-id="d9ee0-131">ユーザーのエクスぺリエンスを計画する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-131">Plan my users’ experience</span></span>](5-envision-plan-my-users-experience.md) <br> [<span data-ttu-id="d9ee0-132">成功計画を文書化する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-132">Document success plan</span></span>](6-envision-document-my-success-plan.md)    | [<span data-ttu-id="d9ee0-133">サービスを準備する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-133">Prepare my service</span></span>](1-onboard-prepare-my-service.md) <br> [<span data-ttu-id="d9ee0-134">ユーザーを準備する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-134">Prepare my users</span></span>](2-onboard-prepare-my-users.md) <br> [<span data-ttu-id="d9ee0-135">サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-135">Deploy my service</span></span>](3-onboard-deploy-my-service.md)  <br> <br> <br> <br>     | [<span data-ttu-id="d9ee0-136">サービスを運用する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-136">Operate my service</span></span>](1-drive-value-operate-my-service.md) <br> [<span data-ttu-id="d9ee0-137">サービスを強化する</span><span class="sxs-lookup"><span data-stu-id="d9ee0-137">Enhance my service</span></span>](2-drive-value-enhance-my-service.md) <br> <br> <br> <br> <br>      |

<span data-ttu-id="d9ee0-138">コンテンツは整然とした形式で提示され、エンドツーエンドの展開の手順を最初から最後まで説明するように作成されています。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-138">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="d9ee0-139">既に積極的に展開を行っている場合でも、該当するコンテンツの領域を参照することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-139">If you’re already actively deploying, we still encourage you to reference the applicable content areas.</span></span>


> [!TIP]
> <span data-ttu-id="d9ee0-140">この実践的なガイダンスには、各アクティビティおよび重要なディスカッションの例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-140">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="d9ee0-141">このドキュメントでは、これらの例はヒントの吹き出し内に含まれていいて、テンプレートとして再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-141">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="d9ee0-142">「TBA」(今後追加予定) と記載されている場所には、計画プロセスの一部として完了する必要がある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="d9ee0-142">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>
