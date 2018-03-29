---
title: SessionCorrelation テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="397ca-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="397ca-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="397ca-105">SessionCorrelation はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="397ca-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="397ca-106">各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="397ca-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="397ca-107">**列**</span><span class="sxs-lookup"><span data-stu-id="397ca-107">**Column**</span></span>|<span data-ttu-id="397ca-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="397ca-108">**Data Type**</span></span>|<span data-ttu-id="397ca-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="397ca-109">**Key/Index**</span></span>|<span data-ttu-id="397ca-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="397ca-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="397ca-111">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="397ca-111">**Checksum**</span></span> <br/> |<span data-ttu-id="397ca-112">int</span><span class="sxs-lookup"><span data-stu-id="397ca-112">int</span></span>  <br/> |||
|<span data-ttu-id="397ca-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="397ca-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="397ca-114">int</span><span class="sxs-lookup"><span data-stu-id="397ca-114">int</span></span>  <br/> |<span data-ttu-id="397ca-115">Primary</span><span class="sxs-lookup"><span data-stu-id="397ca-115">Primary</span></span>  <br/> |<span data-ttu-id="397ca-116">この A を識別する一意の番号/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="397ca-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="397ca-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="397ca-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="397ca-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="397ca-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="397ca-119">一意</span><span class="sxs-lookup"><span data-stu-id="397ca-119">Unique</span></span>  <br/> |<span data-ttu-id="397ca-120">関連付けられたセッションが同じ相関関係 ID をが</span><span class="sxs-lookup"><span data-stu-id="397ca-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="397ca-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="397ca-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="397ca-122">datetime</span><span class="sxs-lookup"><span data-stu-id="397ca-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="397ca-123">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="397ca-123">For internal use only.</span></span>  <br/> |
   

