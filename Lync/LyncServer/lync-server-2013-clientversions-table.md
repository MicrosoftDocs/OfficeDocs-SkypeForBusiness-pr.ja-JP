---
title: 'Lync Server 2013: ClientVersions テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857db525a61f478073d72a011d86ab34eff36d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="59bb0-102">Lync Server 2013 の ClientVersions テーブル</span><span class="sxs-lookup"><span data-stu-id="59bb0-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59bb0-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="59bb0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="59bb0-104">ClientVersions テーブルは、データベースに記録されているセッションに参加しているさまざまなクライアントの種類とバージョンの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="59bb0-104">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="59bb0-105">テーブル内の各レコードは、1つのクライアントバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="59bb0-105">Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59bb0-106">列</span><span class="sxs-lookup"><span data-stu-id="59bb0-106">Column</span></span></th>
<th><span data-ttu-id="59bb0-107">データ型</span><span class="sxs-lookup"><span data-stu-id="59bb0-107">Data Type</span></span></th>
<th><span data-ttu-id="59bb0-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="59bb0-108">Key/Index</span></span></th>
<th><span data-ttu-id="59bb0-109">詳細</span><span class="sxs-lookup"><span data-stu-id="59bb0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59bb0-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="59bb0-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="59bb0-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="59bb0-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="59bb0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="59bb0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="59bb0-113">このクライアントの種類とバージョンを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="59bb0-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59bb0-114"><strong>バージョン</strong></span><span class="sxs-lookup"><span data-stu-id="59bb0-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="59bb0-115"><strong>nvarchar(256)</strong></span><span class="sxs-lookup"><span data-stu-id="59bb0-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59bb0-116">バージョン名。</span><span class="sxs-lookup"><span data-stu-id="59bb0-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59bb0-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="59bb0-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="59bb0-118">int</span><span class="sxs-lookup"><span data-stu-id="59bb0-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59bb0-119">セッションで使用するクライアントの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="59bb0-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="59bb0-120">詳細については、「 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 の Useragentdef テーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59bb0-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="59bb0-121">このフィールドは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="59bb0-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

