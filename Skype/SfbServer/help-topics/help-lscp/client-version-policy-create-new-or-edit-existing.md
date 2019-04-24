---
title: クライアント バージョン ポリシーを新規作成または既存の編集
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 ビジネス サーバー 2015 の Skype に含まれている機能の最大限に活用し、全体的なユーザー エクスペリエンスを向上させるために、環境内で使用されているクライアント バージョンを制限するのにはクライアント バージョン フィルターを使用することができます。 クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。
ms.openlocfilehash: 80494c52aa20175a74daac7b094600bb4590d92a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234715"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="b1036-106">クライアント バージョン ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="b1036-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="b1036-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b1036-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b1036-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="b1036-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="b1036-109">ビジネス サーバー 2015 の Skype に含まれている機能の最大限に活用し、全体的なユーザー エクスペリエンスを向上させるために、環境内で使用されているクライアント バージョンを制限するのにはクライアント バージョン フィルターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b1036-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="b1036-110">クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1036-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1036-p103">フィルターは、優先順にリストされます。たとえば、バージョン 1.5 を実行するクライアントの接続を許可するフィルターの後に、2.0 より古いバージョンを実行するクライアントを禁止するフィルターを設定した場合、最初のフィルターが優先されるため、バージョン 1.5 を実行するクライアントの接続は許可されます。</span><span class="sxs-lookup"><span data-stu-id="b1036-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b1036-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="b1036-113">Tasks you can perform</span></span>

<span data-ttu-id="b1036-114">[**新しいクライアント バージョン ポリシーの作成**] または [**編集 クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1036-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="b1036-115">クライアント バージョン ポリシーの名前や説明を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="b1036-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="b1036-116">クライアント バージョン ポリシーのクライアント バージョン ルールを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="b1036-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b1036-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="b1036-117">UI Reference</span></span>

<span data-ttu-id="b1036-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b1036-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b1036-119">**スコープ**クライアント バージョン ポリシーのスコープ (サイト、プール、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="b1036-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="b1036-120">**名**追加したり、クライアント バージョン ポリシーの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b1036-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="b1036-121">**説明**[クライアント バージョン ポリシー] ページで、ボックスの一覧で、ポリシーを識別するに役立つ説明を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b1036-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="b1036-122">**新しい**新しいクライアント バージョン ルールは、ポリシーに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b1036-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="b1036-123">**詳細を表示します。** このオプションは、クライアント バージョン ルールのオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1036-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="b1036-124">**削除**このオプションは、選択したクライアントのバージョンのルールをポリシーから削除します。</span><span class="sxs-lookup"><span data-stu-id="b1036-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="b1036-125">**上下矢印キー**このオプション選択したクライアントのバージョンのルールを上下優先移動します。</span><span class="sxs-lookup"><span data-stu-id="b1036-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="b1036-126">ルールは、一覧の順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="b1036-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="b1036-p105">クライアント間およびクライアント バージョン間での相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョン ポリシーの使用の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1036-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

