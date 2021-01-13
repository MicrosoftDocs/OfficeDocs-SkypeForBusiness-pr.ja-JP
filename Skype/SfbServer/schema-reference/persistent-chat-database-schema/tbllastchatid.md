---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816007"
---
# <a name="tbllastchatid"></a><span data-ttu-id="4f3b0-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="4f3b0-103">tblLastChatId</span></span>
 
<span data-ttu-id="4f3b0-104">tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f3b0-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="4f3b0-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-105">**Columns**</span></span>

|<span data-ttu-id="4f3b0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-106">**Column**</span></span>|<span data-ttu-id="4f3b0-107">**型**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-107">**Type**</span></span>|<span data-ttu-id="4f3b0-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4f3b0-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="4f3b0-109">nodeID</span></span>  <br/> |<span data-ttu-id="4f3b0-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="4f3b0-110">int, not null</span></span>  <br/> |<span data-ttu-id="4f3b0-111">ノード ID (チャット ルーム種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="4f3b0-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="4f3b0-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="4f3b0-112">lastChatID</span></span>  <br/> |<span data-ttu-id="4f3b0-113">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="4f3b0-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="4f3b0-114">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="4f3b0-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="4f3b0-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-115">**Keys**</span></span>

|<span data-ttu-id="4f3b0-116">**列**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-116">**Column**</span></span>|<span data-ttu-id="4f3b0-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="4f3b0-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="4f3b0-118">主キー (処理には nodeID のみで十分)。</span><span class="sxs-lookup"><span data-stu-id="4f3b0-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="4f3b0-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="4f3b0-119">nodeID</span></span>  <br/> |<span data-ttu-id="4f3b0-120">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="4f3b0-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4f3b0-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f3b0-121">See also</span></span>

[<span data-ttu-id="4f3b0-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="4f3b0-122">tblChat</span></span>](tblchat.md)
