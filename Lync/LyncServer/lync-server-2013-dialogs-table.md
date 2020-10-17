---
title: 'Lync Server 2013: Dialogs テーブル'
description: 'Lync Server 2013: Dialogs テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559703"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="b5ce5-103">Lync Server 2013 のダイアログテーブル</span><span class="sxs-lookup"><span data-stu-id="b5ce5-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5ce5-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b5ce5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b5ce5-105">Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5ce5-106">Column</span><span class="sxs-lookup"><span data-stu-id="b5ce5-106">Column</span></span></th>
<th><span data-ttu-id="b5ce5-107">データ型</span><span class="sxs-lookup"><span data-stu-id="b5ce5-107">Data Type</span></span></th>
<th><span data-ttu-id="b5ce5-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b5ce5-108">Key/Index</span></span></th>
<th><span data-ttu-id="b5ce5-109">詳細</span><span class="sxs-lookup"><span data-stu-id="b5ce5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5ce5-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5ce5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ce5-111">日付型</span><span class="sxs-lookup"><span data-stu-id="b5ce5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5ce5-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b5ce5-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5ce5-113">セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ce5-114"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="b5ce5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ce5-115">int</span><span class="sxs-lookup"><span data-stu-id="b5ce5-115">int</span></span></p></td>
<td><p><span data-ttu-id="b5ce5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b5ce5-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5ce5-117">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-117">ID number to identify the session.</span></span> <span data-ttu-id="b5ce5-118">セッションを一意に識別するために SessionIDTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5ce5-119"><strong>ExternalChecksum サム</strong></span><span class="sxs-lookup"><span data-stu-id="b5ce5-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ce5-120">int</span><span class="sxs-lookup"><span data-stu-id="b5ce5-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b5ce5-121">ExternalID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="b5ce5-122">このフィールドは、データベースの検索速度を向上させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5ce5-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="b5ce5-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5ce5-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="b5ce5-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b5ce5-125">SIP ダイアログ ID。バイナリとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="b5ce5-126">バイナリの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="b5ce5-127">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="b5ce5-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="b5ce5-128">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="b5ce5-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

