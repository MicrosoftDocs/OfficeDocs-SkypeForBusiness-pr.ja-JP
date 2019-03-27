---
title: ブランチ オフィス アプライアンス全般設定エキスパンダー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 既存のリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの設定を編集するのには次のセクションが表示されます。
ms.openlocfilehash: 336d64edfac0bda730a289284075267d7e7984d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884944"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="0e384-103">ブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="0e384-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="0e384-104">既存のリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの設定を編集するのには次のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e384-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="0e384-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="0e384-105">General settings</span></span>

- <span data-ttu-id="0e384-106">復元の設定</span><span class="sxs-lookup"><span data-stu-id="0e384-106">Resiliency settings</span></span>

- <span data-ttu-id="0e384-107">仲介サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="0e384-107">Mediation Server settings</span></span>



<span data-ttu-id="0e384-108">リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーには、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e384-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="0e384-109">全般設定</span><span class="sxs-lookup"><span data-stu-id="0e384-109">General settings</span></span>

<span data-ttu-id="0e384-110">リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの完全修飾ドメイン名 (FQDN) です。</span><span class="sxs-lookup"><span data-stu-id="0e384-110">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0e384-111">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="0e384-111">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="0e384-112">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e384-112">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="0e384-p102">[**すべての構成済み IP アドレスを使用する**] または [**サービスの使用を選択した IP アドレスに限定する**] を選択できます。[**サービスの使用を選択した IP アドレスに限定する**] を選択する場合、公衆交換電話網 (PSTN) ゲートウェイを除くすべての通信にサーバーが使用するプライマリ IP アドレスを定義します。PSTN 使用には、別の IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="0e384-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="0e384-116">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e384-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="0e384-117">アーカイブ サーバーを関連付けるを使用すると、選択すると、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーとアーカイブ サーバーを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0e384-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0e384-118">」ドロップ ダウン リストからサーバーを選択してから定義済みのアーカイブ サーバーを選択したり、新しいアーカイブ サーバーを指定する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e384-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0e384-119">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e384-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="0e384-120">関連付ける監視サーバーを使用すると、選択すると、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーと監視サーバーを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0e384-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0e384-121">」ドロップ ダウン リストからサーバーを選択することにより、既に定義されているサーバーの監視から選択したり、新しい監視サーバーを指定する**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e384-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="0e384-122">プールを使用すると、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバー、エッジ サーバーまたはプールに関連付ける場合に選択するエッジを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0e384-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0e384-123">ドロップダウン リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規**] をクリックして新しいエッジ サーバーやプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e384-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="0e384-124">復元</span><span class="sxs-lookup"><span data-stu-id="0e384-124">Resiliency</span></span>

<span data-ttu-id="0e384-p106">復元により、レジストラー プールの可用性を高めることができます。バックアップ レジストラーを指定することで、プライマリ レジストラーに障害が発生した場合、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムに応じて、ユーザーの機能性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e384-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="0e384-128">」ドロップ ダウン リストからエンタープライズ エディションのフロント エンド プールまたは Standard Edition フロント エンド Server リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーのバックアップ レジストラーとして動作するを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e384-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="0e384-129">フェールオーバーまたは代替の時間間隔を有効にする設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e384-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="0e384-130">フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすることにより、障害が発生したレジストラーを自動検出し、プライマリ レジストラーが回復してレジストラー プロセスを引き継ぎ可能になったことを自動的に判定するためのフォールバック時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="0e384-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e384-131">障害検出とフォールバックの間隔を定義する場合は、レジストラーが短時間応答しなかった場合にフェールオーバーとフォールバックが発生するような間隔を入力しないよう注意してください。</span><span class="sxs-lookup"><span data-stu-id="0e384-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="0e384-132">プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e384-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="0e384-133">リカバリ性に優れたブランチ アプライアンスまたはプールへのサイト内に存続可能ブランチ サーバーや標準的なフロント エンド サーバーのエディションの既定値は、120 秒の間のフェイル オーバーとフォールバックの 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="0e384-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="0e384-134">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="0e384-134">Mediation Server</span></span>

<span data-ttu-id="0e384-135">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e384-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="0e384-136">**仲介サーバーを 1 か所に配置を有効に**するのチェック ボックスが、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーで利用可能な仲介サーバーが併設されているため</span><span class="sxs-lookup"><span data-stu-id="0e384-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="0e384-137">定義するポートをリッスンしているプールのサーバーでトランスポート層セキュリティ (TLS) の。</span><span class="sxs-lookup"><span data-stu-id="0e384-137">You define the listening port on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="0e384-138">既定では、このポートは 5067 です。</span><span class="sxs-lookup"><span data-stu-id="0e384-138">By default, this port is 5067.</span></span> <span data-ttu-id="0e384-139">**有効にする TCP ポート**を選択する場合は、配置されている仲介サーバーの TCP ポートを定義してください。</span><span class="sxs-lookup"><span data-stu-id="0e384-139">If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server.</span></span> <span data-ttu-id="0e384-140">これは、オプションの設定、およびゲートウェイの要件や、これが必要なかどうかを決定するのには、PSTN の要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e384-140">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="0e384-141">既定では、TCP ポートの値は 5068 がします。</span><span class="sxs-lookup"><span data-stu-id="0e384-141">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="0e384-142">配置されている仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="0e384-142">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="0e384-143">ゲートウェイが定義されている場合は、仲介サーバーに関連付けるに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e384-143">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="0e384-144">ゲートウェイを定義していない場合に定義可能なゲートウェイが存在するときは、[**新規**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e384-144">If you have not defined any gateways, but you have them available to define, you can select **New**.</span></span> <span data-ttu-id="0e384-145">この仲介サーバーで既に構成されているゲートウェイを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e384-145">You can also remove gateways that are already configured for this Mediation Server.</span></span> <span data-ttu-id="0e384-146">ゲートウェイを選択して、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e384-146">Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="0e384-147">仲介サーバーに関連付けられている 1 つ以上のゲートウェイがある場合は、関連付けられている最初のゲートウェイがデフォルト ゲートウェイになります。</span><span class="sxs-lookup"><span data-stu-id="0e384-147">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="0e384-148">別のゲートウェイをデフォルト ゲートウェイとして選択する必要がある場合は、デフォルトにするゲートウェイを選択して、[**デフォルトに設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e384-148">If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e384-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e384-149">See also</span></span>

<span data-ttu-id="0e384-150">詳細を定義して、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの設定の構成については、[ブランチ サイトの復元ソリューション](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e384-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


