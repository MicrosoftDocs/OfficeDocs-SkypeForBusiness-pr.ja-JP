---
title: 'Lync Server 2013: 場所に基づくルーティングでサポートされていない機能'
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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="550a3-102">Lync Server 2013 の場所に基づくルーティングでサポートされていない機能</span><span class="sxs-lookup"><span data-stu-id="550a3-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="550a3-103">_**最終更新日:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="550a3-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="550a3-104">位置情報に基づくルーティングは、次の種類の操作には適用されません。</span><span class="sxs-lookup"><span data-stu-id="550a3-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="550a3-105">Lync エンドポイントがこれらの機能を使って PSTN エンドポイントを操作する場合、位置情報に基づくルーティングは強制されません。</span><span class="sxs-lookup"><span data-stu-id="550a3-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="550a3-106">会議への PSTN ダイヤルイン</span><span class="sxs-lookup"><span data-stu-id="550a3-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="550a3-107">応答グループによる PSTN 通話の着信および発信</span><span class="sxs-lookup"><span data-stu-id="550a3-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="550a3-108">通話保留による PSTN 通話の保留または再開</span><span class="sxs-lookup"><span data-stu-id="550a3-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="550a3-109">アナウンス サービスへの PSTN 通話の着信</span><span class="sxs-lookup"><span data-stu-id="550a3-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="550a3-110">着信 PSTN 通話のグループ通話ピックアップによる再開</span><span class="sxs-lookup"><span data-stu-id="550a3-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="550a3-111">次の一覧の操作の種類に位置ベースのルーティングルールを適用するには、会議で位置情報に基づくルーティングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="550a3-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="550a3-112">会議からの PSTN ダイヤルアウト</span><span class="sxs-lookup"><span data-stu-id="550a3-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="550a3-113">ピアツーピアの音声会話から PSTN エンドポイントを利用する会議へのエスカレーション</span><span class="sxs-lookup"><span data-stu-id="550a3-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="550a3-114">PSTN エンドポイントを利用する取次転送</span><span class="sxs-lookup"><span data-stu-id="550a3-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="550a3-115">会議で位置情報に基づくルーティングを有効にするには、「 [Lync Server 2013 の会議での位置情報に基づくルーティング](lync-server-2013-location-based-routing-for-conferencing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="550a3-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="550a3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="550a3-116">See Also</span></span>


[<span data-ttu-id="550a3-117">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="550a3-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

