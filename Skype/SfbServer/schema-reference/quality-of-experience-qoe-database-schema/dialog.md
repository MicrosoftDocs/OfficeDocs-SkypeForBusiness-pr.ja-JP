---
title: Dialog テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212573"
---
# <a name="dialog-table"></a><span data-ttu-id="39694-103">Dialog テーブル</span><span class="sxs-lookup"><span data-stu-id="39694-103">Dialog table</span></span>
 
<span data-ttu-id="39694-104">ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。</span><span class="sxs-lookup"><span data-stu-id="39694-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="39694-105">**列**</span><span class="sxs-lookup"><span data-stu-id="39694-105">**Column**</span></span>|<span data-ttu-id="39694-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="39694-106">**Data Type**</span></span>|<span data-ttu-id="39694-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="39694-107">**Key/Index**</span></span>|<span data-ttu-id="39694-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="39694-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39694-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="39694-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="39694-110">datetime</span><span class="sxs-lookup"><span data-stu-id="39694-110">datetime</span></span>  <br/> |<span data-ttu-id="39694-111">Primary</span><span class="sxs-lookup"><span data-stu-id="39694-111">Primary</span></span>  <br/> |<span data-ttu-id="39694-112">「優れた品質 (QoE) エージェントが呼び出し元または呼び出し先のいずれかから最初のレポートを受信するときの時間です。</span><span class="sxs-lookup"><span data-stu-id="39694-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="39694-113">セッションを一意に識別するのには SessionSeq と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="39694-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="39694-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="39694-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="39694-115">int</span><span class="sxs-lookup"><span data-stu-id="39694-115">int</span></span>  <br/> |<span data-ttu-id="39694-116">Primary</span><span class="sxs-lookup"><span data-stu-id="39694-116">Primary</span></span>  <br/> |<span data-ttu-id="39694-117">セッションが同じ ConferenceDateTime がある場合を区別するためにシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="39694-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="39694-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="39694-118">**DialogID**</span></span> <br/> |<span data-ttu-id="39694-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="39694-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="39694-120">グローバルに一意な ID をダイアログです。</span><span class="sxs-lookup"><span data-stu-id="39694-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="39694-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="39694-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="39694-122">int</span><span class="sxs-lookup"><span data-stu-id="39694-122">int</span></span>  <br/> |<span data-ttu-id="39694-123">インデックス</span><span class="sxs-lookup"><span data-stu-id="39694-123">index</span></span>  <br/> |<span data-ttu-id="39694-124">ダイアログ ID のチェックサム</span><span class="sxs-lookup"><span data-stu-id="39694-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

