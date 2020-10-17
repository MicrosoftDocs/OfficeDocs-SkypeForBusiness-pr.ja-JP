---
title: 'Lync Server 2013: CallType テーブル'
description: 'Lync Server 2013: CallType テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565173"
---
# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="1bfcd-103">Lync Server 2013 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="1bfcd-103">CallType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bfcd-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1bfcd-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1bfcd-105">CallType テーブルは、可能な通話の種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="1bfcd-105">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bfcd-106">Column</span><span class="sxs-lookup"><span data-stu-id="1bfcd-106">Column</span></span></th>
<th><span data-ttu-id="1bfcd-107">データ型</span><span class="sxs-lookup"><span data-stu-id="1bfcd-107">Data Type</span></span></th>
<th><span data-ttu-id="1bfcd-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="1bfcd-108">Key/Index</span></span></th>
<th><span data-ttu-id="1bfcd-109">詳細</span><span class="sxs-lookup"><span data-stu-id="1bfcd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bfcd-110"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="1bfcd-110"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1bfcd-111">int</span><span class="sxs-lookup"><span data-stu-id="1bfcd-111">int</span></span></p></td>
<td><p><span data-ttu-id="1bfcd-112">Primary</span><span class="sxs-lookup"><span data-stu-id="1bfcd-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bfcd-113"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1bfcd-113"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1bfcd-114">nvarchar</span><span class="sxs-lookup"><span data-stu-id="1bfcd-114">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1bfcd-115">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1bfcd-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="1bfcd-116">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="1bfcd-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="1bfcd-117">1–インスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="1bfcd-117">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="1bfcd-118">2--アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="1bfcd-118">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="1bfcd-119">3--音声</span><span class="sxs-lookup"><span data-stu-id="1bfcd-119">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="1bfcd-120">4–音声およびビデオ</span><span class="sxs-lookup"><span data-stu-id="1bfcd-120">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="1bfcd-121">5–ファイル転送</span><span class="sxs-lookup"><span data-stu-id="1bfcd-121">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

