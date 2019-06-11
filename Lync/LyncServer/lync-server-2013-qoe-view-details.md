---
title: 'Lync Server 2013: QoE ビューの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="36932-102">Lync Server 2013 の QoE ビューの詳細</span><span class="sxs-lookup"><span data-stu-id="36932-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36932-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="36932-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="36932-104">ビューでは、QoE SQL データベースからデータを返す最も一般的なシナリオがカバーされています。</span><span class="sxs-lookup"><span data-stu-id="36932-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="36932-105">データベーステーブルに直接アクセスするのではなく、カスタムレポートの作成に使用することをお勧めします。これは、ビューが将来のリリースとの下位互換性を維持する可能性が高いためです。</span><span class="sxs-lookup"><span data-stu-id="36932-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36932-106">ビュー名</span><span class="sxs-lookup"><span data-stu-id="36932-106">View Name</span></span></th>
<th><span data-ttu-id="36932-107">説明</span><span class="sxs-lookup"><span data-stu-id="36932-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36932-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 の AudioStreamDetail ビュー</a></span><span class="sxs-lookup"><span data-stu-id="36932-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-109">データベース内の各オーディオストリームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36932-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 での MediaLine の表示</a></span><span class="sxs-lookup"><span data-stu-id="36932-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-111">データベース内の各メディア行に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="36932-112">1つのオーディオセッションには通常、1つのオーディオメディアラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="36932-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="36932-113">通常、1つのオーディオとビデオ (A/V) セッションには、1つのオーディオメディアラインと1つのビデオメディアラインが含まれます。ただし、会議デバイスが使用されている場合、または [ギャラリー] ビューを使用している場合は、2つのビデオメディアがセッションに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36932-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36932-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 の NetworkConfigurationSettings view</a></span><span class="sxs-lookup"><span data-stu-id="36932-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-115">ネットワーク構成に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36932-116"><a href="lync-server-2013-session-view.md">Lync Server 2013 のセッションビュー</a></span><span class="sxs-lookup"><span data-stu-id="36932-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-117">データベースにレコードがあるセッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36932-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 での UserAgent の表示</a></span><span class="sxs-lookup"><span data-stu-id="36932-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-119">データベースにレコードがあるセッションに関連しているユーザーエージェントに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36932-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 の VideoStreamDetail ビュー</a></span><span class="sxs-lookup"><span data-stu-id="36932-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="36932-121">データベース内の各ビデオストリームに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="36932-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

