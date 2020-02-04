---
title: 'Lync Server 2013: System Center Operations Manager を使用して Lync Server を監視する'
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
ms.openlocfilehash: 0b5a251853efe20cc867f78f4f932e2c43efd22c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="0b504-102">System Center Operations Manager での Lync Server 2013 の監視</span><span class="sxs-lookup"><span data-stu-id="0b504-102">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b504-103">_**最終更新日:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="0b504-103">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="0b504-104">Lync Server 管理パック (MP) は、Lync Server の展開を監視するために選択できる監視ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="0b504-104">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="0b504-105">MP は、従来のイベントログとパフォーマンスカウンターベースのインストルメンテーションを実装し、いくつかの主要な正常性インジケーターのペアイベント (失敗/成功) など、Lync Server で新しく利用可能なインストルメンテーションを有効にします\* 。また、新しい代理トランザクション (テスト-Cs Windows PowerShell コマンドレット) も完全に実装します。</span><span class="sxs-lookup"><span data-stu-id="0b504-105">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="0b504-106">Lync Server 2013 管理パックと関連ドキュメントは、で[http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468)確認できます。</span><span class="sxs-lookup"><span data-stu-id="0b504-106">You can find the Lync Server 2013 Management Pack and its related documentation at [http://go.microsoft.com/fwlink/p/?LinkId=400468](http://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="0b504-107">System Center Operations Manager 2012 を実行している場合は、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b504-107">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

