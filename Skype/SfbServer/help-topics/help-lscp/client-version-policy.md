---
title: クライアント バージョン ポリシー
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 ビジネス サーバー 2015 の Skype に含まれている機能の最大限に活用し、全体的なユーザー エクスペリエンスを向上させるために、環境内で使用されているクライアント バージョンを制限するのにはクライアント バージョン フィルターを使用することができます。 クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。
ms.openlocfilehash: 67524a0f00a4251db3a16667340c959ca3628547
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23247018"
---
# <a name="client-version-policy"></a><span data-ttu-id="96eec-106">クライアント バージョン ポリシー</span><span class="sxs-lookup"><span data-stu-id="96eec-106">Client Version Policy</span></span>

<span data-ttu-id="96eec-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="96eec-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="96eec-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="96eec-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="96eec-109">ビジネス サーバー 2015 の Skype に含まれている機能の最大限に活用し、全体的なユーザー エクスペリエンスを向上させるために、環境内で使用されているクライアント バージョンを制限するのにはクライアント バージョン フィルターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="96eec-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="96eec-110">クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="96eec-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="96eec-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="96eec-111">Tasks you can perform</span></span>

<span data-ttu-id="96eec-112">[**クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96eec-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="96eec-113">(**グローバル**) の既定のクライアント バージョン ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="96eec-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="96eec-114">特定のサイトまたはプールのクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="96eec-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="96eec-115">個別のユーザーに割り当てることのできるクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="96eec-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="96eec-116">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="96eec-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="96eec-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="96eec-117">UI Reference</span></span>

<span data-ttu-id="96eec-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="96eec-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="96eec-119">**新しい**1 つまたは複数のクライアント バージョン ポリシーの各を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="96eec-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="96eec-120">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="96eec-120">Site policy</span></span>

  - <span data-ttu-id="96eec-121">プール ポリシー</span><span class="sxs-lookup"><span data-stu-id="96eec-121">Pool policy</span></span>

  - <span data-ttu-id="96eec-122">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="96eec-122">User policy</span></span>

- <span data-ttu-id="96eec-123">**編集**クライアント バージョン ポリシーのいずれかのオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="96eec-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="96eec-124">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="96eec-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="96eec-125">**詳細を表示します。** このオプションは、クライアント バージョン ポリシーのオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="96eec-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="96eec-126">**すべてを選択**このオプションでは、一覧のすべてのクライアント バージョン ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="96eec-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="96eec-127">**削除**このオプションは、すべての選択したクライアント バージョン ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="96eec-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="96eec-128">**更新**すべてのクライアント バージョン ポリシーのオプションの状態を確認するクライアント バージョン ポリシーの一覧を更新できます。</span><span class="sxs-lookup"><span data-stu-id="96eec-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="96eec-129">クライアントとクライアントのバージョン間での相互運用性に関する詳細については、計画ドキュメントに[Lync 2013 プレビューでのクライアントの相互運用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96eec-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="96eec-130">クライアント バージョン ポリシーの使用についての詳細は、操作マニュアルで[の組織でサポートされるクライアント バージョンの指定](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96eec-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

