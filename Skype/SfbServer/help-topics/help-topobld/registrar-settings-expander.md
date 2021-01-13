---
title: レジストラー設定エキスパンダー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818297"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="0a5c8-105">レジストラー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="0a5c8-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="0a5c8-p102">復元は、レジストラー プールの高可用性と障害復旧を提供します。プライマリ レジストラーに障害が発生した場合にバックアップ レジストラーを提供することで、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐことができるため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムによっては、機能が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="0a5c8-109">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの [**プロパティの編集**] ダイアログ ボックスの [**復元**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="0a5c8-110">**関連付けられたユーザー サービスとバックアップ レジストラー プール** ドロップダウン リストで、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーのバックアップ レジストラーとして機能する Enterprise Edition フロントエンド プールまたは Standard Edition フロントエンド サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="0a5c8-111">**フェールオーバーとフェールバックを有効にする** 障害が発生したレジストラーの自動検出と、プライマリ レジストラーがバックアップされ、レジストラー プロセスを再開する準備ができていることを自動的に判断するには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="0a5c8-112">**エラー検出間隔 (秒)** プライマリ レジストラーに障害が発生したと判断するまでの経過時間 (秒) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="0a5c8-113">既定値は 120 秒です。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-113">The default value is 120 seconds.</span></span> <span data-ttu-id="0a5c8-114">[フェールオーバーとフェールバックを有効にする] を選択 **した場合、このフィールドは必須です**。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="0a5c8-115">**フォールバック検出間隔 (秒)** プライマリ レジストラーがバックアップされたと判断するまでの経過時間 (秒) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="0a5c8-116">既定値は 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-116">The default value is 240 seconds.</span></span> <span data-ttu-id="0a5c8-117">[フェールオーバーとフォールバックを有効にする] を選択 **した場合、このフィールドは必須です**。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0a5c8-p105">障害検出間隔と代替検出間隔を定義するときには、レジストラーが短時間で応答できなかった場合にフェールオーバーと代替を引き起こすような間隔を入力しないように注意してください。プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a5c8-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

