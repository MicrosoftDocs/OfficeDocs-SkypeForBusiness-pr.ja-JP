---
title: クライアント バージョン ポリシー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれている機能を最大限に活用し、全体的なユーザーエクスペリエンスを向上させるには、クライアントバージョンフィルターを使用して、環境で使用されるクライアントのバージョンを制限します。 クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。
ms.openlocfilehash: ac43816dfe3b5afac44bf846f76f92dc80667930
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823070"
---
# <a name="client-version-policy"></a><span data-ttu-id="887d1-106">クライアント バージョン ポリシー</span><span class="sxs-lookup"><span data-stu-id="887d1-106">Client Version Policy</span></span>

<span data-ttu-id="887d1-107">現在の環境でサポートするクライアントのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="887d1-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="887d1-108">バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="887d1-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="887d1-109">Skype for Business Server 2015 に含まれている機能を最大限に活用し、全体的なユーザーエクスペリエンスを向上させるには、クライアントバージョンフィルターを使用して、環境で使用されるクライアントのバージョンを制限します。</span><span class="sxs-lookup"><span data-stu-id="887d1-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="887d1-110">クライアント バージョン フィルターを使用すると、複数のクライアント バージョンをサポートすることで発生するコストを抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="887d1-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="887d1-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="887d1-111">Tasks you can perform</span></span>

<span data-ttu-id="887d1-112">[**クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="887d1-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="887d1-113">既定の (**グローバル**) クライアントのバージョンポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="887d1-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="887d1-114">特定のサイトまたはプールのクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="887d1-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="887d1-115">個別のユーザーに割り当てることのできるクライアント バージョン ポリシーを作成する。</span><span class="sxs-lookup"><span data-stu-id="887d1-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="887d1-116">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="887d1-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="887d1-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="887d1-117">UI Reference</span></span>

<span data-ttu-id="887d1-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="887d1-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="887d1-119">**新規**次のいずれかのクライアントバージョンポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="887d1-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="887d1-120">サイト ポリシー</span><span class="sxs-lookup"><span data-stu-id="887d1-120">Site policy</span></span>

  - <span data-ttu-id="887d1-121">プール ポリシー</span><span class="sxs-lookup"><span data-stu-id="887d1-121">Pool policy</span></span>

  - <span data-ttu-id="887d1-122">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="887d1-122">User policy</span></span>

- <span data-ttu-id="887d1-123">**編集**いずれかのクライアントのバージョンポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="887d1-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="887d1-124">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="887d1-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="887d1-125">**詳細を表示**このオプションを選択すると、ダイアログボックスが開き、クライアントのバージョンポリシーのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="887d1-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="887d1-126">**すべて選択**このオプションでは、リスト内のすべてのクライアントバージョンポリシーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="887d1-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="887d1-127">**削除**このオプションでは、選択したすべてのクライアントのバージョンポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="887d1-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="887d1-128">**更新**クライアントのバージョンポリシーの一覧を更新して、すべてのクライアントのバージョンポリシーのオプションの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="887d1-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="887d1-p104">クライアント間およびクライアント バージョン間での相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョン ポリシーの使用の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="887d1-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

