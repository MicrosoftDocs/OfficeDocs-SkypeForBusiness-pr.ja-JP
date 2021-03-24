---
title: クライアント バージョン ポリシー [新規の作成] または [既存の編集]
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
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。 クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。
ms.openlocfilehash: 614719a4d0152df4e451793e4845e7a6f72a59cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095611"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="a824d-106">クライアント バージョン ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="a824d-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="a824d-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="a824d-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a824d-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="a824d-109">Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="a824d-110">クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="a824d-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a824d-p103">フィルターは、優先順にリストされます。たとえば、バージョン 1.5 を実行するクライアントに接続を許可するフィルターの後に、2.0 より古いバージョンを実行するクライアントを禁止するフィルターを設定した場合、最初のフィルターが優先されるため、バージョン 1.5 を実行するクライアントの接続が許可されます。</span><span class="sxs-lookup"><span data-stu-id="a824d-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a824d-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="a824d-113">Tasks you can perform</span></span>

<span data-ttu-id="a824d-114">[**新しいクライアント バージョン ポリシーの作成**] または [**編集 クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="a824d-115">クライアント バージョン ポリシーの名前や説明を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="a824d-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="a824d-116">クライアント バージョン ポリシーのクライアント バージョン ルールを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="a824d-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a824d-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="a824d-117">UI Reference</span></span>

<span data-ttu-id="a824d-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="a824d-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="a824d-119">**スコープ** クライアント バージョン ポリシーのスコープ (サイト、プール、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="a824d-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="a824d-120">**名前** クライアント バージョン ポリシーの名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="a824d-121">**説明** [クライアント バージョン ポリシー] ページの一覧で、ポリシーの識別に役立つ説明を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="a824d-122">**New** 新しいクライアント バージョン ルールをポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a824d-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="a824d-123">**詳細の表示** このオプションは、クライアント バージョン ルールのオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a824d-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="a824d-124">**削除** このオプションは、選択したクライアント バージョン ルールをポリシーから削除します。</span><span class="sxs-lookup"><span data-stu-id="a824d-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="a824d-125">**上下の矢印** このオプションは、選択したクライアント バージョン ルールを優先度で上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="a824d-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="a824d-126">ルールは、一覧表示された順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="a824d-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="a824d-127">クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a824d-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="a824d-128">クライアント バージョン ポリシーの操作の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a824d-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>