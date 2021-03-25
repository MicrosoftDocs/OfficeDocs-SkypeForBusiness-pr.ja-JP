---
title: 応答グループ 新規または既存のエージェント グループの編集を作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: エージェント グループでは、応答グループへの通話に応答できるユーザー (エージェントと呼ばれます) およびグループ内のすべてのエージェントに適用される設定が定義されています。
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118966"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="da6a7-103">応答グループ: エージェント グループの新規作成または既存エージェント グループの編集</span><span class="sxs-lookup"><span data-stu-id="da6a7-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="da6a7-104">エージェント グループでは、応答グループへの通話に応答できるユーザー (エージェントと呼ばれます) およびグループ内のすべてのエージェントに適用される設定が定義されています。</span><span class="sxs-lookup"><span data-stu-id="da6a7-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="da6a7-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="da6a7-105">UI Reference</span></span>

<span data-ttu-id="da6a7-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="da6a7-107">**名前** 各エージェント グループには、一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="da6a7-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="da6a7-108">グループの関数を識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="da6a7-109">たとえば、ヘルプ デスクです。</span><span class="sxs-lookup"><span data-stu-id="da6a7-109">For example, Help Desk.</span></span>

- <span data-ttu-id="da6a7-110">**説明** このフィールドはオプションです。</span><span class="sxs-lookup"><span data-stu-id="da6a7-110">**Description** This field is optional.</span></span> <span data-ttu-id="da6a7-111">グループに関する追加の詳細を提供するために使用します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="da6a7-112">**参加ポリシー** エージェントが応答グループにサインインする方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="da6a7-113">[ **非公式** ] を選択して、グループ内のエージェントがサインインとサインアウトを行う必要がなことを指定します。非公式エージェントは、サインイン時に自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="da6a7-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="da6a7-114">既定値は [**非公式**] です。</span><span class="sxs-lookup"><span data-stu-id="da6a7-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="da6a7-115">グループ **内のエージェント** がサインインとサインアウトを行う必要がある場合は、[Formal] を選択します。このオプションを選択すると、エージェントはクライアントのメニュー項目をクリックしてブラウザーを開き、サインインおよびサインアウト用の Web ページ コンソールを表示します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="da6a7-116">**アラート時間 (秒)** 次に使用可能なエージェントに呼び出しを提供する前に、エージェントを呼び出す時間 (秒) を指定します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="da6a7-117">値は 10 秒以上 180 秒未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="da6a7-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="da6a7-118">既定値は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="da6a7-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="da6a7-119">**ルーティング方法** エージェントが呼び出しを受信する順序を決定する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="da6a7-120">最も長くアイドル状態である ([**連絡可能**] または [**非アクティブ**] である) エージェントに新しい通話を最初に提供する場合は、[**最長アイドル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="da6a7-p105">新しい通話を、有効なすべてのエージェントに同時に提供するには、[**パラレル**] を選択します。通話は、最初に受け付けたエージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="da6a7-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="da6a7-123">新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="da6a7-124">新しい通話を、常に [**エージェント**] の一覧での順にエージェントに提供するには、[**シリアル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="da6a7-125">[ **応答]** を選択して、現在のプレゼンスに関係なく、サインインしているすべてのエージェントと応答グループ アプリケーションに同時に新しい呼び出しを提供します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="da6a7-126">エージェントとして構成されている応答とクライアント ユーザーは、待機中のすべての呼び出しを確認し、任意の順序で待機中の呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="da6a7-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="da6a7-127">呼び出しは、それを受け入れる最初のエージェントに送信され、他の応答とユーザーは呼び出しを表示しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="da6a7-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="da6a7-128">**エージェント** 次のいずれかの方法で、応答グループのエージェントになるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="da6a7-129">[ **既存のメール配布リストを使用して** Exchange 配布リストを使用する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="da6a7-130">配布リストの電子メール アドレスを [**配布リストのアドレス**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="da6a7-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="da6a7-p108">エージェント グループに対して選択できる配布リストは 1 つだけです。配布リストに入れ子になった配布リストが含まれる場合、入れ子となった配布リストはエージェント グループに含まれません。</span><span class="sxs-lookup"><span data-stu-id="da6a7-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="da6a7-133">配布リスト内でのエージェントの順序により、ラウンド ロビンおよびシリアルのルーティングでエージェントが通話を受ける順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="da6a7-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="da6a7-134">非表示のメンバーシップや非表示のリストは、応答グループの管理者またはユーザーに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="da6a7-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="da6a7-135">詳細については [、「Skype for Business でエージェント グループを作成または変更する」を参照してください](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)。</span><span class="sxs-lookup"><span data-stu-id="da6a7-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="da6a7-p110">応答グループのエージェントとして割り当てるユーザーを選択する場合は、[**エージェントのカスタム グループを定義する**] を選択します。リストにエージェントを追加するには、[**選択**] をクリックします。選択されているエージェントをリストから削除するには、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da6a7-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="da6a7-p111">上下矢印を使用すると、選択したエージェントがエージェント リスト内で上下に移動します。リスト内でのエージェントの順序により、ラウンド ロビンおよびシリアルのルーティングでエージェントが通話を受ける順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="da6a7-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="da6a7-141">応答グループの機能の詳細については、「計画」のドキュメントの「Plan for the [Response Group application in Skype for Business Server」](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da6a7-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="da6a7-142">エージェント グループの使用の詳細については、「操作」のドキュメントの「[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da6a7-142">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>