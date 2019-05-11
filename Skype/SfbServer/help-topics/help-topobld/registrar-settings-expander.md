---
title: レジストラー設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: 復元機能では、レジストラー プールの高可用性と災害復旧を提供します。 プライマリのレジストラーでは、レジストラーは、障害が発生したレジストラーに引き継ぐことができますバックアップの障害が発生した場合は、バックアップ レジストラーを提供することにより、ユーザーがログオンし、通信を許可します。 可能性のある環境での機能の制限、プライマリ レジストラーによっては、システムが失敗しました。
ms.openlocfilehash: ec503f074ca196433ae894ea9a35e38f964301ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919683"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="aecf0-105">レジストラー設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="aecf0-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="aecf0-106">復元機能では、レジストラー プールの高可用性と災害復旧を提供します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="aecf0-107">プライマリのレジストラーでは、レジストラーは、障害が発生したレジストラーに引き継ぐことができますバックアップの障害が発生した場合は、バックアップ レジストラーを提供することにより、ユーザーがログオンし、通信を許可します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="aecf0-108">可能性のある環境での機能の制限、プライマリ レジストラーによっては、システムが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="aecf0-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="aecf0-109">リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの**プロパティの編集**] ダイアログ ボックスの [**復元**] セクションでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="aecf0-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="aecf0-110">**ユーザーの関連付けられているサービスおよびバックアップ レジストラー プール**ボックスの一覧では、エンタープライズ エディションのフロント エンド プールまたは標準エディション フロント エンド サーバーは、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーのバックアップ レジストラーとして動作することを選択します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="aecf0-111">**フェイル オーバーおよびフェイル バックを有効にします。** レジストラーと自動決定であるプライマリ レジストラーをバックアップし、登録プロセスを再開する準備が、障害の自動検出を許可するには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="aecf0-112">**障害検出の間隔 (秒)** プライマリ レジストラーが失敗したことを決定するまでの間隔の秒数を入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="aecf0-113">既定値は、120 秒です。</span><span class="sxs-lookup"><span data-stu-id="aecf0-113">The default value is 120 seconds.</span></span> <span data-ttu-id="aecf0-114">**有効にするフェイル オーバーおよびフェイル バック**を選択した場合、このフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="aecf0-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="aecf0-115">**フォールバックの検出の間隔 (秒)** プライマリ レジストラーがバックアップされていると判断がされるまでの秒数を入力します。</span><span class="sxs-lookup"><span data-stu-id="aecf0-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="aecf0-116">既定値は、240 秒です。</span><span class="sxs-lookup"><span data-stu-id="aecf0-116">The default value is 240 seconds.</span></span> <span data-ttu-id="aecf0-117">**フェイル オーバーを有効にしてフォールバック**を選択した場合、このフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="aecf0-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="aecf0-118">障害検出の間隔およびフォールバックの検出の間隔を定義する場合は、フェイル オーバーが発生する間隔を入力しないように注意し、レジストラーは、短時間の応答に失敗した場合に発生するフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="aecf0-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="aecf0-119">プライマリ レジストラー プールまたはサーバーの読み込みに時間が短時間で応答しないことが可能です。</span><span class="sxs-lookup"><span data-stu-id="aecf0-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

