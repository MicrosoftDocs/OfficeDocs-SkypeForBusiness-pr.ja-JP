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
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="61760-102">Lync Server 2013 の tblFileToken</span><span class="sxs-lookup"><span data-stu-id="61760-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61760-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="61760-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="61760-104">tblFileToken には、ファイル転送のための一時トークンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="61760-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="61760-105">行</span><span class="sxs-lookup"><span data-stu-id="61760-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61760-106">列</span><span class="sxs-lookup"><span data-stu-id="61760-106">Column</span></span></th>
<th><span data-ttu-id="61760-107">型</span><span class="sxs-lookup"><span data-stu-id="61760-107">Type</span></span></th>
<th><span data-ttu-id="61760-108">説明</span><span class="sxs-lookup"><span data-stu-id="61760-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61760-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="61760-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="61760-110">nvarchar (50)、null ではない</span><span class="sxs-lookup"><span data-stu-id="61760-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="61760-111">一意のトークン (GUID)。</span><span class="sxs-lookup"><span data-stu-id="61760-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61760-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="61760-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="61760-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="61760-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="61760-114">ファイルを転送するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="61760-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61760-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="61760-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="61760-116">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="61760-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="61760-117">チャットルームノードの GUID です。</span><span class="sxs-lookup"><span data-stu-id="61760-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61760-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="61760-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="61760-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="61760-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="61760-120">有効期限。</span><span class="sxs-lookup"><span data-stu-id="61760-120">Expiration time.</span></span> <span data-ttu-id="61760-121">(固定されていない限り、トークンは30分後に期限切れになります (このコラムの次の説明を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="61760-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61760-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="61760-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="61760-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61760-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61760-124">転送されたファイルの URL (コンプライアンスサービスの使用の場合)。</span><span class="sxs-lookup"><span data-stu-id="61760-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61760-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="61760-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="61760-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61760-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61760-127">転送されたファイル (コンプライアンスサービスの使用の場合) のサムネイルの URL。</span><span class="sxs-lookup"><span data-stu-id="61760-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61760-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="61760-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="61760-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="61760-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="61760-130">実際のファイル転送操作のタイムスタンプ (コンプライアンスサービスの使用の場合)。</span><span class="sxs-lookup"><span data-stu-id="61760-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61760-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="61760-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="61760-132">bit</span><span class="sxs-lookup"><span data-stu-id="61760-132">bit</span></span></p></td>
<td><p><span data-ttu-id="61760-133">アップロードの場合は True(コンプライアンスサービスの使用のために) False を返します。</span><span class="sxs-lookup"><span data-stu-id="61760-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61760-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="61760-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="61760-135">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="61760-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="61760-136">トークンがピン留めされている場合は True です。</span><span class="sxs-lookup"><span data-stu-id="61760-136">True if token is pinned.</span></span> <span data-ttu-id="61760-137">これは、コンプライアンスサービスが関連するフィールドを取得できるようになるまで、トークンをテーブルに保持するために使われます。</span><span class="sxs-lookup"><span data-stu-id="61760-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="61760-138">機能</span><span class="sxs-lookup"><span data-stu-id="61760-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61760-139">列</span><span class="sxs-lookup"><span data-stu-id="61760-139">Column</span></span></th>
<th><span data-ttu-id="61760-140">説明</span><span class="sxs-lookup"><span data-stu-id="61760-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61760-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="61760-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="61760-142">主キー。</span><span class="sxs-lookup"><span data-stu-id="61760-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61760-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="61760-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="61760-144">TblNode Guid テーブルで参照されている外部キー。</span><span class="sxs-lookup"><span data-stu-id="61760-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

