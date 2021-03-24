---
title: テスト デバイス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロール パネルの [テスト デバイス] ページの一覧にデバイスが表示されます。'
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099353"
---
# <a name="test-device"></a><span data-ttu-id="71d03-106">テスト デバイス</span><span class="sxs-lookup"><span data-stu-id="71d03-106">Test Device</span></span>

<span data-ttu-id="71d03-107">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="71d03-108">デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。</span><span class="sxs-lookup"><span data-stu-id="71d03-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="71d03-109">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="71d03-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="71d03-110">デバイスを追加すると、Skype for Business Server コントロールパネルの [テスト デバイス] ページの一覧にデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71d03-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="71d03-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="71d03-111">Tasks you can perform</span></span>

<span data-ttu-id="71d03-112">[テスト デバイス] ページで次のタスク **を実行** できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="71d03-113">テスト デバイスをグローバルまたは特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="71d03-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="71d03-114">既存のテスト デバイスのオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="71d03-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="71d03-115">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="71d03-115">UI Reference</span></span>

<span data-ttu-id="71d03-116">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="71d03-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="71d03-117">**New** 次のスコープを持つ新しいテスト デバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="71d03-118">グローバル</span><span class="sxs-lookup"><span data-stu-id="71d03-118">Global</span></span>

  - <span data-ttu-id="71d03-119">サイト</span><span class="sxs-lookup"><span data-stu-id="71d03-119">Site</span></span>

- <span data-ttu-id="71d03-120">**編集** リスト内のテスト デバイスのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="71d03-121">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="71d03-122">**詳細の表示** このオプションは、テスト デバイスのオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="71d03-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="71d03-123">**[すべて選択]** このオプションは、リスト内のすべてのテスト デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="71d03-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="71d03-124">**削除** このオプションは、選択したテスト デバイスをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="71d03-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="71d03-125">**更新** テスト デバイスの一覧を更新して、すべてのテスト デバイスのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="71d03-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="71d03-126">デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71d03-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="71d03-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="71d03-127">See also</span></span>

[<span data-ttu-id="71d03-128">テスト デバイス: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="71d03-128">Test Device: Create New or Edit Existing</span></span>](test-device-create-new-or-edit-existing.md)

[<span data-ttu-id="71d03-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="71d03-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="71d03-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="71d03-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="71d03-131">組織内のデバイスのソフトウェア更新プログラムを表示する</span><span class="sxs-lookup"><span data-stu-id="71d03-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)