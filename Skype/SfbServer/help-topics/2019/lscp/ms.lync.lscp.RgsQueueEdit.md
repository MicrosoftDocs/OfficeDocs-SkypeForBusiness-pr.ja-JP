---
title: 応答グループキューの新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 応答グループキューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。
ms.openlocfilehash: 9cf88e66886794ee016f1faa03c4ee773ea568b7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793495"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="6e07a-103">応答グループのキュー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="6e07a-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="6e07a-104">応答グループキューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6e07a-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="6e07a-105">UI Reference</span></span>

<span data-ttu-id="6e07a-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6e07a-107">**名前**各キューには名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07a-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="6e07a-108">キューのわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="6e07a-109">**説明**このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6e07a-109">**Description** This field is optional.</span></span> <span data-ttu-id="6e07a-110">キューの追加情報を提供する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="6e07a-111">**グループ**キューに割り当てるエージェントグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="6e07a-112">[**選択**] をクリックして、エージェントグループを一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="6e07a-113">[**削除**] をクリックして、選択したエージェントグループを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="6e07a-114">上方向キーと下方向キーを押すと、選択したエージェントグループがリスト内で上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="6e07a-115">エージェントグループの順序は、Skype for Business Server が利用可能なエージェントを検索する順序に影響します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="6e07a-116">つまり、リスト内の最初のグループは、利用可能なエージェントを検索し、次に2番目のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="6e07a-117">**キューのタイムアウトを有効にする**このチェックボックスをオンにすると、発信者が通話に応答するまでの間、保留が待機する最大時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e07a-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="6e07a-118">このオプションを選択する場合は、次の項目も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07a-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="6e07a-119">**タイムアウト期間 (秒)** エージェントが通話に応答するまで待機できる最大時間 (秒数) を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="6e07a-120">**通話アクション**通話がタイムアウトになったときに発生するアクションを選択します。以下の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="6e07a-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="6e07a-121">**[切断]**</span><span class="sxs-lookup"><span data-stu-id="6e07a-121">**Disconnect**</span></span>

  - <span data-ttu-id="6e07a-122">**ボイスメールに転送する**このオプションを選択した場合は、[ **sip アドレス**] に「sip:<username> @ <domainname> 」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6e07a-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="6e07a-123">**電話番号に転送**このオプションを選択した場合、[ **sip アドレス**] に「sip:<number> @ <domainname> 」の形式で電話番号を入力します (たとえば、sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6e07a-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="6e07a-124">**SIP アドレスに転送**通話を別のユーザーに転送する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="6e07a-125">[ **Sip アドレス**] に、ユーザーの URI を「sip:<username>@<domainname>」という形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="6e07a-126">**別のキューに転送する**このオプションを選択した場合は、着信がタイムアウトになったときに着信を受け取るキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="6e07a-127">**キューのオーバーフローを有効にする**このチェックボックスをオンにすると、キューに保持できる通話の最大数が指定されます。</span><span class="sxs-lookup"><span data-stu-id="6e07a-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="6e07a-128">このオプションを選択する場合は、次の項目も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e07a-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="6e07a-129">**通話の最大数**キューに保持できる通話の最大数を選択または入力します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="6e07a-130">**通話を転送する**キューのオーバーフローしきい値に達したときにアクションを実行する呼び出しを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="6e07a-131">**通話アクション**キューのオーバーフローしきい値に達したときに発生するアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="6e07a-132">以下の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="6e07a-132">Your choices are:</span></span>

  - <span data-ttu-id="6e07a-133">**[切断]**</span><span class="sxs-lookup"><span data-stu-id="6e07a-133">**Disconnect**</span></span>

  - <span data-ttu-id="6e07a-134">**ボイスメールに転送する**このオプションを選択した場合は、[ **sip アドレス**] に「sip:<username> @ <domainname> 」という形式でボイスメールアドレスを入力します (たとえば、sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6e07a-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="6e07a-135">**電話番号に転送**このオプションを選択した場合、[ **sip アドレス**] に「sip:<number> @ <domainname> 」の形式で電話番号を入力します (たとえば、sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="6e07a-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="6e07a-136">**SIP アドレスに転送**通話を別のユーザーに転送する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="6e07a-137">[ **Sip アドレス**] に、ユーザーの URI を「sip:<username>@<domainname>」という形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="6e07a-138">**別のキューに転送する**このオプションを選択した場合は、キューのオーバーフローしきい値に達したときに、着信を受け取るキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e07a-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="6e07a-139">回答グループの機能の詳細については、計画ドキュメントの「 [Skype For Business Server での応答グループアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e07a-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="6e07a-140">キューの使用の詳細については、「操作」のドキュメントの「[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e07a-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


