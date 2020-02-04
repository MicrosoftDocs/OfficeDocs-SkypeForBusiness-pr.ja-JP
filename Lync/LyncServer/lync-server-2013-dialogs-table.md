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
ms.openlocfilehash: 326ecac8df81eeba11ed29ff9f1968b681cdb98f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="30250-102">Lync Server 2013 の Dialogs テーブル</span><span class="sxs-lookup"><span data-stu-id="30250-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30250-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="30250-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="30250-104">Dialogs テーブルは、ピアツーピアセッションの DialogIDs に関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="30250-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30250-105">列</span><span class="sxs-lookup"><span data-stu-id="30250-105">Column</span></span></th>
<th><span data-ttu-id="30250-106">データ型</span><span class="sxs-lookup"><span data-stu-id="30250-106">Data Type</span></span></th>
<th><span data-ttu-id="30250-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="30250-107">Key/Index</span></span></th>
<th><span data-ttu-id="30250-108">詳細</span><span class="sxs-lookup"><span data-stu-id="30250-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30250-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="30250-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="30250-110">datetime</span><span class="sxs-lookup"><span data-stu-id="30250-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="30250-111">Primary</span><span class="sxs-lookup"><span data-stu-id="30250-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="30250-112">セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="30250-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30250-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="30250-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="30250-114">int</span><span class="sxs-lookup"><span data-stu-id="30250-114">int</span></span></p></td>
<td><p><span data-ttu-id="30250-115">Primary</span><span class="sxs-lookup"><span data-stu-id="30250-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="30250-116">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="30250-116">ID number to identify the session.</span></span> <span data-ttu-id="30250-117">セッションを一意に識別するために SessionIDTime と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="30250-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30250-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="30250-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="30250-119">int</span><span class="sxs-lookup"><span data-stu-id="30250-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30250-120">ExternalID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="30250-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="30250-121">このフィールドは、データベースの検索速度を上げるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="30250-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30250-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="30250-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="30250-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="30250-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30250-124">SIP ダイアログ ID。バイナリとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="30250-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="30250-125">バイナリの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30250-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="30250-126">ダイアログ; 開始タグからタグへ</span><span class="sxs-lookup"><span data-stu-id="30250-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="30250-127">このデータは、次の構文を使用してテキスト形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="30250-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

