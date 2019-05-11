---
title: デバイス ログの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。 組織のデータ管理戦略の一環として、ログ データのキャッシュのサイズ、ログ ファイルのサイズ、またはパージされる前にログ ファイルが保持される期間の長さのしきい値を設定する可能性があります。 組織の要件に従って、これらの設定を変更することができます。 デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。 ログ設定はグローバルに、またはサイトごとに変更できます。
ms.openlocfilehash: b4475efcee20846a7ff651265a13b34b3b9a43a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914031"
---
# <a name="device-log-configuration"></a><span data-ttu-id="99841-107">デバイス ログの構成</span><span class="sxs-lookup"><span data-stu-id="99841-107">Device Log Configuration</span></span>

<span data-ttu-id="99841-108">デバイス更新 Web サービスは、デバイス更新アクティビティが記録されるログ ファイルを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="99841-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="99841-109">組織のデータ管理戦略の一環として、ログ データのキャッシュのサイズ、ログ ファイルのサイズ、またはパージされる前にログ ファイルが保持される期間の長さのしきい値を設定する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99841-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="99841-110">組織の要件に従って、これらの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="99841-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="99841-111">デバイス更新 Web サービスが自動的にログ ファイルを削除しないようにした場合は、ログ ファイルを必要に応じて手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99841-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="99841-112">ログ設定はグローバルに、またはサイトごとに変更できます。</span><span class="sxs-lookup"><span data-stu-id="99841-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="99841-113">デバイス更新 Web サービスでログ ファイルを保持するよう構成した日数より古いログ ファイル (既定では 10 日間より古いログ ファイル) を、デバイス更新 Web サービスが自動的に削除する時刻も構成できます。</span><span class="sxs-lookup"><span data-stu-id="99841-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="99841-114">ビジネス サーバーのコントロール パネルの Skype を使用して、この設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="99841-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="99841-115">代わりに、ビジネス サーバー管理シェルの Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99841-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="99841-116">期限切れのログ ファイルを削除する時刻を指定するには、-LogCleanUpTimeOfDay パラメーターを使用して**新規 CsDeviceUpdateConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="99841-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="99841-117">詳細については、[新規 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99841-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="99841-p104">ファイルを削除すると、ファイル システムから完全に削除されます。ファイルを削除した後に復旧することはできません。</span><span class="sxs-lookup"><span data-stu-id="99841-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="99841-120">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="99841-120">Tasks you can perform</span></span>

<span data-ttu-id="99841-121">[**デバイス ログの構成**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="99841-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="99841-122">グローバルな、または特定のサイトやプールのデバイス ログ構成を追加します。</span><span class="sxs-lookup"><span data-stu-id="99841-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="99841-123">既存のデバイス ログ構成のオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="99841-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="99841-124">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="99841-124">UI Reference</span></span>

<span data-ttu-id="99841-125">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="99841-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="99841-126">**新しい**次のスコープを持つ新しいデバイス ログの構成を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="99841-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="99841-127">グローバル</span><span class="sxs-lookup"><span data-stu-id="99841-127">Global</span></span>

  - <span data-ttu-id="99841-128">サイト</span><span class="sxs-lookup"><span data-stu-id="99841-128">Site</span></span>

- <span data-ttu-id="99841-129">**編集**一覧でデバイス ログ構成のオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="99841-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="99841-130">このオプションを使用すると、以下を実行できます、します。</span><span class="sxs-lookup"><span data-stu-id="99841-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="99841-131">**詳細を表示します。** このオプションは、デバイスのログの構成のオプションを変更できるダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="99841-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="99841-132">**すべてを選択**一覧にすべてのデバイスのログ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="99841-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="99841-133">**削除**このオプションは、すべてのデバイスが選択されているログの構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="99841-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="99841-134">**更新**デバイス ログ構成のすべてのオプションの状態を確認するデバイス ログ構成の一覧を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="99841-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="99841-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="99841-135">See also</span></span>

[<span data-ttu-id="99841-136">Modify Settings for Log Files of Device Update Activity</span><span class="sxs-lookup"><span data-stu-id="99841-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
