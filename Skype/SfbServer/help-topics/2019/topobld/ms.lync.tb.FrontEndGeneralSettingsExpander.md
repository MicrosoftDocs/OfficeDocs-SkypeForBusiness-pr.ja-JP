---
title: フロントエンド全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 既存のフロントエンド プールまたは Standard Edition サーバーの設定を編集するには、以下のセクションに示す手順に従って操作します。
ms.openlocfilehash: 76992a6d88c25a1907e4bb2cc1f6dee69a418f01
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688517"
---
# <a name="front-end-general-settings-expander"></a><span data-ttu-id="0c754-103">フロントエンド全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="0c754-103">Front End General Settings Expander</span></span>

<span data-ttu-id="0c754-104">既存のフロントエンド プールまたは Standard Edition サーバーの設定を編集するには、以下のセクションに示す手順に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="0c754-104">To edit the settings for an existing Front End pool or Standard Edition server, you are presented with the following sections:</span></span>

- <span data-ttu-id="0c754-105">全般設定</span><span class="sxs-lookup"><span data-stu-id="0c754-105">General settings</span></span>

- <span data-ttu-id="0c754-106">復元の設定</span><span class="sxs-lookup"><span data-stu-id="0c754-106">Resiliency settings</span></span>

- <span data-ttu-id="0c754-107">Web サービスの設定</span><span class="sxs-lookup"><span data-stu-id="0c754-107">Web services settings</span></span>

- <span data-ttu-id="0c754-108">仲介サーバーの設定</span><span class="sxs-lookup"><span data-stu-id="0c754-108">Mediation Server settings</span></span>

## <a name="front-end-pool"></a><span data-ttu-id="0c754-109">フロントエンド プール</span><span class="sxs-lookup"><span data-stu-id="0c754-109">Front End pool</span></span>

<span data-ttu-id="0c754-p101">フロントエンド プールには、全般、復元、Web サービス、および仲介サーバーの設定を構成できます。詳細については、以下のサブセクションを参照してください。フロントエンド プールの設定の定義および構成の詳細については、「[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-p101">For a Front End pool, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="0c754-113">全般設定</span><span class="sxs-lookup"><span data-stu-id="0c754-113">General Settings</span></span>

<span data-ttu-id="0c754-114">以下の全般設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-114">You can configure the following general settings:</span></span>

- <span data-ttu-id="0c754-p102">[**FQDN**]。プールの FQDN を編集して変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p102">**FQDN**. Edit the FQDN of the pool to change it.</span></span>

- <span data-ttu-id="0c754-p103">[**ロード バランサー機器の監視ポートの有効化**]。チェック ボックスをオンにし、ロード バランサー機器でプール サーバーの状態を監視するために使用するポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p103">**Enable hardware load balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the pool servers.</span></span>

- <span data-ttu-id="0c754-p104">[**特徴と機能**] で、このプールに併置する追加の役割を定義します。次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p104">In **Features and Functionality**, define the additional roles that you want to collocate with this pool. You can configure the following settings:</span></span>

  - <span data-ttu-id="0c754-p105">[**電話会議**]。音声、ビデオ、およびアプリケーション共有が含まれます。このオプションを選択した後で、ダイヤルイン (PSTN) 会議を選択できます。公衆交換電話網 (PSTN) ゲートウェイは、仲介サーバーの設定を行うときに後で指定して定義します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p105">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select Dial-in (PSTN) conferencing. You specify and define a public switched telephone network (PSTN) gateway in the "Mediation Server Settings" subsection later in this section.</span></span>

  - <span data-ttu-id="0c754-125">[**エンタープライズ VoIP**]。</span><span class="sxs-lookup"><span data-stu-id="0c754-125">**Enterprise Voice**.</span></span> <span data-ttu-id="0c754-126">内部のボイスオーバー IP 通話を、修飾されたハンドセットとデバイス、および Skype for Business クライアントに対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="0c754-126">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="0c754-127">外部通話機能を有効にするには、仲介サーバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-127">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="0c754-128">詳細については、このトピックの「仲介サーバー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-128">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="0c754-129">[**関連付け**] では、次の情報を編集または指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-129">In **Associations**, edit or specify the following:</span></span>

  - <span data-ttu-id="0c754-p107">[**SQL ストア**]。既存の SQL Server データベースを変更するか、フロントエンド プールのデータベースを保持する SQL Server ベースの新しいデータベースを作成します。リストから新しい SQL Server インスタンスを選択するか、[**新規作成**] をクリックして新しいエントリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p107">**SQL Store**. Modify an existing SQL Server database or create a new SQL Server-based database to hold the Front End pool databases. You can select a new instance of SQL Server from the list or create a new entry by clicking **New**.</span></span>

    <span data-ttu-id="0c754-p108">[**SQL Server ストア ミラーリングの有効化**] をオンにしてから、ミラーリングに使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p108">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="0c754-p109">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオンにして、ミラーリング監視として使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p109">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="0c754-p110">[**ファイル共有**]。フロントエンド プールで使用するファイル ストアを変更できます。定義済みのファイル ストアのリストから選択すると、新しいファイル ストアを選択できます。[**新規作成**] をクリックすると、新しいファイル ストアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p110">**File share**. Modify the file store that the Front End pool is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c754-141">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-141">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="0c754-p111">[**アーカイブ**]。アーカイブ サーバー ストアをフロントエンド プールと関連付けます。リストからサーバーを選択して定義済みのアーカイブ SQL Server ストアを選択するか、[**新規作成**] をクリックして新しいアーカイブ サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p111">**Archiving**. Associate an Archiving Server store with the Front End pool. You can select from an already defined Archiving SQL Server store by selecting the server from the list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c754-145">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-145">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

    <span data-ttu-id="0c754-p112">[**SQL Server ストア ミラーリングの有効化**] をオンにしてから、ミラーリングに使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p112">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="0c754-p113">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオンにして、ミラーリング監視として使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p113">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="0c754-p114">[**監視 (CDR および QoE 指標)**]。監視 SQL Server ストアをフロントエンド プールと関連付けます。リストからサーバーを選択して定義済みの監視サーバーを選択するか、[**新規作成**] をクリックして新しい監視サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p114">**Monitoring (CDR and QoE metrics)**. Select to associate a Monitoring SQL Server store with the Front End pool. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

    <span data-ttu-id="0c754-p115">[**SQL Server ストア ミラーリングの有効化**] をオンにしてから、ミラーリングに使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p115">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="0c754-p116">[**SQL Server ミラーリング監視を自動フェールオーバーの有効化のために使用**] をオンにして、ミラーリング監視として使用するサーバーを選択します。[**新規**] をクリックして、新しい SQL Server ストアを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p116">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="0c754-p117">[**エッジ プールの関連付け (メディア コンポーネント用)**]。エッジ サーバーまたはプールをフロントエンド プールと関連付けます。リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規作成**] をクリックして新しいエッジ サーバーやプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p117">**Associate Edge pool (for media components)**. Associate an Edge Server or pool with the Front End pool. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

  - <span data-ttu-id="0c754-p118">[**Office Web Apps サーバーの関連付け**]。Office Web Apps サーバーをフロントエンド プールと関連付けるには、このオプションを選択します。リストから既存のサーバーを選択するか、または、[**新規**] をクリックして新しい Office Web Apps サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p118">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

### <a name="resiliency"></a><span data-ttu-id="0c754-163">復元</span><span class="sxs-lookup"><span data-stu-id="0c754-163">Resiliency</span></span>

<span data-ttu-id="0c754-p119">復元は、プールの高可用性と障害復旧を提供します。バックアップを用意することで、プライマリ サーバーに障害が発生しても、バックアップ サーバーが引き継ぐことができるので、ユーザーはサインインして通信することができます。プライマリ サーバーで障害が発生したシステムに応じて、ユーザーの機能性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-p119">Resiliency provides disaster recovery and high availability for the pool. By providing a backup, if the primary server fails, the backup server can take over, enabling users to sign in and communicate. There may be reduced functionality for users, depending on which systems have failed with the primary server.</span></span>

<span data-ttu-id="0c754-p120">リストから、プールのバックアップ サーバーとして動作するフロントエンド プールまたは Standard Edition サーバーを選択します。フェールオーバーとフォールバックの時間間隔を有効にすることもできます。フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすると、障害が起きたサーバーを自動検出し、プライマリ サーバーが回復したことを自動的に判定するためのフォールバック時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p120">From the list, select the Front End pool or Standard Edition server that will act as the backup server for the pool. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed server, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c754-p121">障害検出とフォールバックの時間間隔を定義するときには、サーバーが短時間で応答できなかった場合にフェールオーバーとフォールバックを引き起こすような間隔を入力しないように注意してください。プライマリ サーバーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。フェールオーバーとフォールバックの既定値は、プールからプール、またはプールから Standard Edition サーバーの場合で 300 秒と 600 秒です。サイトからプールまたは Standard Edition サーバーでの存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの場合、フェールオーバーの既定値は 120 秒で、フォールバックの既定値は 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p121">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server fails to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, depending on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

> [!CAUTION]
> <span data-ttu-id="0c754-p122">**フェールオーバー時間間隔**の最小値は 90 秒以上に設定してください。この値を 90 秒未満にすると、値として 90 秒が使用されます。クラスター間 ping 時間は 30 秒なので、90 秒未満にすると、プライマリ サーバーとバックアップ サーバーの間で一方が他方のサーバーの使用可能状態を判別しようとするとき、循環往復が発生して動作に悪影響を及ぼす可能性があります。90 秒未満では、プライマリ サーバーが実際に使用不可能なのかどうかを確認するのに時間が足りません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p122">The minimum value for the **failover interval** should not be set lower than 90 seconds. If you do set the value to less than 90 seconds, the value of 90 seconds is used. The intercluster ping time is 30 seconds, and a setting lower than 90 seconds may cause the primary and backup servers to cycle up and down, causing an undesirable impact to production, as the servers try to resolve the viable status of the other. Less than 90 seconds does not allow for enough time to determine that the primary server is actually unavailable or not.</span></span>

### <a name="web-services"></a><span data-ttu-id="0c754-178">Web サービス</span><span class="sxs-lookup"><span data-stu-id="0c754-178">Web Services</span></span>

<span data-ttu-id="0c754-179">フロントエンド プールの Web サービスの追加設定を編集または指定するには、[**内部 Web サービス**] と [**外部 Web サービス**] の設定を変更または指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-179">To edit or specify additional setting for the web services on the Front End pool, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="0c754-180">[**内部 Web サービス**]。次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-180">In **Internal Web services**, specify the following:</span></span>

> [!CAUTION]
> <span data-ttu-id="0c754-181">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-181">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="0c754-182">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を**pool01.contoso.com**として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して**pool01.contoso.com**を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0c754-182">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="0c754-183">ディレクターも展開する場合、任意のディレクターまたはディレクタープール用に定義された外部 Web サービスの FQDN は、他のすべてのディレクターまたはディレクタープール、および任意のフロントエンドプールまたはフロントエンドサーバーから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-183">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool, as well as from any Front End pool or Front End Server.</span></span> <span data-ttu-id="0c754-184">自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-184">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director, or Director pool.</span></span>

- <span data-ttu-id="0c754-p124">[**FQDN の上書き**] を選択すると、プールの**内部 Web** サービス ID として別の FQDN を指定できます。この設定の既定値は、フロントエンド プールとして定義されている現在のプール名です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p124">If you select **Override FQDN**, you can specify a different FQDN for the **Internal Web** services identity on the pool. By default, the setting is the current pool name as defined for the Front End pool.</span></span>

- <span data-ttu-id="0c754-p125">展開で必要となる HTTP および HTTPS のリッスン ポートと公開ポート。既定の設定である HTTP のポート 80 と HTTPS のポート 443 は、最も一般的な設定です。通常、組織内またはインフラストラクチャ設計上の特別な要件がない限り、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p125">Listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed, unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="0c754-189">[**外部 Web サービス**]。次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-189">In **External Web services**, specify the following:</span></span>

- <span data-ttu-id="0c754-p126">外部 Web サービスの FQDN。ここで指定する FQDN は、通常、リバース プロキシなどの外部接続要件に含まれる要件に従って定義されます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p126">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="0c754-192">展開で必要となる HTTP および HTTPS のリッスン ポートと公開ポート。</span><span class="sxs-lookup"><span data-stu-id="0c754-192">Listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="0c754-193">既定の設定である HTTP のポート 8080 と HTTPS のポート 4443 が初期定義されています。</span><span class="sxs-lookup"><span data-stu-id="0c754-193">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="0c754-194">リッスン ポートのこれらの設定は、リバース プロキシと外部ネットワークの要件に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="0c754-194">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="0c754-195">公開ポートは、既定で HTTP のポート 80 と HTTPS のポート 443 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0c754-195">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="0c754-196">これらの値により、プールで着信要求をリッスンするときのポートが決まります。</span><span class="sxs-lookup"><span data-stu-id="0c754-196">These values determine what ports the pool will listen for incoming requests.</span></span> <span data-ttu-id="0c754-197">通常、プールのポート要件が競合しない限り、これらの変更は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-197">Typically, these do not need to be changed, unless there is a conflict of port requirements on the pool.</span></span> <span data-ttu-id="0c754-198">内部と外部の公開ポートで同じポート値が使用されることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="0c754-198">Internal and external published ports using the same port values are expected.</span></span> <span data-ttu-id="0c754-199">これは競合ではありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-199">This is not a conflict.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="0c754-200">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="0c754-200">Mediation Server</span></span>

<span data-ttu-id="0c754-201">[**仲介サーバー**]。次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-201">In **Mediation Server**, specify the following:</span></span>

- <span data-ttu-id="0c754-p128">仲介サーバーをプールに併置する場合、[**併置された仲介サーバーが有効**] チェック ボックスをオンにします。仲介サーバーを併置しない場合、このセクションで使用できる設定はありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p128">If you collocate the Mediation Server with the pool, select the **Collocated Mediation Server enabled** check box. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="0c754-p129">仲介サーバーの併置を有効にした場合は、プール サーバーでのトランスポート層セキュリティ (TLS) のリッスン ポート範囲を定義します。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択する場合は、併置する仲介サーバーの伝送制御プロトコル (TCP) ポートを定義する必要があります。これはオプション設定です。この設定が必要かどうかは、ゲートウェイまたは PSTN の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p129">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="0c754-p130">併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p130">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="0c754-p131">仲介サーバーに関連付けられたトランクが複数ある場合は、ゲートウェイを選択してから [**既定値にする**] をクリックすることにより、既定のトランクを指定できます。既定としてのゲートウェイを選択解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c754-p131">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="0c754-213">フロントエンド プールの設定の定義および構成の詳細については、「[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-213">For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

## <a name="standard-edition-server"></a><span data-ttu-id="0c754-214">Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="0c754-214">Standard Edition Server</span></span>

<span data-ttu-id="0c754-p132">Standard Edition サーバーには、全般、復元、Web サービス、および仲介サーバーの設定を構成できます。詳細については、以下のサブセクションを参照してください。Standard Edition サーバーの設定の定義および構成の詳細については、「[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)」および「[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-p132">For a Standard Edition server, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="0c754-218">全般設定</span><span class="sxs-lookup"><span data-stu-id="0c754-218">General Settings</span></span>

<span data-ttu-id="0c754-219">以下の全般設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-219">You can configure the following general settings:</span></span>

- <span data-ttu-id="0c754-220">[**FQDN**]。</span><span class="sxs-lookup"><span data-stu-id="0c754-220">**FQDN**.</span></span> <span data-ttu-id="0c754-221">Note that the FQDN cannot be changed.</span><span class="sxs-lookup"><span data-stu-id="0c754-221">Note that the FQDN cannot be changed.</span></span> <span data-ttu-id="0c754-222">You must remove and redefine the Standard Edition server to change the FQDN associated with it.</span><span class="sxs-lookup"><span data-stu-id="0c754-222">You must remove and redefine the Standard Edition server to change the FQDN associated with it.</span></span>

- <span data-ttu-id="0c754-p134">[**すべての構成済み IP アドレスを使用する**] または [**選択された IP アドレスのみにサービスの使用を制限する**] を選択します。定義済みの IP アドレスにサービスを制限する設定を選択する場合は、PSTN の場合を除いて、すべての通信でサーバーが使用するプライマリ IP アドレスを定義します。PSTN 使用には、別の IP アドレスを定義します。[**IPv6 を有効にする**] を選択して、このサーバーに対して IPv6 を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p134">Select **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to limit the service to defined IP addresses, you will define the Primary IP address that the server will use for all communications, except for PSTN. You define a separate IP address for PSTN usage. You can also select **Enable IPv6** to enable IPv6 for this server.</span></span>

- <span data-ttu-id="0c754-p135">[**ロード バランサー機器の監視ポートの有効化**]。チェック ボックスをオンにし、ロード バランサー機器でサーバーの状態を監視するために使用するポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p135">**Enable Hardware Load Balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the server.</span></span>

- <span data-ttu-id="0c754-p136">[**特徴と機能**] では、このサーバーに併置する追加の役割を定義します。次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p136">In **Features and Functionality**, define the additional roles that you want to collocate with this server. You can configure the following settings:</span></span>

  - <span data-ttu-id="0c754-p137">[**電話会議**]。音声、ビデオ、およびアプリケーション共有が含まれます。このオプションを選択した後で、[**ダイヤルイン (PSTN) 会議**] を選択できます。PSTN ゲートウェイは、仲介サーバーの設定を行うときに後で指定して定義できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p137">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select **Dial-in (PSTN) conferencing**. You can specify and define a PSTN gateway later under Mediation Server settings.</span></span>

  - <span data-ttu-id="0c754-235">[**エンタープライズ VoIP**]。</span><span class="sxs-lookup"><span data-stu-id="0c754-235">**Enterprise Voice**.</span></span> <span data-ttu-id="0c754-236">内部のボイスオーバー IP 通話を、修飾されたハンドセットとデバイス、および Skype for Business クライアントに対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="0c754-236">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="0c754-237">外部通話機能を有効にするには、仲介サーバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-237">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="0c754-238">詳細については、このトピックの「仲介サーバー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-238">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="0c754-239">[**関連付け**] では、次の情報を編集または指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-239">In **Associations** you can edit or specify the following:</span></span>

  - <span data-ttu-id="0c754-p139">[**SQL Server ストア**] を選択して、SQL Server ストアをフロントエンド サーバーと関連付けます。ミラーリングを有効にし、ミラーリング監視サーバーを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p139">Select **SQL Server store** to associate a SQL Server store with the Front End server. You can also enable mirroring and select a mirroring witness server.</span></span>

  - <span data-ttu-id="0c754-p140">[**ファイル共有**]。Standard Edition サーバーで使用するファイル ストアを変更できます。定義済みのファイル ストアのリストから選択すると、新しいファイル ストアを選択できます。[**新規作成**] をクリックすると、新しいファイル ストアを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p140">**File share**. Modify the file store that the Standard Edition server is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c754-246">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-246">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="0c754-p141">[**アーカイブ**]。アーカイブ SQL Server ストアを Standard Edition サーバーと関連付けます。リストからサーバーを選択して定義済みのアーカイブ ストアを選択するか、[**新規作成**] をクリックして新しいアーカイブ ストアを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p141">**Archiving**. Associate an Archiving SQL Server store with the Standard Edition server. You can select from an already defined Archiving store by selecting the server from the list, or click **New** to specify a new Archiving store.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c754-250">新しく定義したトポロジの公開前に、指定するサーバーが存在し、ドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-250">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="0c754-p142">[**監視 (CDR および QoE 指標)**]。監視 SQL Server ストアを Standard Edition サーバーと関連付けます。リストからサーバーを選択して定義済みの監視サーバーを選択するか、[**新規作成**] をクリックして新しい監視サーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p142">**Monitoring (CDR and QoE metrics**. Associate a Monitoring SQL Server store with the Standard Edition server. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

  - <span data-ttu-id="0c754-p143">[**Office Web Apps サーバーの関連付け**]。Office Web Apps サーバーをフロントエンド プールと関連付けるには、このオプションを選択します。リストから既存のサーバーを選択するか、または、[**新規**] をクリックして新しい Office Web Apps サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c754-p143">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

  - <span data-ttu-id="0c754-p144">[**エッジ プールの関連付け**]。エッジ サーバーまたはプールを Standard Edition サーバーと関連付けます。リストからサーバーを選択して定義済みのエッジ サーバーやプールから選択するか、[**新規作成**] をクリックして新しいエッジ サーバーやプールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p144">**Associate Edge pool**. Associate an Edge Server or pool with the Standard Edition server. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

### <a name="resiliency"></a><span data-ttu-id="0c754-260">復元</span><span class="sxs-lookup"><span data-stu-id="0c754-260">Resiliency</span></span>

<span data-ttu-id="0c754-p145">復元は、サーバーの高可用性と障害復旧を提供します。バックアップを用意することで、プライマリ サーバーに障害が発生しても、バックアップ サーバーが引き継ぐことができるので、ユーザーはサインインして通信することができます。障害が発生したシステムによっては、ユーザーの機能性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c754-p145">Resiliency provides disaster recovery and high availability for the server. By providing a backup, if the primary server fails, the backup can take over, enabling users to sign in and communicate. It is possible that there will be reduced functionality for users, depending on what systems have also failed.</span></span>

<span data-ttu-id="0c754-p146">リストから、サーバーのバックアップとして動作するフロントエンド プールまたは Standard Edition サーバーを選択します。フェールオーバーとフォールバックの時間間隔を有効にすることもできます。フェールオーバーとフォールバックの時間設定 (秒単位で指定) を有効にすると、障害が起きたレジストラーを自動検出し、プライマリ サーバーが回復したことを自動的に判定するためのフォールバック時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p146">From the list, select the Front End pool or Standard Edition server that will act as the backup for the server. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c754-p147">障害検出とフォールバックの時間間隔を定義するときには、サーバーが短時間で応答できなかった場合にフェールオーバーとフォールバックを引き起こすような間隔を入力しないように注意してください。プライマリ サーバーは、プールまたはサーバーの負荷状態によっては短時間で応答しない可能性があります。フェールオーバーとフォールバックの既定値は、プールからプール、またはプールから Standard Edition サーバーの場合で 300 秒と 600 秒です。サイトからプールまたは Standard Edition サーバーでの存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの場合、フェールオーバーの既定値は 120 秒で、フォールバックの既定値は 240 秒です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p147">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server should fail to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, based on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

### <a name="web-services"></a><span data-ttu-id="0c754-271">Web サービス</span><span class="sxs-lookup"><span data-stu-id="0c754-271">Web Services</span></span>

<span data-ttu-id="0c754-272">サーバーの Web サービスの追加設定を編集または指定するには、[**内部 Web サービス**] と [**外部 Web サービス**] の設定を変更または指定します。</span><span class="sxs-lookup"><span data-stu-id="0c754-272">To edit or specify additional setting for the web services on the server, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="0c754-273">[**内部 Web サービス**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-273">For **Internal Web services**, you can specify the following:</span></span>

- <span data-ttu-id="0c754-p148">[FQDN の上書き] を選択すると、サーバーの内部 Web サービス ID として別の FQDN を指定できます。この設定の既定値は、Standard Edition サーバーとして定義されている現在のサーバー名です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p148">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the server. By default, the setting is the current server name as defined for the Standard Edition server.</span></span>

- <span data-ttu-id="0c754-p149">展開で必要となる HTTP および HTTPS のリッスン ポートと公開ポート。既定の設定である HTTP のポート 80 と HTTPS のポート 443 は、最も一般的な設定です。通常、組織内またはインフラストラクチャ設計上の特別な要件がない限り、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p149">Listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings, and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="0c754-278">[**外部 Web サービス**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-278">For **External Web services**, you can specify the following:</span></span>

- <span data-ttu-id="0c754-p150">外部 Web サービスの FQDN。ここで指定する FQDN は、通常、リバース プロキシなどの外部接続要件に含まれる要件に従って定義されます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p150">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="0c754-p151">展開で必要とされる HTTP および HTTPS のリッスン ポート。既定の設定である HTTP のポート 8080 と HTTPS のポート 4443 が初期定義されています。リッスン ポートのこれらの設定は、リバース プロキシと外部ネットワークの要件に応じて変更します。これらの値により、サーバーで着信要求をリッスンするときのポートが決まります。サーバーでのポート要件の競合が生じない限り、通常、これらのポートを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p151">Listening ports for HTTP and HTTPS that your deployment requires. The default setting of port 8080 for HTTP and port 4443 for HTTPS is defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. These values determine what ports the server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the server.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="0c754-286">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="0c754-286">Mediation Server</span></span>

<span data-ttu-id="0c754-287">[**仲介サーバー**] では、次の情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c754-287">For **Mediation Server**, you can specify the following:</span></span>

- <span data-ttu-id="0c754-p152">仲介サーバーをサーバーに併置する場合、[**併置された仲介サーバーが有効**] チェック ボックスをオンにします。仲介サーバーを併置しない場合、このセクションで使用できる設定はありません。</span><span class="sxs-lookup"><span data-stu-id="0c754-p152">If you collocate the Mediation Server with the server, select the check box **Collocated Mediation Server enabled**. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="0c754-p153">仲介サーバーの併置を有効にした場合は、サーバーでの TLS のリッスン ポート範囲を定義します。既定のポートは 5067 です。[**TCP ポートを有効にする**] を選択する場合は、併置する仲介サーバーの TCP ポートを定義する必要があります。これはオプション設定です。この設定が必要かどうかは、ゲートウェイまたは PSTN の要件を参照して判断してください。既定では、TCP ポートの値は 5068 です。</span><span class="sxs-lookup"><span data-stu-id="0c754-p153">If you have enabled the collocation of the Mediation Server, you define the listening port range on the server for TLS. By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="0c754-p154">併置された仲介サーバーに関連付けるトランク。トランクを既に定義している場合は、それらを仲介サーバーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c754-p154">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="0c754-p155">仲介サーバーに関連付けられたゲートウェイが複数ある場合は、ゲートウェイを選択してから [**既定値にする**] をクリックすることにより、既定のゲートウェイを指定できます。既定としてのゲートウェイを選択解除するには、[**既定値の解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c754-p155">If you have more than one gateway associated with a Mediation Server, you can specify a default gateway by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="0c754-299">Standard Edition サーバーの設定の定義および構成の詳細については、「[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)」および「[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c754-299">For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


