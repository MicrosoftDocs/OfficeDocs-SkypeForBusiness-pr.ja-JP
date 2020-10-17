---
title: Lync Server 2013 のバックアップレジストラー関係
description: Lync Server 2013 のバックアップレジストラー関係。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b0bfce6444ae78c2fb792a6d63dba4bf36b1791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552319"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="024c9-103">Lync Server 2013 のバックアップレジストラーの関係</span><span class="sxs-lookup"><span data-stu-id="024c9-103">Backup Registrar relationships in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="024c9-104">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="024c9-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="024c9-105">障害復旧の機能を提供するほか、ペアになった 2 つのプールは互いにバックアップ レジストラーの役割も果たします。</span><span class="sxs-lookup"><span data-stu-id="024c9-105">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="024c9-106">Lync Server 2013 では、フロントエンドプール間のバックアップレジストラーの関係は、常に1:1 および相互になります。</span><span class="sxs-lookup"><span data-stu-id="024c9-106">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="024c9-107">これは、P1 が P2 のバックアップであれば P2 が P1 のバックアップでなければならず、また双方がその他のいかなるフロントエンド プールのバックアップにもなれないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="024c9-107">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="024c9-108">これは、Lync Server 2010 からの変更で、フロントエンドプールのバックアップの関係は最大でも1です。</span><span class="sxs-lookup"><span data-stu-id="024c9-108">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="024c9-109">2つのフロントエンドプール間のバックアップ関係は、1:1 および対称である必要がありますが、各フロントエンドプールは、Lync Server 2010 の場合と同様に、任意の数の存続可能ブランチアプライアンスのバックアップレジストラーにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="024c9-109">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="024c9-110">Lync Server 2013 では、存続可能ブランチアプライアンスに所属しているユーザーに対して障害復旧サポートが拡張されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="024c9-110">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="024c9-111">存続可能ブランチアプライアンスのバックアップとして機能するフロントエンドプールが停止すると、存続可能ブランチアプライアンスにサインインしたユーザーは、フロントエンドプールに所属するユーザーがバックアップフロントエンドプールにフェールオーバーした後でも復元モードになります。</span><span class="sxs-lookup"><span data-stu-id="024c9-111">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

