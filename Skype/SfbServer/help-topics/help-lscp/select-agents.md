---
title: エージェントの選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: 担当者は、応答グループの通話に応答するように指定されているユーザーです。 応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。 エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。 有効なユーザーは、Skype for Business Server およびエンタープライズ Voip に対応しています。
ms.openlocfilehash: 2950295bcf78ee2c7c904375d009a8fba085b85f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822310"
---
# <a name="select-agents"></a><span data-ttu-id="966d5-106">エージェントの選択</span><span class="sxs-lookup"><span data-stu-id="966d5-106">Select Agents</span></span>

<span data-ttu-id="966d5-107">担当者は、応答グループの通話に応答するように指定されているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="966d5-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="966d5-108">応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="966d5-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="966d5-109">エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。</span><span class="sxs-lookup"><span data-stu-id="966d5-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="966d5-110">有効なユーザーは、Skype for Business Server およびエンタープライズ Voip に対応しています。</span><span class="sxs-lookup"><span data-stu-id="966d5-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="966d5-111">[**エージェントの選択**] ダイアログ ボックスを使用して、エージェント グループに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="966d5-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="966d5-112">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="966d5-112">UI Reference</span></span>

<span data-ttu-id="966d5-113">[**エージェントの選択**] ダイアログ ボックスには次のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="966d5-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="966d5-114">**検索**ユーザーの SIP アドレスまたは表示名を検索します。</span><span class="sxs-lookup"><span data-stu-id="966d5-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="966d5-115">アドレスまたは名前のすべてまたは一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="966d5-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="966d5-116">Skype for Business Server およびエンタープライズ Voip を有効にしているすべてのユーザーを表示するには、[検索] ボックスを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="966d5-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="966d5-117">**表示するユーザーの最大数**表示される返される結果の数を変更します。</span><span class="sxs-lookup"><span data-stu-id="966d5-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="966d5-118">このカウンターを使って、検索結果の数が多い場合に検索を制限します。</span><span class="sxs-lookup"><span data-stu-id="966d5-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="966d5-119">[**エージェントの選択**] ダイアログ ボックスには次のフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="966d5-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="966d5-120">**エージェント**検索によって返されるユーザー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="966d5-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="966d5-121">**SIP アドレス**検索によって返されるユーザー SIP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="966d5-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="966d5-122">**テレフォニー**ユーザーに対して定義された [ **Telephony** ] フィールドの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="966d5-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="966d5-123">**有効**ユーザーに対して定義されている**Lync Server の [有効**] フィールドの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="966d5-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="966d5-124">エージェント グループの使用の詳細については、「操作」のドキュメントの「[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="966d5-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


