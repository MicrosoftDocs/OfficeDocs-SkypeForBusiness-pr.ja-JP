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
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 既存の存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの設定を編集するには、以下のセクションが表示されます。
ms.openlocfilehash: 40ebf4a22bcfc3392c2f1dc8238a46b610d22281
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216128"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="47298-103">ブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="47298-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="47298-104">既存の存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの設定を編集するには、以下のセクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47298-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="47298-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="47298-105">General settings</span></span>

- <span data-ttu-id="47298-106">復元の設定</span><span class="sxs-lookup"><span data-stu-id="47298-106">Resiliency settings</span></span>

- <span data-ttu-id="47298-107">仲介サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="47298-107">Mediation Server settings</span></span>



<span data-ttu-id="47298-108">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーでは、以下が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47298-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="47298-109">全般設定</span><span class="sxs-lookup"><span data-stu-id="47298-109">General settings</span></span>

<span data-ttu-id="47298-p101">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの完全修飾ドメイン名 (FQDN)。値を変更するには、サーバーの FQDN を編集します。新しい値と一致しているドメイン ネーム システム (DNS) ホスト (A) レコードがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="47298-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="47298-p102">[**すべての構成済み IP アドレスを使用する**] または [**サービスの使用を選択した IP アドレスに限定する**] を選択できます。[**サービスの使用を選択した IP アドレスに限定する**] を選択する場合、公衆交換電話網 (PSTN) ゲートウェイを除くすべての通信にサーバーが使用するプライマリ IP アドレスを定義します。PSTN 使用には、別の IP アドレスを定義します。</span><span class="sxs-lookup"><span data-stu-id="47298-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="47298-116">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="47298-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="47298-117">[アーカイブサーバーの関連付け] では、アーカイブサーバーを存続可能 Branch Appliance または存続可能ブランチサーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="47298-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="47298-118">定義済みのアーカイブサーバーから選択するには、ドロップダウンリストからサーバーを選択するか、[ **新規** ] をクリックして新しいアーカイブサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="47298-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="47298-119">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="47298-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="47298-120">[監視サーバーの関連付け] を選択すると、監視サーバーを存続可能 Branch Appliance または存続可能 Branch Server に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="47298-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="47298-121">定義済みの監視サーバーから選択するには、ドロップダウンリストからサーバーを選択するか、[ **新規** ] をクリックして新しい監視サーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="47298-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="47298-122">[エッジプールの関連付け] を選択すると、エッジサーバーまたはプールを存続可能 Branch Appliance または存続可能 Branch Server に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="47298-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="47298-123">ドロップダウン リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規**] をクリックして新しいエッジ サーバーやプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="47298-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="47298-124">性</span><span class="sxs-lookup"><span data-stu-id="47298-124">Resiliency</span></span>

<span data-ttu-id="47298-p106">復元により、レジストラー プールの可用性を高めることができます。バックアップ レジストラーを指定することで、プライマリ レジストラーに障害が発生した場合、バックアップ レジストラーが障害が発生したレジストラーの処理を引き継ぐため、ユーザーがログオンして通信することができます。プライマリ レジストラーで障害が発生したシステムに応じて、ユーザーの機能性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47298-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="47298-128">ドロップダウンリストから、Enterprise Edition フロントエンドプールまたは Standard Edition フロントエンドサーバーを選択します。これは、存続可能 Branch Appliance または存続可能 Branch Server のバックアップレジストラーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="47298-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="47298-129">フェールオーバーとフォールバックの時間間隔を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="47298-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="47298-130">フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすることにより、障害が発生したレジストラーを自動検出し、プライマリ レジストラーが回復してレジストラー プロセスを引き継ぎ可能になったことを自動的に判定するためのフォールバック時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="47298-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47298-131">障害検出とフォールバックの間隔を定義する際に、レジストラーが短時間応答しなかった場合にフェールオーバーとフォールバックが発生するような間隔を入力しないよう、注意してください。</span><span class="sxs-lookup"><span data-stu-id="47298-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="47298-132">プライマリ レジストラーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47298-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="47298-133">サイト内の存続可能 Branch Appliance または存続可能 Branch Server の既定値は、プールまたは Standard Edition フロントエンドサーバーでは、フェールオーバーの場合は120秒、フォールバックの場合は240秒です。</span><span class="sxs-lookup"><span data-stu-id="47298-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="47298-134">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="47298-134">Mediation Server</span></span>

<span data-ttu-id="47298-135">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47298-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="47298-136">仲介サーバーが配置されているため、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの [**配置された仲介サーバーの有効化**] のチェック ボックスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="47298-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="47298-p109">プール サーバーにトランスポート層セキュリティ (TLS) のリッスン ポートを定義します。既定のポートは 5067 です。[**TCP ポートの有効化**] を選択する場合は、共存仲介サーバーの TCP ポートを定義する必要があります。これはオプション設定です。この設定が必要かどうかは、ゲートウェイまたは PSTN の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="47298-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="47298-p110">配置された仲介サーバーに関連付ける PSTN ゲートウェイを定義します。ゲートウェイを既に定義している場合は、それらのゲートウェイを仲介サーバーに関連付けることができます。ゲートウェイを定義していない場合に定義可能なゲートウェイが存在するときは、**[新規]** を選択できます。この仲介サーバーに既に構成されているゲートウェイを削除することもできます。ゲートウェイを選択して、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47298-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="47298-p111">仲介サーバーに複数のゲートウェイを関連付けている場合は、関連付けた最初のゲートウェイが既定のゲートウェイとなります。別のゲートウェイをデフォルト ゲートウェイとして選択する必要がある場合は、デフォルトにするゲートウェイを選択して、**[デフォルトに設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47298-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="47298-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="47298-149">See also</span></span>

<span data-ttu-id="47298-150">存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの設定の定義と構成の詳細については、「[Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47298-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


