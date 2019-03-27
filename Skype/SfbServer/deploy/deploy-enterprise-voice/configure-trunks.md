---
title: ビジネス サーバー用の Skype でトランクを構成します。
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '概要: は、Skype のビジネス サーバーの仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。'
ms.openlocfilehash: c47d1ff06fe695be939758c8444dac246c555de9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892858"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="d32db-103">ビジネス サーバー用の Skype でトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="d32db-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="d32db-104">**の概要:** Skype のビジネス サーバーの仲介サーバーとエンタープライズ VoIP のピア間のトランクを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d32db-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="d32db-105">エンタープライズ VoIP 展開の一部として、仲介サーバーと 1 つ以上のエンタープライズ VoIP クライアントと、組織内のデバイスの公衆交換電話網 (PSTN) 接続を提供する次のピア間のトランクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d32db-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="d32db-106">インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続</span><span class="sxs-lookup"><span data-stu-id="d32db-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="d32db-107">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="d32db-107">PSTN gateway</span></span>
    
- <span data-ttu-id="d32db-108">構内交換機 (PBX)</span><span class="sxs-lookup"><span data-stu-id="d32db-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="d32db-109">詳細については、 [Skype のビジネス サーバーの PSTN への接続の計画](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d32db-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="d32db-110">ビジネス サーバーの機能のための Skype では、ゲートウェイと仲介サーバーの間で複数のアソシエーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d32db-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="d32db-111">これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コント ローラー (SBC)、または IP PBX との間の論理的な関連付けには、トランクを定義することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="d32db-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="d32db-112">ゲートウェイを仲介サーバー (つまり、トランクなど) に関連付けるには、トポロジ ビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d32db-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="d32db-113">割り当てまたはトランクを Skype のビジネス サーバーの削除、最初にトポロジ ビルダーでトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d32db-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="d32db-114">トランクは、次の関連で構成されています: ドメイン名 (FQDN)、仲介サーバーのリッスン ポート、ゲートウェイの FQDN、およびゲートウェイ リッスン ポートを仲介サーバーの完全修飾します。</span><span class="sxs-lookup"><span data-stu-id="d32db-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="d32db-115">複数のトランクを構成するには、同じゲートウェイと仲介サーバーとの間の複数の関連付けを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d32db-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="d32db-116">これは、構内交換 (機 PBX) の interoperational のシナリオで特に便利ですが、エンタープライズ VoIP インフラストラクチャに追加の復元機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d32db-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="d32db-117">トランクを定義するときは、工順に関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d32db-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="d32db-118">ルートにトランクを関連付けるには、トポロジ ビルダーでは、トランクの簡易名を定義します。</span><span class="sxs-lookup"><span data-stu-id="d32db-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="d32db-119">この単純な名前は、ビジネス サーバーのコントロール パネル]、トランクできるルートに関連付けられているに、Skype でトランクの名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="d32db-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="d32db-120">トランクの単純な名前は、サーバー管理シェルのビジネスに、Skype からゲートウェイの名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="d32db-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="d32db-121">管理者は、仲介サーバーに関連付けられている既定のトランクを選択してください。</span><span class="sxs-lookup"><span data-stu-id="d32db-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="d32db-122">トポロジ ビルダーでは、関連付けられている仲介サーバーを右クリックし、し、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32db-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="d32db-123">仲介サーバーのデフォルト ゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="d32db-123">Specify the default gateway for the Mediation Server.</span></span> 
  

