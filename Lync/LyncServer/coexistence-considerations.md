---
title: 共存の考慮事項
description: 共存の考慮事項。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd1f9525b37bdee3249e0e47352fdea1bc7f012f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547033"
---
# <a name="coexistence-considerations"></a><span data-ttu-id="f89e1-103">共存の考慮事項</span><span class="sxs-lookup"><span data-stu-id="f89e1-103">Coexistence considerations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89e1-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f89e1-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f89e1-105">移行後、Lync Server 2013、常設チャットサーバープールのみが存在し、従来の展開を使用停止にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f89e1-105">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="f89e1-106">移行が完了する前、および現在のグループチャットサーバーの展開を完全に使用停止にする前に、次のいずれかの展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f89e1-106">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="f89e1-107">Lync server 2013、常設チャットサーバープール。 Lync Server 2013 プールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89e1-107">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="f89e1-108">Lync server 2010、グループチャットプール。 Lync Server 2010 プールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89e1-108">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="f89e1-109">Office Communications Server 2007 R2 グループチャットプール。これは、Office Communications Server 2007 R2 プールに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89e1-109">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="f89e1-p101">これらの展開は共存できますが、カテゴリ、ルーム、およびアドイン間のやり取りはできません。</span><span class="sxs-lookup"><span data-stu-id="f89e1-p101">These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="f89e1-112">手動構成を使用すると、従来のクライアント (グループチャットクライアント) は、Office Communications Server 2007 R2、Lync Server 2010、グループチャット、または Lync Server 2013 に対して、一度に1つのプールに接続できます。</span><span class="sxs-lookup"><span data-stu-id="f89e1-112">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="f89e1-113">Lync 2013 (クライアント) は、従来のグループチャットサーバープールではなく、Lync Server 2013、常設チャットサーバープールとのみ対話できます。</span><span class="sxs-lookup"><span data-stu-id="f89e1-113">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="f89e1-114">Lync 2013 (クライアント) で常設チャットを使用するには、ユーザーが Lync 2013 に所属し、ポリシーによって有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89e1-114">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

