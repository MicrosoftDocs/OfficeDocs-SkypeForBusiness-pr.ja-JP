---
title: 'Lync Server 2013: Lync Server プールの復元'
description: 'Lync Server 2013: Lync Server プールの復元'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543813"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="68b23-103">Lync server 2013 での Lync Server プールの復元</span><span class="sxs-lookup"><span data-stu-id="68b23-103">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b23-104">_**トピックの最終更新日:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="68b23-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="68b23-105">Lync Server の展開には、次の種類のプールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="68b23-105">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="68b23-106">フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="68b23-106">Front End Server</span></span>

  - <span data-ttu-id="68b23-107">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="68b23-107">Mediation Server</span></span>

  - <span data-ttu-id="68b23-108">常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="68b23-108">Persistent Chat Server</span></span>

  - <span data-ttu-id="68b23-109">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="68b23-109">Edge Server</span></span>

<span data-ttu-id="68b23-110">プール全体で停止が発生する場合は、プール内の各メンバーサーバーに対して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="68b23-110">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="68b23-111">フロントエンドプールの場合は、バックエンドサーバーを最初に復元してから、各フロントエンドサーバーを復元します。</span><span class="sxs-lookup"><span data-stu-id="68b23-111">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="68b23-112">詳細については、「 [Lync server 2013 で Enterprise edition のバックエンドサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) 」および「 [lync Server 2013 で enterprise edition のメンバーサーバーを復元](lync-server-2013-restoring-an-enterprise-edition-member-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b23-112">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="68b23-113">その他すべての種類のプールでは、各メンバー サーバーを復元します。</span><span class="sxs-lookup"><span data-stu-id="68b23-113">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="68b23-114">詳細については、「 [Lync server 2013 で Enterprise Edition のメンバーサーバーを復元する](lync-server-2013-restoring-an-enterprise-edition-member-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b23-114">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

