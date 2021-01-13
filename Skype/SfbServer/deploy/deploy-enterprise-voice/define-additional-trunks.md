---
title: Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: Skype for Business Server のトポロジ ビルダーで仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法について説明します。'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836997"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="3b81b-103">Skype for Business Server のトポロジ ビルダーで追加のトランクを定義する</span><span class="sxs-lookup"><span data-stu-id="3b81b-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="3b81b-104">**概要:** Skype for Business Server のトポロジ ビルダーで、仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="3b81b-105">ピアを仲介サーバーに関連付ける追加のトランクを定義するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="3b81b-106">ピアは、公衆交換電話網 (PSTNエンタープライズ VoIP接続できるユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3b81b-107">ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。</span><span class="sxs-lookup"><span data-stu-id="3b81b-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="3b81b-108">トランクは、仲介サーバーとゲートウェイの間の論理接続です。</span><span class="sxs-lookup"><span data-stu-id="3b81b-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b81b-109">このトピックでは、「展開」のドキュメントの [「Skype for Business Server](define-a-gateway.md) のトポロジ ビルダーでゲートウェイを定義する」で説明するように、少なくとも 1 つの仲介サーバーまたはスタンドアロンの仲介サーバーまたはプールを使用して PSTN ゲートウェイとルート トランクをセットアップしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b81b-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="3b81b-110">仲介サーバーとゲートウェイ ピアの間に追加のトランクを定義するには</span><span class="sxs-lookup"><span data-stu-id="3b81b-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="3b81b-111">トポロジ ビルダーの起動: **[** スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business Server 2015]** をクリックして **、[Skype for Business Server 2015Topology Builder]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b81b-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="3b81b-112">[Skype for Business Server] の [サイト名] の **[共有** コンポーネント] で、[ **トランク** ] ノードを右クリックし、[新しいトランク] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3b81b-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="3b81b-113">[**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="3b81b-114">2 つのトランクに同じ名前を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="3b81b-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="3b81b-115">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b81b-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="3b81b-116">[**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3b81b-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="3b81b-117">**[PSTN** ゲートウェイのリッスン ポート] で、ピア (PSTN ゲートウェイ、IP-PBX、または SBC) が、このトランクに関連付けられる仲介サーバーから SIP メッセージを受信するリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="3b81b-118">既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。</span><span class="sxs-lookup"><span data-stu-id="3b81b-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="3b81b-119">既定の存続可能ブランチ アプライアンス ポートは、TCP の場合は 5081、TLS の場合は 5082 です。</span><span class="sxs-lookup"><span data-stu-id="3b81b-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="3b81b-120">[**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b81b-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b81b-121">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="3b81b-122">[ **関連付けられた仲介サーバー**] で、このピアのルート トランクに関連付ける仲介サーバー プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="3b81b-123">[ **関連付けられた仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリッスン ポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b81b-124">Skype for Business Server で複数のトランクがサポートされている場合、異なるトランク名を持つ 2 つのトランクを同じ関連付けられた仲介サーバー ポートと IP/PSTN ゲートウェイのリッスン ポートで **構成することはできません。**</span><span class="sxs-lookup"><span data-stu-id="3b81b-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="3b81b-125">Skype for Business Server での複数のトランクのサポートにより、仲介サーバーで複数の SIP 信号ポートを定義して、複数のピアと通信できます。</span><span class="sxs-lookup"><span data-stu-id="3b81b-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="3b81b-126">トランクを定義する場合、関連付けられた仲介 **サーバー** のポート番号は、仲介サーバーが許可するプロトコルのリッスン ポートの範囲内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b81b-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="3b81b-127">このポート範囲は、Skype for Business Server プールと仲介サーバー プールで定義されます。</span><span class="sxs-lookup"><span data-stu-id="3b81b-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="3b81b-128">関連する仲介サーバー プールを右クリックし、[プロパティの編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b81b-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="3b81b-129">[**リッスン ポート**] フィールドでポート範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b81b-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="3b81b-130">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b81b-130">Click **OK**.</span></span> 
    

