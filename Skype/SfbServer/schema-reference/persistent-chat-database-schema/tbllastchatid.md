---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="730a1-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="730a1-103">tblLastChatId</span></span>
 
<span data-ttu-id="730a1-104">tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="730a1-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="730a1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="730a1-105">**Columns**</span></span>

|<span data-ttu-id="730a1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="730a1-106">**Column**</span></span>|<span data-ttu-id="730a1-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="730a1-107">**Type**</span></span>|<span data-ttu-id="730a1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="730a1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="730a1-109">ノード</span><span class="sxs-lookup"><span data-stu-id="730a1-109">nodeID</span></span>  <br/> |<span data-ttu-id="730a1-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="730a1-110">int, not null</span></span>  <br/> |<span data-ttu-id="730a1-111">ノード ID (チャット ルーム タイプのみ)。</span><span class="sxs-lookup"><span data-stu-id="730a1-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="730a1-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="730a1-112">lastChatID</span></span>  <br/> |<span data-ttu-id="730a1-113">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="730a1-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="730a1-114">最後に使用されるチャットの id。</span><span class="sxs-lookup"><span data-stu-id="730a1-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="730a1-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="730a1-115">**Keys**</span></span>

|<span data-ttu-id="730a1-116">**列**</span><span class="sxs-lookup"><span data-stu-id="730a1-116">**Column**</span></span>|<span data-ttu-id="730a1-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="730a1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="730a1-118">\<ノード、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="730a1-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="730a1-119">主キー (単なるノードは、処理のための十分な)。</span><span class="sxs-lookup"><span data-stu-id="730a1-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="730a1-120">ノード</span><span class="sxs-lookup"><span data-stu-id="730a1-120">nodeID</span></span>  <br/> |<span data-ttu-id="730a1-121">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="730a1-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="730a1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="730a1-122">See also</span></span>

#### 

[<span data-ttu-id="730a1-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="730a1-123">tblChat</span></span>](tblchat.md)

