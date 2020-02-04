---
title: 会議ポリシー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: 会議ポリシーは、会議中にユーザーが利用できる機能 (会議とも呼ばれます) を定義します。
ms.openlocfilehash: 6d6795d1aa36dbbfe0bb43fb884102fdf224cded
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705072"
---
# <a name="conferencing-policy"></a><span data-ttu-id="76e5c-103">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="76e5c-103">Conferencing Policy</span></span>

<span data-ttu-id="76e5c-104">会議ポリシーは、会議中にユーザーが利用できる機能 (会議とも呼ばれます) を定義します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="76e5c-105">会議ポリシーには、グローバルポリシーと、必要に応じて1つまたは複数のサイトとユーザーのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="76e5c-106">**グローバルポリシー:** グローバルポリシーは既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="76e5c-107">グローバル ポリシーは編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="76e5c-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="76e5c-108">グローバル ポリシーを削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="76e5c-109">**サイトポリシー (オプション):** 1つ以上のサイト会議のポリシーを作成し、それぞれのポリシーを特定のサイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="76e5c-110">サイトポリシーはグローバルポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="76e5c-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="76e5c-111">**ユーザーポリシー (オプション):** 1つまたは複数のユーザー会議のポリシーを作成し、それぞれに特定のユーザーまたはユーザーグループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="76e5c-112">ユーザーポリシーはグローバルポリシーとサイトポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="76e5c-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="76e5c-113">[**会議ポリシー** ] ページには、組織で定義されているすべての会議ポリシーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="76e5c-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="76e5c-114">Tasks you can perform</span></span>

<span data-ttu-id="76e5c-115">[**場所ポリシー**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="76e5c-116">新しいサイト会議ポリシーまたはユーザー会議ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="76e5c-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="76e5c-117">グローバル ポリシーまたは既存のサイト ポリシーやユーザー ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="76e5c-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="76e5c-118">サイト ポリシーやユーザー ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="76e5c-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="76e5c-119">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="76e5c-119">UI Reference</span></span>

<span data-ttu-id="76e5c-120">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="76e5c-121">**新規**新しいサイト会議ポリシーまたはユーザー会議ポリシーを開始します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="76e5c-122">**編集**選択された会議ポリシーを開いて編集するか、リスト内のすべての会議ポリシーを選択するか、選択したサイトポリシーまたはユーザーポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="76e5c-123">グローバル ポリシーに対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="76e5c-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="76e5c-124">**更新**会議のポリシーの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="76e5c-125">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="76e5c-126">**名前**会議ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="76e5c-127">**スコープ**会議ポリシーのスコープ (グローバル、サイト、またはユーザー) を識別します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="76e5c-128">**データの共同作業**会議ポリシーでデータの共同作業が会議で許可されていることを指定しているかどうかを確認しました。</span><span class="sxs-lookup"><span data-stu-id="76e5c-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="76e5c-129">**アプリケーション共有**会議ポリシーによってアプリケーションの共有が会議で許可されているかどうかが確認されました。</span><span class="sxs-lookup"><span data-stu-id="76e5c-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="76e5c-130">**オーディオ**会議ポリシーで、音声が会議で許可されていることを指定しているかどうかを確認しました。</span><span class="sxs-lookup"><span data-stu-id="76e5c-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="76e5c-131">**ビデオ**会議ポリシーで、ビデオが会議で許可されていることを指定しているかどうかを確認しました。</span><span class="sxs-lookup"><span data-stu-id="76e5c-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="76e5c-132">**PSTN**会議ポリシーで PSTN ダイヤルイン会議が許可されているかどうかを確認しました。</span><span class="sxs-lookup"><span data-stu-id="76e5c-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="76e5c-133">**レコーディング**会議ポリシーでレコーディングが許可されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="76e5c-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="76e5c-p104">会議の機能の詳細については、「計画」のドキュメントの「[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)」を参照してください。会議ポリシーの使用の詳細については、「操作」のドキュメントの「[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76e5c-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


