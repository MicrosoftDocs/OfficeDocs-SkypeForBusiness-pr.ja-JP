---
title: 'Lync Server 2013: ClientVersions ビュー'
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
ms.openlocfilehash: 1a7e62fbf56d270c6d2d0c65415dc28dd30e4449
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="15d3e-102">Lync Server 2013 の ClientVersions ビュー</span><span class="sxs-lookup"><span data-stu-id="15d3e-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d3e-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="15d3e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="15d3e-104">ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="15d3e-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="15d3e-105">ビュー内の各レコードは、1 つのクライアント バージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="15d3e-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="15d3e-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="15d3e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15d3e-107">一部の列には複数のレコードが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="15d3e-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d3e-108">列</span><span class="sxs-lookup"><span data-stu-id="15d3e-108">Column</span></span></th>
<th><span data-ttu-id="15d3e-109">データ型</span><span class="sxs-lookup"><span data-stu-id="15d3e-109">Data Type</span></span></th>
<th><span data-ttu-id="15d3e-110">詳細</span><span class="sxs-lookup"><span data-stu-id="15d3e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d3e-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="15d3e-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d3e-112">int</span><span class="sxs-lookup"><span data-stu-id="15d3e-112">int</span></span></p></td>
<td><p><span data-ttu-id="15d3e-113">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="15d3e-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d3e-114"><strong>バージョン</strong></span><span class="sxs-lookup"><span data-stu-id="15d3e-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="15d3e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15d3e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15d3e-116">ユーザー エージェントを表す。</span><span class="sxs-lookup"><span data-stu-id="15d3e-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d3e-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="15d3e-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="15d3e-118">int</span><span class="sxs-lookup"><span data-stu-id="15d3e-118">int</span></span></p></td>
<td><p><span data-ttu-id="15d3e-119">クライアントの種類。</span><span class="sxs-lookup"><span data-stu-id="15d3e-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d3e-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="15d3e-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="15d3e-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="15d3e-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="15d3e-p102">クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。</span><span class="sxs-lookup"><span data-stu-id="15d3e-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

