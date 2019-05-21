---
title: クライアントバージョンポリシーの新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれている機能を最大限に活用し、全体的なユーザーエクスペリエンスを向上させるには、クライアントバージョンフィルターを使用して、環境で使用されるクライアントのバージョンを制限します。 クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300015"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="97c16-106">クライアント バージョン ポリシー: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="97c16-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="97c16-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="97c16-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="97c16-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="97c16-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="97c16-109">Skype for Business Server 2015 に含まれている機能を最大限に活用し、全体的なユーザーエクスペリエンスを向上させるには、クライアントバージョンフィルターを使用して、環境で使用されるクライアントのバージョンを制限します。</span><span class="sxs-lookup"><span data-stu-id="97c16-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="97c16-110">クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="97c16-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c16-p103">フィルターは、優先順にリストされます。たとえば、バージョン 1.5 を実行するクライアントの接続を許可するフィルターの後に、2.0 より古いバージョンを実行するクライアントを禁止するフィルターを設定した場合、最初のフィルターが優先されるため、バージョン 1.5 を実行するクライアントの接続は許可されます。</span><span class="sxs-lookup"><span data-stu-id="97c16-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="97c16-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="97c16-113">Tasks you can perform</span></span>

<span data-ttu-id="97c16-114">[**新しいクライアント バージョン ポリシーの作成**] または [**編集 クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="97c16-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="97c16-115">クライアント バージョン ポリシーの名前や説明を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="97c16-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="97c16-116">クライアント バージョン ポリシーのクライアント バージョン ルールを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="97c16-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="97c16-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="97c16-117">UI Reference</span></span>

<span data-ttu-id="97c16-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="97c16-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="97c16-119">**スコープ**クライアントのバージョンポリシーのスコープ (サイト、プール、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="97c16-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="97c16-120">**名前**クライアントのバージョンポリシーの名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="97c16-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="97c16-121">**説明**[クライアントのバージョンポリシー] ページの一覧でポリシーを識別するのに役立つ説明を追加できます。</span><span class="sxs-lookup"><span data-stu-id="97c16-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="97c16-122">**新規**新しいクライアントバージョンの規則をポリシーに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="97c16-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="97c16-123">**詳細を表示**このオプションを選択すると、ダイアログボックスが開き、クライアントのバージョンルールのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="97c16-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="97c16-124">**削除**このオプションでは、選択したクライアントバージョンのルールがポリシーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="97c16-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="97c16-125">**上矢印と下矢印**このオプションでは、選択したクライアントバージョンの規則が [優先順位] に移動します。</span><span class="sxs-lookup"><span data-stu-id="97c16-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="97c16-126">ルールは、記載されている順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="97c16-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="97c16-p105">クライアント間およびクライアント バージョン間での相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョン ポリシーの使用の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97c16-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

