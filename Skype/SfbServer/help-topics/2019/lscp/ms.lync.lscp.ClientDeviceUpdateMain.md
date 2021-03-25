---
title: デバイス更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft は、サーバーにインポートしてユーザーに配布できる Skype for Business Phone Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースします。 最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページに移動し、Phone Edition を検索します。最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルが抽出された後、Import-CsDeviceUpdate コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル (このファイルの名前はUCUpdates.cab)。 詳細については、「Import-CsDeviceUpdate」を参照してください。
ms.openlocfilehash: f62ece38e33bfdc02a6110bb7cc4e53210c9b500
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120256"
---
# <a name="device-update"></a><span data-ttu-id="3bd1d-106">デバイス更新</span><span class="sxs-lookup"><span data-stu-id="3bd1d-106">Device Update</span></span>

<span data-ttu-id="3bd1d-107">Microsoft は、サーバーにインポートしてユーザーに配布できる Skype for Business Phone Edition のデバイス ファームウェア更新プログラムの新しいセットを定期的にリリースします。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="3bd1d-108">最新のデバイス更新ルールのセットを取得するには、Microsoft Web サイトの [ヘルプとサポート] ページに移動し、"Phone Edition" を検索します。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="3bd1d-109">最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="3bd1d-110">ファイルが抽出された後 **、Import-CsDeviceUpdate** コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル (このファイルの名前はUCUpdates.cab)。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="3bd1d-111">詳細については [、「Import-CsDeviceUpdate」を参照してください](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-111">For details, see [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="3bd1d-112">デバイス更新ルールをインポートした後、[デバイスの更新]ページを使用して、組織のデバイスのこれらのルールを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="3bd1d-113">ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3bd1d-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="3bd1d-114">Tasks you can perform</span></span>

<span data-ttu-id="3bd1d-115">[**デバイスの更新**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="3bd1d-116">一覧のデバイス更新を承認する。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="3bd1d-117">保留中のデバイス更新を取り消したり、元に戻したりする。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="3bd1d-118">一覧からデバイス更新を削除する。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3bd1d-119">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="3bd1d-119">UI Reference</span></span>

<span data-ttu-id="3bd1d-120">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="3bd1d-121">**編集** このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="3bd1d-122">**[すべて選択]** このオプションは、リスト内のすべてのデバイス更新プログラムを選択します。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="3bd1d-123">**削除** このオプションは、選択したデバイスの更新プログラムをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="3bd1d-124">**アクション** 一覧で 1 つ以上の更新プログラムを選択し、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="3bd1d-125">**保留中の更新プログラムのキャンセル** このオプションを使用すると、選択した更新プログラムが組織のデバイスに展開されません。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="3bd1d-126">**承認** このオプションを使用すると、選択した更新プログラムを組織のデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="3bd1d-127">**復元** このオプションを使用すると、以前に承認された更新プログラムを組織のデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="3bd1d-128">**更新** リストを更新して、すべてのデバイス更新プログラムの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="3bd1d-129">デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="3bd1d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bd1d-130">See also</span></span>

[<span data-ttu-id="3bd1d-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="3bd1d-131">Import-CsDeviceUpdate</span></span>](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)