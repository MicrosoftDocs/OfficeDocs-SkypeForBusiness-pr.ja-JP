---
title: 応答グループ キューを新規作成または既存の編集
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 応答グループ キューは、エージェントが呼び出しに応答するまでの応答グループへの呼び出しを保持します。
ms.openlocfilehash: 7c56554571d09279ce896798d6c7e21dae5f9f3d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993496"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="ecbca-103">応答グループのキュー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="ecbca-103">Response Groups Queue: Create New or Edit Existing</span></span>
 
<span data-ttu-id="ecbca-104">応答グループ キューは、エージェントが呼び出しに応答するまでの応答グループへの呼び出しを保持します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="ecbca-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="ecbca-105">UI Reference</span></span>

<span data-ttu-id="ecbca-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="ecbca-107">**名**各キューには、名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="ecbca-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="ecbca-108">キューの内容を示す名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-108">Type a descriptive name for the queue.</span></span>
    
- <span data-ttu-id="ecbca-109">**説明**このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ecbca-109">**Description** This field is optional.</span></span> <span data-ttu-id="ecbca-110">キューに関する追加情報を提供するのにには、それを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-110">Use it to provide additional details about the queue.</span></span>
    
- <span data-ttu-id="ecbca-111">**グループ**キューに割り当てるエージェント グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="ecbca-112">エージェント グループを一覧に追加する**選択**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecbca-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="ecbca-113">リストから選択されたエージェントのグループを削除する**削除**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecbca-113">Click **Remove** to delete the selected agent group from the list.</span></span>
    
    <span data-ttu-id="ecbca-114">上下矢印キー選択したエージェントのグループを上下移動、ボックスの一覧でします。</span><span class="sxs-lookup"><span data-stu-id="ecbca-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="ecbca-115">エージェント グループの順序では、Skype のビジネス サーバーが利用可能なエージェントの検索順序に影響します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="ecbca-116">一覧の最初のグループは、2 番目のグループというように続いて、利用可能なエージェントの最初検索されます。</span><span class="sxs-lookup"><span data-stu-id="ecbca-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>
    
- <span data-ttu-id="ecbca-117">**キューのタイムアウトを有効にします。** まで保留中のエージェントが呼び出しに応答を呼び出し元の時間の最大期間を指定するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="ecbca-118">このオプションを選択する場合は、以下を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecbca-118">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="ecbca-119">**タイムアウト期間 (秒)** 選択するか、エージェントが呼び出しに応答する前に、呼び出し元が待機する秒の最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>
    
  - <span data-ttu-id="ecbca-120">**呼び出しアクション**呼び出しがタイムアウトしたときに発生するアクションを選択します。選択内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ecbca-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>
    
  - <span data-ttu-id="ecbca-121">**[切断]**</span><span class="sxs-lookup"><span data-stu-id="ecbca-121">**Disconnect**</span></span>
    
  - <span data-ttu-id="ecbca-122">**ボイス メールに転送する****SIP アドレス**でこのオプションを選択する場合は、形式の sip にボイス ・ メール ・ アドレスを入力:<username> @ <domainname> (sip:bob@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="ecbca-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="ecbca-123">**電話番号に転送する**入力形式の sip の電話番号を**SIP アドレス**でこのオプションを選択した場合:<number> @ <domainname> (sip:+14255550121@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="ecbca-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="ecbca-124">**SIP アドレスに転送する**他のユーザーへの呼び出しを転送するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="ecbca-125">**SIP アドレス**を、sip の形式でユーザーの URI を入力:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="ecbca-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="ecbca-126">**別のキューに転送する**このオプションを選択する場合は、呼び出しのタイムアウトを受信する場合の呼び出しは、キューに参照します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>
    
- <span data-ttu-id="ecbca-127">**キューのオーバーフローを有効にします。** キューが保持できる呼び出しの最大数を指定するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="ecbca-128">このオプションを選択する場合は、以下を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecbca-128">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="ecbca-129">**呼び出しの最大数**選択するかの呼び出しは、キューが保持できる最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>
    
  - <span data-ttu-id="ecbca-130">**呼び出しを転送します。** 呼び出しは、キューのオーバーフローしきい値が満たされたときにアクションを実行するを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>
    
  - <span data-ttu-id="ecbca-131">**呼び出しアクション**キューのオーバーフローしきい値に達したときに発生するアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="ecbca-132">選択内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ecbca-132">Your choices are:</span></span>
    
  - <span data-ttu-id="ecbca-133">**[切断]**</span><span class="sxs-lookup"><span data-stu-id="ecbca-133">**Disconnect**</span></span>
    
  - <span data-ttu-id="ecbca-134">**ボイス メールに転送する****SIP アドレス**でこのオプションを選択する場合は、形式の sip にボイス ・ メール ・ アドレスを入力:<username> @ <domainname> (sip:bob@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="ecbca-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="ecbca-135">**電話番号に転送する**入力形式の sip の電話番号を**SIP アドレス**でこのオプションを選択した場合:<number> @ <domainname> (sip:+14255550121@contoso.com など)。</span><span class="sxs-lookup"><span data-stu-id="ecbca-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="ecbca-136">**SIP アドレスに転送する**他のユーザーへの呼び出しを転送するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="ecbca-137">**SIP アドレス**を、sip の形式でユーザーの URI を入力:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="ecbca-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="ecbca-138">**別のキューに転送する**このオプションを選択する場合は、キューのオーバーフローしきい値に達したときに呼び出しを受信するキューを参照します。</span><span class="sxs-lookup"><span data-stu-id="ecbca-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>
    
<span data-ttu-id="ecbca-139">応答のグループの特徴と機能についての詳細は、計画のドキュメントで[ビジネス サーバーの Skype で応答グループ アプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbca-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="ecbca-140">キューの操作についての詳細は、操作マニュアルの[応答グループ キューの管理](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbca-140">For details about working with queues, see [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>
  

