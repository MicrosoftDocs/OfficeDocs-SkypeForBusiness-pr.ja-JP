---
title: デバイス ログの構成
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
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データのキャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前に保持される時間の長さに関するしきい値を設定できます。 これらの設定は、組織の要件に従って変更できます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: 27b4382c84d6aa12a642f191a6167e99ac10565c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829487"
---
# <a name="device-log-configuration"></a><span data-ttu-id="901c1-107">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="901c1-107">Device Log Configuration</span></span>

<span data-ttu-id="901c1-108">デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="901c1-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="901c1-109">組織のデータ管理戦略の一環として、ログ データのキャッシュ サイズ、ログ ファイル サイズ、またはログ ファイルが削除される前に保持される期間にしきい値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="901c1-110">これらの設定は、組織の要件に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="901c1-111">デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901c1-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="901c1-112">ログ設定はグローバルに、またはサイトごとに変更できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="901c1-113">デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="901c1-114">この設定は、Skype for Business Server コントロール パネルを使用して変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="901c1-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="901c1-115">代わりに、Skype for Business Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="901c1-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="901c1-116">期限切れのログ ファイルを削除する時刻を指定するには **、New-CsDeviceUpdateConfiguration** コマンドレットに -LogCleanUpTimeOfDay パラメーターを指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="901c1-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="901c1-117">詳細については [、「New-CsDeviceUpdateConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="901c1-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="901c1-p104">ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="901c1-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="901c1-120">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="901c1-120">Tasks you can perform</span></span>

<span data-ttu-id="901c1-121">[**デバイス ログの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="901c1-122">グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="901c1-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="901c1-123">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="901c1-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="901c1-124">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="901c1-124">UI Reference</span></span>

<span data-ttu-id="901c1-125">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="901c1-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="901c1-126">**新規** 次のスコープで新しいデバイス ログ構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="901c1-127">グローバル</span><span class="sxs-lookup"><span data-stu-id="901c1-127">Global</span></span>

  - <span data-ttu-id="901c1-128">Site</span><span class="sxs-lookup"><span data-stu-id="901c1-128">Site</span></span>

- <span data-ttu-id="901c1-129">**編集** デバイス ログ構成のオプションは、一覧で変更できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="901c1-130">このオプションを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="901c1-131">**詳細の表示** このオプションを選択すると、デバイス ログ構成のオプションを変更できるダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="901c1-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="901c1-132">**すべて選択** このオプションは、一覧内のすべてのデバイス ログ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="901c1-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="901c1-133">**削除** このオプションを選択すると、選択したデバイス ログ構成はすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="901c1-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="901c1-134">**更新** デバイス ログ構成リストを更新して、すべてのデバイス ログ構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="901c1-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="901c1-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="901c1-135">See also</span></span>

[<span data-ttu-id="901c1-136">デバイス更新アクティビティのログ ファイルの設定の変更</span><span class="sxs-lookup"><span data-stu-id="901c1-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
