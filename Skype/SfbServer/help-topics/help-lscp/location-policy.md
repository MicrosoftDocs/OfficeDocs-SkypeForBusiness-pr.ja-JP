---
title: 場所のポリシー
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
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。
ms.openlocfilehash: 00c0635e6833c5cb4f356de2914abb50eb4ddafc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822700"
---
# <a name="location-policy"></a><span data-ttu-id="662ed-103">場所のポリシー</span><span class="sxs-lookup"><span data-stu-id="662ed-103">Location Policy</span></span>

<span data-ttu-id="662ed-104">場所ポリシーは、拡張 9-1-1 (E9-1-1) を有効にするかどうか、E9-1-1 の使用方法、およびユーザーと連絡先での場所情報の使用方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="662ed-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="662ed-105">場所ポリシーには、グローバル ポリシーと、オプションで 1 つ以上のサイト ポリシーおよびユーザー ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="662ed-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="662ed-106">**グローバルポリシー:** グローバルポリシーは既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="662ed-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="662ed-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="662ed-108">グローバル ポリシーを削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="662ed-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="662ed-109">**サイトポリシー (オプション):** 1つ以上のサイトの場所のポリシーを作成できます。各ポリシーは特定のサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="662ed-110">サイトポリシーはグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="662ed-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="662ed-111">**ユーザーポリシー (オプション):** 1つまたは複数のユーザーの位置情報ポリシーを作成することができます。各ポリシーは特定のユーザーまたはユーザーのグループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="662ed-112">ユーザーポリシーはグローバルポリシーとサイトポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="662ed-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="662ed-113">場所ポリシーは、サブネットのグループであるネットワーク サイトに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="662ed-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="662ed-114">ネットワーク サイトに割り当てられた場所ポリシーは、他のすべてのユーザー ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="662ed-115">コマンドレットを使用して場所のポリシーをネットワークサイトに割り当てる方法について詳しくは、「 [Skype For Business Server 2015 でネットワークサイトに位置情報ポリシーを追加する](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="662ed-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="662ed-116">Skype for Business Server コントロールパネルを使用して場所のポリシーをネットワークサイトに割り当てる方法について詳しくは、「[ネットワークサイトを構成](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="662ed-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="662ed-117">[**場所ポリシー**] ページには、組織で定義されているすべての場所ポリシーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="662ed-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="662ed-118">Tasks you can perform</span></span>

<span data-ttu-id="662ed-119">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="662ed-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="662ed-120">新しいサイトの場所ポリシーまたはユーザーの場所ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="662ed-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="662ed-121">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="662ed-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="662ed-122">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="662ed-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="662ed-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="662ed-123">UI Reference</span></span>

<span data-ttu-id="662ed-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="662ed-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="662ed-125">**新規**新しいサイトの場所のポリシーまたはユーザーの場所のポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="662ed-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="662ed-126">**編集**選択した場所のポリシーを開いて編集するか、一覧からすべての場所のポリシーを選択するか、選択したサイトポリシーまたはユーザーポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="662ed-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="662ed-127">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="662ed-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="662ed-128">**更新**場所のポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="662ed-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="662ed-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="662ed-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="662ed-130">**名前**場所のポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="662ed-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="662ed-131">**スコープ**場所ポリシーのスコープ (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="662ed-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="662ed-132">**E9-1-1**この場所ポリシーが割り当てられているユーザーが E9 に対して有効になっているかどうかを確認しました。</span><span class="sxs-lookup"><span data-stu-id="662ed-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="662ed-133">**場所**クライアントが Skype for Business Server を新しい場所に登録したときに位置情報の入力を求めるメッセージを表示するかどうかを指定します。また、場所情報を入力せずに、ユーザーがメッセージを閉じると、免責事項が表示されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="662ed-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="662ed-134">**PSTN の利用状況**このプロファイルを使ってクライアントから緊急通話をルーティングするために使用される、公衆交換電話網 (PSTN) 使用法を指定します。</span><span class="sxs-lookup"><span data-stu-id="662ed-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="662ed-135">**E9-1-1**緊急サービスに接続するためにダイヤルされた番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="662ed-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="662ed-136">**E9 マスク**ユーザーがダイヤルする番号を指定します。これにより、緊急電話番号に変換されます。</span><span class="sxs-lookup"><span data-stu-id="662ed-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="662ed-137">エンタープライズ Voip サービスの機能と機能の詳細については、計画ドキュメントの「 [E9 の概要](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="662ed-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="662ed-138">場所ポリシーの使用の詳細については、「操作」のドキュメントの「[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="662ed-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


