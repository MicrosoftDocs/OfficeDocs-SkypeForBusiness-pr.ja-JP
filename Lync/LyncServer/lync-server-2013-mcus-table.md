---
title: 'Lync Server 2013: Mcus テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="b983f-102">Lync Server 2013 の Mcus テーブル</span><span class="sxs-lookup"><span data-stu-id="b983f-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b983f-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b983f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b983f-104">Mcu テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="b983f-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="b983f-105">各レコードには、1つの会議サービスに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="b983f-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="b983f-106">これには、IM 会議サービスと、(フロントエンドサーバーでプロセスとして実行される) テレフォニー会議サービス、および Web 会議サービスと A/V 会議サービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b983f-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b983f-107">列</span><span class="sxs-lookup"><span data-stu-id="b983f-107">Column</span></span></th>
<th><span data-ttu-id="b983f-108">データ型</span><span class="sxs-lookup"><span data-stu-id="b983f-108">Data Type</span></span></th>
<th><span data-ttu-id="b983f-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="b983f-109">Key/Index</span></span></th>
<th><span data-ttu-id="b983f-110">詳細</span><span class="sxs-lookup"><span data-stu-id="b983f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b983f-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="b983f-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="b983f-112">int</span><span class="sxs-lookup"><span data-stu-id="b983f-112">int</span></span></p></td>
<td><p><span data-ttu-id="b983f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b983f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b983f-114">この会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="b983f-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b983f-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="b983f-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b983f-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b983f-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b983f-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="b983f-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="b983f-118">inyint</span><span class="sxs-lookup"><span data-stu-id="b983f-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="b983f-119"> 外部</span><span class="sxs-lookup"><span data-stu-id="b983f-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="b983f-120">会議サーバーの種類 (例: チャット (Im の場合) または conf: オーディオビデオ)。</span><span class="sxs-lookup"><span data-stu-id="b983f-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="b983f-121">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b983f-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

