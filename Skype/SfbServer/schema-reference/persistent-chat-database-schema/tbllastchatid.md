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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505091"
---
# <a name="tbllastchatid"></a><span data-ttu-id="8234b-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="8234b-103">tblLastChatId</span></span>
 
<span data-ttu-id="8234b-104">tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8234b-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="8234b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8234b-105">**Columns**</span></span>

|<span data-ttu-id="8234b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="8234b-106">**Column**</span></span>|<span data-ttu-id="8234b-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="8234b-107">**Type**</span></span>|<span data-ttu-id="8234b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="8234b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8234b-109">ノード</span><span class="sxs-lookup"><span data-stu-id="8234b-109">nodeID</span></span>  <br/> |<span data-ttu-id="8234b-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8234b-110">int, not null</span></span>  <br/> |<span data-ttu-id="8234b-111">ノード ID (チャット ルーム タイプのみ)。</span><span class="sxs-lookup"><span data-stu-id="8234b-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="8234b-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="8234b-112">lastChatID</span></span>  <br/> |<span data-ttu-id="8234b-113">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="8234b-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="8234b-114">最後に使用されるチャットの id。</span><span class="sxs-lookup"><span data-stu-id="8234b-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="8234b-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="8234b-115">**Keys**</span></span>

|<span data-ttu-id="8234b-116">**列**</span><span class="sxs-lookup"><span data-stu-id="8234b-116">**Column**</span></span>|<span data-ttu-id="8234b-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="8234b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8234b-118">\<ノード、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="8234b-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="8234b-119">主キー (単なるノードは、処理のための十分な)。</span><span class="sxs-lookup"><span data-stu-id="8234b-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="8234b-120">ノード</span><span class="sxs-lookup"><span data-stu-id="8234b-120">nodeID</span></span>  <br/> |<span data-ttu-id="8234b-121">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="8234b-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8234b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8234b-122">See also</span></span>

[<span data-ttu-id="8234b-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="8234b-123">tblChat</span></span>](tblchat.md)