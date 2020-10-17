---
title: 'Lync Server 2013: ConferenceUris ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris view
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49733750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5c2ff93d4c3230991f4b9d0d4d746754a42ac44
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507844"
---
# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="68781-102">Lync Server 2013 の ConferenceUris ビュー</span><span class="sxs-lookup"><span data-stu-id="68781-102">ConferenceUris view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68781-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="68781-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="68781-104">ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="68781-104">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="68781-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="68781-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68781-106">Column</span><span class="sxs-lookup"><span data-stu-id="68781-106">Column</span></span></th>
<th><span data-ttu-id="68781-107">データ型</span><span class="sxs-lookup"><span data-stu-id="68781-107">Data Type</span></span></th>
<th><span data-ttu-id="68781-108">詳細</span><span class="sxs-lookup"><span data-stu-id="68781-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68781-109">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="68781-109">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="68781-110">int</span><span class="sxs-lookup"><span data-stu-id="68781-110">int</span></span></p></td>
<td><p><span data-ttu-id="68781-111">会議 URI を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="68781-111">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68781-112">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="68781-112">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="68781-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="68781-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="68781-114">電話会議の URI。</span><span class="sxs-lookup"><span data-stu-id="68781-114">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68781-115">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="68781-115">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="68781-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68781-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68781-117">電話会議の URI の種類。</span><span class="sxs-lookup"><span data-stu-id="68781-117">Type of conference URI.</span></span> <span data-ttu-id="68781-118">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68781-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

