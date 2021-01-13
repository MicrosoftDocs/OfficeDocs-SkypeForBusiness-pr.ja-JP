---
title: Skype for Business Server でトランクを構成する
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: Skype for Business Server で仲介サーバーとピア間のトランクを構成エンタープライズ VoIPを構成する方法について学習します。'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824957"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="dae47-103">Skype for Business Server でトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="dae47-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="dae47-104">**概要:** Skype for Business Server で仲介サーバーとピア間のトランクを構成するエンタープライズ VoIPを確認します。</span><span class="sxs-lookup"><span data-stu-id="dae47-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="dae47-105">エンタープライズ VoIP 展開の一環として、仲介サーバーと次の 1 つ以上のピア間のトランクを構成して、組織内の エンタープライズ VoIP クライアントおよびデバイスに公衆交換電話網 (PSTN) 接続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="dae47-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="dae47-106">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="dae47-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="dae47-107">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="dae47-107">PSTN gateway</span></span>
    
- <span data-ttu-id="dae47-108">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="dae47-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="dae47-109">詳細については [、「Skype for Business Server での PSTN 接続の計画」を参照してください](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)。</span><span class="sxs-lookup"><span data-stu-id="dae47-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="dae47-110">Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dae47-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="dae47-111">これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。</span><span class="sxs-lookup"><span data-stu-id="dae47-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="dae47-112">トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="dae47-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="dae47-113">Skype for Business Server でトランクを割り当てるまたは削除するには、最初にトポロジ ビルダーでトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae47-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="dae47-114">トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリッスン ポート、ゲートウェイ FQDN、およびゲートウェイ リッスン ポートの関連付けで構成されます。</span><span class="sxs-lookup"><span data-stu-id="dae47-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="dae47-115">複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dae47-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="dae47-116">これにより、PBX (エンタープライズ VoIP) の相互運用シナリオで特に役立つ、ネットワーク インフラストラクチャの回復性が向上します。</span><span class="sxs-lookup"><span data-stu-id="dae47-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="dae47-117">トランクが定義されている場合は、ルートに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae47-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="dae47-118">トランクをルートに関連付ける場合は、トポロジ ビルダーでトランクの簡単な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="dae47-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="dae47-119">この簡単な名前は、トランクをルートに関連付けできる Skype for Business Server コントロール パネルのトランク名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="dae47-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="dae47-120">単純なトランク名は、Skype for Business Server 管理シェルからのゲートウェイ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="dae47-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="dae47-121">管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dae47-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="dae47-122">トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dae47-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="dae47-123">仲介サーバーの既定のゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="dae47-123">Specify the default gateway for the Mediation Server.</span></span> 
  

