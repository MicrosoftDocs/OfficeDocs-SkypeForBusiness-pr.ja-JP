---
title: 'Lync Server 2013: ContentTypes テーブル'
description: 'Lync Server 2013: ContentTypes テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 446623ae0ef15d70cd6d85019dfe8eb999f3b2fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571683"
---
# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="64d90-103">Lync Server 2013 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="64d90-103">ContentTypes table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64d90-104">_**トピックの最終更新日:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="64d90-104">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="64d90-105">ContentTypes テーブルは、ピアツーピアセッションと電話会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="64d90-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="64d90-106">テーブル内の各レコードは、1つのコンテンツタイプを表します。</span><span class="sxs-lookup"><span data-stu-id="64d90-106">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64d90-107">Column</span><span class="sxs-lookup"><span data-stu-id="64d90-107">Column</span></span></th>
<th><span data-ttu-id="64d90-108">データ型</span><span class="sxs-lookup"><span data-stu-id="64d90-108">Data Type</span></span></th>
<th><span data-ttu-id="64d90-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="64d90-109">Key/Index</span></span></th>
<th><span data-ttu-id="64d90-110">詳細</span><span class="sxs-lookup"><span data-stu-id="64d90-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64d90-111"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="64d90-111"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="64d90-112">int</span><span class="sxs-lookup"><span data-stu-id="64d90-112">int</span></span></p></td>
<td><p><span data-ttu-id="64d90-113">Primary</span><span class="sxs-lookup"><span data-stu-id="64d90-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="64d90-114">コンテンツタイプを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="64d90-114">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64d90-115"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="64d90-115"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="64d90-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64d90-116">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="64d90-117">コンテンツタイプの名前。</span><span class="sxs-lookup"><span data-stu-id="64d90-117">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

