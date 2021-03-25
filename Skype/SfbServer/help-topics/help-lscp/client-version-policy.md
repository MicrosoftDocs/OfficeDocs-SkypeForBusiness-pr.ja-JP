---
title: クライアント バージョン ポリシー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。 クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。
ms.openlocfilehash: 0af11ac26a73452412c653c04233df7b932f2b49
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118646"
---
# <a name="client-version-policy"></a><span data-ttu-id="c6118-106">クライアント バージョン ポリシー</span><span class="sxs-lookup"><span data-stu-id="c6118-106">Client Version Policy</span></span>

<span data-ttu-id="c6118-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="c6118-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c6118-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="c6118-109">Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="c6118-110">クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="c6118-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c6118-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="c6118-111">Tasks you can perform</span></span>

<span data-ttu-id="c6118-112">[**クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="c6118-113">既定の (グローバル) **クライアント** バージョン ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="c6118-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="c6118-114">特定のサイトまたはプールのクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="c6118-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="c6118-115">個別のユーザーに割り当てることのできるクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="c6118-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="c6118-116">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="c6118-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c6118-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="c6118-117">UI Reference</span></span>

<span data-ttu-id="c6118-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="c6118-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c6118-119">**New** 次のクライアント バージョン ポリシーのそれぞれを 1 つ以上作成できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="c6118-120">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="c6118-120">Site policy</span></span>

  - <span data-ttu-id="c6118-121">プール ポリシー</span><span class="sxs-lookup"><span data-stu-id="c6118-121">Pool policy</span></span>

  - <span data-ttu-id="c6118-122">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="c6118-122">User policy</span></span>

- <span data-ttu-id="c6118-123">**編集** クライアント バージョン ポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="c6118-124">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="c6118-125">**詳細の表示** このオプションは、クライアント バージョン ポリシーのオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6118-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="c6118-126">**[すべて選択]** このオプションは、リスト内のすべてのクライアント バージョン ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6118-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="c6118-127">**削除** このオプションは、選択したクライアント バージョン ポリシーをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="c6118-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="c6118-128">**更新** クライアント バージョン ポリシーの一覧を更新して、すべてのクライアント バージョン ポリシーのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c6118-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="c6118-129">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6118-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="c6118-130">クライアント バージョン ポリシーの操作の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6118-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>