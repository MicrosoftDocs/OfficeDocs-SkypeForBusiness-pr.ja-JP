---
title: ファイル転送テーブル (Skype for Business Server 2015)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 各レコードは、1つのファイル転送セッションを表します。
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815215"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0d8bb-103">ファイル転送テーブル (Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="0d8bb-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d8bb-104">各レコードは、1つのファイル転送セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="0d8bb-105">**列**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-105">**Column**</span></span>|<span data-ttu-id="0d8bb-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-106">**Data Type**</span></span>|<span data-ttu-id="0d8bb-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-107">**Key/Index**</span></span>|<span data-ttu-id="0d8bb-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0d8bb-109">**セッション Id**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="0d8bb-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0d8bb-110">datetime</span></span>  <br/> |<span data-ttu-id="0d8bb-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0d8bb-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0d8bb-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-112">Time of session request.</span></span> <span data-ttu-id="0d8bb-113">セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="0d8bb-114">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0d8bb-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="0d8bb-116">int</span><span class="sxs-lookup"><span data-stu-id="0d8bb-116">int</span></span>  <br/> |<span data-ttu-id="0d8bb-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="0d8bb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0d8bb-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-118">ID number to identify the session.</span></span> <span data-ttu-id="0d8bb-119">セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="0d8bb-120">詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0d8bb-121">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-121">**File Name**</span></span> <br/> |<span data-ttu-id="0d8bb-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0d8bb-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="0d8bb-123">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="0d8bb-125">長さ</span><span class="sxs-lookup"><span data-stu-id="0d8bb-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="0d8bb-126">同じファイル名を含むファイル転送を区別する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-127">**クッキー**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-127">**Cookie**</span></span> <br/> |<span data-ttu-id="0d8bb-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="0d8bb-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="0d8bb-129">Primary</span><span class="sxs-lookup"><span data-stu-id="0d8bb-129">Primary</span></span>  <br/> |<span data-ttu-id="0d8bb-130">すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-131">**受諾**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-131">**Accept**</span></span> <br/> |<span data-ttu-id="0d8bb-132">bit</span><span class="sxs-lookup"><span data-stu-id="0d8bb-132">bit</span></span>  <br/> ||<span data-ttu-id="0d8bb-133">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="0d8bb-134">TRUE の場合は、拒否とキャンセルは NULL になります。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-134">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-135">**拒否**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-135">**Reject**</span></span> <br/> |<span data-ttu-id="0d8bb-136">bit</span><span class="sxs-lookup"><span data-stu-id="0d8bb-136">bit</span></span>  <br/> ||<span data-ttu-id="0d8bb-137">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="0d8bb-138">TRUE の場合は、Accept と Cancel は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-138">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-139">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-139">**Cancel**</span></span> <br/> |<span data-ttu-id="0d8bb-140">bit</span><span class="sxs-lookup"><span data-stu-id="0d8bb-140">bit</span></span>  <br/> ||<span data-ttu-id="0d8bb-141">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="0d8bb-142">TRUE の場合は、Accept と Reject は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-142">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="0d8bb-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="0d8bb-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="0d8bb-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="0d8bb-144">Datetime</span></span>  <br/> ||<span data-ttu-id="0d8bb-145">監視サービスで内部的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="0d8bb-146">このフィールドは、Skype for Business Server 2015 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0d8bb-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

