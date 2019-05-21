---
title: テスト デバイス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: '[テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [テストデバイス] ページの一覧に表示されます。'
ms.openlocfilehash: 223efaf8a72c5ea0b7922a28b1dc26a6395e43ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293201"
---
# <a name="test-device"></a><span data-ttu-id="13af2-106">テスト デバイス</span><span class="sxs-lookup"><span data-stu-id="13af2-106">Test Device</span></span>

<span data-ttu-id="13af2-107">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="13af2-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="13af2-108">デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="13af2-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="13af2-109">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="13af2-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="13af2-110">デバイスを追加すると、そのデバイスは、Skype for Business Server コントロールパネルの [**テストデバイス**] ページの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="13af2-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="13af2-111">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="13af2-111">Tasks you can perform</span></span>

<span data-ttu-id="13af2-112">**テストデバイス**ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="13af2-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="13af2-113">テストデバイスをグローバルに、または特定のサイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="13af2-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="13af2-114">既存のテストデバイスのオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="13af2-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="13af2-115">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="13af2-115">UI Reference</span></span>

<span data-ttu-id="13af2-116">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="13af2-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="13af2-117">**新規**次のスコープを使用して、新しいテストデバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="13af2-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="13af2-118">グローバル</span><span class="sxs-lookup"><span data-stu-id="13af2-118">Global</span></span>

  - <span data-ttu-id="13af2-119">サイト</span><span class="sxs-lookup"><span data-stu-id="13af2-119">Site</span></span>

- <span data-ttu-id="13af2-120">**編集**リスト内のテストデバイスのオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="13af2-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="13af2-121">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="13af2-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="13af2-122">**詳細を表示**このオプションを選択すると、テストデバイスのオプションを変更できるダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="13af2-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="13af2-123">**すべて選択**このオプションでは、リスト内のすべてのテストデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="13af2-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="13af2-124">**削除**このオプションでは、選択したすべてのテストデバイスを削除します。</span><span class="sxs-lookup"><span data-stu-id="13af2-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="13af2-125">**更新**テストデバイスの一覧を更新して、すべてのテストデバイスのオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="13af2-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="13af2-126">デバイスのテストの詳細については、「操作」のドキュメントの「[Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13af2-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="13af2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="13af2-127">See also</span></span>

[<span data-ttu-id="13af2-128">テスト デバイス: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="13af2-128">Test Device: Create New or Edit Existing</span></span>](test-device-create-new-or-edit-existing.md)

[<span data-ttu-id="13af2-129">新規-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="13af2-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="13af2-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="13af2-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="13af2-131">組織内のデバイスのソフトウェア更新プログラムを表示する</span><span class="sxs-lookup"><span data-stu-id="13af2-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
