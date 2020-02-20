---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 9e3d80b1a326140a94b840c212fc8577a73e468f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="29c53-102">Lync Server 2013 の tblFileToken</span><span class="sxs-lookup"><span data-stu-id="29c53-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29c53-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="29c53-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="29c53-104">tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="29c53-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="29c53-105">Columns</span><span class="sxs-lookup"><span data-stu-id="29c53-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c53-106">列</span><span class="sxs-lookup"><span data-stu-id="29c53-106">Column</span></span></th>
<th><span data-ttu-id="29c53-107">種類</span><span class="sxs-lookup"><span data-stu-id="29c53-107">Type</span></span></th>
<th><span data-ttu-id="29c53-108">説明</span><span class="sxs-lookup"><span data-stu-id="29c53-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c53-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="29c53-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="29c53-110">NULL でない nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="29c53-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="29c53-111">一意のトークン (GUID)。</span><span class="sxs-lookup"><span data-stu-id="29c53-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c53-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="29c53-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="29c53-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="29c53-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="29c53-114">ファイルを転送するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="29c53-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c53-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="29c53-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="29c53-116">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="29c53-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="29c53-117">チャット ルーム ノードの GUID。</span><span class="sxs-lookup"><span data-stu-id="29c53-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c53-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="29c53-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="29c53-119">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="29c53-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="29c53-p101">有効期限。固定されていない場合、トークンの有効期限は 30 分 （この列の以下の説明を参照)。</span><span class="sxs-lookup"><span data-stu-id="29c53-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c53-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="29c53-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="29c53-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c53-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c53-124">転送ファイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="29c53-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c53-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="29c53-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="29c53-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29c53-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29c53-127">転送ファイルのサムネイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="29c53-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c53-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="29c53-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="29c53-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="29c53-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="29c53-130">実際のファイル転送操作のタイムスタンプ (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="29c53-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c53-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="29c53-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="29c53-132">若干</span><span class="sxs-lookup"><span data-stu-id="29c53-132">bit</span></span></p></td>
<td><p><span data-ttu-id="29c53-133">アップロードの場合は True、ダウンロードの場合 False (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="29c53-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29c53-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="29c53-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="29c53-135">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="29c53-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="29c53-p102">トークンが固定されている場合は True。Compliance Service が関連フィールドを取得できるようになるまで、テーブル内にトークンを維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="29c53-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="29c53-138">Keys</span><span class="sxs-lookup"><span data-stu-id="29c53-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29c53-139">列</span><span class="sxs-lookup"><span data-stu-id="29c53-139">Column</span></span></th>
<th><span data-ttu-id="29c53-140">説明</span><span class="sxs-lookup"><span data-stu-id="29c53-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29c53-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="29c53-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="29c53-142">主キー。</span><span class="sxs-lookup"><span data-stu-id="29c53-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29c53-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="29c53-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="29c53-144">tblNode.nodeGuid テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="29c53-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

