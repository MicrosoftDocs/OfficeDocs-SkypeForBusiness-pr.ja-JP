---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295511"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="a5a28-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a5a28-103">tblComplianceData</span></span>
 
<span data-ttu-id="a5a28-104">tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5a28-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="a5a28-105">**行**</span><span class="sxs-lookup"><span data-stu-id="a5a28-105">**Columns**</span></span>

|<span data-ttu-id="a5a28-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a5a28-106">**Column**</span></span>|<span data-ttu-id="a5a28-107">**型**</span><span class="sxs-lookup"><span data-stu-id="a5a28-107">**Type**</span></span>|<span data-ttu-id="a5a28-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="a5a28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5a28-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a5a28-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="a5a28-110">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5a28-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a5a28-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="a5a28-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a5a28-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="a5a28-112">entryDate</span></span>  <br/> |<span data-ttu-id="a5a28-113">smalldatetime、null ではない</span><span class="sxs-lookup"><span data-stu-id="a5a28-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="a5a28-114">挿入の時刻 (その場合は、cmplType = 9 の場合は、その場合はプレースホルダーのみのエントリであるため)。</span><span class="sxs-lookup"><span data-stu-id="a5a28-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="a5a28-115">cmplType 種類</span><span class="sxs-lookup"><span data-stu-id="a5a28-115">cmplType</span></span>  <br/> |<span data-ttu-id="a5a28-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5a28-116">int, not null</span></span>  <br/> | <span data-ttu-id="a5a28-117">コンプライアンスイベントの種類:</span><span class="sxs-lookup"><span data-stu-id="a5a28-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="a5a28-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="a5a28-118">1: Chat</span></span> <br/>  <span data-ttu-id="a5a28-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="a5a28-119">2: Backchat</span></span> <br/>  <span data-ttu-id="a5a28-120">3: ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="a5a28-120">3: File download</span></span> <br/>  <span data-ttu-id="a5a28-121">4: ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="a5a28-121">4: File upload</span></span> <br/>  <span data-ttu-id="a5a28-122">9: 暫定ファイル送信</span><span class="sxs-lookup"><span data-stu-id="a5a28-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="a5a28-123">10: チャットの削除 (置換あり)</span><span class="sxs-lookup"><span data-stu-id="a5a28-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="a5a28-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="a5a28-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="a5a28-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="a5a28-125">cmplTime</span></span>  <br/> |<span data-ttu-id="a5a28-126">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5a28-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="a5a28-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="a5a28-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="a5a28-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="a5a28-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="a5a28-129">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="a5a28-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a5a28-130">チャネルの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="a5a28-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="a5a28-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="a5a28-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="a5a28-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a5a28-132">bigint</span></span>  <br/> |<span data-ttu-id="a5a28-133">チャット ID (chatId テーブルに対応する tblChat)。</span><span class="sxs-lookup"><span data-stu-id="a5a28-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="a5a28-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="a5a28-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="a5a28-135">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="a5a28-135">int, not null</span></span>  <br/> |<span data-ttu-id="a5a28-136">ポスターのプリンシパル ID (tblPrincipal ID テーブルに対応)</span><span class="sxs-lookup"><span data-stu-id="a5a28-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="a5a28-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="a5a28-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="a5a28-138">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="a5a28-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a5a28-139">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="a5a28-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="a5a28-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="a5a28-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="a5a28-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a5a28-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a5a28-142">メッセージ (エンコードは、cmplType 型によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="a5a28-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="a5a28-143">**キー**</span><span class="sxs-lookup"><span data-stu-id="a5a28-143">**Key**</span></span>

|<span data-ttu-id="a5a28-144">**列**</span><span class="sxs-lookup"><span data-stu-id="a5a28-144">**Column**</span></span>|<span data-ttu-id="a5a28-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="a5a28-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a5a28-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a5a28-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="a5a28-147">主キー。</span><span class="sxs-lookup"><span data-stu-id="a5a28-147">Primary key.</span></span>  <br/> |
   

