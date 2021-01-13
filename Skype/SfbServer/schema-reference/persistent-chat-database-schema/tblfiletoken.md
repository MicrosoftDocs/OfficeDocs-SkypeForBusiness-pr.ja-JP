---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816017"
---
# <a name="tblfiletoken"></a><span data-ttu-id="bfdd9-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="bfdd9-103">tblFileToken</span></span>
 
<span data-ttu-id="bfdd9-104">tblFileToken には、ファイル送信を目的とする一時的なトークンが格納されます。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="bfdd9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-105">**Columns**</span></span>

|<span data-ttu-id="bfdd9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-106">**Column**</span></span>|<span data-ttu-id="bfdd9-107">**型**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-107">**Type**</span></span>|<span data-ttu-id="bfdd9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bfdd9-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="bfdd9-109">fileToken</span></span>  <br/> |<span data-ttu-id="bfdd9-110">NULL でない nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="bfdd9-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="bfdd9-111">一意のトークン (GUID)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="bfdd9-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="bfdd9-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="bfdd9-113">int, not null</span></span>  <br/> |<span data-ttu-id="bfdd9-114">ファイルを転送するプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="bfdd9-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="bfdd9-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="bfdd9-116">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="bfdd9-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="bfdd9-117">チャット ルーム ノードの GUID。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="bfdd9-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="bfdd9-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="bfdd9-119">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="bfdd9-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="bfdd9-p101">有効期限。固定されていない場合、トークンの有効期限は 30 分 （この列の以下の説明を参照)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="bfdd9-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="bfdd9-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfdd9-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bfdd9-124">転送ファイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="bfdd9-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="bfdd9-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bfdd9-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bfdd9-127">転送ファイルのサムネイルの URL (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="bfdd9-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="bfdd9-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="bfdd9-129">datetime2</span></span>  <br/> |<span data-ttu-id="bfdd9-130">実際のファイル転送操作のタイムスタンプ (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="bfdd9-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="bfdd9-132">bit</span><span class="sxs-lookup"><span data-stu-id="bfdd9-132">bit</span></span>  <br/> |<span data-ttu-id="bfdd9-133">アップロードの場合は True、ダウンロードの場合 False (Compliance Service で使用)。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="bfdd9-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="bfdd9-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="bfdd9-135">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="bfdd9-135">bit, not null</span></span>  <br/> |<span data-ttu-id="bfdd9-136">トークンが固定されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-136">True if token is pinned.</span></span> <span data-ttu-id="bfdd9-137">コンプライアンス サービスが関連フィールドを取得できるまで、トークンをテーブルに保持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="bfdd9-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-138">**Keys**</span></span>

|<span data-ttu-id="bfdd9-139">**列**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-139">**Column**</span></span>|<span data-ttu-id="bfdd9-140">**説明**</span><span class="sxs-lookup"><span data-stu-id="bfdd9-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfdd9-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="bfdd9-141">fileToken</span></span>  <br/> |<span data-ttu-id="bfdd9-142">主キー。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bfdd9-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="bfdd9-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="bfdd9-144">tblNode.nodeGuid テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="bfdd9-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

