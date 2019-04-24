---
title: tblComplianceData
ms.reviewer: ''
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
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212615"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="647a9-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="647a9-103">tblComplianceData</span></span>
 
<span data-ttu-id="647a9-104">tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="647a9-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="647a9-105">**列**</span><span class="sxs-lookup"><span data-stu-id="647a9-105">**Columns**</span></span>

|<span data-ttu-id="647a9-106">**列**</span><span class="sxs-lookup"><span data-stu-id="647a9-106">**Column**</span></span>|<span data-ttu-id="647a9-107">**型**</span><span class="sxs-lookup"><span data-stu-id="647a9-107">**Type**</span></span>|<span data-ttu-id="647a9-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="647a9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="647a9-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="647a9-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="647a9-110">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="647a9-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="647a9-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="647a9-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="647a9-112">entryDate</span></span>  <br/> |<span data-ttu-id="647a9-113">smalldatetime 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="647a9-114">挿入の時間 (cmplType の未来がありますエントリであるため、プレース ホルダーにだけそのような場合に 9 を =)。</span><span class="sxs-lookup"><span data-stu-id="647a9-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="647a9-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="647a9-115">cmplType</span></span>  <br/> |<span data-ttu-id="647a9-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-116">int, not null</span></span>  <br/> | <span data-ttu-id="647a9-117">コンプライアンス イベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="647a9-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="647a9-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="647a9-118">1: Chat</span></span> <br/>  <span data-ttu-id="647a9-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="647a9-119">2: Backchat</span></span> <br/>  <span data-ttu-id="647a9-120">3: ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="647a9-120">3: File download</span></span> <br/>  <span data-ttu-id="647a9-121">4: ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="647a9-121">4: File upload</span></span> <br/>  <span data-ttu-id="647a9-122">9: 仮のファイル転送</span><span class="sxs-lookup"><span data-stu-id="647a9-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="647a9-123">10: 削除 (置換) とのチャット</span><span class="sxs-lookup"><span data-stu-id="647a9-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="647a9-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="647a9-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="647a9-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="647a9-125">cmplTime</span></span>  <br/> |<span data-ttu-id="647a9-126">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="647a9-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="647a9-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="647a9-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="647a9-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="647a9-129">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="647a9-130">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="647a9-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="647a9-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="647a9-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="647a9-132">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="647a9-132">bigint</span></span>  <br/> |<span data-ttu-id="647a9-133">(TblChat.chatId のテーブルに対応する) の ID をチャットします。</span><span class="sxs-lookup"><span data-stu-id="647a9-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="647a9-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="647a9-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="647a9-135">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-135">int, not null</span></span>  <br/> |<span data-ttu-id="647a9-136">(TblPrincipal.prinID のテーブルに対応する) ポスターのプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="647a9-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="647a9-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="647a9-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="647a9-138">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="647a9-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="647a9-139">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="647a9-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="647a9-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="647a9-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="647a9-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="647a9-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="647a9-142">メッセージ (エンコーディングは cmplType)。</span><span class="sxs-lookup"><span data-stu-id="647a9-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="647a9-143">**キー**</span><span class="sxs-lookup"><span data-stu-id="647a9-143">**Key**</span></span>

|<span data-ttu-id="647a9-144">**列**</span><span class="sxs-lookup"><span data-stu-id="647a9-144">**Column**</span></span>|<span data-ttu-id="647a9-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="647a9-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="647a9-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="647a9-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="647a9-147">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="647a9-147">Primary key.</span></span>  <br/> |
   

