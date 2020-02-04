---
title: Lync Server 2010 用のエッジ設定編集エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: エッジサーバーまたはエッジプールの設定を編集するには、次のプロパティを設定します。
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697382"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2dfe5-103">Lync Server 2010 用のエッジ設定編集エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="2dfe5-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="2dfe5-104">エッジサーバーまたはエッジプールの設定を編集するには、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="2dfe5-105">**[全般]**</span><span class="sxs-lookup"><span data-stu-id="2dfe5-105">**General**</span></span>
  
- <span data-ttu-id="2dfe5-106">**内部プールの FQDN**: 内部プールの完全修飾ドメイン名は、ドメインネームシステム (DNS) Host (A または AAAA for IPv6) レコードで定義されているエッジサーバーまたはエッジプールの id です。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="2dfe5-107">他のセッション開始プロトコルパートナーとのフェデレーションにエッジサーバーまたはエッジプールを有効にする場合は、[**このエッジプールに対してフェデレーションを有効にする (port 5061)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2dfe5-108">フェデレーション用には、1つのエッジサーバーまたはエッジプールのみを定義できます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="2dfe5-109">関連付けられているスクリーンショットに示されている構成は、別のエッジサーバーまたはエッジプールが既にフェデレーション用に構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="2dfe5-110">フェデレーション用の外部 DNS SRV レコード (_sipfederationtls _tcp。\<外部ドメイン名\>) は、フェデレーション用にエッジサーバーまたはエッジプールをポイントします。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="2dfe5-111">既定では、TCP ポート4443での**内部構成レプリケーションポート (HTTPS)** は、中央管理ストアのローカル (つまり、エッジサーバーのローカル) コピーがレプリケートされるポートです。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="2dfe5-112">中央管理ストアのローカルコピーは、各コンピューターの SQL Server の**Rtclocal**データベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="2dfe5-113">複製は、サーバーの全体管理サーバー (または、中央管理サーバーの役割を保持するフロントエンドサーバーまたはフロントエンドプール) からエッジサーバーへ、または内部インターフェイスポートとして、一方向で開始されます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
  <span data-ttu-id="2dfe5-114">**次ホップの選択**</span><span class="sxs-lookup"><span data-stu-id="2dfe5-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="2dfe5-115">**次ホッププール**の一覧を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="2dfe5-116">この役割を担うディレクター、ディレクタープール、フロントエンドサーバー、フロントエンドプールのいずれかを定義します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="2dfe5-117">次ホッププールは、エッジサーバーまたはエッジプールの内部インターフェイスからの受信 SIP メッセージを受け付けるサーバーまたはサーバープールで、エッジ内部インターフェイスに送信 SIP を送信します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2dfe5-118">ディレクターはオプションの役割であり、ディレクターを展開しないことにした場合、フロントエンドサーバー (単一のコンピューターまたはプール) はディレクターの役割を引き受けます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
  <span data-ttu-id="2dfe5-119">**外部設定**</span><span class="sxs-lookup"><span data-stu-id="2dfe5-119">**External settings**</span></span>
  
<span data-ttu-id="2dfe5-120">プロパティのこのセクションでは、エッジサーバーまたはエッジプールの外部設定のプロパティを編集できます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="2dfe5-121">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="2dfe5-122">各 Edge Server サービスに個別の IP アドレスと完全修飾ドメイン名を割り当てる場合は、[ **web 会議と IP アドレスを別々に使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2dfe5-123">このチェックボックスをオンにしない場合は、エッジサービスごとに個別のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="2dfe5-124">各エッジサービスは、アクセスエッジサービスに対して定義されている FQDN を共有するため、同じ IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="2dfe5-125">各エッジサービスは、個別の IP アドレスと同じポート、または同じ IP アドレスと一意のポート値のいずれかによって一意に識別される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="2dfe5-126">ネットワークアドレス変換 (NAT) デバイスの背後に表示されるプライベートアドレスまたはその他のアドレスを使用するように A/v edge サービスを構成する場合は **、[a/v edge サービスを NAT で有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="2dfe5-127">**アクセスエッジサービス**を編集するには、Host (A) で定義されているアクセスエッジサービスの**プール FQDN**を定義し、レコードとポート値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="2dfe5-128">**Web 会議エッジサービス**を編集するには、DNS で定義されている Web 会議エッジサービスの**プール FQDN**を、Host (a、IPv6 が使用される場合は AAAA) レコードとポート値として定義します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="2dfe5-129">**A/v edge サービス**を編集するには、Host (a) によって定義された a/v edge サービスの**プール FQDN**を定義し、レコードとポート値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2dfe5-130">[ **Web 会議と A/V で個別の FQDN と IP アドレスを有効に**する] チェックボックスをオンにした場合は、アクセスエッジサービスプールの FQDN のみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="2dfe5-131">3つのエッジサービスごとに個別のポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-131">Assign distinct ports for each of the three Edge services.</span></span>
  
  <span data-ttu-id="2dfe5-132">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="2dfe5-133">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="2dfe5-134">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="2dfe5-134">**Help** Displays this help screen.</span></span>
  

