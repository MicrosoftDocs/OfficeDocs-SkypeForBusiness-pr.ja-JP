---
title: 自動応答および通話キューの通話に Teams から直接応答する
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: クラウドの自動応答および通話キューについて説明し、Teams 内でこれらの呼び出しに応答する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a508aeb6c5e1359c9b3432834f2f0f3d141aea2d
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516797"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="2134e-103">自動応答および通話キューの通話に Teams から直接応答する</span><span class="sxs-lookup"><span data-stu-id="2134e-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="2134e-104">Teams ユーザーは、クラウドの自動応答および通話キューを Teams クライアントから直接受信および応答できます。</span><span class="sxs-lookup"><span data-stu-id="2134e-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="2134e-105">Teams ユーザーの場合、一般的に自動応答機能が利用可能になり、通話キュー機能はプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="2134e-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="2134e-106">自動応答および通話キューとは</span><span class="sxs-lookup"><span data-stu-id="2134e-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="2134e-107">クラウドの自動応答は、組織に対して通話を行うときに、人間のオペレーターの代わりに再生される一連の音声メッセージまたは音声ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="2134e-107">An auto attendant is a series of voice prompts or and audio file that callers hear instead of a human operator when they call into an organization.</span></span> <span data-ttu-id="2134e-108">自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2134e-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="2134e-p103">クラウド通話キューには、誰かが組織の電話番号に電話をかけた際に流れる挨拶メッセージ、通話を自動的に保留する機能、および保留中に電話をかけてきた方に音楽を流し、その間に通話への対応が可能な次の電話エージェントを探す機能が含まれています。1 つまたは複数の通話キューを組織のために作成できます。</span><span class="sxs-lookup"><span data-stu-id="2134e-p103">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="2134e-111">自動応答または通話キューの通話を処理する</span><span class="sxs-lookup"><span data-stu-id="2134e-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="2134e-112">ユーザーは、通話に応答する前に、着信通話と自動応答または通話キューを区別できます。</span><span class="sxs-lookup"><span data-stu-id="2134e-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="2134e-113">各通話には、発信者の名前や番号に加えて、発信者が連絡しようとしている人に関する情報が含まれ、ユーザーに発信者に対応するためのより良いコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="2134e-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="2134e-114">次の図は、自動応答または通話キューからの着信通話がユーザーにどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="2134e-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![着信通知のスクリーンショット](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="2134e-116">自動応答または通話キューの通話に応答すると、ユーザーは他の通話と同様に処理できます&#x2014。別のユーザーを追加したり、会議を行ったり、別の相手に転送したりできます。</span><span class="sxs-lookup"><span data-stu-id="2134e-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="2134e-117">また、自動応答呼び出しは、ユーザーの構成に基づいて転送されます。</span><span class="sxs-lookup"><span data-stu-id="2134e-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="2134e-118">通話キューの通話は、ユーザーの構成に基づいて転送されません。</span><span class="sxs-lookup"><span data-stu-id="2134e-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="2134e-119">これは、エージェントが呼び出しに応答でき、発信者が予期せず転送されない限り、発信者がキューに残るようにするためです。</span><span class="sxs-lookup"><span data-stu-id="2134e-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="2134e-120">サポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="2134e-120">Supported clients and calls</span></span>

<span data-ttu-id="2134e-121">自動応答および通話キューの通話は、次のクライアントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2134e-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="2134e-122">Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="2134e-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="2134e-123">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="2134e-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="2134e-124">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="2134e-124">Microsoft Teams app</span></span>
-   <span data-ttu-id="2134e-125">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="2134e-125">Microsoft Teams app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="2134e-126">Microsoft Teams の自動応答と通話キューのサポートを構成する</span><span class="sxs-lookup"><span data-stu-id="2134e-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="2134e-127">Microsoft Teams で自動応答および通話キューの通話を受信するには、相互運用性ポリシーおよびアップグレード ポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2134e-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="2134e-128">「[Teams を Skype for Business と一緒に使用する組織の移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)」を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2134e-128">[Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md)</span></span> <span data-ttu-id="2134e-129">自動応答や通話キューが設定されておらず、設定したい場合は、「[クラウドの自動応答をセットアップする](create-a-phone-system-auto-attendant.md)」および「[クラウドの通話キューを作成する](create-a-phone-system-call-queue.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2134e-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2134e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2134e-130">Related topics</span></span>

-   [<span data-ttu-id="2134e-131">Office 365 の電話システムとは</span><span class="sxs-lookup"><span data-stu-id="2134e-131">What is Phone System in Office 365?</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="2134e-132">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="2134e-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-   [<span data-ttu-id="2134e-133">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="2134e-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="2134e-134">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="2134e-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

