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
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 回復性は、レジストラープールの高可用性と障害回復機能を提供します。 プライマリレジストラーの障害が発生した場合にバックアップレジストラーを提供することによって、バックアップレジストラーは、失敗したレジストラーを引き継ぐことができるため、ユーザーはログオンして通信することができます。 ユーザーは、プライマリレジストラーで障害が発生したシステムによっては、機能が制限される可能性があります。
ms.openlocfilehash: bac382486b45acbb2e25d3be26d23ea67f1aa15b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696732"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="fc688-105">レジストラー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="fc688-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="fc688-106">回復性は、レジストラープールの高可用性と障害回復機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc688-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="fc688-107">プライマリレジストラーの障害が発生した場合にバックアップレジストラーを提供することによって、バックアップレジストラーは、失敗したレジストラーを引き継ぐことができるため、ユーザーはログオンして通信することができます。</span><span class="sxs-lookup"><span data-stu-id="fc688-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="fc688-108">ユーザーは、プライマリレジストラーで障害が発生したシステムによっては、機能が制限される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc688-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="fc688-109">Survivable Branch Appliance または Survivable Branch Server の [**プロパティの編集**] ダイアログボックスの [**回復性**] セクションで、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fc688-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="fc688-110">**関連付けられているユーザーサービスとバックアップレジストラープール**ドロップダウンリストで、Survivable Branch Appliance または Survivable Branch Server のバックアップレジストラーとして機能する Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="fc688-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="fc688-111">**フェールオーバーとフェールバックを有効にする**この設定を選択すると、失敗したレジストラーが自動検出され、プライマリレジストラーがバックアップされ、レジストラープロセスを再開する準備ができたことが自動判断されます。</span><span class="sxs-lookup"><span data-stu-id="fc688-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="fc688-112">**失敗検出の間隔 (秒)** プライマリレジストラーが失敗したと判断されるまでの時間 (秒数) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc688-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="fc688-113">既定値は120秒です。</span><span class="sxs-lookup"><span data-stu-id="fc688-113">The default value is 120 seconds.</span></span> <span data-ttu-id="fc688-114">[**フェールオーバーとフェールバックを有効に**する] を選択した場合、このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="fc688-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="fc688-115">**フォールバック検出の間隔 (秒)** プライマリレジストラーがバックアップされたことを確認するまでの時間 (秒数) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc688-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="fc688-116">既定値は240秒です。</span><span class="sxs-lookup"><span data-stu-id="fc688-116">The default value is 240 seconds.</span></span> <span data-ttu-id="fc688-117">[**フェールオーバーとフォールバックを有効に**する] を選択した場合、このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="fc688-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="fc688-118">障害検出間隔とフォールバック検出間隔を定義した場合、レジストラーが短時間応答しない場合は、フェールオーバーとフォールバックが発生する間隔を入力しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc688-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="fc688-119">プールまたはサーバーの読み込みに基づいて、プライマリレジストラーが短時間応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fc688-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

