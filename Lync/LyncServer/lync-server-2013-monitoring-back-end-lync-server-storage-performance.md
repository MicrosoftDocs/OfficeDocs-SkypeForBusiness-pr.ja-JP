---
title: 'Lync Server 2013: バックエンド Lync Server ストレージのパフォーマンスの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531954"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="15b94-102">バックエンド Lync Server 2013 ストレージのパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="15b94-102">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b94-103">_**トピックの最終更新日:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="15b94-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="15b94-104">Lync Server 2013 のバックエンドデータベースは、Lync Server 2013 の展開において非常に重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="15b94-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="15b94-105">Lync Server 2013 のバックエンドが最適に実行されていることを確認するために、データベースとそれぞれのトランザクションログを絶えず監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15b94-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="15b94-106">次の表に、ストレージのパフォーマンスに関する情報を取得するために監視する必要があるパフォーマンスカウンターを示します。</span><span class="sxs-lookup"><span data-stu-id="15b94-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="15b94-107">これらのカウンターのベースライン値は、最初に決定する必要があります (システムの負荷が分散されているときに、システムが通常、予想される負荷)。</span><span class="sxs-lookup"><span data-stu-id="15b94-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="15b94-108">監視するパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="15b94-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15b94-109">パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="15b94-109">Performance Counter</span></span></th>
<th><span data-ttu-id="15b94-110">ベースラインのしきい値</span><span class="sxs-lookup"><span data-stu-id="15b94-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15b94-111">トランザクション/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="15b94-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b94-112">トランザクション/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="15b94-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b94-113">トランザクション/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="15b94-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b94-114">ログのフラッシュ/秒 (RTC)</span><span class="sxs-lookup"><span data-stu-id="15b94-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b94-115">ログのフラッシュ/秒 (rtcdyn)</span><span class="sxs-lookup"><span data-stu-id="15b94-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b94-116">ログのフラッシュ/秒 (tempdb)</span><span class="sxs-lookup"><span data-stu-id="15b94-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b94-117">ディスク転送/秒 (読み取り + 書き込み)-RTC db</span><span class="sxs-lookup"><span data-stu-id="15b94-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b94-118">ディスク転送/秒-RTC ログ</span><span class="sxs-lookup"><span data-stu-id="15b94-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b94-119">ディスク転送/秒-rtcdyn db</span><span class="sxs-lookup"><span data-stu-id="15b94-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b94-120">ディスク転送/sec-rtcdyn ログ</span><span class="sxs-lookup"><span data-stu-id="15b94-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

