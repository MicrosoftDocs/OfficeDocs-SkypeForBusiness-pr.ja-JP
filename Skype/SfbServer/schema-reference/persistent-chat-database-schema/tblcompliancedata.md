---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a><span data-ttu-id="f06d1-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="f06d1-103">tblComplianceData</span></span>
 
<span data-ttu-id="f06d1-104">tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f06d1-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="f06d1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f06d1-105">**Columns**</span></span>

|<span data-ttu-id="f06d1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f06d1-106">**Column**</span></span>|<span data-ttu-id="f06d1-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="f06d1-107">**Type**</span></span>|<span data-ttu-id="f06d1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="f06d1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f06d1-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f06d1-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="f06d1-110">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f06d1-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="f06d1-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f06d1-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="f06d1-112">entryDate</span></span>  <br/> |<span data-ttu-id="f06d1-113">smalldatetime 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="f06d1-114">挿入の時間 (cmplType の未来がありますエントリであるため、プレース ホルダーにだけそのような場合に 9 を =)。</span><span class="sxs-lookup"><span data-stu-id="f06d1-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="f06d1-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="f06d1-115">cmplType</span></span>  <br/> |<span data-ttu-id="f06d1-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-116">int, not null</span></span>  <br/> | <span data-ttu-id="f06d1-117">コンプライアンス イベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="f06d1-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="f06d1-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="f06d1-118">1: Chat</span></span> <br/>  <span data-ttu-id="f06d1-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="f06d1-119">2: Backchat</span></span> <br/>  <span data-ttu-id="f06d1-120">3: ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="f06d1-120">3: File download</span></span> <br/>  <span data-ttu-id="f06d1-121">4: ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="f06d1-121">4: File upload</span></span> <br/>  <span data-ttu-id="f06d1-122">9: 仮のファイル転送</span><span class="sxs-lookup"><span data-stu-id="f06d1-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="f06d1-123">10: 削除 (置換) とのチャット</span><span class="sxs-lookup"><span data-stu-id="f06d1-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="f06d1-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="f06d1-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="f06d1-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="f06d1-125">cmplTime</span></span>  <br/> |<span data-ttu-id="f06d1-126">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="f06d1-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f06d1-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="f06d1-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="f06d1-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="f06d1-129">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f06d1-130">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="f06d1-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f06d1-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="f06d1-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="f06d1-132">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="f06d1-132">bigint</span></span>  <br/> |<span data-ttu-id="f06d1-133">(TblChat.chatId のテーブルに対応する) の ID をチャットします。</span><span class="sxs-lookup"><span data-stu-id="f06d1-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="f06d1-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="f06d1-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="f06d1-135">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-135">int, not null</span></span>  <br/> |<span data-ttu-id="f06d1-136">(TblPrincipal.prinID のテーブルに対応する) ポスターのプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="f06d1-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f06d1-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="f06d1-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="f06d1-138">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f06d1-139">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="f06d1-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="f06d1-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="f06d1-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="f06d1-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f06d1-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f06d1-142">メッセージ (エンコーディングは cmplType)。</span><span class="sxs-lookup"><span data-stu-id="f06d1-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="f06d1-143">**キー**</span><span class="sxs-lookup"><span data-stu-id="f06d1-143">**Key**</span></span>

|<span data-ttu-id="f06d1-144">**列**</span><span class="sxs-lookup"><span data-stu-id="f06d1-144">**Column**</span></span>|<span data-ttu-id="f06d1-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="f06d1-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f06d1-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f06d1-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="f06d1-147">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="f06d1-147">Primary key.</span></span>  <br/> |
   

