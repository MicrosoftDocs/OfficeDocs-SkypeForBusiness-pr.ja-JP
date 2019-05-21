---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295399"
---
# <a name="tbllastchatid"></a><span data-ttu-id="31b8f-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="31b8f-103">tblLastChatId</span></span>
 
<span data-ttu-id="31b8f-104">tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31b8f-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="31b8f-105">**行**</span><span class="sxs-lookup"><span data-stu-id="31b8f-105">**Columns**</span></span>

|<span data-ttu-id="31b8f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="31b8f-106">**Column**</span></span>|<span data-ttu-id="31b8f-107">**型**</span><span class="sxs-lookup"><span data-stu-id="31b8f-107">**Type**</span></span>|<span data-ttu-id="31b8f-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="31b8f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="31b8f-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="31b8f-109">nodeID</span></span>  <br/> |<span data-ttu-id="31b8f-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="31b8f-110">int, not null</span></span>  <br/> |<span data-ttu-id="31b8f-111">ノード ID (チャットルームの種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="31b8f-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="31b8f-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="31b8f-112">lastChatID</span></span>  <br/> |<span data-ttu-id="31b8f-113">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="31b8f-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="31b8f-114">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="31b8f-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="31b8f-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="31b8f-115">**Keys**</span></span>

|<span data-ttu-id="31b8f-116">**列**</span><span class="sxs-lookup"><span data-stu-id="31b8f-116">**Column**</span></span>|<span data-ttu-id="31b8f-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="31b8f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31b8f-118">\<nodeID、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="31b8f-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="31b8f-119">主キー (nodeID だけが処理に十分な場合)。</span><span class="sxs-lookup"><span data-stu-id="31b8f-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="31b8f-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="31b8f-120">nodeID</span></span>  <br/> |<span data-ttu-id="31b8f-121">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="31b8f-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="31b8f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="31b8f-122">See also</span></span>

[<span data-ttu-id="31b8f-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="31b8f-123">tblChat</span></span>](tblchat.md)
