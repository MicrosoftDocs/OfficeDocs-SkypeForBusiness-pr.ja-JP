---
title: 割り当てられていない電話番号
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826887"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="a5000-104">割り当てられていない電話番号</span><span class="sxs-lookup"><span data-stu-id="a5000-104">Unassigned Phone Number</span></span>

<span data-ttu-id="a5000-p102">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5000-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="a5000-p103">割り当てられていない番号の表の構成方法はその使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を調整できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a5000-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5000-113">未使用の番号の表を構成する前に、アナウンスを 1 つ以上既に定義しているか、Exchange UM の自動応答を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5000-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="a5000-114">[**未使用の番号**] ページには、組織で定義されている未使用の番号の範囲が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5000-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a5000-115">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="a5000-115">Tasks you can perform</span></span>

<span data-ttu-id="a5000-116">[**未使用の番号**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a5000-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="a5000-117">未使用の番号範囲を作成する</span><span class="sxs-lookup"><span data-stu-id="a5000-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="a5000-118">既存の未使用の番号範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="a5000-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="a5000-119">未使用の番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="a5000-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="a5000-120">未使用の番号範囲の順序を変更し、未使用の番号に一致する着信に最初に適用するアクションを決定する</span><span class="sxs-lookup"><span data-stu-id="a5000-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a5000-121">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="a5000-121">UI Reference</span></span>

<span data-ttu-id="a5000-122">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="a5000-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="a5000-123">**新規** 新しい割り当てられていない番号範囲を開始します。</span><span class="sxs-lookup"><span data-stu-id="a5000-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="a5000-124">**編集** 選択した割り当てられていない番号範囲を編集用に開き、一覧内のすべての割り当てられていない番号範囲を選択するか、選択した割り当てられていない番号範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="a5000-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="a5000-125">**上へ移動** 選択した割り当てられていない番号範囲を一覧内で上に移動し、Skype for Business Server が一覧内の他の範囲に指定されたアクションを適用する前に、指定されたアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5000-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a5000-126">Skype for Business Server は、割り当てられていない番号の表を上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5000-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="a5000-127">たとえば、最後のアクションを指定している範囲がある場合は、その範囲が一覧の一番下にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5000-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="a5000-128">**下へ移動** 選択した割り当てられていない番号範囲をリスト内で下に移動します。</span><span class="sxs-lookup"><span data-stu-id="a5000-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="a5000-129">**すべて確定** 割り当てられていない番号範囲に加えたすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a5000-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a5000-130">このコマンドは、[**新規 未使用の番号範囲**] ページと [**編集 未使用の番号範囲**] ページで行われたすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a5000-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="a5000-131">**更新** 割り当てられていない番号範囲の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="a5000-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="a5000-132">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="a5000-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a5000-133">**名前** 割り当てられていない番号範囲を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="a5000-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="a5000-134">**State** データベースに保存されている番号範囲と保存されていない番号範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="a5000-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="a5000-135">**開始範囲** 割り当てられていない番号範囲の開始番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5000-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="a5000-136">**終了範囲** 割り当てられていない番号範囲の終了番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5000-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="a5000-137">**Destination** この割り当てられていない番号範囲への着信呼び出しを処理するアナウンス アプリケーションをホストするアプリケーション サービスのサービス ID。</span><span class="sxs-lookup"><span data-stu-id="a5000-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="a5000-138">**アナウンス** この割り当てられていない番号の範囲で再生されるアナウンス。</span><span class="sxs-lookup"><span data-stu-id="a5000-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="a5000-139">アナウンスの機能の詳細については、「計画」のドキュメントの [「Plan for the Announcement application in Skype for Business 2015」](../../plan-your-deployment/enterprise-voice-solution/announcement.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5000-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="a5000-140">未使用の番号範囲の操作の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5000-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


