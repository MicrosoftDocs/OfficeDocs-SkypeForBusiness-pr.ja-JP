---
title: 'Lync Server 2013: CodecDescription テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9c6cbdfd24517308321f5f3838fba56e90f842
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="fdd85-102">Lync Server 2013 の CodecDescription テーブル</span><span class="sxs-lookup"><span data-stu-id="fdd85-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdd85-103">_**最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="fdd85-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="fdd85-104">CodecDescription テーブルでは、一意のコーデック識別子が対応するコーデックにマップされます。</span><span class="sxs-lookup"><span data-stu-id="fdd85-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="fdd85-105">コーデックは、伝送とブロードキャスト用のデジタルシグナルをエンコードし、再生のためにそれらのシグナルをデコードするために使われます。</span><span class="sxs-lookup"><span data-stu-id="fdd85-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="fdd85-106">この表は Microsoft Lync Server 2013 で導入されました</span><span class="sxs-lookup"><span data-stu-id="fdd85-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdd85-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fdd85-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fdd85-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fdd85-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdd85-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fdd85-112">smallint</span><span class="sxs-lookup"><span data-stu-id="fdd85-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="fdd85-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fdd85-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdd85-114">コーデックに割り当てられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fdd85-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdd85-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fdd85-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fdd85-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="fdd85-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fdd85-117">一意</span><span class="sxs-lookup"><span data-stu-id="fdd85-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="fdd85-118">CodecDescriptionKey に対応するコーデックの固有の説明です。</span><span class="sxs-lookup"><span data-stu-id="fdd85-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

