---
title: クライアント バージョン ポリシー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。
ms.openlocfilehash: c52921df4e68b8273a4e87af0cfe54105e8a10ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812397"
---
# <a name="client-version-policy"></a><span data-ttu-id="9cf64-104">クライアント バージョン ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cf64-104">Client Version Policy</span></span>

<span data-ttu-id="9cf64-105">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="9cf64-106">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="9cf64-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="9cf64-107">Skype for Business Server に含まれる機能を最大に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="9cf64-108">クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9cf64-109">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="9cf64-109">Tasks you can perform</span></span>

<span data-ttu-id="9cf64-110">[**クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="9cf64-111">既定の (グローバル) **クライアント バージョン** ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="9cf64-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="9cf64-112">特定のサイトまたはプールのクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="9cf64-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="9cf64-113">個別のユーザーに割り当てることのできるクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="9cf64-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="9cf64-114">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="9cf64-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9cf64-115">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="9cf64-115">UI Reference</span></span>

<span data-ttu-id="9cf64-116">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="9cf64-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="9cf64-117">**新規** 次のクライアント バージョン ポリシーは、それぞれ 1 つ以上作成できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="9cf64-118">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cf64-118">Site policy</span></span>

  - <span data-ttu-id="9cf64-119">プール ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cf64-119">Pool policy</span></span>

  - <span data-ttu-id="9cf64-120">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="9cf64-120">User policy</span></span>

- <span data-ttu-id="9cf64-121">**編集** 任意のクライアント バージョン ポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="9cf64-122">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="9cf64-123">**詳細の表示** このオプションを選択すると、クライアント バージョン ポリシーのオプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="9cf64-124">**すべて選択** このオプションでは、一覧内のすべてのクライアント バージョン ポリシーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="9cf64-125">**Delete** このオプションでは、選択したクライアント バージョン ポリシーすべてが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="9cf64-126">**更新** クライアント バージョン ポリシーの一覧を更新して、すべてのクライアント バージョン ポリシーのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9cf64-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="9cf64-127">クライアントとクライアント バージョン間の相互運用性の詳細については、「計画」のドキュメントの「 [クライアント](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) の相互運用性」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cf64-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9cf64-128">クライアント バージョン ポリシーの操作の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cf64-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

