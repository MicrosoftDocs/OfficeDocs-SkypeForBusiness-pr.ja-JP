---
title: Dialog テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: ダイアログテーブルはサポートテーブルです。各レコードは、1つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809535"
---
# <a name="dialog-table"></a><span data-ttu-id="01871-103">Dialog テーブル</span><span class="sxs-lookup"><span data-stu-id="01871-103">Dialog table</span></span>
 
<span data-ttu-id="01871-104">ダイアログテーブルはサポートテーブルです。各レコードは、1つのセッション開始プロトコル (SIP) ダイアログを表します。</span><span class="sxs-lookup"><span data-stu-id="01871-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="01871-105">**列**</span><span class="sxs-lookup"><span data-stu-id="01871-105">**Column**</span></span>|<span data-ttu-id="01871-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="01871-106">**Data Type**</span></span>|<span data-ttu-id="01871-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="01871-107">**Key/Index**</span></span>|<span data-ttu-id="01871-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="01871-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01871-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="01871-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="01871-110">datetime</span><span class="sxs-lookup"><span data-stu-id="01871-110">datetime</span></span>  <br/> |<span data-ttu-id="01871-111">Primary</span><span class="sxs-lookup"><span data-stu-id="01871-111">Primary</span></span>  <br/> |<span data-ttu-id="01871-112">卓越した品質 (QoE) エージェントが、呼び出し元または呼び出し元から最初のレポートを受け取る時刻。</span><span class="sxs-lookup"><span data-stu-id="01871-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="01871-113">セッションを一意に識別するために SessionSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="01871-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="01871-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="01871-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="01871-115">int</span><span class="sxs-lookup"><span data-stu-id="01871-115">int</span></span>  <br/> |<span data-ttu-id="01871-116">Primary</span><span class="sxs-lookup"><span data-stu-id="01871-116">Primary</span></span>  <br/> |<span data-ttu-id="01871-117">セッションを区別するための順序番号 (同じ ConferenceDateTime がある場合)。</span><span class="sxs-lookup"><span data-stu-id="01871-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="01871-118">**この Id**</span><span class="sxs-lookup"><span data-stu-id="01871-118">**DialogID**</span></span> <br/> |<span data-ttu-id="01871-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="01871-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="01871-120">グローバルに一意のダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="01871-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="01871-121">**このチェックサム**</span><span class="sxs-lookup"><span data-stu-id="01871-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="01871-122">int</span><span class="sxs-lookup"><span data-stu-id="01871-122">int</span></span>  <br/> |<span data-ttu-id="01871-123">位置</span><span class="sxs-lookup"><span data-stu-id="01871-123">index</span></span>  <br/> |<span data-ttu-id="01871-124">ダイアログ ID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="01871-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

