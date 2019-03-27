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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876628"
---
# <a name="dialog-table"></a><span data-ttu-id="f0fec-103">Dialog テーブル</span><span class="sxs-lookup"><span data-stu-id="f0fec-103">Dialog table</span></span>
 
<span data-ttu-id="f0fec-104">ダイアログはサポートのテーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。</span><span class="sxs-lookup"><span data-stu-id="f0fec-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="f0fec-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f0fec-105">**Column**</span></span>|<span data-ttu-id="f0fec-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="f0fec-106">**Data Type**</span></span>|<span data-ttu-id="f0fec-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="f0fec-107">**Key/Index**</span></span>|<span data-ttu-id="f0fec-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f0fec-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0fec-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="f0fec-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="f0fec-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f0fec-110">datetime</span></span>  <br/> |<span data-ttu-id="f0fec-111">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fec-111">Primary</span></span>  <br/> |<span data-ttu-id="f0fec-112">「優れた品質 (QoE) エージェントが呼び出し元または呼び出し先のいずれかから最初のレポートを受信するときの時間です。</span><span class="sxs-lookup"><span data-stu-id="f0fec-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="f0fec-113">セッションを一意に識別するのには SessionSeq と組み合わせてを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0fec-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="f0fec-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="f0fec-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="f0fec-115">int</span><span class="sxs-lookup"><span data-stu-id="f0fec-115">int</span></span>  <br/> |<span data-ttu-id="f0fec-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f0fec-116">Primary</span></span>  <br/> |<span data-ttu-id="f0fec-117">セッションが同じ ConferenceDateTime がある場合を区別するためにシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="f0fec-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="f0fec-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="f0fec-118">**DialogID**</span></span> <br/> |<span data-ttu-id="f0fec-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="f0fec-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="f0fec-120">グローバルに一意な ID をダイアログです。</span><span class="sxs-lookup"><span data-stu-id="f0fec-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="f0fec-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="f0fec-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="f0fec-122">int</span><span class="sxs-lookup"><span data-stu-id="f0fec-122">int</span></span>  <br/> |<span data-ttu-id="f0fec-123">インデックス</span><span class="sxs-lookup"><span data-stu-id="f0fec-123">index</span></span>  <br/> |<span data-ttu-id="f0fec-124">ダイアログ ID のチェックサム</span><span class="sxs-lookup"><span data-stu-id="f0fec-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

