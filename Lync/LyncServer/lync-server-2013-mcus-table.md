---
title: 'Lync Server 2013: Mcu テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b82d01c96f22aabb797bdcf04820cfb944ccb7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="ff432-102">Lync Server 2013 の mcu テーブル</span><span class="sxs-lookup"><span data-stu-id="ff432-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff432-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ff432-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ff432-104">Mcu テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ff432-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="ff432-105">各レコードには、1つの会議サービスに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ff432-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="ff432-106">これらには、IM 会議サービスと、電話会議サービス (フロントエンドサーバー上でプロセスとして実行される)、Web 会議サービス、音声ビデオ会議サービスなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff432-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff432-107">列</span><span class="sxs-lookup"><span data-stu-id="ff432-107">Column</span></span></th>
<th><span data-ttu-id="ff432-108">データ型</span><span class="sxs-lookup"><span data-stu-id="ff432-108">Data Type</span></span></th>
<th><span data-ttu-id="ff432-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ff432-109">Key/Index</span></span></th>
<th><span data-ttu-id="ff432-110">詳細</span><span class="sxs-lookup"><span data-stu-id="ff432-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff432-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="ff432-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff432-112">int</span><span class="sxs-lookup"><span data-stu-id="ff432-112">int</span></span></p></td>
<td><p><span data-ttu-id="ff432-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ff432-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff432-114">この会議サーバーを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="ff432-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff432-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="ff432-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ff432-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ff432-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff432-117"><strong>McuTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ff432-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff432-118">inyint</span><span class="sxs-lookup"><span data-stu-id="ff432-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="ff432-119"> 外部</span><span class="sxs-lookup"><span data-stu-id="ff432-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff432-120">電話会議サーバーの種類 (例: チャット (Im) または conf: audio ビデオ)。</span><span class="sxs-lookup"><span data-stu-id="ff432-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="ff432-121">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff432-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

