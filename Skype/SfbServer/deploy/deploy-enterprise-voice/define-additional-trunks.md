---
title: Skype でトポロジ ビルダーでビジネスのサーバーの追加トランクを定義します。
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: は、Skype でトポロジ ビルダーでビジネス サーバーの仲介サーバーとゲートウェイ ピアとの間の他のトランクを定義する方法を説明します。'
ms.openlocfilehash: 874d32053f4c3d91f16818bd34dc11806de8692c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223163"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="16d75-103">Skype でトポロジ ビルダーでビジネスのサーバーの追加トランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="16d75-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="16d75-104">**の概要:** ビジネス サーバーの Skype でトポロジ ビルダーでは、仲介サーバーとゲートウェイ ピアとの間の他のトランクを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16d75-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="16d75-105">以下の手順を実行する仲介サーバーのピアを関連付けることができます追加のトランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="16d75-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="16d75-106">ピアが接続を公衆交換電話網 (PSTN) とエンタープライズ VoIP が有効なユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="16d75-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="16d75-107">ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。</span><span class="sxs-lookup"><span data-stu-id="16d75-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="16d75-108">トランクは、仲介サーバーとゲートウェイ間の論理接続です。</span><span class="sxs-lookup"><span data-stu-id="16d75-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16d75-109">このトピックであると想定 PSTN ゲートウェイのセットアップとルートのトランクを少なくとも 1 つ配置されているか、スタンドアロン仲介サーバーまたはプールの展開に関するドキュメントで[Skype のビジネス サーバーで、トポロジ ビルダーでゲートウェイを定義](define-a-gateway.md)する」で説明されているようです。</span><span class="sxs-lookup"><span data-stu-id="16d75-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="16d75-110">仲介サーバーとゲートウェイ ピアとの間の他のトランクを定義するのには</span><span class="sxs-lookup"><span data-stu-id="16d75-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="16d75-111">開始トポロジ ビルダー: [**スタート**] ボタン [**すべてのプログラム**] をクリックして、**ビジネス サーバー 2015 の Skype**を**Skype ビジネス サーバー 2015Topology ビルダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d75-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="16d75-112">Skype ビジネス サーバー、サイト名、**共有コンポーネント**の下にある**トランク**] ノードを右クリックし、**新しいトランク**。</span><span class="sxs-lookup"><span data-stu-id="16d75-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="16d75-113">[**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="16d75-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="16d75-114">2 つのトランクに同じ名前を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="16d75-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="16d75-115">トランスポートの種類としては、トランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d75-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="16d75-116">[**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="16d75-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="16d75-117">[ **PSTN ゲートウェイのリッスン ポート**をリッスンしているポートを入力しますピア (PSTN ゲートウェイ、IP-PBX、または SBC) がこのトランクに関連付けられる仲介サーバーからの SIP メッセージを受け取ることです。</span><span class="sxs-lookup"><span data-stu-id="16d75-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="16d75-118">既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。</span><span class="sxs-lookup"><span data-stu-id="16d75-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="16d75-119">デフォルトのリカバリ性に優れたブランチ アプライアンスのポートは、TCP の 5081 および TLS の 5082 です。</span><span class="sxs-lookup"><span data-stu-id="16d75-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="16d75-120">[**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d75-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="16d75-121">セキュリティ上の理由により、TLS を使用することができる仲介サーバーには、ピアを配置することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="16d75-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="16d75-122">[**仲介サーバーの関連付けられている**、このピア ツー ピアのルートのトランクに関連付けるには、仲介サーバー プールを選択します</span><span class="sxs-lookup"><span data-stu-id="16d75-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="16d75-123">**関連付けられている仲介サーバーのポート**] の下には、リッスン ポートを仲介サーバーがピアから SIP メッセージを受信するを入力します。</span><span class="sxs-lookup"><span data-stu-id="16d75-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="16d75-124">ビジネス サーバーの Skype の複数のトランク サポート、トランクを別の名前を持つ 2 つのトランクを同じ**仲介サーバーの関連付けられているポート**と**IP ネットワーク アドレスのリッスン ポート**を構成できません。</span><span class="sxs-lookup"><span data-stu-id="16d75-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="16d75-125">ビジネス サーバーの Skype の複数のトランク サポート、複数の SIP ポートの信号は通信は、仲介サーバーの複数のピアにします。</span><span class="sxs-lookup"><span data-stu-id="16d75-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="16d75-126">トランクを定義する場合、仲介サーバーで許可されているそれぞれのプロトコルをリッスンしているポートの範囲内で**関連付けられている仲介サーバーのポート**番号を引き起こすことがあります。</span><span class="sxs-lookup"><span data-stu-id="16d75-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="16d75-127">このポートの範囲は、ビジネスのサーバーおよび仲介サーバー プールの Skype で定義されています。</span><span class="sxs-lookup"><span data-stu-id="16d75-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="16d75-128">関連の仲介サーバー プールを右クリックし、**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="16d75-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="16d75-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="16d75-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="16d75-130">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d75-130">Click **OK**.</span></span> 
    

