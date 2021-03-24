---
title: Test Device Create New or Edit Existing
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: テスト デバイス機能はデバイス更新機能と連携して動作します。 [テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、Skype for Business Server コントロール パネルの [テスト デバイス] ページの一覧にデバイスが表示されます。
ms.openlocfilehash: 959abca17e208a397cbdd9ad6a69ba241aad4362
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100633"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="20578-107">テスト デバイス: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="20578-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="20578-108">テスト デバイス機能はデバイス更新機能と連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="20578-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="20578-109">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="20578-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="20578-110">デバイスは、グローバル (環境全体を通じて) または 1 つのサイト内でテストできます。</span><span class="sxs-lookup"><span data-stu-id="20578-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="20578-111">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="20578-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="20578-112">デバイスを追加すると、Skype for Business Server コントロールパネルの [テスト デバイス] ページの一覧にデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20578-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="20578-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="20578-113">Tasks you can perform</span></span>

<span data-ttu-id="20578-114">[**新規 テスト デバイス**] または [**編集 テスト デバイス**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20578-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="20578-115">新しいテスト デバイスを追加する。</span><span class="sxs-lookup"><span data-stu-id="20578-115">Add a new test device.</span></span>

- <span data-ttu-id="20578-116">既存のテスト デバイスのプロパティを変更する。</span><span class="sxs-lookup"><span data-stu-id="20578-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="20578-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="20578-117">UI Reference</span></span>

<span data-ttu-id="20578-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="20578-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="20578-119">**スコープ** テスト デバイスのスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="20578-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="20578-120">**名前** テスト デバイスの名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="20578-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="20578-121">**デバイス名** テスト デバイスの名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="20578-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="20578-122">**識別子の種類** デバイスの識別に使用する方法を選択するには、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="20578-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="20578-123">**MAC アドレス**</span><span class="sxs-lookup"><span data-stu-id="20578-123">**MAC address**</span></span>

  - <span data-ttu-id="20578-124">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="20578-124">**Serial number**</span></span>

- <span data-ttu-id="20578-125">**一意識別子** デバイスの MAC アドレスまたはシリアル番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="20578-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="20578-126">デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20578-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="20578-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="20578-127">See also</span></span>

[<span data-ttu-id="20578-128">テスト デバイス</span><span class="sxs-lookup"><span data-stu-id="20578-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="20578-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="20578-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="20578-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="20578-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="20578-131">組織内のデバイスのソフトウェア更新プログラムを表示する</span><span class="sxs-lookup"><span data-stu-id="20578-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)