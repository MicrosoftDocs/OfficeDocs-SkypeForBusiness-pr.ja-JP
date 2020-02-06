---
title: ブランチ オフィス アプライアンス全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 既存の Survivable Branch Appliance または Survivable ブランチサーバーの設定を編集するには、次のセクションが表示されます。
ms.openlocfilehash: ebc3c0d0961fd239ad2b72469b1029ac7b7274d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820299"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="4be2e-103">ブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="4be2e-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="4be2e-104">既存の Survivable Branch Appliance または Survivable ブランチサーバーの設定を編集するには、次のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="4be2e-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="4be2e-105">General settings</span></span>

- <span data-ttu-id="4be2e-106">復元の設定</span><span class="sxs-lookup"><span data-stu-id="4be2e-106">Resiliency settings</span></span>

- <span data-ttu-id="4be2e-107">仲介サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="4be2e-107">Mediation Server settings</span></span>



<span data-ttu-id="4be2e-108">Survivable Branch Appliance または Survivable ブランチサーバーの場合、次の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="4be2e-109">全般設定</span><span class="sxs-lookup"><span data-stu-id="4be2e-109">General settings</span></span>

<span data-ttu-id="4be2e-110">Survivable Branch Appliance または Survivable ブランチサーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="4be2e-110">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="4be2e-111">値を変更するには、サーバーの FQDN を編集します。</span><span class="sxs-lookup"><span data-stu-id="4be2e-111">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="4be2e-112">新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-112">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="4be2e-p102">[**すべての構成済み IP アドレスを使用する**] または [**サービスの使用を選択した IP アドレスに限定する**] を選択できます。[**サービスの使用を選択した IP アドレスに限定する**] を選択する場合、公衆交換電話網 (PSTN) ゲートウェイを除くすべての通信にサーバーが使用するプライマリ IP アドレスを定義します。PSTN 使用には、別の IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="4be2e-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="4be2e-116">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="4be2e-117">[アーカイブサーバーの関連付け] を選択すると、アーカイブサーバーを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="4be2e-118">ドロップダウンリストからサーバーを選ぶか、[**新規**] をクリックして新しいアーカイブサーバーを指定して、既に定義されたアーカイブサーバーから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4be2e-119">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="4be2e-120">[監視サーバーの関連付け] では、監視サーバーを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="4be2e-121">ドロップダウンリストからサーバーを選ぶか、[**新規**] をクリックして、新しい監視サーバーを指定して、既に定義されている監視サーバーから選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="4be2e-122">[Edge プールの関連付け] を選択すると、エッジサーバーまたはプールを Survivable Branch Appliance または Survivable Branch Server に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="4be2e-123">ドロップダウン リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規**] をクリックして新しいエッジ サーバーやプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="4be2e-124">復元</span><span class="sxs-lookup"><span data-stu-id="4be2e-124">Resiliency</span></span>

<span data-ttu-id="4be2e-p106">復元により、レジストラー プールの可用性を高めることができます。バックアップ レジストラーを指定することで、プライマリ レジストラーに障害が発生した場合、障害が発生したレジストラーの処理をバックアップ レジストラーが引き継ぐため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムに応じて、ユーザーの機能性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="4be2e-128">ドロップダウンリストから、Survivable Branch Appliance または Survivable Branch Server のバックアップレジストラーとして機能する Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="4be2e-129">フェールオーバーまたは代替の時間間隔を有効にする設定を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="4be2e-130">フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすることにより、障害が発生したレジストラーを自動検出し、プライマリ レジストラーが回復してレジストラー プロセスを引き継ぎ可能になったことを自動的に判定するためのフォールバック時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4be2e-131">障害検出とフォールバックの間隔を定義する場合は、レジストラーが短時間応答しなかった場合にフェールオーバーとフォールバックが発生するような間隔を入力しないよう注意してください。</span><span class="sxs-lookup"><span data-stu-id="4be2e-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="4be2e-132">プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="4be2e-133">サイト内の Survivable Branch Appliance または Survivable Branch Server の既定値は、1つのプールまたは標準エディションのフロントエンドサーバーに対する120秒のフェールオーバーおよび240秒です。</span><span class="sxs-lookup"><span data-stu-id="4be2e-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="4be2e-134">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="4be2e-134">Mediation Server</span></span>

<span data-ttu-id="4be2e-135">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="4be2e-136">仲介サーバーが併置されているため、Survivable Branch Appliance または Survivable Branch Server では、併置され**ている仲介サーバー**のチェックボックスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4be2e-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="4be2e-137">トランスポート層セキュリティ (TLS) のプールサーバーでリッスンポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4be2e-137">You define the listening port on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="4be2e-138">既定では、このポートは5067です。</span><span class="sxs-lookup"><span data-stu-id="4be2e-138">By default, this port is 5067.</span></span> <span data-ttu-id="4be2e-139">[ **Tcp ポートを有効に**する] を選択した場合は、併置された仲介サーバーの tcp ポートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-139">If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server.</span></span> <span data-ttu-id="4be2e-140">これはオプションの設定であり、必要に応じてゲートウェイまたは PSTN の要件を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-140">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="4be2e-141">既定では、[TCP ポート] の値は5068です。</span><span class="sxs-lookup"><span data-stu-id="4be2e-141">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="4be2e-142">併置された仲介サーバーに関連付けられている PSTN ゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="4be2e-142">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="4be2e-143">既にゲートウェイが定義されている場合は、それらを仲介サーバーと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-143">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="4be2e-144">ゲートウェイを定義していない場合に定義可能なゲートウェイが存在するときは、[**新規**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-144">If you have not defined any gateways, but you have them available to define, you can select **New**.</span></span> <span data-ttu-id="4be2e-145">この仲介サーバーに既に構成されているゲートウェイを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="4be2e-145">You can also remove gateways that are already configured for this Mediation Server.</span></span> <span data-ttu-id="4be2e-146">ゲートウェイを選択して、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4be2e-146">Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="4be2e-147">仲介サーバーと関連付けられているゲートウェイが複数ある場合は、最初に関連付けられたゲートウェイが既定のゲートウェイになります。</span><span class="sxs-lookup"><span data-stu-id="4be2e-147">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="4be2e-148">別のゲートウェイをデフォルト ゲートウェイとして選択する必要がある場合は、デフォルトにするゲートウェイを選択して、[**デフォルトに設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4be2e-148">If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4be2e-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="4be2e-149">See also</span></span>

<span data-ttu-id="4be2e-150">Survivable Branch Appliance または Survivable ブランチサーバーの設定の定義と構成の詳細については、「[ブランチサイトの回復性ソリューション](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4be2e-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


