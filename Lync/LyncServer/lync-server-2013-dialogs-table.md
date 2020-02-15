---
title: 'Lync Server 2013: Dialogs テーブル'
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
ms.openlocfilehash: be0bb5a603f856aa0faa02074962618fcb82448e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="26358-102">Lync Server 2013 のダイアログテーブル</span><span class="sxs-lookup"><span data-stu-id="26358-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26358-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26358-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26358-104">Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="26358-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26358-105">列</span><span class="sxs-lookup"><span data-stu-id="26358-105">Column</span></span></th>
<th><span data-ttu-id="26358-106">データ型</span><span class="sxs-lookup"><span data-stu-id="26358-106">Data Type</span></span></th>
<th><span data-ttu-id="26358-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="26358-107">Key/Index</span></span></th>
<th><span data-ttu-id="26358-108">詳細</span><span class="sxs-lookup"><span data-stu-id="26358-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26358-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="26358-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26358-110">日付型</span><span class="sxs-lookup"><span data-stu-id="26358-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="26358-111">Primary</span><span class="sxs-lookup"><span data-stu-id="26358-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="26358-112">セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="26358-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26358-113"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="26358-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="26358-114">int</span><span class="sxs-lookup"><span data-stu-id="26358-114">int</span></span></p></td>
<td><p><span data-ttu-id="26358-115">Primary</span><span class="sxs-lookup"><span data-stu-id="26358-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="26358-116">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="26358-116">ID number to identify the session.</span></span> <span data-ttu-id="26358-117">セッションを一意に識別するために SessionIDTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="26358-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26358-118"><strong>ExternalChecksum サム</strong></span><span class="sxs-lookup"><span data-stu-id="26358-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="26358-119">int</span><span class="sxs-lookup"><span data-stu-id="26358-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="26358-120">ExternalID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="26358-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="26358-121">このフィールドは、データベースの検索速度を向上させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="26358-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26358-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="26358-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="26358-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="26358-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="26358-124">SIP ダイアログ ID。バイナリとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="26358-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="26358-125">バイナリの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26358-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="26358-126">dialog、from タグ、およびタグ</span><span class="sxs-lookup"><span data-stu-id="26358-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="26358-127">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="26358-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

