---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929932"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="13d5d-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="13d5d-103">tblComplianceData</span></span>
 
<span data-ttu-id="13d5d-104">tblComplianceData には、まだ対応アダプターで処理されていないコンプライアンス イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13d5d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="13d5d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="13d5d-105">**Columns**</span></span>

|<span data-ttu-id="13d5d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="13d5d-106">**Column**</span></span>|<span data-ttu-id="13d5d-107">**型**</span><span class="sxs-lookup"><span data-stu-id="13d5d-107">**Type**</span></span>|<span data-ttu-id="13d5d-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="13d5d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="13d5d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="13d5d-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="13d5d-110">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="13d5d-111">イベント id です。</span><span class="sxs-lookup"><span data-stu-id="13d5d-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="13d5d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="13d5d-112">entryDate</span></span>  <br/> |<span data-ttu-id="13d5d-113">smalldatetime 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="13d5d-114">挿入の時間 (cmplType の未来がありますエントリであるため、プレース ホルダーにだけそのような場合に 9 を =)。</span><span class="sxs-lookup"><span data-stu-id="13d5d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="13d5d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="13d5d-115">cmplType</span></span>  <br/> |<span data-ttu-id="13d5d-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-116">int, not null</span></span>  <br/> | <span data-ttu-id="13d5d-117">コンプライアンス イベントの種類です。</span><span class="sxs-lookup"><span data-stu-id="13d5d-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="13d5d-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="13d5d-118">1: Chat</span></span> <br/>  <span data-ttu-id="13d5d-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="13d5d-119">2: Backchat</span></span> <br/>  <span data-ttu-id="13d5d-120">3: ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="13d5d-120">3: File download</span></span> <br/>  <span data-ttu-id="13d5d-121">4: ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="13d5d-121">4: File upload</span></span> <br/>  <span data-ttu-id="13d5d-122">9: 仮のファイル転送</span><span class="sxs-lookup"><span data-stu-id="13d5d-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="13d5d-123">10: 削除 (置換) とのチャット</span><span class="sxs-lookup"><span data-stu-id="13d5d-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="13d5d-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="13d5d-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="13d5d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="13d5d-125">cmplTime</span></span>  <br/> |<span data-ttu-id="13d5d-126">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="13d5d-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="13d5d-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="13d5d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="13d5d-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="13d5d-129">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="13d5d-130">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="13d5d-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="13d5d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="13d5d-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="13d5d-132">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="13d5d-132">bigint</span></span>  <br/> |<span data-ttu-id="13d5d-133">(TblChat.chatId のテーブルに対応する) の ID をチャットします。</span><span class="sxs-lookup"><span data-stu-id="13d5d-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="13d5d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="13d5d-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="13d5d-135">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-135">int, not null</span></span>  <br/> |<span data-ttu-id="13d5d-136">(TblPrincipal.prinID のテーブルに対応する) ポスターのプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="13d5d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="13d5d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="13d5d-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="13d5d-138">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="13d5d-139">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="13d5d-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="13d5d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="13d5d-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="13d5d-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="13d5d-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="13d5d-142">メッセージ (エンコーディングは cmplType)。</span><span class="sxs-lookup"><span data-stu-id="13d5d-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="13d5d-143">**キー**</span><span class="sxs-lookup"><span data-stu-id="13d5d-143">**Key**</span></span>

|<span data-ttu-id="13d5d-144">**列**</span><span class="sxs-lookup"><span data-stu-id="13d5d-144">**Column**</span></span>|<span data-ttu-id="13d5d-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="13d5d-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="13d5d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="13d5d-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="13d5d-147">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="13d5d-147">Primary key.</span></span>  <br/> |
   

