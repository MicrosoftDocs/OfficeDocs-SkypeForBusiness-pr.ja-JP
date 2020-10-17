---
title: 'Lync Server 2013: ErrorDef テーブル'
description: 'Lync Server 2013: ErrorDef テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542753"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="74b9b-103">Lync Server 2013 の ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="74b9b-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74b9b-104">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="74b9b-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="74b9b-105">ErrorDef テーブルは、発生する可能性がある各エラーの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="74b9b-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="74b9b-106">各レコードは、1種類のエラーです。</span><span class="sxs-lookup"><span data-stu-id="74b9b-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74b9b-107">Column</span><span class="sxs-lookup"><span data-stu-id="74b9b-107">Column</span></span></th>
<th><span data-ttu-id="74b9b-108">データ型</span><span class="sxs-lookup"><span data-stu-id="74b9b-108">Data Type</span></span></th>
<th><span data-ttu-id="74b9b-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="74b9b-109">Key/Index</span></span></th>
<th><span data-ttu-id="74b9b-110">詳細</span><span class="sxs-lookup"><span data-stu-id="74b9b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74b9b-111"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-112">int</span><span class="sxs-lookup"><span data-stu-id="74b9b-112">int</span></span></p></td>
<td><p><span data-ttu-id="74b9b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="74b9b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="74b9b-114">この種類のエラーを識別する一意の ID 番号。</span><span class="sxs-lookup"><span data-stu-id="74b9b-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74b9b-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-116">int</span><span class="sxs-lookup"><span data-stu-id="74b9b-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="74b9b-117">このエラーに関連付けられている標準 SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="74b9b-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74b9b-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-119">int</span><span class="sxs-lookup"><span data-stu-id="74b9b-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="74b9b-120">Microsoft 診断 ID。</span><span class="sxs-lookup"><span data-stu-id="74b9b-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74b9b-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-122">Int</span><span class="sxs-lookup"><span data-stu-id="74b9b-122">Int</span></span></p></td>
<td><p><span data-ttu-id="74b9b-123">外部</span><span class="sxs-lookup"><span data-stu-id="74b9b-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="74b9b-124">呼び出しの種類。</span><span class="sxs-lookup"><span data-stu-id="74b9b-124">Type of the call.</span></span> <span data-ttu-id="74b9b-125">詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b9b-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74b9b-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="74b9b-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="74b9b-128">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="74b9b-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="74b9b-129">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="74b9b-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74b9b-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="74b9b-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="74b9b-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="74b9b-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="74b9b-132">失敗した要求のコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="74b9b-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="74b9b-133">このデータは、次の syntaxt を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="74b9b-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

