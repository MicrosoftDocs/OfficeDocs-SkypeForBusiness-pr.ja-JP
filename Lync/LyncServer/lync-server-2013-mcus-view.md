---
title: 'Lync Server 2013: Mcu ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus view
ms:assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688127(v=OCS.15)
ms:contentKeyID: 49733725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b8eb302dc63a01ad052fd86debec5baac9dd68a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcus-view-in-lync-server-2013"></a><span data-ttu-id="c1a75-102">Lync Server 2013 の mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="c1a75-102">Mcus view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1a75-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c1a75-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c1a75-104">Mcus ビューには、電話会議セッションに参加した MCU に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c1a75-104">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="c1a75-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c1a75-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1a75-106">列</span><span class="sxs-lookup"><span data-stu-id="c1a75-106">Column</span></span></th>
<th><span data-ttu-id="c1a75-107">データ型</span><span class="sxs-lookup"><span data-stu-id="c1a75-107">Data Type</span></span></th>
<th><span data-ttu-id="c1a75-108">詳細</span><span class="sxs-lookup"><span data-stu-id="c1a75-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1a75-109"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="c1a75-109"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="c1a75-110">int</span><span class="sxs-lookup"><span data-stu-id="c1a75-110">int</span></span></p></td>
<td><p><span data-ttu-id="c1a75-111">MCU を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c1a75-111">Unique number identifying the MCU.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1a75-112"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="c1a75-112"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c1a75-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c1a75-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c1a75-114">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="c1a75-114">URI of the MCU.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1a75-115"><strong>Mcuuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="c1a75-115"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c1a75-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c1a75-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c1a75-117">MCU URI の種類。</span><span class="sxs-lookup"><span data-stu-id="c1a75-117">Type of MCU URI.</span></span> <span data-ttu-id="c1a75-118">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a75-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

