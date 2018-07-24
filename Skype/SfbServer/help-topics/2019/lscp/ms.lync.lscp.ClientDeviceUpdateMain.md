---
title: デバイス更新
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: マイクロソフトは定期的に、ビジネス電話編集用に、サーバーにインポートし、ユーザーに配布する、Skype のデバイスのファームウェアの更新プログラムの新しいセットを解放します。 最新の更新プログラム パッケージに、ヘルプとサポート] ページに、マイクロソフト web サイトに、forPhone Edition.Download を検索してデバイス更新ルールの最新のセットを取得し、更新プログラムをアップロードするは、コンピューターのフォルダーにファイルを抽出できます。 ファイルが抽出されたら、抽出したにデバイス更新ルールをインポートするインポート CsDeviceUpdate コマンドレットを使用できます。CAB ファイルの名前は UCUpdates.cab)。 詳細については、インポートの CsDeviceUpdate を参照してください。
ms.openlocfilehash: 3c8ddfbaeabb2b70fcc2661271573ea4a7f62036
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967863"
---
# <a name="device-update"></a><span data-ttu-id="7a1d8-106">デバイスの更新</span><span class="sxs-lookup"><span data-stu-id="7a1d8-106">Device Update</span></span>
 
<span data-ttu-id="7a1d8-107">マイクロソフトは定期的に、ビジネス電話編集用に、サーバーにインポートし、ユーザーに配布する、Skype のデバイスのファームウェアの更新プログラムの新しいセットを解放します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="7a1d8-108">デバイス更新ルールの最新のセットを取得するには、ヘルプとサポート] ページに、マイクロソフト web サイトに、「電話のエディション」を検索します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="7a1d8-109">最新の更新プログラム パッケージをダウンロードし、更新プログラムをアップロードするは、コンピューターのフォルダーにファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="7a1d8-110">ファイルが抽出されたら、抽出したにデバイス更新ルールをインポートする**インポート CsDeviceUpdate**コマンドレットを使用できます。CAB ファイルの名前は UCUpdates.cab)。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="7a1d8-111">詳細については、[インポートの CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>
  
<span data-ttu-id="7a1d8-112">デバイス更新ルールをインポートした後は、表示して、組織のデバイスにこれらのルールを管理する**デバイスの更新**] ページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>
  
> [!TIP]
> <span data-ttu-id="7a1d8-113">ファームウェア更新をテストし、テストが正常なことを確認してから、組織で使用中のすべての関連デバイスに対して更新を使用可能にできます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="7a1d8-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="7a1d8-114">Tasks you can perform</span></span>

<span data-ttu-id="7a1d8-115">[**デバイスの更新**] ページでは次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-115">You can perform the following tasks on the **Device Update** page:</span></span>
  
- <span data-ttu-id="7a1d8-116">一覧のデバイス更新を承認する。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-116">Approve device updates in the list.</span></span>
    
- <span data-ttu-id="7a1d8-117">保留中のデバイス更新を取り消したり、元に戻したりする。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-117">Cancel or restore pending device updates.</span></span>
    
- <span data-ttu-id="7a1d8-118">一覧からデバイス更新を削除する。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-118">Delete device updates from the list.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="7a1d8-119">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="7a1d8-119">UI Reference</span></span>

<span data-ttu-id="7a1d8-120">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="7a1d8-121">**編集**このオプションを使用すると、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-121">**Edit** You can use this option to do the following:</span></span>
    
  - <span data-ttu-id="7a1d8-122">**すべてを選択**一覧にすべてのデバイスの更新プログラムを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-122">**Select All** This option selects all device updates in the list.</span></span>
    
  - <span data-ttu-id="7a1d8-123">**削除**このオプションは、選択したデバイスのすべての更新プログラムを削除します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-123">**Delete** This option deletes all selected device updates.</span></span>
    
- <span data-ttu-id="7a1d8-124">**アクション**リストで 1 つまたは複数の更新プログラムを選択し、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>
    
  - <span data-ttu-id="7a1d8-125">**保留中の更新をキャンセル**このオプションは、選択した更新プログラムが、組織のデバイスに配備されていることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="7a1d8-126">**承認**このオプションは、組織のデバイスに配置する選択した更新プログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="7a1d8-127">**復元**このオプションにより、組織のデバイスに展開する更新プログラムが以前に許可されました。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>
    
- <span data-ttu-id="7a1d8-128">**更新**すべてのデバイスの更新プログラムの状態を確認するのにはリストを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>
    
<span data-ttu-id="7a1d8-129">デバイス更新 Web サービスについての詳細は、計画のドキュメントで[、組織内のデバイスのソフトウェア更新プログラムの表示](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a1d8-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="7a1d8-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a1d8-130">See also</span></span>

[<span data-ttu-id="7a1d8-131">インポート-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="7a1d8-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)