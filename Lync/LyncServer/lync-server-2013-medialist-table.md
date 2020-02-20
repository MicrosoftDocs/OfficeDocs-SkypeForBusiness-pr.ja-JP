---
title: 'Lync Server 2013: MediaList テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d36b399ca6071d8c4d057d02c0814cd03629a5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="d9a5e-102">Lync Server 2013 の MediaList テーブル</span><span class="sxs-lookup"><span data-stu-id="d9a5e-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9a5e-103">_**トピックの最終更新日:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="d9a5e-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="d9a5e-104">MediaList テーブルは、さまざまなメディアの種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d9a5e-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9a5e-105">列</span><span class="sxs-lookup"><span data-stu-id="d9a5e-105">Column</span></span></th>
<th><span data-ttu-id="d9a5e-106">データ型</span><span class="sxs-lookup"><span data-stu-id="d9a5e-106">Data Type</span></span></th>
<th><span data-ttu-id="d9a5e-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="d9a5e-107">Key/Index</span></span></th>
<th><span data-ttu-id="d9a5e-108">詳細</span><span class="sxs-lookup"><span data-stu-id="d9a5e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9a5e-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="d9a5e-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="d9a5e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d9a5e-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d9a5e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d9a5e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="d9a5e-112">値: 1-7</span><span class="sxs-lookup"><span data-stu-id="d9a5e-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a5e-113"><strong>メディア</strong></span><span class="sxs-lookup"><span data-stu-id="d9a5e-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="d9a5e-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9a5e-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d9a5e-115">MediaID とメディアの値の静的マッピング:</span><span class="sxs-lookup"><span data-stu-id="d9a5e-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="d9a5e-116">1– IM</span><span class="sxs-lookup"><span data-stu-id="d9a5e-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-117">2 -- ファイル転送</span><span class="sxs-lookup"><span data-stu-id="d9a5e-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-118">3 -- リモート アシスタンス</span><span class="sxs-lookup"><span data-stu-id="d9a5e-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-119">4 -- アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="d9a5e-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-120">5–音声</span><span class="sxs-lookup"><span data-stu-id="d9a5e-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-121">6–ビデオ</span><span class="sxs-lookup"><span data-stu-id="d9a5e-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="d9a5e-122">7 -- アプリケーション招待</span><span class="sxs-lookup"><span data-stu-id="d9a5e-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9a5e-123">LcsCDR MediaTypes の値のモダリティの種類を決定しようとしている場合は、次の Join スニペットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a5e-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

