---
title: デバイス更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Microsoft は、Skype for Business Phone Edition 用の新しいデバイスファームウェア更新プログラムセットを定期的にリリースします。これにより、サーバーにインポートして、ユーザーに配布することができます。 最新のデバイス更新ルールを取得するには、Microsoft web サイトの [ヘルプとサポート] ページに移動して、[電話] エディションを検索します。最新の更新プログラムパッケージをダウンロードし、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。 ファイルを抽出した後、インポート-CsDeviceUpdate コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル ("UCUpdates .cab" という名前が付いています)。 詳細については、「CsDeviceUpdate のインポート」を参照してください。
ms.openlocfilehash: d4baa87c615189fbe784ba7ce63487107fd56355
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794516"
---
# <a name="device-update"></a><span data-ttu-id="c5abc-106">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="c5abc-106">Device Update</span></span>

<span data-ttu-id="c5abc-107">Microsoft は、Skype for Business Phone Edition 用の新しいデバイスファームウェア更新プログラムセットを定期的にリリースします。これにより、サーバーにインポートして、ユーザーに配布することができます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="c5abc-108">最新のデバイス更新ルールを取得するには、Microsoft web サイトの [ヘルプとサポート] ページにアクセスし、"Phone Edition" を検索します。</span><span class="sxs-lookup"><span data-stu-id="c5abc-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="c5abc-109">最新の更新プログラムパッケージをダウンロードして、更新プログラムをアップロードするコンピューター上のフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c5abc-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="c5abc-110">ファイルを抽出した後、**インポート-CsDeviceUpdate**コマンドレットを使用して、抽出されたデバイス更新ルールをインポートできます。CAB ファイル ("UCUpdates .cab" という名前が付いています)。</span><span class="sxs-lookup"><span data-stu-id="c5abc-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="c5abc-111">詳細については、「 [CsDeviceUpdate のインポート](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5abc-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="c5abc-112">デバイス更新ルールをインポートした後、[**デバイス更新**] ページを使用して、組織のデバイスのこれらのルールを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="c5abc-113">ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c5abc-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="c5abc-114">Tasks you can perform</span></span>

<span data-ttu-id="c5abc-115">[**デバイスの更新**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="c5abc-116">一覧のデバイス更新を承認する。</span><span class="sxs-lookup"><span data-stu-id="c5abc-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="c5abc-117">保留中のデバイス更新を取り消したり、元に戻したりする。</span><span class="sxs-lookup"><span data-stu-id="c5abc-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="c5abc-118">一覧からデバイス更新を削除する。</span><span class="sxs-lookup"><span data-stu-id="c5abc-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c5abc-119">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="c5abc-119">UI Reference</span></span>

<span data-ttu-id="c5abc-120">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="c5abc-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c5abc-121">**編集**このオプションを使うと、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="c5abc-122">**すべて選択**このオプションでは、一覧にあるすべてのデバイスの更新が選択されます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="c5abc-123">**削除**このオプションでは、選択したすべてのデバイスの更新を削除します。</span><span class="sxs-lookup"><span data-stu-id="c5abc-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="c5abc-124">**操作**リストで1つまたは複数の更新を選択して、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="c5abc-125">**保留中の更新をキャンセル**するこのオプションでは、選択した更新プログラムが組織のデバイスに展開されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c5abc-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="c5abc-126">**承認**このオプションでは、選択した更新プログラムを組織のデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="c5abc-127">**復元**このオプションでは、以前に承認された更新を組織のデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="c5abc-128">**更新**リストを更新して、すべてのデバイスの更新の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c5abc-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="c5abc-129">デバイス更新 Web サービスの詳細については、「計画」のドキュメントの「[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5abc-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="c5abc-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5abc-130">See also</span></span>

[<span data-ttu-id="c5abc-131">インポート-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="c5abc-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
