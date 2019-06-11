---
title: 'Lync Server 2013: EdgeServers テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca947d710693590d6121242e79a6d29088432e0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="c65a8-102">Lync Server 2013 の EdgeServers テーブル</span><span class="sxs-lookup"><span data-stu-id="c65a8-102">EdgeServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c65a8-103">_**最終更新日:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="c65a8-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="c65a8-104">EdgeServers テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c65a8-104">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="c65a8-105">各レコードには、データベース内のレコードが含まれる通話に関連する1つの Edge サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c65a8-105">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c65a8-106">列</span><span class="sxs-lookup"><span data-stu-id="c65a8-106">Column</span></span></th>
<th><span data-ttu-id="c65a8-107">データ型</span><span class="sxs-lookup"><span data-stu-id="c65a8-107">Data Type</span></span></th>
<th><span data-ttu-id="c65a8-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="c65a8-108">Key/Index</span></span></th>
<th><span data-ttu-id="c65a8-109">詳細</span><span class="sxs-lookup"><span data-stu-id="c65a8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c65a8-110"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c65a8-110"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c65a8-111">int</span><span class="sxs-lookup"><span data-stu-id="c65a8-111">int</span></span></p></td>
<td><p><span data-ttu-id="c65a8-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c65a8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c65a8-113">このエッジサーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="c65a8-113">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c65a8-114"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="c65a8-114"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c65a8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c65a8-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c65a8-116">エッジサーバー名。</span><span class="sxs-lookup"><span data-stu-id="c65a8-116">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

