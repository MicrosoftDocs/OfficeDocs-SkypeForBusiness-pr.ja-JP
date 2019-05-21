---
title: Skype for Business Server で trunks を構成する
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: Skype for Business Server で仲介サーバーとエンタープライズボイスのピアの間でトランクを構成する方法について説明します。'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289098"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="ba8dd-103">Skype for Business Server で trunks を構成する</span><span class="sxs-lookup"><span data-stu-id="ba8dd-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="ba8dd-104">**概要:** Skype for Business Server で仲介サーバーとエンタープライズボイスのピアの間でトランクを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ba8dd-105">エンタープライズ Voip の展開の一部として、仲介サーバーと次のピアの1つ以上にトランクを構成して、組織内のエンタープライズボイスクライアントとデバイスの公衆交換電話網 (PSTN) 接続を提供できます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="ba8dd-106">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="ba8dd-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="ba8dd-107">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ba8dd-107">PSTN gateway</span></span>
    
- <span data-ttu-id="ba8dd-108">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="ba8dd-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="ba8dd-109">詳細については、「 [Skype For Business Server での PSTN 接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="ba8dd-110">Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="ba8dd-111">これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="ba8dd-112">トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="ba8dd-113">Skype for Business Server でトランクを割り当てまたは削除するには、まず、トポロジビルダーで樹幹を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="ba8dd-114">トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイの FQDN、ゲートウェイのリスニングポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="ba8dd-115">複数の trunks を構成するために、同じゲートウェイと仲介サーバー間に複数の関連付けを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="ba8dd-116">これにより、エンタープライズ Voip インフラストラクチャのさらなる弾力性が提供されます。これは、プライベート支店交換 (PBX) 間の運用シナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="ba8dd-117">トランクが定義されている場合は、ルートに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="ba8dd-118">トランクをルートに関連付けるには、トポロジビルダーでトランクの単純な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="ba8dd-119">この簡易名は、Skype for Business Server コントロールパネルでトランク名として使用されます。ここでは、trunks をルートに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="ba8dd-120">簡単なトランク名は、Skype for Business Server 管理シェルのゲートウェイ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="ba8dd-121">管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="ba8dd-122">トポロジビルダーで、関連する仲介サーバーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="ba8dd-123">仲介サーバーの既定のゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba8dd-123">Specify the default gateway for the Mediation Server.</span></span> 
  

