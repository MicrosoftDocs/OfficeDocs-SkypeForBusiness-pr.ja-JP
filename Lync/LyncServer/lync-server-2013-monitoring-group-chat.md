---
title: 'Lync Server 2013: グループチャットを監視する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="f2cfc-102">Lync Server 2013 でグループチャットを監視する</span><span class="sxs-lookup"><span data-stu-id="f2cfc-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2cfc-103">_**最終更新日:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="f2cfc-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="f2cfc-104">パフォーマンスを向上させるには、Microsoft ダウンロードセンターで入手できる最新の[累積サーバー更新プログラムインストーラー](http://support.microsoft.com/kb/968802)を実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="f2cfc-105">最新の累積更新プログラムを実行していることを前提として、グループチャットサーバーが最適な状態で実行されているかどうかを判断するために、メトリックについて次のストレステストテーブルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="f2cfc-106">環境とユーザーモデルのテスト</span><span class="sxs-lookup"><span data-stu-id="f2cfc-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="f2cfc-107">グループチャットプール内の3つのグループチャットサーバ、それぞれに 8 GB のメモリと8個のプロセッサが搭載されています。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2cfc-108">Enterprise Edition での2台の Lync Server 2013 フロントエンド。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-109">6万で3つのグループチャットサーバに同時に接続できます。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2cfc-110">グループチャットプールによってホストされている25000チャネル。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-111">チャンネルサイズ:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-112">小さいチャンネルサイズ:30</span><span class="sxs-lookup"><span data-stu-id="f2cfc-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-113">ミディアムチャネルサイズ: 150</span><span class="sxs-lookup"><span data-stu-id="f2cfc-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-114">大きいチャンネルサイズ: 2500</span><span class="sxs-lookup"><span data-stu-id="f2cfc-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2cfc-115">チャネル数:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-116">小さいチャンネル数: 24000</span><span class="sxs-lookup"><span data-stu-id="f2cfc-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-117">数値媒体チャネル800</span><span class="sxs-lookup"><span data-stu-id="f2cfc-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-118">大きいチャンネルの番号24</span><span class="sxs-lookup"><span data-stu-id="f2cfc-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-119">チャネルの合計24824</span><span class="sxs-lookup"><span data-stu-id="f2cfc-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-120">チャネルの招待:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-121">チャンネルがチャンネルを招待した残りのチャネル</span><span class="sxs-lookup"><span data-stu-id="f2cfc-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2cfc-122">ユーザーが参加するチャネルの数:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-123">小:12</span><span class="sxs-lookup"><span data-stu-id="f2cfc-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-124">中: 2</span><span class="sxs-lookup"><span data-stu-id="f2cfc-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="f2cfc-125">大: 1</span><span class="sxs-lookup"><span data-stu-id="f2cfc-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-126">参加率:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-127">サーバーあたり10合計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="f2cfc-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2cfc-128">ログアウト率:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-129">サーバーあたり10合計/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="f2cfc-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-130">チャット料金:</span><span class="sxs-lookup"><span data-stu-id="f2cfc-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2cfc-131">1サーバーあたり20合計/秒、6.66/秒</span><span class="sxs-lookup"><span data-stu-id="f2cfc-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2cfc-132">ハードウェア仕様またはユーザープロファイルが異なる場合、次のパフォーマンスカウンターの数値が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2cfc-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="f2cfc-133">監視対象のパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="f2cfc-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2cfc-134">パフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="f2cfc-134">Performance Counter</span></span></th>
<th><span data-ttu-id="f2cfc-135">しきい値</span><span class="sxs-lookup"><span data-stu-id="f2cfc-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2cfc-136">プロセス (ChannelService)-&gt;プロセッサ時間の割合</span><span class="sxs-lookup"><span data-stu-id="f2cfc-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="f2cfc-137">Min: 0</span><span class="sxs-lookup"><span data-stu-id="f2cfc-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

