---
title: Skype for Business Server 2015 の CallType テーブル
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813367"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5e998-103">Skype for Business Server 2015 の CallType テーブル</span><span class="sxs-lookup"><span data-stu-id="5e998-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e998-104">CallType テーブルは、可能な呼び出しの種類の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="5e998-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="5e998-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5e998-105">**Column**</span></span>|<span data-ttu-id="5e998-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5e998-106">**Data Type**</span></span>|<span data-ttu-id="5e998-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5e998-107">**Key/Index**</span></span>|<span data-ttu-id="5e998-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5e998-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e998-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="5e998-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="5e998-110">int</span><span class="sxs-lookup"><span data-stu-id="5e998-110">int</span></span>  <br/> |<span data-ttu-id="5e998-111">Primary</span><span class="sxs-lookup"><span data-stu-id="5e998-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="5e998-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="5e998-112">**CallType**</span></span> <br/> |<span data-ttu-id="5e998-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5e998-113">nvarchar</span></span>  <br/> || <span data-ttu-id="5e998-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e998-114">Allowed values:</span></span> <br/>  <span data-ttu-id="5e998-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="5e998-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="5e998-116">1 - インスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="5e998-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="5e998-117">2 -- アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="5e998-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="5e998-118">3 -- オーディオ</span><span class="sxs-lookup"><span data-stu-id="5e998-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="5e998-119">4 - オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="5e998-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="5e998-120">5 - ファイル転送</span><span class="sxs-lookup"><span data-stu-id="5e998-120">5 - File Transfer</span></span> <br/> |
   

