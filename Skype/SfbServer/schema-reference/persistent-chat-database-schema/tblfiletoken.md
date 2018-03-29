---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken には、ファイル転送のために一時的なトークンが含まれています。
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a><span data-ttu-id="0580b-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="0580b-103">tblFileToken</span></span>
 
<span data-ttu-id="0580b-104">tblFileToken には、ファイル転送のために一時的なトークンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0580b-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="0580b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="0580b-105">**Columns**</span></span>

|<span data-ttu-id="0580b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="0580b-106">**Column**</span></span>|<span data-ttu-id="0580b-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="0580b-107">**Type**</span></span>|<span data-ttu-id="0580b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="0580b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0580b-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="0580b-109">fileToken</span></span>  <br/> |<span data-ttu-id="0580b-110">nvarchar (50) では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="0580b-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="0580b-111">一意のトークン (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="0580b-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="0580b-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="0580b-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="0580b-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="0580b-113">int, not null</span></span>  <br/> |<span data-ttu-id="0580b-114">ファイルの転送は、プリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="0580b-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="0580b-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="0580b-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="0580b-116">GUID では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="0580b-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="0580b-117">チャット ルーム ノードの GUID です。</span><span class="sxs-lookup"><span data-stu-id="0580b-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="0580b-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="0580b-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="0580b-119">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="0580b-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="0580b-120">有効期限。</span><span class="sxs-lookup"><span data-stu-id="0580b-120">Expiration time.</span></span> <span data-ttu-id="0580b-121">(トークン有効期限が切れる 30 分後 (このコラムでは、以下の説明を参照してください) を固定しない限り、します。</span><span class="sxs-lookup"><span data-stu-id="0580b-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="0580b-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="0580b-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="0580b-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0580b-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0580b-124">(コンプライアンス サービスを使用します) に転送されたファイルの URL です。</span><span class="sxs-lookup"><span data-stu-id="0580b-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="0580b-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="0580b-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="0580b-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0580b-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0580b-127">(コンプライアンス サービスを使用します) に転送されたファイルのサムネイルの URL です。</span><span class="sxs-lookup"><span data-stu-id="0580b-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="0580b-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="0580b-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="0580b-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="0580b-129">datetime2</span></span>  <br/> |<span data-ttu-id="0580b-130">実際のファイルのタイムスタンプは、使用するためコンプライアンス サービス) の操作を転送します。</span><span class="sxs-lookup"><span data-stu-id="0580b-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="0580b-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="0580b-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="0580b-132">bit</span><span class="sxs-lookup"><span data-stu-id="0580b-132">bit</span></span>  <br/> |<span data-ttu-id="0580b-133">True の場合これをアップロードするとします。(コンプライアンス サービスを使用します) の場合は false をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0580b-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="0580b-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="0580b-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="0580b-135">ビットの null でないです。</span><span class="sxs-lookup"><span data-stu-id="0580b-135">bit, not null</span></span>  <br/> |<span data-ttu-id="0580b-136">トークンが固定されている場合は true。</span><span class="sxs-lookup"><span data-stu-id="0580b-136">True if token is pinned.</span></span> <span data-ttu-id="0580b-137">コンプライアンス サービスから関連するフィールドを取得することになるまでの表に、トークンを保持するに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0580b-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="0580b-138">**キー**</span><span class="sxs-lookup"><span data-stu-id="0580b-138">**Keys**</span></span>

|<span data-ttu-id="0580b-139">**列**</span><span class="sxs-lookup"><span data-stu-id="0580b-139">**Column**</span></span>|<span data-ttu-id="0580b-140">**説明**</span><span class="sxs-lookup"><span data-stu-id="0580b-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0580b-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="0580b-141">fileToken</span></span>  <br/> |<span data-ttu-id="0580b-142">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="0580b-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0580b-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="0580b-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="0580b-144">TblNode.nodeGuid テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="0580b-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

