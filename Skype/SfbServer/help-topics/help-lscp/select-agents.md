---
title: エージェントの選択
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: エージェントは、応答グループの呼び出しに応答するように指定されているユーザーです。 応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。 エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。 対象となるユーザーは、ビジネスのサーバーおよびエンタープライズ VoIP Skype は有効です。
ms.openlocfilehash: 45f7ff77acc48a5c4000fd985cfdb0ae707deb9e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263423"
---
# <a name="select-agents"></a><span data-ttu-id="9fc16-106">エージェントの選択</span><span class="sxs-lookup"><span data-stu-id="9fc16-106">Select Agents</span></span>

<span data-ttu-id="9fc16-107">エージェントは、応答グループの呼び出しに応答するように指定されているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9fc16-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="9fc16-108">応答グループには、そのグループへの呼び出しを受信できるエージェントを示すエージェント グループが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc16-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="9fc16-109">エージェント グループを作成する方法の 1 つは、適格なユーザーを選択してカスタム グループを定義することです。</span><span class="sxs-lookup"><span data-stu-id="9fc16-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="9fc16-110">対象となるユーザーは、ビジネスのサーバーおよびエンタープライズ VoIP Skype は有効です。</span><span class="sxs-lookup"><span data-stu-id="9fc16-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="9fc16-111">[**エージェントの選択**] ダイアログ ボックスを使用して、エージェント グループに追加するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9fc16-112">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="9fc16-112">UI Reference</span></span>

<span data-ttu-id="9fc16-113">[**エージェントの選択**] ダイアログ ボックスには次のコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="9fc16-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="9fc16-114">**検索**SIP の検索では、アドレスや、ユーザーの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="9fc16-115">アドレスまたは名前の一部または全部を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="9fc16-116">検索ボックスは、Skype ビジネス サーバーとエンタープライズ VoIP を有効になっているすべてのユーザーを表示するのには空のままにします。</span><span class="sxs-lookup"><span data-stu-id="9fc16-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="9fc16-117">**最大ユーザー数を表示するには**表示される検索結果の数を変更します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="9fc16-118">多くの結果が予想される場合は、検索を制限するのにには、このカウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="9fc16-119">[**エージェントの選択**] ダイアログ ボックスには次のフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="9fc16-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="9fc16-120">**エージェント**検索によって返されるユーザー名を表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="9fc16-121">**SIP アドレス**検索によって返されるユーザーの SIP アドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="9fc16-122">**テレフォニー**ユーザーに対して定義されている**テレフォニー**フィールドの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="9fc16-123">**有効になっています。** ユーザーに対して定義されている**Lync Server の Enabled**フィールドの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="9fc16-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="9fc16-124">エージェント グループの操作に関する詳細については、操作マニュアルで[エージェントの管理グループ](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fc16-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


