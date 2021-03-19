---
title: 自動応答と通話キューの呼び出しに応答する
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: クラウドの自動応答および通話キューについて説明し、Teams 内でこれらの呼び出しに応答する方法について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874667"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="e1ccc-103">自動応答および通話キューの通話に Teams から直接応答する</span><span class="sxs-lookup"><span data-stu-id="e1ccc-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="e1ccc-104">Teams ユーザーは、クラウドの自動応答および通話キューを Teams クライアントから直接受信および応答できます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="e1ccc-105">自動応答および通話キューとは</span><span class="sxs-lookup"><span data-stu-id="e1ccc-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="e1ccc-106">クラウドの自動応答は、組織に対して通話を行うときに、人間のオペレーターの代わりに再生される一連の音声メッセージまたは音声ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="e1ccc-107">自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="e1ccc-p102">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-p102">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="e1ccc-110">自動応答または通話キューの通話を処理する</span><span class="sxs-lookup"><span data-stu-id="e1ccc-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="e1ccc-111">ユーザーは、通話に応答する前に、着信通話と自動応答または通話キューを区別できます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="e1ccc-112">各通話には、発信者の名前や番号に加えて、発信者が連絡しようとしている人に関する情報が含まれ、ユーザーに発信者に対応するためのより良いコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="e1ccc-113">次の図は、自動応答または通話キューからの着信通話がユーザーにどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![着信通知のスクリーンショット](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="e1ccc-115">自動応答または通話キューの通話に応答すると、ユーザーは他の通話と同様に処理できます&#x2014。別のユーザーを追加したり、会議を行ったり、別の相手に転送したりできます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="e1ccc-116">また、自動応答通話はユーザーの構成に基づいて転送されます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="e1ccc-117">通話キューの呼び出しは、ユーザーの構成に基づいて転送されません。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="e1ccc-118">これは、エージェントが通話に応答でき、発信者に予期しない転送がされない限り、発信者がキューに留まるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

> <span data-ttu-id="e1ccc-119">エージェントは、通話キュー通話の着信やボイスメールの欠落については通知されません。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-119">Agents are not notified of any missed calls or voicemails for call queue calls.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="e1ccc-120">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="e1ccc-120">Supported clients</span></span>

<span data-ttu-id="e1ccc-121">自動応答および通話キューの通話は、次のクライアントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="e1ccc-122">Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="e1ccc-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="e1ccc-123">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="e1ccc-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="e1ccc-124">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="e1ccc-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="e1ccc-125">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="e1ccc-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="e1ccc-126">Microsoft Teams の自動応答と通話キューのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="e1ccc-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="e1ccc-127">Microsoft Teams で自動応答および通話キューの通話を受信するには、相互運用性ポリシーおよびアップグレード ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="e1ccc-128">「[Teams を Skype for Business と一緒に使用する組織の移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="e1ccc-129">自動応答や通話キューが設定されておらず、設定したい場合は、「[クラウドの自動応答をセットアップする](create-a-phone-system-auto-attendant.md)」および「[クラウドの通話キューを作成する](create-a-phone-system-call-queue.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="e1ccc-130">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e1ccc-130">Known Issues</span></span>

<span data-ttu-id="e1ccc-131">通話キュー エージェントがモバイル デバイスで通話を受信すると、デバイスがロックされている場合に通話が保留される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-131">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="e1ccc-132">ユーザーは最初にデバイスのロックを解除してから、通話に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1ccc-132">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e1ccc-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e1ccc-133">Related topics</span></span>

-    [<span data-ttu-id="e1ccc-134">Microsoft 365 または Office 365 の電話システムとは</span><span class="sxs-lookup"><span data-stu-id="e1ccc-134">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="e1ccc-135">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="e1ccc-135">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="e1ccc-136">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="e1ccc-136">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="e1ccc-137">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e1ccc-137">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

