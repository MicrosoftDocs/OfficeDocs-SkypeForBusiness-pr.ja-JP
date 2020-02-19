---
title: 'Lync Server 2013: ErrorDef テーブル'
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
ms.openlocfilehash: c333017f122454d68bc452a5c183f8c09b6347a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="4915a-102">Lync Server 2013 の ErrorDef テーブル</span><span class="sxs-lookup"><span data-stu-id="4915a-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4915a-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="4915a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="4915a-104">ErrorDef テーブルは、発生する可能性がある各エラーの種類に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4915a-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="4915a-105">各レコードは、1種類のエラーです。</span><span class="sxs-lookup"><span data-stu-id="4915a-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4915a-106">列</span><span class="sxs-lookup"><span data-stu-id="4915a-106">Column</span></span></th>
<th><span data-ttu-id="4915a-107">データ型</span><span class="sxs-lookup"><span data-stu-id="4915a-107">Data Type</span></span></th>
<th><span data-ttu-id="4915a-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="4915a-108">Key/Index</span></span></th>
<th><span data-ttu-id="4915a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="4915a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4915a-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-111">int</span><span class="sxs-lookup"><span data-stu-id="4915a-111">int</span></span></p></td>
<td><p><span data-ttu-id="4915a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4915a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4915a-113">この種類のエラーを識別する一意の ID 番号。</span><span class="sxs-lookup"><span data-stu-id="4915a-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4915a-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-115">int</span><span class="sxs-lookup"><span data-stu-id="4915a-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4915a-116">このエラーに関連付けられている標準 SIP 応答コード。</span><span class="sxs-lookup"><span data-stu-id="4915a-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4915a-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-118">int</span><span class="sxs-lookup"><span data-stu-id="4915a-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4915a-119">Microsoft 診断 ID。</span><span class="sxs-lookup"><span data-stu-id="4915a-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4915a-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-121">Int</span><span class="sxs-lookup"><span data-stu-id="4915a-121">Int</span></span></p></td>
<td><p><span data-ttu-id="4915a-122">外部</span><span class="sxs-lookup"><span data-stu-id="4915a-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4915a-123">呼び出しの種類。</span><span class="sxs-lookup"><span data-stu-id="4915a-123">Type of the call.</span></span> <span data-ttu-id="4915a-124">詳細については、「 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4915a-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4915a-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="4915a-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4915a-127">失敗した要求の種類。</span><span class="sxs-lookup"><span data-stu-id="4915a-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="4915a-128">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="4915a-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4915a-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="4915a-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="4915a-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="4915a-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4915a-131">失敗した要求のコンテンツの種類。</span><span class="sxs-lookup"><span data-stu-id="4915a-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="4915a-132">このデータは、次の syntaxt を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="4915a-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

