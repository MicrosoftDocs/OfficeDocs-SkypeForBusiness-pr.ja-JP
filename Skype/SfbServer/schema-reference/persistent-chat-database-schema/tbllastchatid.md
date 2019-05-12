---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929967"
---
# <a name="tbllastchatid"></a><span data-ttu-id="6da7e-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="6da7e-103">tblLastChatId</span></span>
 
<span data-ttu-id="6da7e-104">tblLastChatId には、ユーザーごとに生成された (および tblChat テーブルで使用されている) 最後のチャット ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6da7e-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="6da7e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6da7e-105">**Columns**</span></span>

|<span data-ttu-id="6da7e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6da7e-106">**Column**</span></span>|<span data-ttu-id="6da7e-107">**型**</span><span class="sxs-lookup"><span data-stu-id="6da7e-107">**Type**</span></span>|<span data-ttu-id="6da7e-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="6da7e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6da7e-109">ノード</span><span class="sxs-lookup"><span data-stu-id="6da7e-109">nodeID</span></span>  <br/> |<span data-ttu-id="6da7e-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="6da7e-110">int, not null</span></span>  <br/> |<span data-ttu-id="6da7e-111">ノード ID (チャット ルーム タイプのみ)。</span><span class="sxs-lookup"><span data-stu-id="6da7e-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="6da7e-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="6da7e-112">lastChatID</span></span>  <br/> |<span data-ttu-id="6da7e-113">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="6da7e-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="6da7e-114">最後に使用されるチャットの id。</span><span class="sxs-lookup"><span data-stu-id="6da7e-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="6da7e-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="6da7e-115">**Keys**</span></span>

|<span data-ttu-id="6da7e-116">**列**</span><span class="sxs-lookup"><span data-stu-id="6da7e-116">**Column**</span></span>|<span data-ttu-id="6da7e-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="6da7e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6da7e-118">\<ノード、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="6da7e-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="6da7e-119">主キー (単なるノードは、処理のための十分な)。</span><span class="sxs-lookup"><span data-stu-id="6da7e-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="6da7e-120">ノード</span><span class="sxs-lookup"><span data-stu-id="6da7e-120">nodeID</span></span>  <br/> |<span data-ttu-id="6da7e-121">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="6da7e-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6da7e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6da7e-122">See also</span></span>

[<span data-ttu-id="6da7e-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="6da7e-123">tblChat</span></span>](tblchat.md)
