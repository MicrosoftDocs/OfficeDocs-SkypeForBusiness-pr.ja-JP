---
title: 応答グループ新規作成または既存のエージェントグループの編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: エージェント グループでは、応答グループへの呼び出しに応答できるユーザー (エージェントと呼ばれます) およびグループ内のすべてのエージェントに適用される設定が定義されています。
ms.openlocfilehash: 2fde88426c659492cff350007b7e88a53581c67d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690912"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="a5e11-103">応答グループ: エージェント グループの新規作成または既存エージェント グループの編集</span><span class="sxs-lookup"><span data-stu-id="a5e11-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="a5e11-104">エージェント グループでは、応答グループへの呼び出しに応答できるユーザー (エージェントと呼ばれます) およびグループ内のすべてのエージェントに適用される設定が定義されています。</span><span class="sxs-lookup"><span data-stu-id="a5e11-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a5e11-105">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="a5e11-105">UI Reference</span></span>

<span data-ttu-id="a5e11-106">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a5e11-107">**名前**各エージェントグループには一意の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e11-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="a5e11-108">グループの関数を識別するわかりやすい名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="a5e11-109">たとえば、[ヘルプデスク] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5e11-109">For example, Help Desk.</span></span>

- <span data-ttu-id="a5e11-110">**説明**このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a5e11-110">**Description** This field is optional.</span></span> <span data-ttu-id="a5e11-111">このグループを使用して、グループに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="a5e11-112">**参加ポリシー**エージェントが応答グループにサインインする方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="a5e11-p103">グループのエージェントがサインインおよびサインアウトする必要がないことを指定するには、[**非公式**] を選択します。非公式のエージェントは、サインインすると自動的にサインインします。既定値は [**非公式**] です。</span><span class="sxs-lookup"><span data-stu-id="a5e11-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>

  - <span data-ttu-id="a5e11-115">グループのエージェントがサインインまたはサインアウトする必要があることを指定するには、[**正式**] を選択します。このオプションを選択すると、エージェントはクライアントのメニュー項目をクリックすると、ブラウザーが開き、サインインとサインアウトのための web ページ本体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5e11-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="a5e11-116">**通知時間 (秒)** 次の使用可能なエージェントへの通話を提供する前に、エージェントを呼び出す秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="a5e11-117">値は、10秒以上かつ180秒未満でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a5e11-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="a5e11-118">既定値は20秒です。</span><span class="sxs-lookup"><span data-stu-id="a5e11-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="a5e11-119">**ルーティング方法**担当者が通話を受ける順序を決定する方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="a5e11-120">新しい呼び出しを、最も長くアイドル状態である ([**連絡可能**] または [**非アクティブ**] である) エージェントに最初に提供する場合は、[**最長アイドル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="a5e11-p105">新しい呼び出しを、有効なすべてのエージェントに同時に提供するには、[**パラレル**] を選択します。呼び出しは、最初に受け付けたエージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="a5e11-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="a5e11-123">新しい呼び出しを、各エージェントに順番に提供するには、[**ラウンド ロビン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="a5e11-124">新しい呼び出しを、常に [**エージェント**] の一覧の順序でエージェントに提供するには、[**シリアル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="a5e11-125">[**応答] を選択し**て、サインインしているすべてのエージェントと、現在のプレゼンスに関係なく同時に応答グループアプリケーションへの新しい通話を提供します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="a5e11-126">エージェントとして構成されているアテンダントとクライアントユーザーは、待機中のすべての通話を表示し、待機中の通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="a5e11-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="a5e11-127">呼び出しを受け付けた最初のエージェントに呼び出しが送信されると、その呼び出しは他のアテンダントとユーザーには表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="a5e11-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="a5e11-128">**エージェント**次のいずれかの方法で、応答グループのエージェントになるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="a5e11-129">Exchange の配布リストを使用するには、[**既存の電子メール配布リストを使用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="a5e11-130">配布リストの電子メール アドレスを [**配布リストのアドレス**] に入力します。</span><span class="sxs-lookup"><span data-stu-id="a5e11-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5e11-p108">エージェント グループに対して選択できる配布リストは 1 つだけです。配布リストに入れ子になった配布リストが含まれる場合、入れ子となった配布リストはエージェント グループに含まれません。</span><span class="sxs-lookup"><span data-stu-id="a5e11-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5e11-133">配布リスト内でのエージェントの順序により、ラウンド ロビンおよびシリアルのルーティングでエージェントが呼び出しを受ける順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="a5e11-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5e11-134">非表示のメンバーシップまたは非表示のリストは、グループ管理者またはユーザーに応答するために表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a5e11-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="a5e11-135">詳細について[は、「Skype For business でエージェントグループを作成または変更](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e11-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="a5e11-p110">応答グループのエージェントとして割り当てるユーザーを選択する場合は、[**エージェントのカスタム グループを定義する**] を選択します。リストにエージェントを追加するには、[**選択**] をクリックします。選択されているエージェントをリストから削除するには、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e11-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="a5e11-p111">上下矢印を使用すると、選択したエージェントがエージェント リスト内で上下に移動します。リスト内でのエージェントの順序により、ラウンド ロビンおよびシリアルのルーティングでエージェントが呼び出しを受ける順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="a5e11-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="a5e11-141">回答グループの機能の詳細については、計画ドキュメントの「 [Skype For Business Server での応答グループアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e11-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="a5e11-142">エージェント グループの使用の詳細については、「操作」のドキュメントの「[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e11-142">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


