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
ms.openlocfilehash: f7512054e3b0f1e4edaf7736558bed1df8c9b08d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524654"
---
# <a name="mcus-view-in-lync-server-2013"></a><span data-ttu-id="a4f8e-102">Lync Server 2013 の mcu ビュー</span><span class="sxs-lookup"><span data-stu-id="a4f8e-102">Mcus view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4f8e-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a4f8e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a4f8e-104">Mcus ビューには、電話会議セッションに参加した MCU に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-104">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="a4f8e-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4f8e-106">Column</span><span class="sxs-lookup"><span data-stu-id="a4f8e-106">Column</span></span></th>
<th><span data-ttu-id="a4f8e-107">データ型</span><span class="sxs-lookup"><span data-stu-id="a4f8e-107">Data Type</span></span></th>
<th><span data-ttu-id="a4f8e-108">詳細</span><span class="sxs-lookup"><span data-stu-id="a4f8e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4f8e-109"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="a4f8e-109"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4f8e-110">int</span><span class="sxs-lookup"><span data-stu-id="a4f8e-110">int</span></span></p></td>
<td><p><span data-ttu-id="a4f8e-111">MCU を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-111">Unique number identifying the MCU.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4f8e-112"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="a4f8e-112"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a4f8e-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a4f8e-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a4f8e-114">MCU の URI。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-114">URI of the MCU.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4f8e-115"><strong>Mcuuritoff</strong></span><span class="sxs-lookup"><span data-stu-id="a4f8e-115"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a4f8e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a4f8e-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a4f8e-117">MCU URI の種類。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-117">Type of MCU URI.</span></span> <span data-ttu-id="a4f8e-118">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4f8e-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

