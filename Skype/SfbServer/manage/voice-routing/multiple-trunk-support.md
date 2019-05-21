---
title: Skype for Business Server での複数のトランクのサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。 これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。 トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274913"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="8fc80-105">Skype for Business Server での複数のトランクのサポート</span><span class="sxs-lookup"><span data-stu-id="8fc80-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="8fc80-106">Skype for Business Server 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8fc80-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="8fc80-107">これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッション境界コントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="8fc80-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="8fc80-108">トポロジビルダーを使用して、ゲートウェイを仲介サーバーに関連付けます (つまり、trunks)。</span><span class="sxs-lookup"><span data-stu-id="8fc80-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="8fc80-109">Skype for Business Server でトランクを割り当てまたは削除するには、まず、トポロジビルダーで樹幹を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc80-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="8fc80-110">トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイの FQDN、ゲートウェイのリスニングポートで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8fc80-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="8fc80-111">複数の trunks を構成するために、同じゲートウェイと仲介サーバー間に複数の関連付けを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="8fc80-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="8fc80-112">これにより、エンタープライズ Voip インフラストラクチャのさらなる弾力性が提供されます。これは、プライベート支店交換 (PBX) 間の運用シナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="8fc80-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="8fc80-113">トランクが定義されている場合は、ルートに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc80-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="8fc80-114">トランクをルートに関連付けるには、トポロジビルダーでトランクの単純な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="8fc80-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="8fc80-115">この簡易名は、Skype for Business Server コントロールパネルでトランク名として使用されます。ここでは、trunks をルートに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8fc80-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="8fc80-116">簡単なトランク名は、Skype for Business Server 管理シェルのゲートウェイ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fc80-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="8fc80-117">管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fc80-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="8fc80-118">トポロジビルダーで、関連する仲介サーバーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fc80-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="8fc80-119">仲介サーバーの既定のゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="8fc80-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="8fc80-120">次の図は、各仲介サーバーとゲートウェイに対して定義されている複数の trunks を示しています。</span><span class="sxs-lookup"><span data-stu-id="8fc80-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![複数のトランクの割り当て](../../media/multiple-trunk-assignments.jpg)
