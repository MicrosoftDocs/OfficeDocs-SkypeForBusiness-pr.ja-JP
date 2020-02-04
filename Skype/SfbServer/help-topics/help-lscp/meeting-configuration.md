---
title: 会議の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 会議構成の設定では、ユーザーが作成できる電話会議の種類を定義し、匿名ユーザーとダイヤルイン会議ユーザーが会議に参加できるようにするかどうかを制御します。 これらの設定はスケジュール設定された会議にのみ適用されます。 これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。
ms.openlocfilehash: 5e4d0b11bc169b7658061e33fdfb8ddf0bd4b044
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700042"
---
# <a name="meeting-configuration"></a><span data-ttu-id="801d5-105">会議の構成</span><span class="sxs-lookup"><span data-stu-id="801d5-105">Meeting Configuration</span></span>

<span data-ttu-id="801d5-p102">会議の構成設定では、ユーザーが作成できる会議 ("ミーティング" とも呼ばれます) の種類を定義でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについて) 制御できます。これらの設定はスケジュール設定された会議にのみ適用されます。これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。</span><span class="sxs-lookup"><span data-stu-id="801d5-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="801d5-109">会議の構成は、グローバル、サイト、またはプールのレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="801d5-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="801d5-110">**グローバル会議の構成:** 既定では、グローバル会議の設定が作成されます。</span><span class="sxs-lookup"><span data-stu-id="801d5-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="801d5-111">グローバルな会議の構成は編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="801d5-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="801d5-112">グローバルな会議の構成を削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="801d5-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="801d5-113">**サイト会議の構成 (オプション):** 1つ以上のサイト会議の構成を作成し、それぞれが特定のサイトに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="801d5-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="801d5-114">サイト構成はグローバル構成よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="801d5-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="801d5-115">**プール会議の構成 (オプション):** 1つまたは複数のプール会議の構成を作成し、それぞれが特定のプールに適用されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="801d5-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="801d5-116">プール構成は、グローバル構成とサイト構成よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="801d5-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="801d5-117">[**会議の構成**] ページには、組織で定義されているすべての会議の構成が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="801d5-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="801d5-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="801d5-118">Tasks you can perform</span></span>

<span data-ttu-id="801d5-119">[**会議の構成**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="801d5-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="801d5-120">新しいサイトの会議の構成またはプールの会議の構成を作成する</span><span class="sxs-lookup"><span data-stu-id="801d5-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="801d5-121">グローバルな構成、既存のサイトの構成、またはプールの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="801d5-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="801d5-122">サイトの構成またはプールの構成を削除する</span><span class="sxs-lookup"><span data-stu-id="801d5-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="801d5-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="801d5-123">UI Reference</span></span>

<span data-ttu-id="801d5-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="801d5-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="801d5-125">**新規**新しいサイト会議の構成またはプールの会議の構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="801d5-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="801d5-126">**編集**選択した会議の設定を開いて編集するか、リスト内のすべての会議の構成を選択するか、選択したサイト構成またはプール構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="801d5-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="801d5-127">グローバルな会議の構成に対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="801d5-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="801d5-128">**更新**会議の構成の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="801d5-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="801d5-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="801d5-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="801d5-130">**名前**会議の構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="801d5-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="801d5-131">**スコープ**会議の構成の範囲 (グローバル、サイト、またはプール) を特定します。</span><span class="sxs-lookup"><span data-stu-id="801d5-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="801d5-132">会議の構成の使用の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="801d5-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


