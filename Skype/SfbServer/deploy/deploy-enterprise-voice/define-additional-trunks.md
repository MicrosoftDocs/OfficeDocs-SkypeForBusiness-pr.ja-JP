---
title: Skype for Business Server の Topology Builder で追加の trunks を定義する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '概要: Skype for Business Server のトポロジビルダーで、仲介サーバーとゲートウェイピアの間に追加のトランクを定義する方法について説明します。'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303313"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="e5e14-103">Skype for Business Server の Topology Builder で追加の trunks を定義する</span><span class="sxs-lookup"><span data-stu-id="e5e14-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="e5e14-104">**概要:** Skype for Business Server のトポロジビルダーで、仲介サーバーとゲートウェイピアの間に追加のトランクを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="e5e14-105">次の手順に従って、ピアを仲介サーバーに関連付けることができる追加のトランクを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="e5e14-106">Peer は、公衆交換電話網 (PSTN) に接続して、エンタープライズ Voip を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e5e14-107">ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。</span><span class="sxs-lookup"><span data-stu-id="e5e14-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="e5e14-108">トランクは、仲介サーバーとゲートウェイの間の論理的な接続です。</span><span class="sxs-lookup"><span data-stu-id="e5e14-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5e14-109">このトピックでは、展開ドキュメントの「 [Skype For Business Server のトポロジビルダーでのゲートウェイの定義](define-a-gateway.md)」の説明に従って、少なくとも1つの併置またはスタンドアロンの仲介サーバーまたはプールで PSTN ゲートウェイとルートトランクをセットアップしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e5e14-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="e5e14-110">仲介サーバーとゲートウェイピアの間に追加のトランクを定義するには</span><span class="sxs-lookup"><span data-stu-id="e5e14-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="e5e14-111">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **skype for business Server 2015**]、[ **Skype for business server 2015topology Builder] の**順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="e5e14-112">[Skype for Business Server] の [サイト名]、[**共有コンポーネント**] で、[ **Trunks** ] ノードを右クリックし、[**新しいトランク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="e5e14-113">[**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="e5e14-114">2 つのトランクに同じ名前を付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5e14-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="e5e14-115">トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e14-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="e5e14-116">[**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e5e14-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="e5e14-117">[ **Pstn ゲートウェイのリスニングポート**] で、ピア (pstn ゲートウェイ、IP PBX、または SBC) がこのトランクに関連付けられている仲介サーバーから SIP メッセージを受信するリッスンポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="e5e14-118">既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。</span><span class="sxs-lookup"><span data-stu-id="e5e14-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="e5e14-119">既定の Survivable Branch Appliance ポートは、TCP と5082の TLS 用の5081です。</span><span class="sxs-lookup"><span data-stu-id="e5e14-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="e5e14-120">[**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5e14-121">セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="e5e14-122">[**関連付けられた仲介サーバー**] で、このピアのルートトランクに関連付ける仲介サーバープールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="e5e14-123">[**関連付けられた仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリスニングポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5e14-124">Skype for Business Server で複数のトランクがサポートされている場合、複数のトランク名を持つ2つの trunks を構成することはできません。**関連する仲介サーバーのポート**と**IP/PSTN ゲートウェイのリスニングポート**を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5e14-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="e5e14-125">Skype for Business Server で複数のトランクがサポートされていると、複数のピアと通信するために、複数の SIP シグナリングポートを仲介サーバーで定義できます。</span><span class="sxs-lookup"><span data-stu-id="e5e14-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="e5e14-126">トランクを定義する場合、**関連する仲介サーバーのポート**番号は、仲介サーバーで許可されている各プロトコルのリッスンポートの範囲内である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5e14-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="e5e14-127">このポート範囲は、Skype for Business Server および仲介サーバープールで定義されています。</span><span class="sxs-lookup"><span data-stu-id="e5e14-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="e5e14-128">関連する仲介サーバープールを右クリックし、[**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5e14-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="e5e14-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="e5e14-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="e5e14-130">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5e14-130">Click **OK**.</span></span> 
    

