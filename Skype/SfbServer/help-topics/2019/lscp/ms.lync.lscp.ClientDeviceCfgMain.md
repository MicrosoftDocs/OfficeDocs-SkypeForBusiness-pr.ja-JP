---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データ キャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前にログ ファイルを保持する時間の長さにしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: c9bd2c3077325540e6151fabd7bc4127b909a12a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120276"
---
# <a name="device-log-configuration"></a><span data-ttu-id="7965c-107">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="7965c-107">Device Log Configuration</span></span>

<span data-ttu-id="7965c-108">デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="7965c-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="7965c-109">組織のデータ管理戦略の一環として、ログ データ キャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前にログ ファイルを保持する時間の長さにしきい値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="7965c-110">これらの設定は、組織の要件に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="7965c-111">デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7965c-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="7965c-112">ログ設定はグローバルに、またはサイトごとに変更できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="7965c-113">デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="7965c-114">この設定は、Skype for Business Server コントロール パネルを使用して変更できません。</span><span class="sxs-lookup"><span data-stu-id="7965c-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7965c-115">代わりに、Skype for Business Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7965c-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7965c-116">期限切れのログ ファイルを削除する時刻を指定するには、-LogCleanUpTimeOfDay パラメーターと一緒に **New-CsDeviceUpdateConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7965c-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="7965c-117">詳細については [、「New-CsDeviceUpdateConfiguration」を参照してください](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7965c-117">For details, see [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="7965c-p104">ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="7965c-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7965c-120">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="7965c-120">Tasks you can perform</span></span>

<span data-ttu-id="7965c-121">[**デバイス ログの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="7965c-122">グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="7965c-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="7965c-123">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="7965c-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7965c-124">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="7965c-124">UI Reference</span></span>

<span data-ttu-id="7965c-125">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="7965c-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="7965c-126">**New** 次のスコープで新しいデバイス ログ構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="7965c-127">グローバル</span><span class="sxs-lookup"><span data-stu-id="7965c-127">Global</span></span>

  - <span data-ttu-id="7965c-128">サイト</span><span class="sxs-lookup"><span data-stu-id="7965c-128">Site</span></span>

- <span data-ttu-id="7965c-129">**編集** リスト内のデバイス ログ構成のオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="7965c-130">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="7965c-131">**詳細の表示** このオプションは、デバイス ログ構成のオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="7965c-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="7965c-132">**[すべて選択]** このオプションは、リスト内のすべてのデバイス ログ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="7965c-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="7965c-133">**削除** このオプションは、選択したデバイス ログ構成をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="7965c-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="7965c-134">**更新** デバイス ログ構成リストを更新して、すべてのデバイス ログ構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7965c-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="7965c-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="7965c-135">See also</span></span>

[<span data-ttu-id="7965c-136">デバイス更新アクティビティのログ ファイルの設定の変更</span><span class="sxs-lookup"><span data-stu-id="7965c-136">Modify Settings for Log Files of Device Update Activity</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)