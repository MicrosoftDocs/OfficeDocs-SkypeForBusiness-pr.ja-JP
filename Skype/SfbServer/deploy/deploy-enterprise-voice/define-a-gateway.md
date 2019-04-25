---
title: ビジネス サーバーの Skype でトポロジ ビルダーでゲートウェイを定義します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '概要: は、Skype でトポロジ ビルダーでビジネス サーバーの PSTN ゲートウェイを定義する方法を説明します。'
ms.openlocfilehash: 036c6805ab2c4821ee1bb0544b75553ab40c7100
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223178"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="b4e39-103">ビジネス サーバーの Skype でトポロジ ビルダーでゲートウェイを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="b4e39-104">**の概要:** ビジネス サーバーの Skype でトポロジ ビルダーで、PSTN ゲートウェイを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="b4e39-105">以下の手順を実行するには、エンタープライズ VoIP が有効なユーザーに公衆交換電話網 (PSTN) への接続を提供する仲介サーバーを関連付けることができますピアを定義するのにはトポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="b4e39-106">仲介サーバーのピアには、PSTN ゲートウェイ、IP PBX、または、セッション ボーダー コント ローラー (SBC) は、インターネット テレフォニー サービス プロバイダー (ITSP)、SIP トランクを構成することで接続するができます。</span><span class="sxs-lookup"><span data-stu-id="b4e39-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="b4e39-107">仲介サーバーのピアを定義するには</span><span class="sxs-lookup"><span data-stu-id="b4e39-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="b4e39-108">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b4e39-109">ビジネス サーバー、サイト名、共有のコンポーネントでは、Skype で、 **PSTN ゲートウェイ**のノードを右クリックし、**新しい PSTN ゲートウェイ**です。</span><span class="sxs-lookup"><span data-stu-id="b4e39-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="b4e39-110">[**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4e39-111">トランスポートの種類としては、トランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4e39-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="b4e39-112">新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="b4e39-113">PSTN ゲートウェイのルート トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="b4e39-114">トランクは、仲介サーバーと、組によって一意に識別するゲートウェイとの間の論理接続です。</span><span class="sxs-lookup"><span data-stu-id="b4e39-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="b4e39-115">{仲介サーバーの FQDN、仲介サーバーのリスニング ポート (TLS または TCP): ゲートウェイの ip アドレスと FQDN、ゲートウェイのリッスン ポート。</span><span class="sxs-lookup"><span data-stu-id="b4e39-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="b4e39-116">トポロジ ビルダーで、PSTN ゲートウェイを定義するときは、トポロジに PSTN ゲートウェイを正常に追加するのにはルートのトランクを定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b4e39-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="b4e39-117">ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。</span><span class="sxs-lookup"><span data-stu-id="b4e39-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="b4e39-118">**IP ネットワーク アドレスのリッスン ポート**] の下には、ゲートウェイ、PBX、または SBC を PSTN ゲートウェイのトランク ルートに関連付けられる仲介サーバーからの SIP メッセージを使用するリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="b4e39-119">(既定では、ポートは 5066 の伝送制御プロトコル (TCP) と PSTN ゲートウェイ、PBX、または SBC の 5067 のトランスポート層セキュリティ (TLS)。</span><span class="sxs-lookup"><span data-stu-id="b4e39-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="b4e39-120">支店サイトにあるリカバリ性に優れたブランチ アプライアンスに対する既定のポートは、5081 tcp と TLS の 5082)。</span><span class="sxs-lookup"><span data-stu-id="b4e39-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="b4e39-121">[**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4e39-122">セキュリティ上の理由により、TLS を使用することができる仲介サーバーには、ピアを配置することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="b4e39-123">**関連付けられている仲介サーバー**] の下には、この PSTN ゲートウェイのトランク ルートに関連付けるには、仲介サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="b4e39-124">**関連付けられている仲介サーバーのポート**] の下には、仲介サーバーはゲートウェイからの SIP メッセージを使用するリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b4e39-125">ビジネス サーバーに対する Skype の複数のトランク サポート、複数の SIP シグナルの複数の PSTN ゲートウェイとの通信の仲介サーバー上のポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b4e39-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="b4e39-126">トランクを定義する場合、仲介サーバーで許可されているそれぞれのプロトコルをリッスンしているポートの範囲内で**関連付けられている仲介サーバーのポート**を引き起こすことがあります。</span><span class="sxs-lookup"><span data-stu-id="b4e39-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="b4e39-127">このポートの範囲は、ビジネスのサーバーおよび仲介プールの Skype で定義されます。</span><span class="sxs-lookup"><span data-stu-id="b4e39-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="b4e39-128">目的の仲介サーバー プールを右クリックし、**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="b4e39-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="b4e39-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="b4e39-130">定義されたピアが実行中で、指定した FQDN または IP アドレスを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b4e39-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="b4e39-131">次に、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="b4e39-132">[**Skype for Business Server**] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4e39-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

