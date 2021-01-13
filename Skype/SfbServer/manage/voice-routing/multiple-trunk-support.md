---
title: Skype for Business Server での複数トランクのサポート
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。 これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。 トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826227"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="30660-105">Skype for Business Server での複数トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="30660-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="30660-106">Skype for Business Server の機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。</span><span class="sxs-lookup"><span data-stu-id="30660-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="30660-107">これらの関連付けは、仲介サーバー プールと公衆交換電話網 (PSTN) ゲートウェイ、セッション ボーダー コントローラー (SBC)、または IP-PBX の間の論理的な関連付けであるトランクを定義することで行います。</span><span class="sxs-lookup"><span data-stu-id="30660-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="30660-108">トポロジ ビルダーを使用して、ゲートウェイを仲介サーバー (トランク) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="30660-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="30660-109">Skype for Business Server でトランクを割り当てるまたは削除するには、最初にトポロジ ビルダーでトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30660-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="30660-110">トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーリッスン ポート、ゲートウェイ FQDN、およびゲートウェイ リッスン ポートの関連付けで構成されます。</span><span class="sxs-lookup"><span data-stu-id="30660-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="30660-111">複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。</span><span class="sxs-lookup"><span data-stu-id="30660-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="30660-112">これにより、PBX (エンタープライズ VoIP) の相互運用シナリオで特に役立つ、ネットワーク インフラストラクチャの回復性が向上します。</span><span class="sxs-lookup"><span data-stu-id="30660-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="30660-113">トランクが定義されている場合は、ルートに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30660-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="30660-114">トランクをルートに関連付ける場合は、トポロジ ビルダーでトランクの簡単な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="30660-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="30660-115">この簡単な名前は、トランクをルートに関連付けできる Skype for Business Server コントロール パネルのトランク名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="30660-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="30660-116">単純なトランク名は、Skype for Business Server 管理シェルからのゲートウェイ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="30660-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="30660-117">管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30660-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="30660-118">トポロジ ビルダーで、関連付けられた仲介サーバーを右クリックし、[プロパティ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="30660-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="30660-119">仲介サーバーの既定のゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="30660-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="30660-120">次の図は、仲介サーバーとゲートウェイごとに定義されている複数のトランクを示しています。</span><span class="sxs-lookup"><span data-stu-id="30660-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![複数トランク割り当て](../../media/multiple-trunk-assignments.jpg)
