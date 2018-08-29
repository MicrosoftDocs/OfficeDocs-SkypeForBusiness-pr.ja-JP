---
title: 会議の構成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 会議の構成設定は、ユーザーが作成、および匿名ユーザーやダイヤルイン会議のユーザーがこれらの会議に参加できますか (またはかどうか) を制御することができます (また calledmeetings) の会議の種類を定義します。 これらの設定はスケジュール設定された会議にのみ適用されます。 これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。
ms.openlocfilehash: 7d815877375759a45de4df6543eca8ef82af1481
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244210"
---
# <a name="meeting-configuration"></a><span data-ttu-id="2b1bc-105">会議の構成</span><span class="sxs-lookup"><span data-stu-id="2b1bc-105">Meeting Configuration</span></span>

<span data-ttu-id="2b1bc-p102">会議の構成設定では、ユーザーが作成できる会議 ("ミーティング" とも呼ばれます) の種類を定義でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについて) 制御できます。これらの設定はスケジュール設定された会議にのみ適用されます。これらの設定は、クライアントで [今すぐミーティング] オプションをクリックして作成された臨時の会議には適用されません。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="2b1bc-109">会議の構成は、グローバル、サイト、またはプールのレベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="2b1bc-110">**グローバル会議構成:** グローバル会議構成が既定で作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="2b1bc-111">グローバルな会議の構成は編集できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="2b1bc-112">グローバルな会議の構成を削除しようとすると、設定がすべて既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="2b1bc-113">**サイトの会議構成 (オプション):** 1 つを作成することができます。 または会議の構成以上のサイトでは、それぞれの特定のサイトに適用します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="2b1bc-114">サイト構成では、グローバル構成をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="2b1bc-115">**プール会議の構成 (オプション):** 1 つを作成することができますか、特定のプールに適用されるそれぞれの会議の構成、複数のプールです。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="2b1bc-116">プールの構成は、サイト構成、グローバル設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="2b1bc-117">[**会議の構成**] ページには、組織で定義されているすべての会議の構成が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2b1bc-118">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="2b1bc-118">Tasks you can perform</span></span>

<span data-ttu-id="2b1bc-119">[**会議の構成**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="2b1bc-120">新しいサイトの会議の構成またはプールの会議の構成を作成する</span><span class="sxs-lookup"><span data-stu-id="2b1bc-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="2b1bc-121">グローバルな構成、既存のサイトの構成、またはプールの構成を変更する</span><span class="sxs-lookup"><span data-stu-id="2b1bc-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="2b1bc-122">サイトの構成またはプールの構成を削除する</span><span class="sxs-lookup"><span data-stu-id="2b1bc-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2b1bc-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="2b1bc-123">UI Reference</span></span>

<span data-ttu-id="2b1bc-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="2b1bc-125">**新しい**新しいサイトの会議構成またはプールの会議の構成を開始します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="2b1bc-126">**編集**編集するために選択した会議の構成を開き、一覧で、会議のすべての構成を選択または、選択したサイトまたはプール構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b1bc-127">グローバルな会議の構成に対して [**削除**] を使用すると、設定が既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="2b1bc-128">**更新**会議の構成の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="2b1bc-129">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2b1bc-130">**名**会議の構成を識別します。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="2b1bc-131">**スコープ**会議の構成のスコープを識別します。 グローバル、サイト、またはプール。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="2b1bc-132">会議の構成の操作の詳細についてを参照してください[を作成する、または会議の構成設定のコレクションを変更する](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)の操作マニュアルを参照。</span><span class="sxs-lookup"><span data-stu-id="2b1bc-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


