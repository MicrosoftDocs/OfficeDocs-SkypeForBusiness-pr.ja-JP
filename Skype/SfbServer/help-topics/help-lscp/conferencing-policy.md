---
title: 会議ポリシー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: 会議ポリシーは、(ミーティングとも呼ばれます) 会議中にユーザーが利用可能なある機能を定義します。
ms.openlocfilehash: 62aa6dbe2c237cd27a1dc8798da70a68685640ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929091"
---
# <a name="conferencing-policy"></a><span data-ttu-id="05cdc-103">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="05cdc-103">Conferencing Policy</span></span>

<span data-ttu-id="05cdc-104">会議ポリシーは、(ミーティングとも呼ばれます) 会議中にユーザーが利用可能なある機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="05cdc-105">会議ポリシーには、グローバル ポリシーと、必要に応じて、1 つまたは複数のサイトとユーザーのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="05cdc-106">**グローバル ポリシー:** グローバル ポリシーが既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="05cdc-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="05cdc-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="05cdc-108">グローバル ポリシーを削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="05cdc-109">**サイトのポリシー (オプション):** 1 つまたは複数サイト会議ポリシーを特定のサイトに適用されるを作成します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="05cdc-110">サイト ポリシーは、グローバル ポリシーをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="05cdc-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="05cdc-111">**ユーザーのポリシー (オプション):** 1 つまたは複数のユーザー会議ポリシーを特定のユーザーまたはユーザー グループに適用されるを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="05cdc-112">ユーザー ポリシーは、グローバル ポリシーおよびサイト ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="05cdc-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="05cdc-113">**会議ポリシー**のページには、組織に対して定義されているすべての会議ポリシーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="05cdc-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="05cdc-114">Tasks you can perform</span></span>

<span data-ttu-id="05cdc-115">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="05cdc-116">新しいサイトの会議ポリシーまたはユーザーの会議ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="05cdc-117">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="05cdc-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="05cdc-118">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="05cdc-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="05cdc-119">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="05cdc-119">UI Reference</span></span>

<span data-ttu-id="05cdc-120">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="05cdc-121">**新しい**新しいサイトの会議ポリシーまたはユーザーの会議ポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="05cdc-122">**編集**編集するために選択した会議ポリシーを開き、一覧で、すべての会議ポリシーを選択または選択したサイト ポリシーまたはユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05cdc-123">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="05cdc-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="05cdc-124">**更新**会議ポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="05cdc-125">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="05cdc-126">**名**会議ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="05cdc-127">**スコープ**会議ポリシーのスコープを識別します。 グローバル、サイト、またはユーザー。</span><span class="sxs-lookup"><span data-stu-id="05cdc-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="05cdc-128">**共同作業データ**かどうか会議ポリシーでは、会議で共同作業データを許可することを指定を確認します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="05cdc-129">**アプリケーションの共有**かどうか会議ポリシーでは、会議のアプリケーション共有を許可することを指定を確認します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="05cdc-130">**オーディオ**会議ポリシーでは、会議でそのオーディオは許可されて指定かどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="05cdc-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="05cdc-131">**ビデオ**会議ポリシーでは、そのビデオは、会議で許可されて指定かどうかをチェックします。</span><span class="sxs-lookup"><span data-stu-id="05cdc-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="05cdc-132">**PSTN**PSTN ダイヤルイン会議が許可されているかどうか、会議ポリシーを指定を確認します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="05cdc-133">**記録**かどうか会議ポリシーでは、会議の記録を許可することを指定を確認します。</span><span class="sxs-lookup"><span data-stu-id="05cdc-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="05cdc-p104">会議の機能の詳細については、「計画」のドキュメントの「[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)」を参照してください。会議ポリシーの使用の詳細については、「操作」のドキュメントの「[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05cdc-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


