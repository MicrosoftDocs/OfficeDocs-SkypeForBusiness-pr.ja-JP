---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547633"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="7426b-103">Lync Server 2013 の tblFileToken</span><span class="sxs-lookup"><span data-stu-id="7426b-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7426b-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7426b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7426b-105">tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="7426b-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="7426b-106">段組み</span><span class="sxs-lookup"><span data-stu-id="7426b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7426b-107">Column</span><span class="sxs-lookup"><span data-stu-id="7426b-107">Column</span></span></th>
<th><span data-ttu-id="7426b-108">種類</span><span class="sxs-lookup"><span data-stu-id="7426b-108">Type</span></span></th>
<th><span data-ttu-id="7426b-109">説明</span><span class="sxs-lookup"><span data-stu-id="7426b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7426b-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="7426b-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7426b-111">NULL でない nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="7426b-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="7426b-112">一意のトークン (GUID)。</span><span class="sxs-lookup"><span data-stu-id="7426b-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7426b-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="7426b-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="7426b-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="7426b-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7426b-115">ファイルを転送するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="7426b-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7426b-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7426b-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7426b-117">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="7426b-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7426b-118">チャット ルーム ノードの GUID。</span><span class="sxs-lookup"><span data-stu-id="7426b-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7426b-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="7426b-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="7426b-120">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="7426b-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="7426b-p101">有効期限。固定されていない場合、トークンの有効期限は 30 分 （この列の以下の説明を参照)。</span><span class="sxs-lookup"><span data-stu-id="7426b-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7426b-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="7426b-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="7426b-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7426b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7426b-125">転送ファイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="7426b-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7426b-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="7426b-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="7426b-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7426b-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7426b-128">転送ファイルのサムネイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="7426b-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7426b-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="7426b-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="7426b-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="7426b-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="7426b-131">実際のファイル転送操作のタイムスタンプ (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="7426b-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7426b-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="7426b-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="7426b-133">若干</span><span class="sxs-lookup"><span data-stu-id="7426b-133">bit</span></span></p></td>
<td><p><span data-ttu-id="7426b-134">アップロードの場合は True、ダウンロードの場合 False (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="7426b-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7426b-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="7426b-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="7426b-136">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="7426b-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="7426b-p102">トークンが固定されている場合は True。Compliance Service が関連フィールドを取得できるようになるまで、テーブル内にトークンを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7426b-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7426b-139">Keys</span><span class="sxs-lookup"><span data-stu-id="7426b-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7426b-140">列</span><span class="sxs-lookup"><span data-stu-id="7426b-140">Column</span></span></th>
<th><span data-ttu-id="7426b-141">説明</span><span class="sxs-lookup"><span data-stu-id="7426b-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7426b-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="7426b-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="7426b-143">主キー。</span><span class="sxs-lookup"><span data-stu-id="7426b-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7426b-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="7426b-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="7426b-145">tblNode.nodeGuid テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="7426b-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

