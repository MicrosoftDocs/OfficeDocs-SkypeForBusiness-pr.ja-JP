---
title: 'Lync Server 2013: ContentTypes テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c068d0e6d72980175aa1123ece05c40bbe72239b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="contenttypes-table-in-lync-server-2013"></a><span data-ttu-id="9e227-102">Lync Server 2013 の ContentTypes テーブル</span><span class="sxs-lookup"><span data-stu-id="9e227-102">ContentTypes table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e227-103">_**トピックの最終更新日:** 2010-11-07_</span><span class="sxs-lookup"><span data-stu-id="9e227-103">_**Topic Last Modified:** 2010-11-07_</span></span>

<span data-ttu-id="9e227-104">ContentTypes テーブルは、ピアツーピアセッションと電話会議セッションの両方で使用されるコンテンツタイプのリストを格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="9e227-104">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="9e227-105">テーブル内の各レコードは、1つのコンテンツタイプを表します。</span><span class="sxs-lookup"><span data-stu-id="9e227-105">Each record in the table represents one content type.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e227-106">列</span><span class="sxs-lookup"><span data-stu-id="9e227-106">Column</span></span></th>
<th><span data-ttu-id="9e227-107">データ型</span><span class="sxs-lookup"><span data-stu-id="9e227-107">Data Type</span></span></th>
<th><span data-ttu-id="9e227-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="9e227-108">Key/Index</span></span></th>
<th><span data-ttu-id="9e227-109">詳細</span><span class="sxs-lookup"><span data-stu-id="9e227-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e227-110"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9e227-110"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9e227-111">int</span><span class="sxs-lookup"><span data-stu-id="9e227-111">int</span></span></p></td>
<td><p><span data-ttu-id="9e227-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9e227-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9e227-113">コンテンツタイプを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="9e227-113">Unique number identifying the content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e227-114"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9e227-114"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9e227-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9e227-115">nvarchar(256)</span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="9e227-116">コンテンツタイプの名前。</span><span class="sxs-lookup"><span data-stu-id="9e227-116">Content type name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

