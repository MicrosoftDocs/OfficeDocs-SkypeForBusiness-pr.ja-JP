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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814585"
---
# <a name="tbllastchatid"></a><span data-ttu-id="22483-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="22483-103">tblLastChatId</span></span>
 
<span data-ttu-id="22483-104">tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22483-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="22483-105">**行**</span><span class="sxs-lookup"><span data-stu-id="22483-105">**Columns**</span></span>

|<span data-ttu-id="22483-106">**列**</span><span class="sxs-lookup"><span data-stu-id="22483-106">**Column**</span></span>|<span data-ttu-id="22483-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="22483-107">**Type**</span></span>|<span data-ttu-id="22483-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="22483-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22483-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="22483-109">nodeID</span></span>  <br/> |<span data-ttu-id="22483-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="22483-110">int, not null</span></span>  <br/> |<span data-ttu-id="22483-111">ノード ID (チャットルームの種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="22483-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="22483-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="22483-112">lastChatID</span></span>  <br/> |<span data-ttu-id="22483-113">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="22483-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="22483-114">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="22483-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="22483-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="22483-115">**Keys**</span></span>

|<span data-ttu-id="22483-116">**列**</span><span class="sxs-lookup"><span data-stu-id="22483-116">**Column**</span></span>|<span data-ttu-id="22483-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="22483-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22483-118">\<nodeID、lastChatID\></span><span class="sxs-lookup"><span data-stu-id="22483-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="22483-119">主キー (nodeID だけが処理に十分な場合)。</span><span class="sxs-lookup"><span data-stu-id="22483-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="22483-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="22483-120">nodeID</span></span>  <br/> |<span data-ttu-id="22483-121">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="22483-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22483-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="22483-122">See also</span></span>

[<span data-ttu-id="22483-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="22483-123">tblChat</span></span>](tblchat.md)
