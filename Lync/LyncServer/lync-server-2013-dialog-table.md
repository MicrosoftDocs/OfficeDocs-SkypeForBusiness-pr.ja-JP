---
title: 'Lync Server 2013: Dialog テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18646cb43bc957ebee7da0a313e840cc18f3ed54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="abd44-102">Lync Server 2013 のダイアログテーブル</span><span class="sxs-lookup"><span data-stu-id="abd44-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd44-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="abd44-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="abd44-104">Dialog テーブルは、サポートテーブルです。各レコードは、1つのセッション開始プロトコル (SIP) ダイアログを表します。</span><span class="sxs-lookup"><span data-stu-id="abd44-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abd44-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="abd44-106"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="abd44-107"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="abd44-108"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abd44-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="abd44-110">日付型</span><span class="sxs-lookup"><span data-stu-id="abd44-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="abd44-111">Primary</span><span class="sxs-lookup"><span data-stu-id="abd44-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="abd44-112">[最高水準 (QoE)] エージェントが、呼び出し元または呼び出し先から最初のレポートを受信する時間。</span><span class="sxs-lookup"><span data-stu-id="abd44-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="abd44-113">セッションを一意に識別するために SessionSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="abd44-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd44-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="abd44-115">int</span><span class="sxs-lookup"><span data-stu-id="abd44-115">int</span></span></p></td>
<td><p><span data-ttu-id="abd44-116">Primary</span><span class="sxs-lookup"><span data-stu-id="abd44-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="abd44-117">同じ ConferenceDateTime を持つセッションを区別するためのシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="abd44-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abd44-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="abd44-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="abd44-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="abd44-120">グローバルに一意のダイアログ ID です。</span><span class="sxs-lookup"><span data-stu-id="abd44-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abd44-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="abd44-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="abd44-122">int</span><span class="sxs-lookup"><span data-stu-id="abd44-122">int</span></span></p></td>
<td><p><span data-ttu-id="abd44-123">index</span><span class="sxs-lookup"><span data-stu-id="abd44-123">index</span></span></p></td>
<td><p><span data-ttu-id="abd44-124">ダイアログ ID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="abd44-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

