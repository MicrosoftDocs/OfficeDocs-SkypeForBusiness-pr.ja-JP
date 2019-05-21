---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル転送のための一時トークンが含まれています。
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295406"
---
# <a name="tblfiletoken"></a><span data-ttu-id="3b316-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="3b316-103">tblFileToken</span></span>
 
<span data-ttu-id="3b316-104">tblFileToken には、ファイル転送のための一時トークンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b316-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="3b316-105">**行**</span><span class="sxs-lookup"><span data-stu-id="3b316-105">**Columns**</span></span>

|<span data-ttu-id="3b316-106">**列**</span><span class="sxs-lookup"><span data-stu-id="3b316-106">**Column**</span></span>|<span data-ttu-id="3b316-107">**型**</span><span class="sxs-lookup"><span data-stu-id="3b316-107">**Type**</span></span>|<span data-ttu-id="3b316-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="3b316-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b316-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="3b316-109">fileToken</span></span>  <br/> |<span data-ttu-id="3b316-110">nvarchar (50)、null ではない</span><span class="sxs-lookup"><span data-stu-id="3b316-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="3b316-111">一意のトークン (GUID)。</span><span class="sxs-lookup"><span data-stu-id="3b316-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="3b316-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="3b316-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="3b316-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="3b316-113">int, not null</span></span>  <br/> |<span data-ttu-id="3b316-114">ファイルを転送するプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="3b316-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="3b316-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="3b316-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="3b316-116">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="3b316-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="3b316-117">チャットルームノードの GUID です。</span><span class="sxs-lookup"><span data-stu-id="3b316-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="3b316-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="3b316-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="3b316-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="3b316-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="3b316-120">有効期限。</span><span class="sxs-lookup"><span data-stu-id="3b316-120">Expiration time.</span></span> <span data-ttu-id="3b316-121">(固定されていない限り、トークンは30分後に期限切れになります (このコラムの次の説明を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3b316-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="3b316-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="3b316-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="3b316-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3b316-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3b316-124">転送されたファイルの URL (コンプライアンスサービスの使用の場合)。</span><span class="sxs-lookup"><span data-stu-id="3b316-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="3b316-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="3b316-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="3b316-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3b316-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3b316-127">転送されたファイル (コンプライアンスサービスの使用の場合) のサムネイルの URL。</span><span class="sxs-lookup"><span data-stu-id="3b316-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="3b316-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="3b316-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="3b316-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="3b316-129">datetime2</span></span>  <br/> |<span data-ttu-id="3b316-130">実際のファイル転送操作のタイムスタンプ (コンプライアンスサービスの使用の場合)。</span><span class="sxs-lookup"><span data-stu-id="3b316-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="3b316-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="3b316-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="3b316-132">bit</span><span class="sxs-lookup"><span data-stu-id="3b316-132">bit</span></span>  <br/> |<span data-ttu-id="3b316-133">アップロードの場合は True(コンプライアンスサービスの使用のために) False を返します。</span><span class="sxs-lookup"><span data-stu-id="3b316-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="3b316-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="3b316-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="3b316-135">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="3b316-135">bit, not null</span></span>  <br/> |<span data-ttu-id="3b316-136">トークンがピン留めされている場合は True です。</span><span class="sxs-lookup"><span data-stu-id="3b316-136">True if token is pinned.</span></span> <span data-ttu-id="3b316-137">これは、コンプライアンスサービスが関連するフィールドを取得できるようになるまで、トークンをテーブルに保持するために使われます。</span><span class="sxs-lookup"><span data-stu-id="3b316-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="3b316-138">**機能**</span><span class="sxs-lookup"><span data-stu-id="3b316-138">**Keys**</span></span>

|<span data-ttu-id="3b316-139">**列**</span><span class="sxs-lookup"><span data-stu-id="3b316-139">**Column**</span></span>|<span data-ttu-id="3b316-140">**説明**</span><span class="sxs-lookup"><span data-stu-id="3b316-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b316-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="3b316-141">fileToken</span></span>  <br/> |<span data-ttu-id="3b316-142">主キー。</span><span class="sxs-lookup"><span data-stu-id="3b316-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3b316-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="3b316-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="3b316-144">TblNode Guid テーブルで参照されている外部キー。</span><span class="sxs-lookup"><span data-stu-id="3b316-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

