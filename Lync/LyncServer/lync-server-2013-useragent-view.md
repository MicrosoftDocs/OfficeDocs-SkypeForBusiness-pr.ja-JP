---
title: 'Lync Server 2013: UserAgent view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="2473e-102">Lync Server 2013 での UserAgent の表示</span><span class="sxs-lookup"><span data-stu-id="2473e-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2473e-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2473e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2473e-104">UserAgent ビューには、データベース内のレコードを持つセッションに関連しているユーザーエージェントに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="2473e-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="2473e-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2473e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2473e-106">列</span><span class="sxs-lookup"><span data-stu-id="2473e-106">Column</span></span></th>
<th><span data-ttu-id="2473e-107">データ型</span><span class="sxs-lookup"><span data-stu-id="2473e-107">Data Type</span></span></th>
<th><span data-ttu-id="2473e-108">詳細</span><span class="sxs-lookup"><span data-stu-id="2473e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2473e-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="2473e-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="2473e-110">int</span><span class="sxs-lookup"><span data-stu-id="2473e-110">int</span></span></p></td>
<td><p><span data-ttu-id="2473e-111">このユーザーエージェントを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="2473e-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2473e-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="2473e-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="2473e-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2473e-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2473e-114">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="2473e-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2473e-115">UAType</span><span class="sxs-lookup"><span data-stu-id="2473e-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="2473e-116">smallint</span><span class="sxs-lookup"><span data-stu-id="2473e-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="2473e-117">ユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="2473e-117">Type of user agent.</span></span> <span data-ttu-id="2473e-118">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2473e-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2473e-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="2473e-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="2473e-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2473e-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2473e-121">ユーザーエージェントが属しているカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="2473e-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="2473e-122">たとえば、ユーザーエージェント Conferencing_Attendant_ 1.0 は UACategory CAA をに属しています。</span><span class="sxs-lookup"><span data-stu-id="2473e-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

