---
title: 'Lync Server 2013: IPv6 の移行と共存の考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4a042089c0961eb8ea8313b78bbfcafa72c999
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="8d6b6-102">Lync Server 2013 での IPv6 の移行と共存の考慮事項</span><span class="sxs-lookup"><span data-stu-id="8d6b6-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d6b6-103">_**トピックの最終更新日:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="8d6b6-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="8d6b6-104">IP version 6 (IPv6) は、Lync Server 2010 または Office Communications Server ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="8d6b6-105">パイロット目的で、Lync Server 2010 と Lync Server 2013 のデュアルスタック共存をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="8d6b6-106">任意のプールに対して IPv6 (デュアルスタックネットワーク) を有効にする前に、特定の中央サイトのすべてのプールを Lync Server 2013 にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="8d6b6-107">IPv6 に対応したプールのみを構成する必要がある場合は、テスト用のラボ環境に IPv6 専用のプールを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="8d6b6-108">次のシナリオは、移行と共存でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="8d6b6-109">Lync server 2013、Lync Server 2010、および Office Communications Server 2007 R2 プールを IPv4 モードで使用すると、デュアルスタックモードで Lync Server 2013 と共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="8d6b6-110">Ipv6 専用のプールが孤立している場合は、Lync Server 2013 プールを IPv6 専用モードにします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

