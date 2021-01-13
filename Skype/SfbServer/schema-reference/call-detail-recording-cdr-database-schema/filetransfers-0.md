---
title: Skype for Business Server 2015 の FileTransfers テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 各レコードは、1 つのファイル転送セッションを表します。
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821697"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="cf55c-103">Skype for Business Server 2015 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="cf55c-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cf55c-104">各レコードは、1 つのファイル転送セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="cf55c-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="cf55c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="cf55c-105">**Column**</span></span>|<span data-ttu-id="cf55c-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="cf55c-106">**Data Type**</span></span>|<span data-ttu-id="cf55c-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="cf55c-107">**Key/Index**</span></span>|<span data-ttu-id="cf55c-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="cf55c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf55c-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="cf55c-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="cf55c-110">日付型</span><span class="sxs-lookup"><span data-stu-id="cf55c-110">datetime</span></span>  <br/> |<span data-ttu-id="cf55c-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cf55c-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cf55c-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="cf55c-112">Time of session request.</span></span> <span data-ttu-id="cf55c-113">セッションを一意に識別するために **SessionIdSeq** と併用されます。</span><span class="sxs-lookup"><span data-stu-id="cf55c-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="cf55c-114">詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf55c-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cf55c-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="cf55c-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="cf55c-116">int</span><span class="sxs-lookup"><span data-stu-id="cf55c-116">int</span></span>  <br/> |<span data-ttu-id="cf55c-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="cf55c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="cf55c-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="cf55c-118">ID number to identify the session.</span></span> <span data-ttu-id="cf55c-119">セッションを一意に識別するために **SessionIdTime** と併用されます。</span><span class="sxs-lookup"><span data-stu-id="cf55c-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="cf55c-120">詳細については [、Skype for Business Server 2015](dialogs.md) の Dialogs テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf55c-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="cf55c-121">**File Name**</span><span class="sxs-lookup"><span data-stu-id="cf55c-121">**File Name**</span></span> <br/> |<span data-ttu-id="cf55c-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cf55c-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="cf55c-123">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="cf55c-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="cf55c-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="cf55c-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="cf55c-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="cf55c-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="cf55c-126">同じファイル名を含むファイル転送を区別するための一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="cf55c-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="cf55c-127">**クッキー**</span><span class="sxs-lookup"><span data-stu-id="cf55c-127">**Cookie**</span></span> <br/> |<span data-ttu-id="cf55c-128">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="cf55c-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="cf55c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="cf55c-129">Primary</span></span>  <br/> |<span data-ttu-id="cf55c-130">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="cf55c-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="cf55c-131">**Accept**</span><span class="sxs-lookup"><span data-stu-id="cf55c-131">**Accept**</span></span> <br/> |<span data-ttu-id="cf55c-132">bit</span><span class="sxs-lookup"><span data-stu-id="cf55c-132">bit</span></span>  <br/> ||<span data-ttu-id="cf55c-p103">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf55c-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="cf55c-135">**Reject**</span><span class="sxs-lookup"><span data-stu-id="cf55c-135">**Reject**</span></span> <br/> |<span data-ttu-id="cf55c-136">bit</span><span class="sxs-lookup"><span data-stu-id="cf55c-136">bit</span></span>  <br/> ||<span data-ttu-id="cf55c-p104">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf55c-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="cf55c-139">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="cf55c-139">**Cancel**</span></span> <br/> |<span data-ttu-id="cf55c-140">bit</span><span class="sxs-lookup"><span data-stu-id="cf55c-140">bit</span></span>  <br/> ||<span data-ttu-id="cf55c-p105">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf55c-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="cf55c-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="cf55c-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="cf55c-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="cf55c-144">Datetime</span></span>  <br/> ||<span data-ttu-id="cf55c-145">監視サービスの内部用テーブル。</span><span class="sxs-lookup"><span data-stu-id="cf55c-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="cf55c-146">このフィールドは、Skype for Business Server 2015 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cf55c-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

