---
title: 場所のポリシー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824787"
---
# <a name="location-policy"></a><span data-ttu-id="82025-103">場所ポリシー</span><span class="sxs-lookup"><span data-stu-id="82025-103">Location Policy</span></span>

<span data-ttu-id="82025-104">場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="82025-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="82025-105">場所ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト ポリシーおよびユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82025-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="82025-106">**グローバル ポリシー:** グローバル ポリシーは既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="82025-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="82025-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="82025-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="82025-108">グローバル ポリシーの削除を試みると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="82025-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="82025-109">**サイト ポリシー (オプション):** 1 つ以上のサイトの場所のポリシーを作成し、それぞれのポリシーを特定のサイトに適用できます。</span><span class="sxs-lookup"><span data-stu-id="82025-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="82025-110">サイト ポリシーはグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="82025-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="82025-111">**ユーザー ポリシー (オプション):** 1 つ以上のユーザーの場所のポリシーを作成できます。各ポリシーは、特定のユーザーまたはユーザー のグループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="82025-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="82025-112">ユーザー ポリシーは、グローバル ポリシーとサイト ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="82025-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="82025-113">場所ポリシーは、サブネットのグループであるネットワーク サイトに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="82025-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="82025-114">ネットワーク サイトに割り当てられた場所ポリシーは、他のすべてのユーザー ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="82025-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="82025-115">コマンドレットを使用してネットワーク サイトに場所ポリシーを割り当てる方法の詳細については [、「Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)のネットワーク サイトに場所ポリシーを追加する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82025-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="82025-116">Skype for Business Server コントロール パネルを使用して場所ポリシーをネットワーク サイトに割り当てる方法の詳細については、「ネットワーク サイトの構成」を [参照してください](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="82025-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="82025-117">[**場所ポリシー**] ページには、組織で定義されているすべての場所ポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="82025-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="82025-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="82025-118">Tasks you can perform</span></span>

<span data-ttu-id="82025-119">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="82025-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="82025-120">新しいサイトの場所ポリシーまたはユーザーの場所ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="82025-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="82025-121">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="82025-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="82025-122">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="82025-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="82025-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="82025-123">UI Reference</span></span>

<span data-ttu-id="82025-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="82025-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="82025-125">**新規** 新しいサイトの場所ポリシーまたはユーザーの場所のポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="82025-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="82025-126">**編集** 選択した場所ポリシーを開き、編集するか、一覧内のすべての場所ポリシーを選択するか、選択したサイト ポリシーまたはユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="82025-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82025-127">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="82025-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="82025-128">**更新** 場所ポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="82025-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="82025-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="82025-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="82025-130">**名前** 場所ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="82025-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="82025-131">**スコープ** 場所ポリシーの範囲 (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="82025-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="82025-132">**E9-1-1** この場所ポリシーを割り当てられたユーザーが E9-1-1 に対して有効になっている場合にオンになります。</span><span class="sxs-lookup"><span data-stu-id="82025-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="82025-133">**場所** クライアントが新しい場所で Skype for Business Server に登録するときにユーザーに場所情報の入力を求めるかどうかを指定し、場所情報を入力せずにプロンプトを閉じた場合に免責事項を表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="82025-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="82025-134">**PSTN 使用法** このプロファイルを使用するクライアントからの緊急通話のルーティングに使用するボイス ルートを決定するために使用する公衆交換電話網 (PSTN) 使用法を指定します。</span><span class="sxs-lookup"><span data-stu-id="82025-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="82025-135">**E9-1-1 番号** 緊急サービスに到達するためにダイヤルされる番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="82025-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="82025-136">**E9-1-1 マスク** ユーザーがダイヤルし、緊急ダイヤル番号に変換される番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="82025-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="82025-137">緊急サービスのエンタープライズ VoIPの詳細については、「計画」のドキュメントの [「E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82025-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="82025-138">場所ポリシーの操作の詳細については、「操作」のドキュメントの「[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82025-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


