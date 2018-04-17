---
title: Cloud Voice の展開
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/10/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4828cb7c27c53387e0efae800167cef1b53dd4b6
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="cloud-voice-deployment"></a><span data-ttu-id="a3ce1-103">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="a3ce1-103">Cloud voice deployment</span></span>

<span data-ttu-id="a3ce1-104">マイクロソフト チーム、チームワークと、Office 365 での通信用のハブは、オーディオ会議や電話システム チーム会議を拡張し、経験を含めるを呼び出すことによって新たなビジネス要件を満たすために、計画を呼び出す機能を備えた外部の関係者は、公衆交換電話網 (PSTN) 経由で接続されています。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the public switched telephone network (PSTN).</span></span>
 
<span data-ttu-id="a3ce1-105">このページの内容は、Teams の Cloud Voice の追加機能がリリースされるたびに更新されます。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>



## <a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="a3ce1-106">Microsoft Teams での電話会議</span><span class="sxs-lookup"><span data-stu-id="a3ce1-106">Audio Conferencing in Microsoft Teams</span></span>


<span data-ttu-id="a3ce1-107">Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="a3ce1-108">Office 365 の[電話会議](https://go.microsoft.com/fwlink/?linkid=858992)で利用できる機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>


## <a name="phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="a3ce1-109">マイクロソフトのチームでの通話プランと電話システム</span><span class="sxs-lookup"><span data-stu-id="a3ce1-109">Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="a3ce1-110">電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-110">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="a3ce1-111">この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-111">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="a3ce1-112">Office 365 の通話プランは、Teams と Skype for Business Online を介して提供される電話システム機能用のアドオン サービスです。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-112">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="a3ce1-113">通話プランは、基本の電話でお客様のビジネスの人の番号し、し、PSTN 上で、組織外の電話を受信できるように提供します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-113">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the PSTN.</span></span>

<span data-ttu-id="a3ce1-114">詳しくは、「[Office 365 での電話システムで利用できる機能](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c)」と「[Office 365 の通話プランについて](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-114">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>


## <a name="practical-guidance-for-audio-conferencing-and-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="a3ce1-115">オーディオ会議およびマイクロソフトのチームの計画を呼び出すと、電話システムに関する実用的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="a3ce1-115">Practical guidance for Audio Conferencing and Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="a3ce1-116">Office 365 fasttrack というお客様の旅のフレームワークを使用してこの実用的なガイドの構成し、フェーズ 3 つ&mdash;ビジョン化トラック、オンボードとドライブの値です。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-116">This practical guidance is organized by using the Office 365 FastTrack customer journey framework and its three phases&mdash;Envision, Onboard, and Drive Value.</span></span> <span data-ttu-id="a3ce1-117">計画、配布、および実装の計画を呼び出すと、正常な電話会議や電話システムの運用を支援するためのものが。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-117">It's intended to help you plan, deliver, and operate a successful Audio Conferencing or Phone System with Calling Plans implementation.</span></span>

|<span data-ttu-id="a3ce1-118">構想</span><span class="sxs-lookup"><span data-stu-id="a3ce1-118">Envision</span></span>  |<span data-ttu-id="a3ce1-119">参加</span><span class="sxs-lookup"><span data-stu-id="a3ce1-119">Onboard</span></span>  |<span data-ttu-id="a3ce1-120">価値の創出</span><span class="sxs-lookup"><span data-stu-id="a3ce1-120">Drive Value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a3ce1-121">自分の成功を定義します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-121">Define my success</span></span> <br> <span data-ttu-id="a3ce1-122">[サービスの決定を行う</span><span class="sxs-lookup"><span data-stu-id="a3ce1-122">Make my service decisions</span></span> <br> <span data-ttu-id="a3ce1-123">自分の環境を評価します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-123">Evaluate my environment</span></span> <br> <span data-ttu-id="a3ce1-124">[サービスの管理を計画します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-124">Plan my service management</span></span> <br> <span data-ttu-id="a3ce1-125">自分のユーザー エクスペリエンスを計画します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-125">Plan my users' experience</span></span> <br> <span data-ttu-id="a3ce1-126">成功計画を文書化します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-126">Document my success plan</span></span>    | <span data-ttu-id="a3ce1-127">サービスを準備します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-127">Prepare my service</span></span> <br> <span data-ttu-id="a3ce1-128">自分のユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-128">Prepare my users</span></span> <br> <span data-ttu-id="a3ce1-129">サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-129">Deploy my service</span></span>  <br> <br> <br> <br>     | <span data-ttu-id="a3ce1-130">自分のサービスを実施します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-130">Operate my service</span></span> <br> <span data-ttu-id="a3ce1-131">サービスを強化します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-131">Enhance my service</span></span> <br> <br> <br> <br> <br>      |

<span data-ttu-id="a3ce1-132">内容は、順序付けられた方法で表示され、開始から終了まで、エンド ・ ツー ・ エンド展開の旅を見てするよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-132">The content is presented in an ordered fashion, and is designed to take you through an end-to-end deployment journey from start to finish.</span></span> <span data-ttu-id="a3ce1-133">既に積極的に導入している場合もお勧め適切なコンテンツ領域を参照することです。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-133">If you're already actively deploying, we still encourage you to reference the applicable content areas.</span></span>



> [!TIP]
> <span data-ttu-id="a3ce1-134">この実用的なガイドで各アクティビティおよびキーの説明を出力する例を提供しています。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-134">In this practical guidance, we're providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="a3ce1-135">このドキュメントで説明する例がヒントの吹き出しの中に囲まれているし、再利用できるテンプレートとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-135">The examples throughout this document are enclosed inside Tip callouts, and they serve as a template that you can reuse.</span></span> <span data-ttu-id="a3ce1-136">「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="a3ce1-136">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>