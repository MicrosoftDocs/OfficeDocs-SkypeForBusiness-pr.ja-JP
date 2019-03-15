---
title: 自動応答および呼び出しキューの通話に Teams から直接応答する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 電話システムの自動応答、通話キューとチーム内のこれらの呼び出しを得ることができる方法を説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 900fe698654a760c9863583da0b3cd161625844d
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569440"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="e0b70-103">自動応答および呼び出しキューの通話に Teams から直接応答する</span><span class="sxs-lookup"><span data-stu-id="e0b70-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="e0b70-104">チームのユーザーが受け取ることができ、ビジネス オンラインの Skype からの応答の呼び出しが自動的に応答し、キューをそのチームのクライアントから直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="e0b70-105">チーム ユーザーの場合は、自動アテンダントの機能が、一般的に使用できる、および呼び出しキュー機能は、プレビューでは。</span><span class="sxs-lookup"><span data-stu-id="e0b70-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="e0b70-106">自動応答とキューを呼び出すか。</span><span class="sxs-lookup"><span data-stu-id="e0b70-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="e0b70-107">電話システムの自動応答は、一連の音声プロンプトまたは組織に電話するときに、人間のオペレーターではなく相手に対して再生するオーディオ ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="e0b70-108">自動応答により、発信者はメニュー システムを介して、通話、電話機のキーパッド (DTMF) を使用したユーザーの特定、音声認識を使用した音声入力を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e0b70-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="e0b70-109">電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。</span><span class="sxs-lookup"><span data-stu-id="e0b70-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="e0b70-110">組織の 1 つまたは複数の呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="e0b70-111">自動アテンダントまたは呼び出しキューの呼び出しを処理します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="e0b70-112">ユーザーは通話に応答する前に、自動アテンダントまたは呼び出しキューからの着信呼び出しを区別することになります。</span><span class="sxs-lookup"><span data-stu-id="e0b70-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="e0b70-113">名前や呼び出し元の数、および呼び出しのたびにした呼び出し元がアクセスしようと、呼び出し元に対応するため、内容をユーザーに与えるについての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0b70-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="e0b70-114">ユーザーに、自動アテンダントまたは呼び出しキューからの着信呼び出しを表示する方法を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![着信通知](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="e0b70-116">ユーザーが、他の呼び出し & #x 2014; のような呼び出しを処理できる、自動アテンダントまたは呼び出しキューの呼び出しが応答すると、1 回追加することや会議の他のユーザーまたは別の関係者への呼び出しを転送します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="e0b70-117">また、自動アテンダントの呼び出しは、ユーザーの構成に基づいて転送されます。</span><span class="sxs-lookup"><span data-stu-id="e0b70-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="e0b70-118">ユーザーの構成に基づくキューの呼び出しの呼び出しは転送されません。</span><span class="sxs-lookup"><span data-stu-id="e0b70-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="e0b70-119">これは、呼び出し元は、エージェントが通話に応答するまでキューに残ることを確認するのには、呼び出し元が予期せずに転送されていないとします。</span><span class="sxs-lookup"><span data-stu-id="e0b70-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="e0b70-120">サポートされているクライアント</span><span class="sxs-lookup"><span data-stu-id="e0b70-120">Supported clients</span></span>

<span data-ttu-id="e0b70-121">自動アテンダントおよび呼び出しキューの呼び出しのサポートは、次のクライアントで利用可能なです。</span><span class="sxs-lookup"><span data-stu-id="e0b70-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="e0b70-122">Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="e0b70-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="e0b70-123">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="e0b70-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="e0b70-124">マイクロソフト チームの iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="e0b70-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="e0b70-125">マイクロソフト チーム Android アプリ</span><span class="sxs-lookup"><span data-stu-id="e0b70-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="e0b70-126">マイクロソフト チームの自動応答、および呼び出しキューのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0b70-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="e0b70-127">自動応答を受信し、マイクロソフトのチームにキューの呼び出しを呼び出しには、相互運用性ポリシーを構成し、ポリシーをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0b70-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="e0b70-128">[移行とビジネス用の Skype とチームを使用する組織の相互運用性](migration-interop-guidance-for-teams-with-skype.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0b70-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="e0b70-129">自動応答がない場合や呼び出しキューが構成され、これを行うには、[電話システムの自動応答を設定](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)し、[電話システムの呼び出しキューを作成する](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0b70-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0b70-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0b70-130">Related topics</span></span>

-   [<span data-ttu-id="e0b70-131">Office 365 の電話システムとは</span><span class="sxs-lookup"><span data-stu-id="e0b70-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="e0b70-132">電話システムの呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="e0b70-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="e0b70-133">電話システムの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="e0b70-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="e0b70-134">電話システムの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e0b70-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

