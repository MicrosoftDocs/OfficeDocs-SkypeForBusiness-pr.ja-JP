---
title: Skype for Business Server のトポロジビルダーでゲートウェイを定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '概要: Skype for Business Server のトポロジビルダーで PSTN ゲートウェイを定義する方法について説明します。'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233219"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="1e00e-103">Skype for Business Server のトポロジビルダーでゲートウェイを定義する</span><span class="sxs-lookup"><span data-stu-id="1e00e-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="1e00e-104">**概要:** Skype for Business Server のトポロジビルダーで PSTN ゲートウェイを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="1e00e-105">次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip を有効にしているユーザー向けに、仲介サーバーを関連付け、PSTN (公衆交換電話網) への接続を提供できるピアを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="1e00e-106">仲介サーバーへのピアは、SIP トランクを構成することによって、接続先のインターネットテレフォニーサービスプロバイダー (ITSP) の PSTN ゲートウェイ、IP PBX、またはセッション境界コントローラー (SBC) にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e00e-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="1e00e-107">仲介サーバーのピアを定義するには</span><span class="sxs-lookup"><span data-stu-id="1e00e-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="1e00e-108">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="1e00e-109">[Skype for Business Server] の [サイト名]、[共有コンポーネント] の順にクリックし、[ **Pstn ゲートウェイ**] ノードを右クリックして、[**新しい pstn ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="1e00e-110">[**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e00e-111">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e00e-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="1e00e-112">新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="1e00e-113">PSTN ゲートウェイのルート トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="1e00e-114">トランクは、仲介サーバーと、組で一意に識別されたゲートウェイの間の論理的な接続です。</span><span class="sxs-lookup"><span data-stu-id="1e00e-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="1e00e-115">{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP と FQDN、ゲートウェイリッスンポート}</span><span class="sxs-lookup"><span data-stu-id="1e00e-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="1e00e-116">トポロジビルダーで PSTN ゲートウェイを定義する場合は、トポロジに PSTN ゲートウェイを正常に追加するためにルートトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e00e-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="1e00e-117">ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。</span><span class="sxs-lookup"><span data-stu-id="1e00e-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="1e00e-118">[ **IP/PSTN ゲートウェイのリスニングポート**] に、PSTN ゲートウェイのルートトランクと関連付けられる仲介サーバーからの SIP メッセージについて、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="1e00e-119">(既定では、ポートは、PSTN ゲートウェイ、PBX、または SBC 上のトランスポート層セキュリティ (TLS) 用の伝送制御プロトコル (TCP) および5067用の5066です。</span><span class="sxs-lookup"><span data-stu-id="1e00e-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="1e00e-120">ブランチサイトの Survivable Branch Appliance では、既定のポートは TCP 用の5081で、TLS の場合は5082です。)</span><span class="sxs-lookup"><span data-stu-id="1e00e-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="1e00e-121">[**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e00e-122">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="1e00e-123">[**関連付けられた仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="1e00e-124">[**関連付けられた仲介サーバーポート**] に、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e00e-125">Skype for Business Server で複数のトランクがサポートされている場合は、複数の PSTN ゲートウェイと通信するために、仲介サーバー上で複数の SIP シグナリングポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="1e00e-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="1e00e-126">トランクを定義する場合、**関連する仲介サーバーポート**は、仲介サーバーで許可されている各プロトコルのリスニングポートの範囲内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e00e-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="1e00e-127">このポート範囲は、「Skype for Business Server」と「仲介プール」で定義されています。</span><span class="sxs-lookup"><span data-stu-id="1e00e-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="1e00e-128">対象の仲介サーバープールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="1e00e-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="1e00e-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="1e00e-130">定義されたピアが実行中で、指定した FQDN または IP アドレスを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e00e-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="1e00e-131">次に、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="1e00e-132">[**Skype for Business Server**] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e00e-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

