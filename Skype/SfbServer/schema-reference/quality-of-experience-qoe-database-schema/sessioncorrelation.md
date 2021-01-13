---
title: SessionCorrelation テーブル
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation テーブルはサポート テーブルです。 各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802657"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="3e51d-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="3e51d-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="3e51d-105">SessionCorrelation テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="3e51d-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="3e51d-106">各レコードは、複数のセッションを関連付けるのに使用される 1 つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="3e51d-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="3e51d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="3e51d-107">**Column**</span></span>|<span data-ttu-id="3e51d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3e51d-108">**Data Type**</span></span>|<span data-ttu-id="3e51d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3e51d-109">**Key/Index**</span></span>|<span data-ttu-id="3e51d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3e51d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3e51d-111">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="3e51d-111">**Checksum**</span></span> <br/> |<span data-ttu-id="3e51d-112">int</span><span class="sxs-lookup"><span data-stu-id="3e51d-112">int</span></span>  <br/> |||
|<span data-ttu-id="3e51d-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="3e51d-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="3e51d-114">int</span><span class="sxs-lookup"><span data-stu-id="3e51d-114">int</span></span>  <br/> |<span data-ttu-id="3e51d-115">Primary</span><span class="sxs-lookup"><span data-stu-id="3e51d-115">Primary</span></span>  <br/> |<span data-ttu-id="3e51d-116">この音声ビデオ会議サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="3e51d-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="3e51d-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="3e51d-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="3e51d-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3e51d-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3e51d-119">一意</span><span class="sxs-lookup"><span data-stu-id="3e51d-119">Unique</span></span>  <br/> |<span data-ttu-id="3e51d-120">関連付けされているセッションの関連付け ID は同じになります。</span><span class="sxs-lookup"><span data-stu-id="3e51d-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="3e51d-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3e51d-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3e51d-122">日付型</span><span class="sxs-lookup"><span data-stu-id="3e51d-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="3e51d-123">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="3e51d-123">For internal use only.</span></span>  <br/> |
   

