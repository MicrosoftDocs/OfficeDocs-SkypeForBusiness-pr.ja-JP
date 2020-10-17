---
title: 'Lync Server 2013: Lync Server を System Center Operations Manager で監視する'
description: 'Lync Server 2013: Lync Server を System Center Operations Manager で監視します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad93c47ab8d157b1e18b4bccc5094408f3d68ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548093"
---
# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="a5b66-103">System Center Operations Manager を使用した Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="a5b66-103">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b66-104">_**トピックの最終更新日:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="a5b66-104">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="a5b66-105">Lync server 管理パック (MP) は、すべての Lync Server の展開を監視するために選択できる監視ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a5b66-105">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="a5b66-106">MP は、従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装して、いくつかの主要な正常性インジケーターのペアイベント (エラー/成功) など、Lync Server で新しく利用可能なインストルメンテーションを有効にし、新しい代理トランザクション (Windows PowerShell コマンドレットのテスト) も完全に実装し \* ます。</span><span class="sxs-lookup"><span data-stu-id="a5b66-106">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="a5b66-107">Lync Server 2013 管理パックとそれに関連するドキュメントは、で見つけることができ [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468) ます。</span><span class="sxs-lookup"><span data-stu-id="a5b66-107">You can find the Lync Server 2013 Management Pack and its related documentation at [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="a5b66-108">System Center Operations Manager 2012 を実行している場合は、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5b66-108">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

