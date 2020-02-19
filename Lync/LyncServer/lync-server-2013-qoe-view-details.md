---
title: 'Lync Server 2013: QoE ビューの詳細'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="1e1c3-102">Lync Server 2013 の QoE ビューの詳細</span><span class="sxs-lookup"><span data-stu-id="1e1c3-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e1c3-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1e1c3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1e1c3-104">ビューは、QoE SQL データベースからデータを返すための最も一般的なシナリオをカバーしています。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="1e1c3-105">データベーステーブルに直接アクセスするのではなく、カスタムレポートを作成するために使用することをお勧めします。これは、ビューが今後のリリースとの下位互換性を維持する可能性が高くなるためです。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e1c3-106">ビュー名</span><span class="sxs-lookup"><span data-stu-id="1e1c3-106">View Name</span></span></th>
<th><span data-ttu-id="1e1c3-107">説明</span><span class="sxs-lookup"><span data-stu-id="1e1c3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e1c3-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013 の AudioStreamDetail ビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-109">データベース内の各オーディオ ストリームについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e1c3-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013 の MediaLine ビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-111">データベース内の各メディア ラインについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="1e1c3-112">通常、1 つの音声セッションに 1 つの音声メディア ラインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="1e1c3-113">また、通常は 1 つの音声ビデオ (A/V) セッションに 1 つの音声メディア ラインと 1 つのビデオ メディア ラインが含まれますが、会議デバイスまたはギャラリー ビューが使用される場合は、セッションに 2 つのビデオ メディア ラインが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e1c3-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013 の NetworkConfigurationSettings ビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-115">ネットワーク構成についての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e1c3-116"><a href="lync-server-2013-session-view.md">Lync Server 2013 のセッションビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-117">データベース内のレコードを持つセッションについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e1c3-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013 の UserAgent ビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-119">データベース内のレコードを持つセッションに関与しているユーザー エージェントについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e1c3-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013 の VideoStreamDetail ビュー</a></span><span class="sxs-lookup"><span data-stu-id="1e1c3-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="1e1c3-121">データベース内の各ビデオ ストリームについての情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="1e1c3-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

