---
title: 'Lync Server 2013: Location-Based ルーティングでサポートされていない機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a7d32c0448abfe3552fdfe657b9c6bec960a08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512864"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="578bd-102">Lync Server 2013 での Location-Based ルーティングでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="578bd-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="578bd-103">_**トピックの最終更新日:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="578bd-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="578bd-104">Location-Based ルーティングは、次の種類の相互作用には適用されません。</span><span class="sxs-lookup"><span data-stu-id="578bd-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="578bd-105">Lync エンドポイントがこれらの機能を使用して PSTN エンドポイントと対話する場合、Location-Based ルーティングは適用されません。</span><span class="sxs-lookup"><span data-stu-id="578bd-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="578bd-106">電話会議への PSTN ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="578bd-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="578bd-107">応答グループを介した着信および発信 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="578bd-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="578bd-108">コールパークによる PSTN 通話のコールパークまたは取得</span><span class="sxs-lookup"><span data-stu-id="578bd-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="578bd-109">アナウンスサービスへの PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="578bd-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="578bd-110">グループ通話ピックアップで取得した PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="578bd-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="578bd-111">次の一覧の操作の種類に Location-Based ルーティングルールを適用するには、電話会議用に Location-Based ルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="578bd-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="578bd-112">会議からの PSTN ダイヤルアウト</span><span class="sxs-lookup"><span data-stu-id="578bd-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="578bd-113">ピアツーピア音声会話から PSTN エンドポイントを含む会議へのエスカレーション</span><span class="sxs-lookup"><span data-stu-id="578bd-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="578bd-114">PSTN エンドポイントを含む提案転送</span><span class="sxs-lookup"><span data-stu-id="578bd-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="578bd-115">会議の Location-Based ルーティングを有効にするには、「 [Lync Server 2013 の会議の場所に基づくルーティング](lync-server-2013-location-based-routing-for-conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="578bd-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="578bd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="578bd-116">See Also</span></span>


[<span data-ttu-id="578bd-117">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="578bd-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

