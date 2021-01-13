---
title: Lync Server 2010 用のエッジ設定編集エキスパンダー
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
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 次のプロパティを構成して、エッジ サーバーまたはエッジ プールの設定を編集します。
ms.openlocfilehash: f77eb71948bbbe6d2fe3e24b400d29e3bf5fd5a5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803297"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f85ae-103">Lync Server 2010 用のエッジ設定エキスパンダーの編集</span><span class="sxs-lookup"><span data-stu-id="f85ae-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="f85ae-104">次のプロパティを構成して、エッジ サーバーまたはエッジ プールの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="f85ae-105">**全般**</span><span class="sxs-lookup"><span data-stu-id="f85ae-105">**General**</span></span>
  
- <span data-ttu-id="f85ae-106">**内部プールの FQDN**: 内部プールの完全修飾ドメイン名は、ドメイン ネーム システム (DNS) ホスト (A または IPv6 の AAAA) レコードで定義されているエッジ サーバーまたはエッジ プールの ID です。</span><span class="sxs-lookup"><span data-stu-id="f85ae-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="f85ae-107">エッジ サーバーまたはエッジ プールと他のセッション開始プロトコル パートナーとのフェデレーションを有効にする場合は、[このエッジ プールのフェデレーションを有効にする (ポート **5061)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f85ae-108">フェデレーション用にアクティブに定義できるエッジ サーバーまたはエッジ プールは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="f85ae-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="f85ae-109">関連するスクリーン ショットに示されている構成は、別のエッジ サーバーまたはエッジ プールが既にフェデレーション用に構成されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f85ae-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="f85ae-110">フェデレーションの外部 DNS SRV レコード (_sipfederationtls._tcp. ) は、フェデレーションのエッジ \<external domain name\> サーバーまたはエッジ プールを指します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="f85ae-111">内部構成レプリケーション ポート **(HTTPS)** は、既定では TCP ポート 4443 で、中央管理ストアのローカル (つまり、エッジ サーバーに対してローカル) コピーがレプリケートされるポートです。</span><span class="sxs-lookup"><span data-stu-id="f85ae-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="f85ae-112">中央管理ストアのローカル コピーは、各コンピューター上の SQL Server **RTCLOCAL** データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f85ae-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="f85ae-113">レプリケーションは、中央管理サーバー (または中央管理サーバーの役割を持つフロントエンド サーバーまたはフロントエンド プール) からエッジ サーバーに対して開始される一方通行であり、内部インターフェイス ポートです。</span><span class="sxs-lookup"><span data-stu-id="f85ae-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="f85ae-114">[**次ホップの選択**]</span><span class="sxs-lookup"><span data-stu-id="f85ae-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="f85ae-115">使用する **次ホップ プール** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="f85ae-116">この役割を担うディレクター、ディレクター プール、フロントエンド サーバー、またはフロントエンド プールを定義します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="f85ae-117">次ホップ プールは、エッジ サーバーまたはエッジ プールの内部インターフェイスからの受信 SIP メッセージを受け入れ、エッジ内部インターフェイスに送信 SIP を送信するサーバーまたはサーバー プールです。</span><span class="sxs-lookup"><span data-stu-id="f85ae-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f85ae-118">ディレクターはオプションの役割であり、ディレクターを展開しない場合は、フロント エンド サーバー (単一のコンピューターまたはプール) がディレクターの役割を引き受けします。</span><span class="sxs-lookup"><span data-stu-id="f85ae-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="f85ae-119">[**外部設定**]</span><span class="sxs-lookup"><span data-stu-id="f85ae-119">**External settings**</span></span>
  
<span data-ttu-id="f85ae-120">プロパティのこのセクションでは、エッジ サーバーまたはエッジ プールの外部設定のプロパティを編集できます。</span><span class="sxs-lookup"><span data-stu-id="f85ae-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="f85ae-121">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f85ae-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="f85ae-122">個別の IP アドレスと完全修飾ドメイン名を各エッジ サーバー サービスに割り当てる場合は、[Web 会議と音声ビデオで別々の **FQDN** と IP アドレスを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f85ae-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f85ae-123">このチェック ボックスをオンにしない場合は、各エッジ サービスに別々のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f85ae-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="f85ae-124">各エッジ サービスは、アクセス エッジ サービスに定義されている FQDN を共有するため、同じ IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="f85ae-125">各エッジ サービスは、個別 IP アドレスと同じポートによって、または同じ IP アドレスと一意のポート値によって一意に識別される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f85ae-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="f85ae-126">ネットワーク アドレス変換 (NAT) デバイスの背後に隠されるプライベート アドレスまたは他のアドレスを使用するために、A/V エッジ サービスを構成する場合は **、[A/V** エッジ サービスが NAT を有効にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="f85ae-127">アクセス エッジサービスを編集するには、ホスト (A、IPv6 を使用する場合は AAAA) レコード、およびポート値によって DNS で定義されているアクセス エッジ サービスのプール **FQDN** を定義します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="f85ae-128">**Web** 会議エッジ サービスを編集するには、ホスト (A、IPv6 を使用する場合は AAAA) レコード、およびポート値によって DNS で定義されている Web 会議エッジ サービスのプール **FQDN** を定義します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="f85ae-129">A/V エッジ サービスを編集するには、ホスト (A、IPv6 を使用する場合は AAAA) レコード、およびポート値によって DNS で定義されている **、A/V** エッジ サービスのプール **FQDN** を定義します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f85ae-130">[Web 会議と音声ビデオで別々の **FQDN** と IP アドレスを有効にする] チェック ボックスをオンにした場合は、アクセス エッジ サービスプールの FQDN のみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="f85ae-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="f85ae-131">3 つのエッジ サービスのそれぞれに個別のポートを割り当ててください。</span><span class="sxs-lookup"><span data-stu-id="f85ae-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="f85ae-132">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="f85ae-133">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f85ae-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="f85ae-134">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="f85ae-134">**Help** Displays this help screen.</span></span>
  

