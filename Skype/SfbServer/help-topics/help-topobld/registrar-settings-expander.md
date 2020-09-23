---
title: レジストラー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 復元は、レジストラー プールの高可用性と障害復旧を提供します。プライマリ レジストラーに障害が発生した場合にバックアップ レジストラーを提供することで、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐことができるため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムによっては、機能が低下する可能性があります。
ms.openlocfilehash: f6ea6907942111db92ca3bfe2dfef1712bd53a62
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217158"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="f8c4f-105">レジストラー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="f8c4f-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="f8c4f-p102">復元は、レジストラー プールの高可用性と障害復旧を提供します。プライマリ レジストラーに障害が発生した場合にバックアップ レジストラーを提供することで、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐことができるため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムによっては、機能が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="f8c4f-109">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの [**プロパティの編集**] ダイアログ ボックスの [**復元**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="f8c4f-110">**関連付けられているユーザーサービスとバックアップレジストラープール** ドロップダウンリストで、Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選択します。これは、存続可能 Branch Appliance または存続可能 Branch Server のバックアップレジストラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="f8c4f-111">**フェールオーバーとフェールバックを有効にする** エラーが発生したレジストラーを自動検出し、プライマリレジストラーがバックアップされてレジストラープロセスを再開する準備が整っているかを自動判別できるようにするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="f8c4f-112">**エラー検出の間隔 (秒)** プライマリレジストラーが失敗したと判断されるまでの経過時間を秒数で入力します。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="f8c4f-113">既定値は 120 秒です。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-113">The default value is 120 seconds.</span></span> <span data-ttu-id="f8c4f-114">このフィールドは、[ **フェールオーバーとフェールバックを有効に**する] を選択した場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="f8c4f-115">**フォールバック検出の間隔 (秒)** プライマリレジストラーのバックアップが決定されるまでの経過時間を秒数で入力します。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="f8c4f-116">既定値は240秒です。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-116">The default value is 240 seconds.</span></span> <span data-ttu-id="f8c4f-117">このフィールドは **、[フェールオーバーとフォールバックを有効に**する] を選択した場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="f8c4f-p105">障害検出間隔と代替検出間隔を定義するときには、レジストラーが短時間で応答できなかった場合にフェールオーバーと代替を引き起こすような間隔を入力しないように注意してください。プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8c4f-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

