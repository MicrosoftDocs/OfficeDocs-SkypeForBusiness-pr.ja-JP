---
title: Cloud Voice の展開
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/13/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45528d71dc04b96d77b454d5db402648779c1ac9
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
#<a name="cloud-voice-deployment"></a><span data-ttu-id="063a5-103">Cloud Voice の展開</span><span class="sxs-lookup"><span data-stu-id="063a5-103">Cloud voice deployment</span></span>

<span data-ttu-id="063a5-104">Office 365 でのチームワークおよび通信のためのハブである Microsoft Teams は、公衆交換電話網 (PSTN) を経由して接続される外部パーティを含めるように Teams の会議および通話のエクスペリエンスを拡大することによって追加のビジネス要件にも適合する、電話会議と通話プランが設定された電話システムの機能を提供するようになりました。</span><span class="sxs-lookup"><span data-stu-id="063a5-104">Microsoft Teams, the hub for teamwork and communications in Office 365, now provides Audio Conferencing and Phone System with Calling Plans capabilities to meet additional business requirements by extending the Teams meeting and calling experience to include external parties connected via the Public Switched Telephone Network (PSTN).</span></span>
 
<span data-ttu-id="063a5-105">このページの内容は、Teams の Cloud Voice の追加機能がリリースされるたびに更新されます。</span><span class="sxs-lookup"><span data-stu-id="063a5-105">We'll update this page as additional cloud voice features for Teams are released over time.</span></span>


##<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="063a5-106">Microsoft Teams での電話会議についての実践的なガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="063a5-106">Practical guidance for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="063a5-107">Office 365 の電話会議では、参加者はどの電話端末からでも Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="063a5-107">Audio Conferencing in Office 365 allows participants to join your Teams meetings from any telephone.</span></span>

<span data-ttu-id="063a5-108">Office 365 の[電話会議](https://go.microsoft.com/fwlink/?linkid=858992)で利用できる機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="063a5-108">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

<span data-ttu-id="063a5-109">この実践的なガイダンスでは、Office 365 FastTrack のお客様が正常なビジネス成果に向けて電話会議の実装を正しく計画、提供、運用できるよう、導入フレームワークと 3 つの段階 (構想、参加、価値の創出) について説明します。</span><span class="sxs-lookup"><span data-stu-id="063a5-109">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases, Envision, Onboard, and Drive Value, to help you plan, deliver, and operate an Audio Conferencing implementation towards succesful business outcomes.</span></span>

> [!TIP]
> <span data-ttu-id="063a5-110">この実践的なガイダンスにはアクティビティや重要なディスカッションの例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="063a5-110">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="063a5-111">このドキュメントでは、これらの例は「ヒント」内に記載されており、テンプレートとして再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="063a5-111">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="063a5-112">「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="063a5-112">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

##<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a><span data-ttu-id="063a5-113">Microsoft Teams の通話プランが設定された電話システムの実践的なガイダンス</span><span class="sxs-lookup"><span data-stu-id="063a5-113">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>

<span data-ttu-id="063a5-114">電話システムは通話のルーティング、ポリシー、ユーザー プロビジョニングを管理するための Office 365 の機能です。</span><span class="sxs-lookup"><span data-stu-id="063a5-114">Phone System is an Office 365 feature that provides the ability to manage call routing, policies, and user provisioning.</span></span> <span data-ttu-id="063a5-115">この機能には、通話管理システム、通話のルーティング、通話コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="063a5-115">This includes phone calling management system, call routing, and call control.</span></span>

<span data-ttu-id="063a5-116">Office 365 の通話プランは、Teams と Skype for Business Online を介して提供される電話システム機能用のアドオン サービスです。</span><span class="sxs-lookup"><span data-stu-id="063a5-116">Office 365 Calling Plans is an add-on service for the Phone System feature, delivered through Teams and Skype for Business Online.</span></span> <span data-ttu-id="063a5-117">通話プランを利用することで、ビジネス ユーザーは代表電話番号を入手でき、公衆交換電話網 (PSTN) を介して組織外での通話の受信と発信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="063a5-117">Calling Plans provide the people in your business with a primary phone number and lets them make and receive phone calls outside of your organization over the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="063a5-118">詳しくは、「[Office 365 での電話システムで利用できる機能](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c)」と「[Office 365 の通話プランについて](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="063a5-118">To learn more, read [Here's what you get with Phone System in Office 365](https://support.office.com/article/Here-s-what-you-get-with-Phone-System-in-Office-365-bc9756d1-8a2f-42c4-98f6-afb17c29231c) and [What are Calling Plans in Office 365?](https://support.office.com/article/What-are-Calling-Plans-in-Office-365-3dc773b9-95e0-4448-b2f1-887c54022429)</span></span>

<span data-ttu-id="063a5-119">この実践的なガイダンスでは、Office 365 FastTrack のお客様が通話プランを実装した電話システムを正しく計画、提供、運用できるよう、導入フレームワークと 3 つの段階 (構想、参加、価値の創出) について説明します。</span><span class="sxs-lookup"><span data-stu-id="063a5-119">This practical guidance takes you through the Office 365 FastTrack customer journey framework and its three phases - Envision, Onboard, and Drive Value - to help you plan, deliver, and operate a successful Phone System with Calling Plans implementation.</span></span>

> [!TIP]
> <span data-ttu-id="063a5-120">この実践的なガイダンスにはアクティビティや重要なディスカッションの例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="063a5-120">In this practical guidance, we are providing example outputs for each activity and key discussion.</span></span> <span data-ttu-id="063a5-121">このドキュメントでは、これらの例は「ヒント」内に記載されており、テンプレートとして再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="063a5-121">The examples throughout this document are enclosed inside TIP callouts and they serve as a template that you can reuse.</span></span> <span data-ttu-id="063a5-122">「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="063a5-122">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>