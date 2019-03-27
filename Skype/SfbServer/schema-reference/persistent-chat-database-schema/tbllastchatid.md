---
title: tblLastChatId
ms.reviewer: ''
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
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884930"
---
# <a name="tbllastchatid"></a><span data-ttu-id="ab6fd-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="ab6fd-103">tblLastChatId</span></span>
 
<span data-ttu-id="ab6fd-104">tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="ab6fd-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-105">**Columns**</span></span>

|<span data-ttu-id="ab6fd-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-106">**Column**</span></span>|<span data-ttu-id="ab6fd-107">**型**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-107">**Type**</span></span>|<span data-ttu-id="ab6fd-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ab6fd-109">ノード</span><span class="sxs-lookup"><span data-stu-id="ab6fd-109">nodeID</span></span>  <br/> |<span data-ttu-id="ab6fd-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-110">int, not null</span></span>  <br/> |<span data-ttu-id="ab6fd-111">ノード ID (チャット ルーム タイプのみ)。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="ab6fd-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="ab6fd-112">lastChatID</span></span>  <br/> |<span data-ttu-id="ab6fd-113">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="ab6fd-114">最後に使用されるチャットの id。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="ab6fd-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-115">**Keys**</span></span>

|<span data-ttu-id="ab6fd-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-116">**Column**</span></span>|<span data-ttu-id="ab6fd-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="ab6fd-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab6fd-118">\<ノード、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="ab6fd-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="ab6fd-119">主キー (単なるノードは、処理のための十分な)。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="ab6fd-120">ノード</span><span class="sxs-lookup"><span data-stu-id="ab6fd-120">nodeID</span></span>  <br/> |<span data-ttu-id="ab6fd-121">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="ab6fd-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ab6fd-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab6fd-122">See also</span></span>

[<span data-ttu-id="ab6fd-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="ab6fd-123">tblChat</span></span>](tblchat.md)
