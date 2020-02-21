---
title: 'Lync Server 2013: グループチャットの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c8d2a544c9a20e16e9a9f6510002ef5dd3e695e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="8503b-102">Lync Server 2013 でのグループチャットの監視</span><span class="sxs-lookup"><span data-stu-id="8503b-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8503b-103">_**トピックの最終更新日:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="8503b-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="8503b-104">パフォーマンスを向上させるために、最新の[累積サーバー更新プログラムインストーラー](https://support.microsoft.com/kb/968802)を Microsoft ダウンロードセンターから入手することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8503b-104">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="8503b-105">最新の累積更新プログラムを実行している場合は、次のストレステストテーブルを基準として使用して、グループチャットサーバーが最適な状態で実行されているかどうか理解します。</span><span class="sxs-lookup"><span data-stu-id="8503b-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="8503b-106">テスト環境とユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="8503b-106">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8503b-107">グループチャットプールに3つのグループチャットサーバー。それぞれに 8 GB のメモリと8個のプロセッサがあります。</span><span class="sxs-lookup"><span data-stu-id="8503b-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8503b-108">Enterprise Edition では、2つの Lync Server 2013 フロントエンドがあります。</span><span class="sxs-lookup"><span data-stu-id="8503b-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8503b-109">6万3つのグループチャットサーバー間での同時ユーザー数。</span><span class="sxs-lookup"><span data-stu-id="8503b-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8503b-110">グループチャットプールによってホストされる25000チャネル</span><span class="sxs-lookup"><span data-stu-id="8503b-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8503b-111">チャネルのサイズ:</span><span class="sxs-lookup"><span data-stu-id="8503b-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-112">小さいチャネルのサイズ:30</span><span class="sxs-lookup"><span data-stu-id="8503b-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="8503b-113">中規模チャネルサイズ: 150</span><span class="sxs-lookup"><span data-stu-id="8503b-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="8503b-114">大きいチャネルのサイズ: 2500</span><span class="sxs-lookup"><span data-stu-id="8503b-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8503b-115">チャネル数:</span><span class="sxs-lookup"><span data-stu-id="8503b-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-116">小さいチャンネル数: 24000</span><span class="sxs-lookup"><span data-stu-id="8503b-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="8503b-117">Medium チャネルの数800</span><span class="sxs-lookup"><span data-stu-id="8503b-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="8503b-118">大きなチャネルの数24</span><span class="sxs-lookup"><span data-stu-id="8503b-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="8503b-119">チャネル合計24824</span><span class="sxs-lookup"><span data-stu-id="8503b-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8503b-120">チャネルの招待:</span><span class="sxs-lookup"><span data-stu-id="8503b-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-121">チャネルの半数はチャネルを招待する</span><span class="sxs-lookup"><span data-stu-id="8503b-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8503b-122">ユーザーが参加したチャネルの数:</span><span class="sxs-lookup"><span data-stu-id="8503b-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-123">小:12</span><span class="sxs-lookup"><span data-stu-id="8503b-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="8503b-124">中: 2</span><span class="sxs-lookup"><span data-stu-id="8503b-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="8503b-125">大: 1</span><span class="sxs-lookup"><span data-stu-id="8503b-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8503b-126">参加率:</span><span class="sxs-lookup"><span data-stu-id="8503b-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-127">サーバーごとに10合計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="8503b-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8503b-128">ログアウト率:</span><span class="sxs-lookup"><span data-stu-id="8503b-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-129">サーバーごとに10合計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="8503b-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8503b-130">チャットレート:</span><span class="sxs-lookup"><span data-stu-id="8503b-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="8503b-131">1サーバーあたり20合計/秒、6.66/秒</span><span class="sxs-lookup"><span data-stu-id="8503b-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="8503b-132">次のパフォーマンスカウンターの数値は、異なるハードウェア仕様またはユーザープロファイルを使用したときに異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8503b-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="8503b-133">監視対象のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="8503b-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8503b-134">パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="8503b-134">Performance Counter</span></span></th>
<th><span data-ttu-id="8503b-135">しきい値</span><span class="sxs-lookup"><span data-stu-id="8503b-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8503b-136">プロセス (ChannelService)-&gt;プロセッサ時間 (%)</span><span class="sxs-lookup"><span data-stu-id="8503b-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="8503b-137">Min: 0</span><span class="sxs-lookup"><span data-stu-id="8503b-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

