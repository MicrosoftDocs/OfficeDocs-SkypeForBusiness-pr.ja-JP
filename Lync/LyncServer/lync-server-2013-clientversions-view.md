---
title: 'Lync Server 2013: ClientVersions ビュー'
description: 'Lync Server 2013: ClientVersions ビュー。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542803"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="6a919-103">Lync Server 2013 の ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="6a919-103">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a919-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6a919-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6a919-105">ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6a919-105">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="6a919-106">ビュー内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="6a919-106">Each record in the view represents one client version.</span></span> <span data-ttu-id="6a919-107">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6a919-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a919-108">一部の列には複数のレコードが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a919-108">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a919-109">Column</span><span class="sxs-lookup"><span data-stu-id="6a919-109">Column</span></span></th>
<th><span data-ttu-id="6a919-110">データ型</span><span class="sxs-lookup"><span data-stu-id="6a919-110">Data Type</span></span></th>
<th><span data-ttu-id="6a919-111">詳細</span><span class="sxs-lookup"><span data-stu-id="6a919-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a919-112"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="6a919-112"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="6a919-113">int</span><span class="sxs-lookup"><span data-stu-id="6a919-113">int</span></span></p></td>
<td><p><span data-ttu-id="6a919-114">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="6a919-114">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a919-115"><strong>バージョン</strong></span><span class="sxs-lookup"><span data-stu-id="6a919-115"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="6a919-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6a919-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6a919-117">ユーザー エージェントを表す。</span><span class="sxs-lookup"><span data-stu-id="6a919-117">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a919-118"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="6a919-118"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6a919-119">int</span><span class="sxs-lookup"><span data-stu-id="6a919-119">int</span></span></p></td>
<td><p><span data-ttu-id="6a919-120">クライアントの種類。</span><span class="sxs-lookup"><span data-stu-id="6a919-120">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a919-121"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="6a919-121"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6a919-122">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6a919-122">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6a919-p102">クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。</span><span class="sxs-lookup"><span data-stu-id="6a919-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

