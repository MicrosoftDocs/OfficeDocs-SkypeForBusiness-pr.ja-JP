---
title: テスト デバイスの新規作成または既存の編集
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: テスト デバイス機能はデバイス更新機能と連携して動作します。 [テスト デバイス] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。 デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。 テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。 デバイスを追加するとき、一覧に表示されます、[テスト デバイス] ページで、Skype のビジネス サーバーのコントロール パネルの。
ms.openlocfilehash: 7f622fc52fe9da95bff18bb3d93080d298a82890
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018993"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="f9c42-107">テスト デバイス: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="f9c42-107">Test Device: Create New or Edit Existing</span></span>
 
<span data-ttu-id="f9c42-108">テスト デバイス機能はデバイス更新機能と連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="f9c42-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="f9c42-109">[**テスト デバイス**] ページにテスト デバイスを追加すると、新しい更新プログラムをプロダクション デバイスに展開する前に、このデバイスを使用して更新プログラムの機能を検証できます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="f9c42-110">デバイスをグローバルに (環境全体を使用して) テストしたり、単独のサイト内でテストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="f9c42-111">テスト デバイスは、そのメディア アクセス制御 (MAC) アドレスまたはシリアル番号で識別します。</span><span class="sxs-lookup"><span data-stu-id="f9c42-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="f9c42-112">デバイスを追加するとき、一覧に表示されます、[**テスト デバイス**] ページで、Skype のビジネス サーバーのコントロール パネルの。</span><span class="sxs-lookup"><span data-stu-id="f9c42-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f9c42-113">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="f9c42-113">Tasks you can perform</span></span>

<span data-ttu-id="f9c42-114">[**新規 テスト デバイス**] または [**編集 テスト デバイス**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>
  
- <span data-ttu-id="f9c42-115">新しいテスト デバイスを追加する。</span><span class="sxs-lookup"><span data-stu-id="f9c42-115">Add a new test device.</span></span>
    
- <span data-ttu-id="f9c42-116">既存のテスト デバイスのプロパティを変更する。</span><span class="sxs-lookup"><span data-stu-id="f9c42-116">Modify the properties of an existing test device.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="f9c42-117">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="f9c42-117">UI Reference</span></span>

<span data-ttu-id="f9c42-118">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="f9c42-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="f9c42-119">**スコープ**テスト デバイスのスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="f9c42-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>
    
- <span data-ttu-id="f9c42-120">**名**追加したり、テスト デバイスの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-120">**Name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="f9c42-121">**デバイス名**追加したり、テスト デバイスの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-121">**Device name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="f9c42-122">**識別子の種類**使用して、次のいずれかを選択してデバイスを識別する方法を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>
    
  - <span data-ttu-id="f9c42-123">**MAC アドレス**</span><span class="sxs-lookup"><span data-stu-id="f9c42-123">**MAC address**</span></span>
    
  - <span data-ttu-id="f9c42-124">**シリアル番号**</span><span class="sxs-lookup"><span data-stu-id="f9c42-124">**Serial number**</span></span>
    
- <span data-ttu-id="f9c42-125">**一意識別子**MAC アドレスまたはデバイスのシリアル番号を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="f9c42-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>
    
<span data-ttu-id="f9c42-126">デバイスのテストについての詳細は、操作マニュアルの[更新プログラムの機能をテストするデバイスの追加](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9c42-126">For details about testing devices, see [Add a Device to Test Update Functionality](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="f9c42-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9c42-127">See also</span></span>

[<span data-ttu-id="f9c42-128">テスト デバイス</span><span class="sxs-lookup"><span data-stu-id="f9c42-128">Test Device</span></span>](ms.lync.lscp.ClientDeviceTestMain.md)

[<span data-ttu-id="f9c42-129">新しい-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f9c42-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="f9c42-130">セット CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f9c42-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="f9c42-131">組織内のデバイスのソフトウェア更新プログラムを表示</span><span class="sxs-lookup"><span data-stu-id="f9c42-131">View Software Updates for Devices in Your Organization</span></span>](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)