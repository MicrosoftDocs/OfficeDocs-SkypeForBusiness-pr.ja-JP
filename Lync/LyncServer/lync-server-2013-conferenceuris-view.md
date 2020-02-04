---
title: 'Lync Server 2013: ConferenceUris view'
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
ms.openlocfilehash: 59b5a88cc24e66fb3938b10a5ceeb8c461be2db3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="00813-102">Lync Server 2013 での ConferenceUris の表示</span><span class="sxs-lookup"><span data-stu-id="00813-102">ConferenceUris view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00813-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="00813-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="00813-104">ConfernceUris ビューには、会議セッションに参加した Uri に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="00813-104">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="00813-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="00813-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00813-106">列</span><span class="sxs-lookup"><span data-stu-id="00813-106">Column</span></span></th>
<th><span data-ttu-id="00813-107">データ型</span><span class="sxs-lookup"><span data-stu-id="00813-107">Data Type</span></span></th>
<th><span data-ttu-id="00813-108">詳細</span><span class="sxs-lookup"><span data-stu-id="00813-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00813-109">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="00813-109">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="00813-110">int</span><span class="sxs-lookup"><span data-stu-id="00813-110">int</span></span></p></td>
<td><p><span data-ttu-id="00813-111">会議 URI を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="00813-111">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00813-112">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="00813-112">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="00813-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="00813-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="00813-114">会議の URI。</span><span class="sxs-lookup"><span data-stu-id="00813-114">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00813-115">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="00813-115">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="00813-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00813-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="00813-117">電話会議 URI の種類。</span><span class="sxs-lookup"><span data-stu-id="00813-117">Type of conference URI.</span></span> <span data-ttu-id="00813-118">詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00813-118">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

