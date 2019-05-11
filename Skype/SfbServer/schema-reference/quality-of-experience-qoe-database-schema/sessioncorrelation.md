---
title: SessionCorrelation テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation はテーブルをサポートします。 各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907081"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="158cb-104">SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="158cb-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="158cb-105">SessionCorrelation はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="158cb-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="158cb-106">各レコードは、複数のセッションを関連付けるために使用される 1 つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="158cb-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="158cb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="158cb-107">**Column**</span></span>|<span data-ttu-id="158cb-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="158cb-108">**Data Type**</span></span>|<span data-ttu-id="158cb-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="158cb-109">**Key/Index**</span></span>|<span data-ttu-id="158cb-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="158cb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="158cb-111">**チェックサム**</span><span class="sxs-lookup"><span data-stu-id="158cb-111">**Checksum**</span></span> <br/> |<span data-ttu-id="158cb-112">int</span><span class="sxs-lookup"><span data-stu-id="158cb-112">int</span></span>  <br/> |||
|<span data-ttu-id="158cb-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="158cb-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="158cb-114">int</span><span class="sxs-lookup"><span data-stu-id="158cb-114">int</span></span>  <br/> |<span data-ttu-id="158cb-115">Primary</span><span class="sxs-lookup"><span data-stu-id="158cb-115">Primary</span></span>  <br/> |<span data-ttu-id="158cb-116">この A を識別する一意の番号/V 会議サーバーです。</span><span class="sxs-lookup"><span data-stu-id="158cb-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="158cb-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="158cb-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="158cb-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="158cb-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="158cb-119">一意</span><span class="sxs-lookup"><span data-stu-id="158cb-119">Unique</span></span>  <br/> |<span data-ttu-id="158cb-120">関連付けられたセッションが同じ相関関係 ID をが</span><span class="sxs-lookup"><span data-stu-id="158cb-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="158cb-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="158cb-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="158cb-122">datetime</span><span class="sxs-lookup"><span data-stu-id="158cb-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="158cb-123">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="158cb-123">For internal use only.</span></span>  <br/> |
   

