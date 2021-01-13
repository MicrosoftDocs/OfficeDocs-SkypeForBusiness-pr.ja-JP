---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809857"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="f20a6-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="f20a6-103">tblComplianceData</span></span>
 
<span data-ttu-id="f20a6-104">tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="f20a6-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="f20a6-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f20a6-105">**Columns**</span></span>

|<span data-ttu-id="f20a6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f20a6-106">**Column**</span></span>|<span data-ttu-id="f20a6-107">**型**</span><span class="sxs-lookup"><span data-stu-id="f20a6-107">**Type**</span></span>|<span data-ttu-id="f20a6-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="f20a6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f20a6-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f20a6-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="f20a6-110">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="f20a6-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f20a6-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="f20a6-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f20a6-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="f20a6-112">entryDate</span></span>  <br/> |<span data-ttu-id="f20a6-113">NULL でない smalldatetime</span><span class="sxs-lookup"><span data-stu-id="f20a6-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="f20a6-114">挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="f20a6-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="f20a6-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="f20a6-115">cmplType</span></span>  <br/> |<span data-ttu-id="f20a6-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f20a6-116">int, not null</span></span>  <br/> | <span data-ttu-id="f20a6-117">コンプライアンス イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="f20a6-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="f20a6-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="f20a6-118">1: Chat</span></span> <br/>  <span data-ttu-id="f20a6-119">2: バックチャット</span><span class="sxs-lookup"><span data-stu-id="f20a6-119">2: Backchat</span></span> <br/>  <span data-ttu-id="f20a6-120">3: ファイル ダウンロード</span><span class="sxs-lookup"><span data-stu-id="f20a6-120">3: File download</span></span> <br/>  <span data-ttu-id="f20a6-121">4: ファイル アップロード</span><span class="sxs-lookup"><span data-stu-id="f20a6-121">4: File upload</span></span> <br/>  <span data-ttu-id="f20a6-122">9: 暫定ファイル転送</span><span class="sxs-lookup"><span data-stu-id="f20a6-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="f20a6-123">10: (置き換えによる) チャットの削除</span><span class="sxs-lookup"><span data-stu-id="f20a6-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="f20a6-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="f20a6-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="f20a6-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="f20a6-125">cmplTime</span></span>  <br/> |<span data-ttu-id="f20a6-126">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="f20a6-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="f20a6-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="f20a6-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="f20a6-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="f20a6-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="f20a6-129">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="f20a6-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f20a6-130">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="f20a6-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f20a6-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="f20a6-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="f20a6-132">bigint</span><span class="sxs-lookup"><span data-stu-id="f20a6-132">bigint</span></span>  <br/> |<span data-ttu-id="f20a6-133">チャット ID (tblChat.chatId テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="f20a6-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="f20a6-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="f20a6-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="f20a6-135">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f20a6-135">int, not null</span></span>  <br/> |<span data-ttu-id="f20a6-136">ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="f20a6-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f20a6-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="f20a6-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="f20a6-138">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="f20a6-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f20a6-139">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="f20a6-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="f20a6-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="f20a6-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="f20a6-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f20a6-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f20a6-142">メッセージ (エンコードは cmplType に依存)。</span><span class="sxs-lookup"><span data-stu-id="f20a6-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="f20a6-143">**キー**</span><span class="sxs-lookup"><span data-stu-id="f20a6-143">**Key**</span></span>

|<span data-ttu-id="f20a6-144">**列**</span><span class="sxs-lookup"><span data-stu-id="f20a6-144">**Column**</span></span>|<span data-ttu-id="f20a6-145">**説明**</span><span class="sxs-lookup"><span data-stu-id="f20a6-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f20a6-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f20a6-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="f20a6-147">主キー。</span><span class="sxs-lookup"><span data-stu-id="f20a6-147">Primary key.</span></span>  <br/> |
   

