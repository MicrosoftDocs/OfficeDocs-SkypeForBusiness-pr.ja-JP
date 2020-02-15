---
title: 'Lync Server 2013: CallType テーブル'
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
ms.openlocfilehash: 3f90be73c63921ebe9971abae85b2da22e76a560
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="8c41a-102">Lync Server 2013 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="8c41a-102">CallType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c41a-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8c41a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8c41a-104">CallType テーブルは、可能な通話の種類の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="8c41a-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c41a-105">列</span><span class="sxs-lookup"><span data-stu-id="8c41a-105">Column</span></span></th>
<th><span data-ttu-id="8c41a-106">データ型</span><span class="sxs-lookup"><span data-stu-id="8c41a-106">Data Type</span></span></th>
<th><span data-ttu-id="8c41a-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="8c41a-107">Key/Index</span></span></th>
<th><span data-ttu-id="8c41a-108">詳細</span><span class="sxs-lookup"><span data-stu-id="8c41a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c41a-109"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="8c41a-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41a-110">int</span><span class="sxs-lookup"><span data-stu-id="8c41a-110">int</span></span></p></td>
<td><p><span data-ttu-id="8c41a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8c41a-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c41a-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="8c41a-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="8c41a-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="8c41a-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8c41a-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8c41a-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="8c41a-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="8c41a-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="8c41a-116">1–インスタントメッセージング</span><span class="sxs-lookup"><span data-stu-id="8c41a-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="8c41a-117">2--アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="8c41a-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="8c41a-118">3--音声</span><span class="sxs-lookup"><span data-stu-id="8c41a-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="8c41a-119">4–音声およびビデオ</span><span class="sxs-lookup"><span data-stu-id="8c41a-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="8c41a-120">5–ファイル転送</span><span class="sxs-lookup"><span data-stu-id="8c41a-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

