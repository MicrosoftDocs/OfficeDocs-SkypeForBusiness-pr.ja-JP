---
title: 応答グループ キュー の作成 新規または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。
ms.openlocfilehash: ee99ac8cb4f3ea9c2f0e1804914eaf30c909a2b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118806"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="59bf4-103">応答グループのキュー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="59bf4-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="59bf4-104">応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="59bf4-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="59bf4-105">UI Reference</span></span>

<span data-ttu-id="59bf4-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="59bf4-107">**名前** 各キューには名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="59bf4-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="59bf4-108">キューのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="59bf4-109">**説明** このフィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="59bf4-109">**Description** This field is optional.</span></span> <span data-ttu-id="59bf4-110">キューに関する追加の詳細を提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="59bf4-111">**グループ** キューに割り当てるエージェント グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="59bf4-112">[選択 **] を** クリックして、エージェント グループをリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="59bf4-113">[ **削除] を** クリックして、選択したエージェント グループを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="59bf4-114">上下の矢印は、選択したエージェント グループをリスト内で上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="59bf4-115">エージェント グループの順序は、Skype for Business Server が使用可能なエージェントを検索する順序に影響します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="59bf4-116">つまり、リスト内の最初のグループが最初に検索され、使用可能なエージェントが検索され、次に 2 番目のグループが検索されます。</span><span class="sxs-lookup"><span data-stu-id="59bf4-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="59bf4-117">**キューのタイム アウトを有効にする** このチェック ボックスをオンにすると、エージェントが通話に応答するまで発信者が待機するまでの最大期間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="59bf4-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="59bf4-118">このオプションを選択する場合は、次の項目も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf4-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="59bf4-119">**タイム アウト期間 (秒)** エージェントが通話に応答するまで発信者が待機できる最大待機時間を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="59bf4-120">**通話アクション** 通話がアウトした場合に発生するアクションを選択します。選択項目は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59bf4-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="59bf4-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="59bf4-121">**Disconnect**</span></span>

  - <span data-ttu-id="59bf4-122">**ボイス メールへの転送** このオプションを選択した場合は **、[SIP アドレス**] に SIP 形式のボイス メール アドレスを入力します <username> (たとえば @ <domainname> 、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="59bf4-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="59bf4-123">**電話番号に転送する** このオプションを選択した場合は **、SIP アドレスに** SIP の形式で電話番号を入力します <number> (たとえば @ <domainname> 、sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="59bf4-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="59bf4-124">**SIP アドレスへの転送** 通話を別のユーザーに転送するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="59bf4-125">**[SIP アドレス]** に、SIP 形式でユーザーの URI を入力します <username> @ <domainname> 。</span><span class="sxs-lookup"><span data-stu-id="59bf4-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="59bf4-126">**別のキューに転送する** このオプションを選択した場合は、通話が時間切れ時に呼び出しを受信するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="59bf4-127">**キュー オーバーフローを有効にする** キューが保持できる呼び出しの最大数を指定するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="59bf4-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="59bf4-128">このオプションを選択する場合は、次の項目も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59bf4-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="59bf4-129">**呼び出しの最大数** キューが保持できる呼び出しの最大数を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="59bf4-130">**通話を転送する** キュー オーバーフローのしきい値が満たされた場合にアクションを実行する呼び出しを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="59bf4-131">**通話アクション** キュー オーバーフローのしきい値が満たされた場合に発生するアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="59bf4-132">次のどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="59bf4-132">Your choices are:</span></span>

  - <span data-ttu-id="59bf4-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="59bf4-133">**Disconnect**</span></span>

  - <span data-ttu-id="59bf4-134">**ボイス メールへの転送** このオプションを選択した場合は **、[SIP アドレス**] に SIP 形式のボイス メール アドレスを入力します <username> (たとえば @ <domainname> 、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="59bf4-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="59bf4-135">**電話番号に転送する** このオプションを選択した場合は **、SIP アドレスに** SIP の形式で電話番号を入力します <number> (たとえば @ <domainname> 、sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="59bf4-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="59bf4-136">**SIP アドレスへの転送** 通話を別のユーザーに転送するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="59bf4-137">**[SIP アドレス]** に、SIP 形式でユーザーの URI を入力します <username> @ <domainname> 。</span><span class="sxs-lookup"><span data-stu-id="59bf4-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="59bf4-138">**別のキューに転送する** このオプションを選択した場合は、キュー オーバーフローしきい値が満たされた場合に呼び出しを受信するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="59bf4-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="59bf4-139">応答グループの機能の詳細については、「計画」のドキュメントの「Plan for the [Response Group application in Skype for Business Server」](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59bf4-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="59bf4-140">キューの使用の詳細については、「操作」のドキュメントの「[Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59bf4-140">For details about working with queues, see [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in the Operations documentation.</span></span>