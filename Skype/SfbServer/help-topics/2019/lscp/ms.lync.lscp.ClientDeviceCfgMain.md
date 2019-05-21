---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一部として、ログデータキャッシュサイズ、ログファイルサイズ、またはログファイルが削除されるまでの一定期間のしきい値を設定することができます。 組織の要件に応じて、これらの設定を変更することができます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: 7c4f532af6e74f8ef13b3b2de17017b66afc0b59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300473"
---
# <a name="device-log-configuration"></a><span data-ttu-id="b64de-107">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="b64de-107">Device Log Configuration</span></span>

<span data-ttu-id="b64de-108">デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="b64de-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="b64de-109">組織のデータ管理戦略の一部として、ログデータキャッシュサイズ、ログファイルサイズ、またはログファイルが削除されるまでの一定期間のしきい値を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b64de-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="b64de-110">組織の要件に応じて、これらの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b64de-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="b64de-111">デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b64de-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="b64de-112">ログ設定はグローバルに、またはサイトごとに変更できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="b64de-113">デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="b64de-114">この設定は、Skype for Business Server コントロールパネルを使用して変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b64de-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b64de-115">代わりに、Skype for Business Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b64de-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b64de-116">有効期限が切れたログファイルを削除する時刻を指定するには、-LogCleanUpTimeOfDay パラメーターを指定して、**新しい-CsDeviceUpdateConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b64de-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="b64de-117">詳しくは、「[新しい-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b64de-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="b64de-p104">ファイルを削除すると、ファイル システムから完全に削除されます。ファイルを削除した後に復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="b64de-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b64de-120">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="b64de-120">Tasks you can perform</span></span>

<span data-ttu-id="b64de-121">[**デバイス ログの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="b64de-122">グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="b64de-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="b64de-123">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="b64de-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b64de-124">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="b64de-124">UI Reference</span></span>

<span data-ttu-id="b64de-125">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b64de-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b64de-126">**新規**次のスコープを持つ新しいデバイスログ構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="b64de-127">グローバル</span><span class="sxs-lookup"><span data-stu-id="b64de-127">Global</span></span>

  - <span data-ttu-id="b64de-128">サイト</span><span class="sxs-lookup"><span data-stu-id="b64de-128">Site</span></span>

- <span data-ttu-id="b64de-129">**編集**一覧のデバイスログ構成のオプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="b64de-130">このオプションを使うと、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b64de-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="b64de-131">**詳細を表示**このオプションを選択すると、デバイスログ構成のオプションを変更できるダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b64de-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="b64de-132">**すべて選択**このオプションでは、一覧にあるすべてのデバイスログの構成が選択されます。</span><span class="sxs-lookup"><span data-stu-id="b64de-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="b64de-133">**削除**このオプションは、選択したすべてのデバイスログ構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="b64de-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="b64de-134">**更新**デバイスログの構成の一覧を更新して、すべてのデバイスログ構成のオプションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b64de-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="b64de-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="b64de-135">See also</span></span>

[<span data-ttu-id="b64de-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="b64de-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
