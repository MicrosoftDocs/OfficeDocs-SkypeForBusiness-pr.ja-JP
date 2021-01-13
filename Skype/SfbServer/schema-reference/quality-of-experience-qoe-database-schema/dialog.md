---
title: ダイアログ テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815847"
---
# <a name="dialog-table"></a><span data-ttu-id="137df-103">ダイアログ テーブル</span><span class="sxs-lookup"><span data-stu-id="137df-103">Dialog table</span></span>
 
<span data-ttu-id="137df-104">Dialog テーブルはサポート テーブルです。各レコードは、1 つのセッション開始プロトコル (SIP) ダイアログを表します。</span><span class="sxs-lookup"><span data-stu-id="137df-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="137df-105">**列**</span><span class="sxs-lookup"><span data-stu-id="137df-105">**Column**</span></span>|<span data-ttu-id="137df-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="137df-106">**Data Type**</span></span>|<span data-ttu-id="137df-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="137df-107">**Key/Index**</span></span>|<span data-ttu-id="137df-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="137df-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="137df-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="137df-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="137df-110">日付型</span><span class="sxs-lookup"><span data-stu-id="137df-110">datetime</span></span>  <br/> |<span data-ttu-id="137df-111">Primary</span><span class="sxs-lookup"><span data-stu-id="137df-111">Primary</span></span>  <br/> |<span data-ttu-id="137df-112">Quality of Excellence (QoE) エージェントが発信者または呼び出し先から最初のレポートを受信した時刻。</span><span class="sxs-lookup"><span data-stu-id="137df-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="137df-113">セッションを一意に識別するために SessionSeq と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="137df-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="137df-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="137df-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="137df-115">int</span><span class="sxs-lookup"><span data-stu-id="137df-115">int</span></span>  <br/> |<span data-ttu-id="137df-116">Primary</span><span class="sxs-lookup"><span data-stu-id="137df-116">Primary</span></span>  <br/> |<span data-ttu-id="137df-117">ConferenceDateTime が同じ場合にセッションを区別するシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="137df-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="137df-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="137df-118">**DialogID**</span></span> <br/> |<span data-ttu-id="137df-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="137df-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="137df-120">グローバルに一意のダイアログ ID。</span><span class="sxs-lookup"><span data-stu-id="137df-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="137df-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="137df-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="137df-122">int</span><span class="sxs-lookup"><span data-stu-id="137df-122">int</span></span>  <br/> |<span data-ttu-id="137df-123">index</span><span class="sxs-lookup"><span data-stu-id="137df-123">index</span></span>  <br/> |<span data-ttu-id="137df-124">ダイアログ ID のチェックサム。</span><span class="sxs-lookup"><span data-stu-id="137df-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

