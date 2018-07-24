---
title: Lync Server 2010 のエッジの設定の拡張を編集します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: エッジ サーバーまたはエッジ プールの設定を編集するには、次のプロパティを構成します。
ms.openlocfilehash: e09f20840627af19f1f9f2fa33dc5ab5f6b342f3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975929"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a><span data-ttu-id="5d879-103">Lync Server 2010 のエッジの設定の拡張を編集します。</span><span class="sxs-lookup"><span data-stu-id="5d879-103">Edit Edge Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="5d879-104">エッジ サーバーまたはエッジ プールの設定を編集するには、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5d879-104">You edit the settings for the Edge Server or Edge pool by configuring the following properties:</span></span> 
  
 <span data-ttu-id="5d879-105">**[全般]**</span><span class="sxs-lookup"><span data-stu-id="5d879-105">**General**</span></span>
  
- <span data-ttu-id="5d879-106">**内部プールの FQDN**: ドメイン ネーム システム (DNS) ホスト (A または AAAA ipv6) レコードに定義されている内部プールの完全修飾ドメイン名は、エッジ サーバーまたはエッジ プールの id。</span><span class="sxs-lookup"><span data-stu-id="5d879-106">**Internal pool FQDN**: The internal pool fully qualified domain name is the identity of the Edge Server or Edge pool as defined in the domain name system (DNS) host (A or AAAA for IPv6) record.</span></span>
    
- <span data-ttu-id="5d879-107">エッジ サーバーまたはエッジのプールの他のセッション開始プロトコルのパートナーとのフェデレーションを有効にする場合は、**このエッジ プール (ポート 5061) のフェデレーションを有効にする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d879-107">Select **Enable federation for this Edge pool (port 5061)** if you want to enable the Edge Server or Edge pool for federation with other session initiation protocol partners.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5d879-108">1 つのエッジ サーバーまたはエッジ プールをフェデレーション用にのみ定義できます。</span><span class="sxs-lookup"><span data-stu-id="5d879-108">You can only define one Edge Server or Edge pool actively for federation.</span></span> <span data-ttu-id="5d879-109">関連のスクリーン ショットに示すように構成するには、フェデレーションの別のエッジ サーバーまたはエッジ プールが既に構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="5d879-109">The configuration shown in the associated screen shot indicates that another Edge Server or Edge pool is already configured for federation.</span></span> <span data-ttu-id="5d879-110">フェデレーションの外部の DNS SRV レコード (_sipfederationtls._tcp です\<。外部のドメイン名\>) は、エッジ サーバーまたはエッジ プールをフェデレーション用にポイントします。</span><span class="sxs-lookup"><span data-stu-id="5d879-110">The external DNS SRV record for federation (_sipfederationtls._tcp.\<external domain name\>) will point to the Edge Server or Edge pool for federation.</span></span> 
  
- <span data-ttu-id="5d879-111">ポートでは、**内部構成レプリケーション ポート (HTTPS)**、既定の TCP ポート 4443 をローカル (つまり、エッジ トランスポート サーバーにローカル) 上の中央管理ストアに複製されます。</span><span class="sxs-lookup"><span data-stu-id="5d879-111">The **Internal Configuration Replication Port (HTTPS)**, by default at TCP port 4443, is the port that the local (that is, local to the Edge Servers) copy of the Central Management store is replicated over.</span></span> <span data-ttu-id="5d879-112">**RTCLOCAL**データベース内の各コンピューター上の SQL Server では、中央管理ストアのローカル コピーします。</span><span class="sxs-lookup"><span data-stu-id="5d879-112">The local copy of the Central Management store is in the **RTCLOCAL** database in the SQL Server on each computer.</span></span> <span data-ttu-id="5d879-113">レプリケーションは一方向、エッジ トランスポート サーバーにサーバーの全体管理サーバー (または、サーバーの全体管理サーバーの役割を保持しているフロント エンド サーバーまたはフロント エンド プール) から開始し、内部インターフェイスのポートします。</span><span class="sxs-lookup"><span data-stu-id="5d879-113">The replication is one-way, initiated from the Central Management Server (or, the Front End Server or Front End pool that holds the Central Management Server role) to the Edge Servers and is an internal interface port.</span></span>
    
 <span data-ttu-id="5d879-114">**次ホップの選択**</span><span class="sxs-lookup"><span data-stu-id="5d879-114">**Next hop selection**</span></span>
  
- <span data-ttu-id="5d879-115">一覧については、**次ホップ プール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d879-115">Select for the list your **Next hop pool**.</span></span> <span data-ttu-id="5d879-116">ディレクター プール、フロント エンド サーバーまたはフロント エンドのプールをこのロールを想定するか、ディレクターを定義します。</span><span class="sxs-lookup"><span data-stu-id="5d879-116">You define either a Director, Director pool, Front End Server or Front End pool to assume this role.</span></span> <span data-ttu-id="5d879-117">次ホップ プールは、サーバーまたはエッジ サーバーから受信した SIP メッセージを受け取るサーバー プールまたはエッジ プールの内部インターフェイスと外部の送信 SIP エッジの内部インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5d879-117">The next hop pool is the server or server pool that will accept inbound SIP messages from the Edge Server or Edge pool internal interface and send outbound SIP to the Edge internal interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d879-118">ダイレクタは、オプションのロールとディレクターを展開しない場合は、1 台のコンピューター (プール) は、フロント エンド サーバーが引き受けるディレクターです。</span><span class="sxs-lookup"><span data-stu-id="5d879-118">The Director is an optional role and if you decide not to deploy Directors, the Front End Servers (single computer or pool) will assume the Director role.</span></span> 
  
 <span data-ttu-id="5d879-119">**外部設定**</span><span class="sxs-lookup"><span data-stu-id="5d879-119">**External settings**</span></span>
  
<span data-ttu-id="5d879-120">プロパティのこのセクションでは、エッジ サーバーまたはエッジ プールの外部設定のプロパティを編集できます。</span><span class="sxs-lookup"><span data-stu-id="5d879-120">This section of the properties allows you to edit properties for the external settings of the Edge Server or Edge pool.</span></span> <span data-ttu-id="5d879-121">編集できるプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5d879-121">The following properties are available to edit:</span></span>
  
- <span data-ttu-id="5d879-122">選択、**を有効にする別の FQDN と IP アドレスの web 会議および A/V**にそれぞれ異なる IP アドレスと完全修飾ドメインを割り当てたい場合はチェック ボックスの名前を各エッジ サーバーのサービスへ。</span><span class="sxs-lookup"><span data-stu-id="5d879-122">Select the **Enable separate FQDN and IP address for web conferencing and A/V** check box if you want to assign distinct IP addresses and fully qualified domain names to each Edge Server service.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d879-123">チェック ボックスをオンにする場合は、エッジ サービスごとに別々 のポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d879-123">If you choose to not select the check box, you must use separate ports for each Edge service.</span></span> <span data-ttu-id="5d879-124">各エッジ サービスは、アクセス エッジ サービスに対して定義されている FQDN を共有して、同じ IP アドレスを使用して、そのためです。</span><span class="sxs-lookup"><span data-stu-id="5d879-124">Each Edge service will share the FQDN defined for the Access Edge service, and will therefore use the same IP address.</span></span> <span data-ttu-id="5d879-125">か、別個の IP アドレスと同じポートは、同じ IP アドレスやポートの一意の値によって、各エッジ サービスを一意に識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d879-125">Each Edge service must be uniquely identified by either a distinct IP address and same port, or the same IP address and unique port values.</span></span> 
  
- <span data-ttu-id="5d879-126">選択**A/音声ビデオ エッジ サービスでは、NAT が有効になっている**、A を構成する場合は、音声ビデオ エッジ サービスのプライベート アドレスまたはネットワーク アドレス変換 (NAT) デバイスの背後にある非表示になるその他のアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d879-126">Select **A/V Edge service is NAT enabled** if you want to configure the A/V Edge service to use a private address or other address that will be hidden behind a network address translation (NAT) device.</span></span>
    
- <span data-ttu-id="5d879-127">**アクセス エッジ サービス**を編集するに定義するアクセス エッジ サービスの**FQDN をプール**でホスト (A、および AAAA IPv6 を使用する場合)、DNS で定義されているレコードとポートの値</span><span class="sxs-lookup"><span data-stu-id="5d879-127">To edit the **Access Edge service**, you define the **Pool FQDN** for the Access Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="5d879-128">**Web 会議エッジ サービス**を編集するには、定義する Web 会議エッジ サービスの**FQDN をプール**でホスト (A、および AAAA IPv6 を使用する場合)、DNS で定義されているレコードとポートの値</span><span class="sxs-lookup"><span data-stu-id="5d879-128">To edit the **Web Conferencing Edge service**, you define a **Pool FQDN** for the Web Conferencing Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
- <span data-ttu-id="5d879-129">編集するのには、 **A/音声ビデオ エッジ サービス**、A の**プールの FQDN**を定義する音声ビデオ エッジ サービスのホスト (A、および AAAA IPv6 を使用する場合) によって、DNS で定義されているレコードとポートの値</span><span class="sxs-lookup"><span data-stu-id="5d879-129">To edit the **A/V Edge service**, you define a **Pool FQDN** for the A/V Edge service as defined in DNS by host (A, and AAAA if IPv6 is used) records and a port value</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5d879-130">選択した場合、**を有効にする別の FQDN と IP アドレスの web 会議および A/V** ] チェック ボックスでは、アクセス エッジ サービスのプールの FQDN のみが編集できます。</span><span class="sxs-lookup"><span data-stu-id="5d879-130">If you have selected the **Enable separate FQDN and IP address for web conferencing and A/V** check box, only the Access Edge service Pool FQDN will be available for editing.</span></span> <span data-ttu-id="5d879-131">3 つのエッジ サービスごとに個別のポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5d879-131">Assign distinct ports for each of the three Edge services.</span></span>
  
 <span data-ttu-id="5d879-132">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="5d879-132">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="5d879-133">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5d879-133">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="5d879-134">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="5d879-134">**Help** Displays this help screen.</span></span>
  

