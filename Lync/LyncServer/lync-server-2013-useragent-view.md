---
title: 'Lync Server 2013: UserAgent ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c30b8e227b55207efe33abb4b6294082660c1f07
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="411c3-102">Lync Server 2013 の UserAgent ビュー</span><span class="sxs-lookup"><span data-stu-id="411c3-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="411c3-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="411c3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="411c3-104">UserAgent ビューには、データベース内のレコードを持つセッションに関係しているユーザーエージェントに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="411c3-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="411c3-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="411c3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="411c3-106">列</span><span class="sxs-lookup"><span data-stu-id="411c3-106">Column</span></span></th>
<th><span data-ttu-id="411c3-107">データ型</span><span class="sxs-lookup"><span data-stu-id="411c3-107">Data Type</span></span></th>
<th><span data-ttu-id="411c3-108">詳細</span><span class="sxs-lookup"><span data-stu-id="411c3-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="411c3-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="411c3-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="411c3-110">int</span><span class="sxs-lookup"><span data-stu-id="411c3-110">int</span></span></p></td>
<td><p><span data-ttu-id="411c3-111">このユーザーエージェントを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="411c3-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="411c3-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="411c3-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="411c3-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="411c3-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="411c3-114">ユーザーエージェント文字列。</span><span class="sxs-lookup"><span data-stu-id="411c3-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="411c3-115">UAType</span><span class="sxs-lookup"><span data-stu-id="411c3-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="411c3-116">smallint</span><span class="sxs-lookup"><span data-stu-id="411c3-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="411c3-117">ユーザーエージェントの種類。</span><span class="sxs-lookup"><span data-stu-id="411c3-117">Type of user agent.</span></span> <span data-ttu-id="411c3-118">詳細については、「 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 の UserAgent テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="411c3-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="411c3-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="411c3-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="411c3-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="411c3-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="411c3-p103">ユーザー エージェントが属するカテゴリ。たとえば、ユーザー エージェント Conferencing_Attendant_1.0 は UACategory CAA に属します。</span><span class="sxs-lookup"><span data-stu-id="411c3-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

