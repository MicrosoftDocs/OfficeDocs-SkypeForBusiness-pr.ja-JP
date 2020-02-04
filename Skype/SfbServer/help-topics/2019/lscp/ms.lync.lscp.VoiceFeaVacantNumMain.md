---
title: 割り当てられていない電話番号
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690392"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="b2124-104">割り当てられていない電話番号</span><span class="sxs-lookup"><span data-stu-id="b2124-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="b2124-105">Skype for business 2019 を Exchange 2013 または Exchange 2016 と統合すると、exchange UM は Skype for Business Server 2019 で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b2124-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="b2124-106">Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を利用して、Exchange UM との統合を強調することができます。</span><span class="sxs-lookup"><span data-stu-id="b2124-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="b2124-p103">未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b2124-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="b2124-p104">割り当てられていない番号の表の構成方法は、その使用方法によって異なります。組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を調整できます。たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2124-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2124-115">未使用の番号の表を構成する前に、アナウンスを 1 つ以上既に定義しているか、Exchange UM の自動応答を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2124-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="b2124-116">[**未使用の番号**] ページには、組織で定義されている未使用の番号の範囲が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2124-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b2124-117">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="b2124-117">Tasks you can perform</span></span>

<span data-ttu-id="b2124-118">[**未使用の番号**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2124-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="b2124-119">未使用の番号範囲を作成する</span><span class="sxs-lookup"><span data-stu-id="b2124-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="b2124-120">既存の未使用の番号範囲を変更する</span><span class="sxs-lookup"><span data-stu-id="b2124-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="b2124-121">未使用の番号範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="b2124-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="b2124-122">未使用の番号範囲の順序を変更し、未使用の番号に一致する着信に最初に適用するアクションを決定する</span><span class="sxs-lookup"><span data-stu-id="b2124-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b2124-123">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="b2124-123">UI Reference</span></span>

<span data-ttu-id="b2124-124">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="b2124-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="b2124-125">**新規**未使用の新しい番号範囲を開始します。</span><span class="sxs-lookup"><span data-stu-id="b2124-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="b2124-126">**編集**選択されている未使用の番号範囲を編集するために開きます。リスト内の未割り当ての番号範囲をすべて選択するか、選択されていない番号範囲を削除します。</span><span class="sxs-lookup"><span data-stu-id="b2124-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="b2124-127">**上へ移動**リスト内の指定されていない番号範囲を上に移動して、Skype for Business Server がすぐに検索し、指定されたアクションを適用してから、リスト内の他の範囲に対して指定されたアクションを適用します。</span><span class="sxs-lookup"><span data-stu-id="b2124-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2124-128">Skype for Business Server は、割り当てられていない番号テーブルを上から下に検索し、割り当てられていない番号に一致する最初の範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2124-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="b2124-129">たとえば、最後の手段のアクションを指定している範囲がある場合は、その範囲を一覧の一番下に置くようにします。</span><span class="sxs-lookup"><span data-stu-id="b2124-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="b2124-130">**下へ移動**選択されている未使用の番号範囲を一覧の下方向に移動します。</span><span class="sxs-lookup"><span data-stu-id="b2124-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="b2124-131">**すべてコミット**未割り当ての番号範囲に加えたすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="b2124-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b2124-132">このコマンドは、[**新規 未使用の番号範囲**] ページと [**編集 未使用の番号範囲**] ページで行われたすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="b2124-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="b2124-133">**更新**割り当てられていない番号範囲の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="b2124-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="b2124-134">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="b2124-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b2124-135">**名前**割り当てられていない番号の範囲を識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="b2124-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="b2124-136">**都道府県**データベースに保存されていて、何の範囲に保存されていないかを示します。</span><span class="sxs-lookup"><span data-stu-id="b2124-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="b2124-137">**開始範囲**割り当てられていない数値の範囲の開始番号。</span><span class="sxs-lookup"><span data-stu-id="b2124-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="b2124-138">**範囲の終了**割り当てられていない数値の範囲の終了番号。</span><span class="sxs-lookup"><span data-stu-id="b2124-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="b2124-139">**宛先**この範囲の未使用の番号への着信通話を処理するアナウンスメントアプリケーションをホストするアプリケーションサービスのサービス ID です。</span><span class="sxs-lookup"><span data-stu-id="b2124-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="b2124-140">**お知らせ**この範囲の未割り当ての番号に対して再生されるお知らせ。</span><span class="sxs-lookup"><span data-stu-id="b2124-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="b2124-141">お知らせ機能と機能の詳細については、計画ドキュメントの「 [Skype For business のアナウンスメントアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2124-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="b2124-142">未使用の番号範囲の使用の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2124-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


