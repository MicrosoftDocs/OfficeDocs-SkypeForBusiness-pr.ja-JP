---
title: 'Lync Server 2013: Lync Server を System Center Operations Manager で監視する'
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
ms.openlocfilehash: 341901ce6d467818e6aac433f7d8ca4dca37adef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="ae406-102">System Center Operations Manager を使用した Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="ae406-102">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae406-103">_**トピックの最終更新日:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="ae406-103">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="ae406-104">Lync server 管理パック (MP) は、すべての Lync Server の展開を監視するために選択できる監視ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ae406-104">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="ae406-105">MP は、従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装して、いくつかの主要な正常性インジケーターのペアイベント (エラー/成功) など、Lync Server で新しく利用可能なインストルメンテーションを有効にし\* 、新しい代理トランザクション (Windows PowerShell コマンドレットのテスト) も完全に実装します。</span><span class="sxs-lookup"><span data-stu-id="ae406-105">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="ae406-106">Lync Server 2013 管理パックとそれに関連するドキュメントは、で[http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468)見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ae406-106">You can find the Lync Server 2013 Management Pack and its related documentation at [http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="ae406-107">System Center Operations Manager 2012 を実行している場合は、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae406-107">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

