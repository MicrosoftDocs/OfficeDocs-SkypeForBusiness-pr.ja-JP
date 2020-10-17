---
title: 'Lync Server 2013: 複数のトランクのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2581ee5f67c6af1c5afd0622f7893ccc2486b51d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507044"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="4c3e0-102">Lync Server 2013 での複数トランクのサポート</span><span class="sxs-lookup"><span data-stu-id="4c3e0-102">Multiple trunk support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c3e0-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4c3e0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4c3e0-104">Lync Server 2013 機能は、ゲートウェイと仲介サーバー間の複数の関連付けをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="4c3e0-105">これらの関連付けは、仲介サーバープールと公衆交換電話網 (PSTN) ゲートウェイ、セッションボーダーコントローラー (SBC)、または ip-pbx との間の論理的な関連付けであるトランクを定義することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="4c3e0-106">トポロジビルダーを使用して、ゲートウェイを仲介サーバー (つまり、トランク) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="4c3e0-107">Lync Server 2013 でトランクを割り当てるまたは削除するには、まず、トポロジビルダーでトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="4c3e0-108">トランクは、仲介サーバーの完全修飾ドメイン名 (FQDN)、仲介サーバーのリッスンポート、ゲートウェイ FQDN、ゲートウェイリッスンポートという関連付けで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="4c3e0-109">複数のトランクを構成するには、同じゲートウェイと仲介サーバーの間に複数の関連付けを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="4c3e0-110">これにより、エンタープライズ Voip インフラストラクチャの弾力性が向上します。これは、構内交換 (PBX) 間の運用シナリオで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="4c3e0-111">トランクが定義されている場合は、ルートに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="4c3e0-112">トランクをルートに関連付けるには、トポロジビルダーでトランクの簡単な名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="4c3e0-113">この単純な名前は、Lync Server コントロールパネルでのトランク名として使用されます。ここで、トランクはルートに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="4c3e0-114">単純なトランク名は、Lync Server 管理シェルからのゲートウェイ名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="4c3e0-115">管理者は、仲介サーバーに関連付けられている既定のトランクを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="4c3e0-116">トポロジビルダーで、関連付けられている仲介サーバーを右クリックし、[ **プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="4c3e0-117">仲介サーバーの既定のゲートウェイを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="4c3e0-118">次の図は、各仲介サーバーとゲートウェイに対して定義されている複数のトランクを示しています。</span><span class="sxs-lookup"><span data-stu-id="4c3e0-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="4c3e0-119">**M-N トランクルーティング**</span><span class="sxs-lookup"><span data-stu-id="4c3e0-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="4c3e0-120">![複数のトランクの割り当て。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "複数のトランクの割り当て。")</span><span class="sxs-lookup"><span data-stu-id="4c3e0-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

